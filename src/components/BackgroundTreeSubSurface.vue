<script setup lang="ts">
import {
  Color,
  InstancedBufferAttribute,
  MathUtils,
  Object3D,
  Vector3,
  //@ts-ignore
} from "three";

import {
  Camera,
  DodecahedronGeometry,
  EffectComposer,
  FXAAPass,
  InstancedMesh,
  PointLight,
  Renderer,
  RenderPass,
  SubSurfaceMaterial,
  Scene,
  UnrealBloomPass,
} from "troisjs";
//@ts-ignore
import chroma from "chroma-js";
import { Ref, onMounted, ref } from "vue";

const { randFloat: rnd, randFloatSpread: rndFS } = MathUtils;

const NUM_INSTANCES = 2000;
//@ts-ignore
const instances = [];
const cscale = chroma.scale(["#dd3e1b", "#0b509c"]);
const target = new Vector3();
const dummyO = new Object3D();
const dummyV = new Vector3();

for (let i = 0; i < NUM_INSTANCES; i++) {
  instances.push({
    position: new Vector3(rndFS(200), rndFS(200), rndFS(200)),
    scale: rnd(0.2, 1),
    velocity: new Vector3(rndFS(2), rndFS(2), rndFS(2)),
    attraction: 0.0025 + rnd(0, 0.01),
    vlimit: 0.3 + rnd(0, 0.2),
  });
}

const renderer: Ref<typeof Renderer | null> = ref(null);
const imesh: Ref<typeof InstancedMesh | null> = ref(null);
const light: Ref<typeof PointLight | null> = ref(null);

onMounted(() => {
  init();
});

function init() {
  // init instanced mesh matrix
  for (let i = 0; i < NUM_INSTANCES; i++) {
    //@ts-ignore
    const { position, scale } = instances[i];
    dummyO.position.copy(position);
    dummyO.scale.set(scale, scale, scale);
    dummyO.updateMatrix();
    imesh.value?.mesh.setMatrixAt(i, dummyO.matrix);
  }
  updateColors();
  if (imesh.value) {
    imesh.value.mesh.instanceMatrix.needsUpdate = true;
  } else {
    console.error(
      "Failed to update instance matrix: 'imesh' is null. Ensure that 'imesh' is correctly initialized and assigned."
    );
  }

  // animate
  if (renderer.value) {
    renderer.value.onBeforeRender(animate);
  } else {
    console.error(
      "Renderer is not initialized. Ensure that the renderer is properly created and assigned before calling onBeforeRender."
    );
  }
}

function animate() {
  if (!renderer.value || !imesh.value || !light.value) return;

  const { pointer } = renderer.value.three;
  target.copy(pointer?.positionV3);
  light.value.light.position.copy(target);

  for (let i = 0; i < NUM_INSTANCES; i++) {
    //@ts-ignore
    const { position, scale, velocity, attraction, vlimit } = instances[i];

    dummyV.copy(target).sub(position).normalize().multiplyScalar(attraction);
    velocity.add(dummyV).clampScalar(-vlimit, vlimit);
    position.add(velocity);

    dummyO.position.copy(position);
    dummyO.scale.set(scale, scale, scale);
    dummyO.lookAt(dummyV.copy(position).add(velocity));
    dummyO.updateMatrix();
    imesh.value.mesh.setMatrixAt(i, dummyO.matrix);
  }
  imesh.value.mesh.instanceMatrix.needsUpdate = true;
}

function updateColors() {
  const colors = [];
  for (let i = 0; i < NUM_INSTANCES; i++) {
    const color = new Color(cscale(rnd(0, 1)).hex());
    colors.push(color.r, color.g, color.b);
  }
  imesh.value?.mesh.geometry.setAttribute(
    "color",
    new InstancedBufferAttribute(new Float32Array(colors), 3)
  );
}
</script>

<template>
  <!-- <Renderer ref="renderer" resize="window" :orbit-ctrl="{ enableDamping: true, dampingFactor: 0.05 }" pointer @click="randomColors" > -->
  <!-- <Renderer ref="renderer" resize="window" pointer @click="randomColors" > -->
  <Renderer ref="renderer" resize="window" pointer>
    <Camera :position="{ z: 300, x: -100 }" />
    <Scene>
      <PointLight ref="light" color="#FFC0C0" />

      <InstancedMesh ref="imesh" :count="NUM_INSTANCES">
        <DodecahedronGeometry :radius="5" />
        <SubSurfaceMaterial :props="{ vertexColors: true }" />
      </InstancedMesh>
    </Scene>
    <EffectComposer>
      <RenderPass />
      <UnrealBloomPass :strength="0.5" />
      <FXAAPass />
    </EffectComposer>
  </Renderer>
</template>

<style>
canvas {
  display: block;
  background-color: transparent !important;
}
</style>
