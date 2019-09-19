<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">nuxt-generate-lifecycle-check</h1>
      <h2 class="subtitle">My prime Nuxt.js project</h2>
      <div class="links">
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">Documentation</a>
        <a href="https://github.com/nuxt/nuxt.js" target="_blank" class="button--grey">GitHub</a>
        <nuxt-link :to="'/'" class="button--grey">Page 1</nuxt-link>
      </div>
      <p>msg is: {{msg}}</p>
    </div>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";

const sleep = ms =>
  new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve();
    }, ms);
  });

export default {
  components: {
    Logo
  },
  data() {
    return {
      msg: "initial"
    };
  },
  created() {
    this.msg = "created";
    console.log("created");
  },
  async asyncData() {
    await sleep(1000);
    console.log("asyncData");
  },
  mounted() {
    this.msg = "mounted";
    console.log("mounted");
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
