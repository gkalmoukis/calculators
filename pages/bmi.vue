<template>
    <h3>BMI (Body Mass Index) Calculator</h3>

    <p>The BMI Calculator form allows you to calculate your BMI based on your weight and height. BMI is a measure of body fat based on height and weight that applies to both adult men and women. BMI is used as a screening tool to identify possible weight problems for adults.</p> 
    <h5>Instructions:</h5>
    <ol>
        <li>Enter your weight in kilograms (kg) in the "Weight" field. The weight must be a number greater than zero and is required to calculate your BMI.</li>
        <li>Enter your height in centimeters (cm) in the "Height" field. The height must be a number greater than zero and is required to calculate your BMI.</li>
        <li>Click the "Calculate BMI" button to calculate your BMI.</li>
        <li>The calculated BMI value will appear below the button with the message "Your BMI is [BMI value]".</li>
        <li>The BMI value will be displayed with two decimal places.</li>
        <li>The message below the BMI value will indicate your weight category based on your BMI.</li>
    </ol>

    <div>
        <form @submit.prevent="calculateBMI">
      <label for="weight">Weight (kg):</label>
      <input id="weight" type="number" v-model="weight" required>
      <br>
      <label for="height">Height (cm):</label>
      <input id="height" type="number" v-model="height" required>
      <br>
      <button type="submit">Calculate BMI</button>
    </form>
    <div v-if="bmi !== null">
      <p class="row"> <span>Your BMI is</span>  <pre>{{ bmi.toFixed(2) }}</pre> </p>
      <p v-if="bmi < 18.5">You are underweight</p>
      <p v-else-if="bmi < 25">Your weight is normal</p>
      <p v-else-if="bmi < 30">You are overweight</p>
      <p v-else>You are obese</p>
    </div>
    </div>
  </template>
  
  <script>
  export default {
    head: {
        title: 'BMI | gkalmoukis',
        meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        {
            hid: 'description',
            name: 'description',
            content: 'The BMI Calculator form allows you to calculate your BMI based on your weight and height.'
        }
    ]},
    
    layout: "default",
        data() {
      return {
        weight: null,
      height: null,
      bmi: null
      };
    },
    methods: {
        calculateBMI() {
      const heightInMeters = this.height / 100;
      this.bmi = this.weight / (heightInMeters * heightInMeters);
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