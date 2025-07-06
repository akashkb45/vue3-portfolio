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
@import url("https://fonts.googleapis.com/css2?family=Arvo:ital,wght@0,400;0,700;1,400;1,700&family=Comfortaa:wght@300..700&family=DM+Sans:ital,opsz,wght@0,9..40,100..1000;1,9..40,100..1000&family=Quicksand:wght@300..700&display=swap");

* {
  font-family: "Quicksand";
}
body {
  margin: 0;
  background: #0f172a;
  color: #fff;
}
</style>
