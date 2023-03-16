<template>
    <h3>Percentage Change Calculator</h3>

    <p>This page provides a percentage change calculator. To use this calculator, simply follow these steps:</p> 
    <ol>
        <li>Enter the original value in the "Original" input field.</li>
        <li>Enter the new value in the "New" input field.</li>
        <li>Click the "Calculate" button to see the percentage change.</li>
        <li>The percentage change will be displayed in the four different formats - percentage fixed, fixed, percentage raw, and raw.</li>
        <li>Click the "Reset" button to clear the input fields and the percentage change display.</li>
    </ol>
    <p>For example, let's say you want to calculate the percentage change of a product's price between its original value of 50 EUR and its new value of 75 EUR. Here's how you can use this form:</p>
    <ul>
        <li>Enter 50 in the "Original" input field.</li>
        <li>Enter 75 in the "New" input field.</li>
        <li>Click the "Calculate" button.</li>
        <li>The percentage change will be displayed in the four different formats.</li>
    </ul>

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
        <button type="submit">Calculate Change</button>
      </form>
      <div v-if="percentageChange !== null">
        <div class="row"> <span>percentage fixed</span>  <pre>{{ percentageChange.toFixed(2) }}%</pre></div>
        <div class="row"> <span>fixed</span>  <pre>{{ percentageChange.toFixed(2) }}</pre> </div>
        <div class="row"> <span>percentage raw</span>  <pre>{{ percentageChange }}%</pre> </div>
        <div class="row"> <span>raw</span>  <pre>{{ percentageChange }}</pre></div>
        <div class="row"> <button @click="resetForm">Reset</button> </div>
    </div>
    </div>
  </template>
  
  <script>
  export default {
    head: {
        title: 'Percentage Change | gkalmoukis',
        meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        {
            hid: 'description',
            name: 'description',
            content: 'This page provides a percentage change calculator.'
        }
    ]},

    layout: "default",
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
      },
      resetForm() {
        this.originalValue = null;
        this.newValue = null;
        this.percentageChange = null;

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