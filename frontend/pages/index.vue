<template>
  <div>
    <img :src="foto" alt="фото" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      foto: null,
      error: null
    };
  },
  async mounted() {
    try {
      this.profiles = await this.$strapi.$profiles.find();
      this.foto = "http://localhost:1337" + this.profiles[0].foto.url;
    } catch (error) {
      this.error = error;
      console.log(this.error);
    }
  }
};
</script>

<style scoped>
body {
  margin: auto;
  background: #eaeaea;
  font-family: "Open Sans", sans-serif;
}

img {
  width: 100%;
}
</style>
