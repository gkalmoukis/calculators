<template>
    <div>
      <h1>Percentage Calculator</h1>
      <h1>Percentage Calculator</h1>
    <p>This tool calculates the percentage of a number. Enter a number and a percentage, and click the "Calculate" button to see the result.</p>
    <h2>Instructions:</h2>
    <ol>
      <li>Enter a number in the input field labeled "Number".</li>
      <li>Enter a percentage in the input field labeled "Percentage".</li>
      <li>Click the "Calculate" button to calculate the percentage of the number.</li>
      <li>The result will be displayed below the input fields in a paragraph element.</li>
    </ol>
    <h2>Example:</h2>
    <p>If you enter the number "100" and the percentage "50" and click the "Calculate" button, the tool will calculate that 50% of 100 is 50 and display the result "50.00" below the input fields.</p>
      <div>
        <label for="numberInput">Number:</label>
        <input id="numberInput" v-model="number" type="number">
      </div>
      <div>
        <label for="percentageInput">Percentage:</label>
        <input id="percentageInput" v-model="percentage" type="number">
        <button @click="calculatePercentage">Calculate</button>
      </div>
      <div v-if="result !== null">
        <p>The {{ percentage }}% of {{ number }} is {{ result }}.</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    head: {
        title: 'Percentage Calculator | gkalmoukis',
        meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        {
            hid: 'description',
            name: 'description',
            content: 'Calculate the percentage of a number with our easy-to-use online tool. Enter a number and percentage and instantly get the result. Perfect for calculating discounts, taxes, and more. Try it now!'
        }
    ]},
    data() {
      return {
        number: '',
        percentage: '',
        result: null
      };
    },
    methods: {
      calculatePercentage() {
        if (this.number !== '' && this.percentage !== '') {
          this.result = (this.number * (this.percentage / 100)).toFixed(2);
        } else {
          this.result = null;
        }
      }
    }
  };
  </script>