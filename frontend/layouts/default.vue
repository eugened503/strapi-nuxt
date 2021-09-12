<template>
  <div>
    <Navbar />
    <div class="container">
      <Nuxt />
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar";
export default {
  components: {
    Navbar
  }
};
</script>

<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  color: #2e495e;
}

.container {
  min-height: 100vh;
  margin-top: 10vh;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  text-align: center;
}
</style>
