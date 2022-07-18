<template>
  <Header title="Random quotes" />
  <Quote :quote="quote" />
  <div class="button-container">
    <button @click="getRandomQuote">Generate</button>
  </div>
  <QuoteList :quotes="quotes" />
</template>

<script>
import Header from "./components/Header.vue";
import Quote from "./components/Quote.vue";
import QuoteList from "./components/QuoteList.vue";

export default {
  name: "App",
  components: { Header, Quote, QuoteList },
  data() {
    return {
      quote: "",
      quotes: [],
    };
  },
  methods: {
    async getRandomQuote() {
      if (this.quote) {
        this.quotes = [...this.quotes, this.quote];
      }
      let data = await fetch("https://animechan.vercel.app/api/random");
      let res = await data.json();
      this.quote = res.quote;
    },
  },
  created() {
    this.getRandomQuote();
  },
};
</script>

<style>
:root {
  --primary: #d81e5b;
  --secondary: #8a4fff;
  --tertiary: #32cbff;
  --dark: #131a26;
  --light: #eee;
  --grey: #848484;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.button-container {
  display: flex;
  justify-content: center;
  padding: 0px 32px;
  margin: 30px auto;
}
.button-container button {
  border: none;
  outline: none;
  background-color: var(--primary);
  padding: 16px 32px;
  border-radius: 99px;
  color: var(--light);
  font-size: 28px;
  font-weight: 700;
  text-transform: uppercase;
  transition: 0.4s;
  cursor: pointer;
}
.button-container button:hover {
  background-color: var(--dark);
}
</style>
