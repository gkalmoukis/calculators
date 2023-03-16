<template>
    <h3>Percentage Change</h3>
    <div>
      <form @submit.prevent="calculatePercentageChange">
        <div>
          <label for="original">Original:</label>
          <input type="number" step="any" id="original" v-model="originalValue">
        </div>
        <div>
          <label for="new">New:</label>
          <input type="number" step="any" id="new" v-model="newValue">
        </div>
        <button type="submit">Calculate</button>
      </form>
      <div v-if="percentageChange !== null">
        <div class="row"> <span>percentage fixed</span>  <pre>{{ percentageChange.toFixed(2) }}%</pre></div>
        <div class="row"> <span>fixed</span>  <pre>{{ percentageChange.toFixed(2) }}</pre> </div>
        <div class="row"> <span>percentage raw</span>  <pre>{{ percentageChange }}%</pre> </div>
        <div class="row"> <span>raw</span>  <pre>{{ percentageChange }}</pre></div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        originalValue: null,
        newValue: null,
        percentageChange: null
      };
    },
    methods: {
      calculatePercentageChange() {
        const originalValue = Number(this.originalValue);
        const newValue = Number(this.newValue);
  
        // Calculate the percentage increase/decrease
        const percentageChange = ((newValue - originalValue) / originalValue) * 100;
  
        // Update the component's state with the result
        this.percentageChange = percentageChange;
      }
    }
  };
  </script>

<style>

.row{ 
    display: flex;
    align-items: center;
}

.row span { 
    margin-right: 0.3rem;
}
</style>