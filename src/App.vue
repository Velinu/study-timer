<template>
  <header>
  </header>
  <main>
    <TimerMain/>
  </main>
  <Footer>
  </Footer>
</template>

<script>
import TimerMain from './components/Timer.vue'

export default {
  name: 'App',
  components: {
    TimerMain
  },
  data() {

  }
}
</script>

<style>
body{
  margin: 0;
}
</style>
