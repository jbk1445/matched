<template>
  <div id="app" class="header" v-if="this.$store.state.token">
    <NaviBar/>
  </div>
  <router-view/>
</template>

<script>
import NaviBar from '@/components/NaviBar.vue'
export default {
  components: {
    NaviBar
  }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap");
.header {
  height: 5%;
}
router-view {
  height: 95%;
}
body {
  font-family: "Roboto", sans-serif;
  background-color: white;
}
</style>
