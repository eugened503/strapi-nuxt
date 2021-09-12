<template>
  <nav class="navbar">
    <ul class="nav">
      <li class="nav-item">
        <nuxt-link class="nav-link" to="/">Главная</nuxt-link>
      </li>
      <li class="nav-item">
        <nuxt-link class="nav-link" to="/about">Обо мне</nuxt-link>
      </li>
      <li class="nav-item">
        <nuxt-link class="nav-link" to="/contacts">Контакты</nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.navbar {
  width: 100%;
  background: #eeeeee;
}

.nav {
  display: flex;
  margin: 0 auto;
  color: black;
  font-weight: 600;
  font-size: 20px;
}
.nav-link {
  color: #666;
}

.nav-link:focus,
.nav-link:hover {
  color: rgb(116, 148, 236);
}
</style>
