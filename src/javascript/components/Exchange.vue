<script>
import { defineComponent } from 'vue';

export default defineComponent({
  async setup() {
    const exchangeRates = await Promise.resolve({
      base: 'EUR',
      date: '2021-05-08',
      rates: {
        GBP: 0.870389,
        USD: 1.216325,
      }
    });

    return { rates: exchangeRates.rates };
  }
});
</script>

<template>
<ul class="list-group">
  <li class="list-group-item">Change to USD: {{ rates.USD }}</li>
  <li class="list-group-item">Change to GBP: {{ rates.GBP }} </li>
</ul>
</template>

