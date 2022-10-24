<template>
  <HelloWorld :objects="objects" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
export default {
  name: "App",
  components: {
    HelloWorld,
  },
  computed: {
    objects() {
      return [
        {
          displayName: "Jonh",
        },
        {
          displayName: "Doe",
        },
      ];
    },
  },
};
</script>

<style></style>
