<template>
    <section>
      <HomeBody v-if="this.$store.state.token"/>
      <HomeBody2 v-else/>
    </section>
    <aside>
      <HomeMenu/>
    </aside>
</template>

<script>
import HomeMenu from '../components/HomeMenu.vue'
import HomeBody from '../components/HomeBody.vue'
import HomeBody2 from '@/components/HomeBody2.vue'
export default {
  data () {
    return {
      isLoggedIn: false
    }
  },
  created () {
    // 로그인 여부 확인 로직
    if (localStorage.getItem('isLoggedIn') === 'true') {
      this.isLoggedIn = true
    }
  },
  watch: {
    isLoggedIn: function (newValue) {
      if (newValue === false) {
        window.location.reload()
      }
    }
  },
  name: 'HomeView',
  components: {
    HomeMenu,
    HomeBody,
    HomeBody2
  }
}
</script>

<style scoped>
aside {
  position: fixed; width: 25%; z-index: 9; right: 0; top: 0; height: 100%; overflow-y: auto; -ms-overflow-style: none; background-color: white; flex: 0.6;
}
section {
  position: fixed; flex: 3;
  height: 100%; width: 75%;
}
</style>
