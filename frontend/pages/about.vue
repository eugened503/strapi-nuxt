<template>
  <p>
    {{ this.info }}
  </p>
</template>

<script>
export default {
  data() {
    return {
      info: null,
      error: null
    };
  },
  async mounted() {
    try {
      this.profiles = await this.$strapi.$profiles.find();
      this.info = this.profiles[0].biography;
    } catch (error) {
      this.error = error;
      console.log(this.error);
    }
  }
};
</script>
