<template>
  <div>is is {{id}}</div>
</template>

<script>
export default {
  name: "TestIndex",
  data() {
    return {
      id: this.$route.params.id
    };
  }
};
</script>