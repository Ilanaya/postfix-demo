<template>
  <div class="objects-table-widget">
    {{ objects[0].displayName }}
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    objects: {
      type: Array,
      required: true,
      validator: (value) => {
        const requiredObjectKeys = ["displayName"];
        // here postfix doesn't work
        return value.every((item) => {
          return requiredObjectKeys.every((key) => key in item);
        });
      },
    },
  },
  computed: {
    test() {
      return this.objects.map(
        ({ displayName }) => `${displayName}${displayName}`
      );
    },
    test2() {
      // eslint-disable-next-line no-unused-vars
      return this.test.forEach((object) => {
        // trigger postfix here - it should work
      });
    },
  },
};
</script>
