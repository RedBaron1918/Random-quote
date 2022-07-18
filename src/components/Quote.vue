<template>
  <section class="quote">
    <div class="quote-content">{{ quote }}</div>
  </section>
</template>

<script>
export default {
  props: ["quote"],
};
</script>

<style scoped>
.quote {
  margin: 0 auto;
  padding: 32px;
  max-width: 720px;
}
.quote-content {
  font-size: 28px;
  font-weight: 700;
  background-color: var(--dark);
  color: var(--light);
  padding: 46px 32px;
  border-radius: 16px;
}
</style>
