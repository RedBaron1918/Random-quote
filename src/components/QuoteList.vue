<template>
  <section class="quote-list">
    <div
      class="quote"
      v-for="(quote, index) in quotes.slice().reverse()"
      :key="index"
    >
      <div class="quote-content">
        {{ quote }}
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: ["quotes"],
};
</script>

<style scoped>
.quote-list {
  margin: 0 auto;
  padding: 32px;
  max-width: 720px;
}
.quote {
  background-color: var(--light);
  padding: 16px;
  border-radius: 16px;
  margin-bottom: 16px;
}
.quote-content {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  line-height: 18px;
  max-height: 18px;
}

.quote-content:hover {
  white-space: unset;
  max-height: unset;
}
</style>
