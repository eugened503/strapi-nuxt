<template>
  <div class="about">
    <ul class="about__key">
      <li class="about__key-item">PHONE</li>
      <li class="about__key-item">EMAIL</li>
      <li class="about__key-item">CITY</li>
      <li class="about__key-item">SOCIAL</li>
    </ul>
    <ul class="about__value">
      <li class="about__value-item">{{ phone }}</li>
      <li class="about__value-item">{{ email }}</li>
      <li class="about__value-item">{{ city }}</li>
      <li class="about__value-item">
        <ul class="about__social">
          <li class="about__social-item">
            <a :href="vkLink" rel="noreferrer" target="_blank">
              <i class="about__social-link fab fa-vk"></i>
            </a>
          </li>
          <li class="about__social-item">
            <a :href="instLink" rel="noreferrer" target="_blank">
              <i class="about__social-link fab fa-instagram"></i>
            </a>
          </li>
          <li class="about__social-item">
            <a :href="inLink" rel="noreferrer" target="_blank">
              <i class="about__social-link fab fa-linkedin"></i>
            </a>
          </li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      phone: null,
      email: null,
      error: null,
      city: null,
      vkLink: null,
      instLink: null,
      inLink: null
    };
  },
  async mounted() {
    try {
      this.profiles = await this.$strapi.$profiles.find();
      this.inLink = this.profiles[0].socials[0].link_in;
      this.vkLink = this.profiles[0].socials[0].link_vk;
      this.instLink = this.profiles[0].socials[0].link_inst;
      this.email = this.profiles[0].email;
      this.city = this.profiles[0].city;
      this.phone = this.profiles[0].phone;
    } catch (error) {
      this.error = error;
      console.log(this.error);
    }
  }
};
</script>

<style scoped>
.about {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  margin-bottom: 20px;
  font-style: normal;
  margin: 23px 0 0 0;
}

.about__key {
  padding: 0;
  margin: 0;
  font-weight: bold;
  font-size: 14px;
}

.about__value {
  padding: 0;
  margin: 0 0 0 40px;
  font-weight: normal;
  font-size: 14px;
}

.about__key-item {
  list-style-type: none;
  margin: 0 0 10px 0;
}

.about__value-item {
  list-style-type: none;
  margin: 0 0 10px 0;
  text-align: left;
  color: #5c5c5c;
}

.about__social {
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
}

.about__social-item {
  padding: 0;
  margin: 0 28px 0 0;
  list-style-type: none;
}

.about__social-link {
  color: black;
}
</style>
