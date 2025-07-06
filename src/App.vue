<template>
  <ProfileDashboard></ProfileDashboard>
</template>

<script>
import ProfileDashboard from "./components/ProfileDashboard.vue";

export default {
  name: "App",
  components: {
    ProfileDashboard,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
