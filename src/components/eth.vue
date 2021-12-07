<template>
  <div id="xxx"></div>
</template>

<script>
import * as three from "three";
import { onMounted } from "@vue/runtime-core";
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader.js";
// import three from "three";

export default {
  name: "Eth3D",
  setup() {
    const x = () => {
      const scene = new three.Scene();
      const camera = new three.PerspectiveCamera(
        75,
        window.innerWidth / window.innerHeight,
        0.1,
        1000
      );
      const renderer = new three.WebGLRenderer();
      renderer.setSize(window.innerWidth, window.innerHeight);
      const node = document.getElementById("xxx");
      node.appendChild(renderer.domElement);

      const loader = new GLTFLoader();

      loader.load(
        "../assets/scene.gltf",
        (gltf) => {
          scene.add(gltf.scene);
        },
        function (xhr) {
          console.log((xhr.loaded / xhr.total) * 100 + "% loaded");
        },
        (err) => {
          console.error(err);
        }
      );

      //   const geometry = new three.BoxGeometry();
      //   const material = new three.MeshBasicMaterial({ color: 0x00ff00 });
      //   const cube = new three.Mesh(geometry, material);
      //   scene.add(cube);

      //   camera.position.z = 5;

      function animate() {
        requestAnimationFrame(animate);
        renderer.render(scene, camera);
        // cube.rotation.x += 0.01;
        // cube.rotation.y += 0.01;
      }
      animate();
    };

    onMounted(x);
  },
};
</script>

<style lang="scss" scoped>
.xxx {
  height: 100vh;
}
</style>
