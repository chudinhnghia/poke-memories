<template>
  <main-screen v-if="statusMatch == 'default'" v-on:gameMode="onHandleBeforeStart($event)"></main-screen>
  <gaming-screen v-if="statusMatch == 'match'"></gaming-screen>
  <end-screen v-if="statusMatch == 'end'"></end-screen>
</template>

<script>
import MainScreen from './components/MainScreen.vue';
import GamingScreen from './components/GamingScreen.vue';
import EndScreen from './components/EndScreen.vue';

export default {
  name: 'App',
  components: {
    MainScreen,
    GamingScreen,
    EndScreen
  },
  data() {
    return {
      statusMatch: "default",
    }
  },
  methods: {
    onHandleBeforeStart(config) {
      console.log("running handle befor start: ", config);
      this.statusMatch = 'match';
    }
  }
}
</script>

<style>

</style>
