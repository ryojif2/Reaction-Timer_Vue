<template>
  <p>Results: {{ score }} ms</p>
  <p>{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Sick skillz";
    } else if (this.score < 500) {
      this.rank = "Not too shabby";
    } else {
      this.rank = "Get Gud";
    }
  },
};
</script>

<style></style>
