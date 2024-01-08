<template>
  <div class="container" @click="fetchNewQuote">
    <div class="quote">
      <blockquote>{{ quote }}</blockquote>
    </div>
  </div>

</template>
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'BeNice',
  data() {
    return {
      quote: '',
    };
  },
  methods: {
    async getRandomQuote(): Promise<string> {
      const response = await fetch("/benice.txt");
      const text = await response.text();
      const QUOTES = text.split("\n");
      const index = Math.floor(Math.random() * QUOTES.length);
      console.log(response);
      return QUOTES[index];
    },
    async fetchNewQuote() {
      this.quote = await this.getRandomQuote();
    },
  },
  async mounted() {
    this.quote = await this.getRandomQuote();
  },
});
</script>
<style scoped>
.container {
  width: 100vw;
  height: 100vh;
}
.quote {
  text-align: center;
  font-size: 1.5rem;
  margin: auto;
  padding: 15px;
  max-width: 70%;
  margin-top: 100px;
}

blockquote {
  font-size: 1.2rem;
  color: #333;
  margin-bottom: 20px;
}

.button {
  border: 0.5px solid #262f34;
  border-radius: 5%;
  background-color: transparent;
  color: #262f34;
  font-weight: 600;
  padding: 0.7em 1.3em;
  align-self: center;
}

@media screen and (max-width: 768px) {
  .container {
    width: 100vw;
    padding-top: 20px;
  }
}
</style>
