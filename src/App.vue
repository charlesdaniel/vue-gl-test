<template>
  <div id="app">
  <vgl-namespace style="display: flex;">
    <vgl-scene name="scn">
      <vgl-box-geometry name="cube" width=3 height=5 depth=10></vgl-box-geometry>
      <vgl-mesh-standard-material name="std"></vgl-mesh-standard-material>
      <vgl-mesh geometry="cube" :position="`${x} ${y} ${z}`" :rotation="`${rx} ${ry} ${rz}`" :scale="`${sx} ${sy} ${sz}`" material="std"></vgl-mesh>
      <vgl-ambient-light color="#ffeecc"></vgl-ambient-light>
      <vgl-directional-light position="0 1 1"></vgl-directional-light>
    </vgl-scene>
    <vgl-renderer scene="scn" camera="cmr1" antialias style="height: 100vh; flex: 1;">
      <vgl-perspective-camera name="cmr1" orbit-position="20 1 0.5"></vgl-perspective-camera>
    </vgl-renderer>
    <div style="width: 1px;"></div>
    <vgl-renderer scene="scn" camera="cmr2" antialias style="height: 100vh; flex: 1;">
      <vgl-perspective-camera name="cmr2" orbit-position="20 2 0.5"></vgl-perspective-camera>
    </vgl-renderer>
    <div style="width: 1px;"></div>
    <vgl-renderer scene="scn" camera="cmr3" antialias style="height: 100vh; flex: 1;">
      <vgl-perspective-camera name="cmr3" orbit-position="20 3 0.5"></vgl-perspective-camera>
    </vgl-renderer>
    <div style="width: 1px;"></div>
    <vgl-renderer scene="scn" camera="cmr4" antialias style="height: 100vh; flex: 1;">
      <vgl-perspective-camera name="cmr4" orbit-position="30 1 1.5"></vgl-perspective-camera>
    </vgl-renderer>
  </vgl-namespace>
  <aside class="control-panel">
    Position:
    <label>x<input type="range" min="-10" max="10" v-model="x"></label>
    <label>y<input type="range" min="-10" max="10" v-model="y"></label>
    <label>z<input type="range" min="-10" max="10" v-model="z"></label>
    <br/>
    Rotation:
    <label>rx<input type="range" min="-10" max="10" v-model="rx"></label>
    <label>ry<input type="range" min="-10" max="10" v-model="ry"></label>
    <label>rz<input type="range" min="-10" max="10" v-model="rz"></label>
    <br/>
    Scale:
    <label>sx<input type="range" min="-10" max="10" v-model="sx"></label>
    <label>sy<input type="range" min="-10" max="10" v-model="sy"></label>
    <label>sz<input type="range" min="-10" max="10" v-model="sz"></label>
  </aside>
  </div>
</template>

<script>
import * as VueGL from "../node_modules/vue-gl/dist/vue-gl.js"

export default {
  name: 'app',
  data() {
    return {
      x: 0,
      y: 0,
      z: 0,
      rx: 0,
      ry: 0,
      rz: 0,
      sx: 1,
      sy: 1,
      sz: 1,
    }
  },
  components: {
    ...VueGL
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
