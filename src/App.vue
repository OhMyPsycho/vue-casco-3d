<template>
<model-obj :backgroundColor="'blue'" 
src="obj/casco.obj" 
:position="{x: 0, y: -25, z: 0}"
:rotation="rotation"
@on-load="onLoad"
mtl="obj/10517_Motorcycle_Helmet_v01_L3.mtl"></model-obj>
</template>

<script>
import { ModelObj } from 'vue-3d-model';

// recursos
// https://hujiulong.github.io/vue-3d-model/#/demo-basic
// https://github.com/hujiulong/vue-3d-model

// propiedades
// https://morioh.com/p/c6a400553459


export default {
  name: 'App',
  data() {
    return {
      rotation: {
        x: -Math.PI / 2,
        y: 0,
        z: 0
      }
    }
  },
  methods: {
    onLoad() {
      this.rotate()
    },
    rotate() {
      this.rotation.z += 0.01;
      requestAnimationFrame(this.rotate)
    }
  },
  components: {
    ModelObj
  }
}
</script>

<style>

</style>
