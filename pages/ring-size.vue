<template>
    <div>
      <h1>Ring Size Calculator</h1>
      <p>The Ring Size Calculator helps you determine your ring size based on your finger circumference or diameter. Here are the instructions for using the calculator:</p>
    <ol>
      <li>Wrap a piece of string or paper around the base of your finger.</li>
      <li>Mark the point where the string or paper overlaps to form a complete circle.</li>
      <li>Measure the length of the string or paper from the starting point to the mark in millimeters.</li>
      <li>Alternatively, measure the diameter of your finger using a ruler in millimeters.</li>
      <li>Enter the finger circumference or diameter in the appropriate input field in the Ring Size Calculator form.</li>
      <li>Click the "Calculate Ring Size" button to calculate your ring size.</li>
      <li>The calculated ring size will be displayed below the button.</li>
      <li>Use the chart below to find your ring size based on the measurement in millimeters.</li>
    </ol>
    <div class="contains-table">

        <table>
          <thead>
            <tr>
              <th>Measurement (mm)</th>
              <th>Ring Size</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>44.2</td>
              <td>3</td>
            </tr>
            <tr>
              <td>45.5</td>
              <td>3.5</td>
            </tr>
            <tr>
              <td>46.8</td>
              <td>4</td>
            </tr>
            <tr>
              <td>48</td>
              <td>4.5</td>
            </tr>
            <tr>
              <td>49.3</td>
              <td>5</td>
            </tr>
            <tr>
              <td>50.6</td>
              <td>5.5</td>
            </tr>
            <tr>
              <td>51.9</td>
              <td>6</td>
            </tr>
            <tr>
              <td>53.1</td>
              <td>6.5</td>
            </tr>
            <tr>
              <td>54.4</td>
              <td>7</td>
            </tr>
            <tr>
              <td>55.7</td>
              <td>7.5</td>
            </tr>
            <tr>
              <td>57</td>
              <td>8</td>
            </tr>
            <tr>
              <td>58.3</td>
              <td>8.5</td>
            </tr>
            <tr>
              <td>59.5</td>
              <td>9</td>
            </tr>
            <tr>
              <td>60.8</td>
              <td>9.5</td>
            </tr>
            <tr>
              <td>62.1</td>
              <td>10</td>
            </tr>
            <tr>
              <td>63.4</td>
              <td>10.5</td>
            </tr>
            
        <tr>
          <td>64.6</td>
          <td>11</td>
        </tr>
        <tr>
          <td>67.2</td>
          <td>11.5</td>
        </tr>
        <tr>
          <td>68.5</td>
          <td>12</td>
        </tr>
        <tr>
          <td>69.7</td>
          <td>12.5</td>
        </tr>
        <tr>
          <td>71</td>
          <td>13</td>
        </tr>
        <tr>
          <td>72.3</td>
          <td>13.5</td>
        </tr>
        <tr>
          <td>73.6</td>
          <td>14</td>
        </tr>
        <tr>
          <td>74.8</td>
          <td>14.5</td>
        </tr>
        <tr>
          <td>76.1</td>
          <td>15</td>
        </tr>
      </tbody>
    </table>
    </div>

      <form @submit.prevent="calculateRingSize">
        <label for="circumference">Finger Circumference (mm):</label>
        <input id="circumference" type="number" v-model="circumference" required>
        <br>
        <label for="diameter">Finger Diameter (mm):</label>
        <input id="diameter" type="number" v-model="diameter" required>
        <br>
        <button type="submit">Calculate Ring Size</button>
      </form>
      <div v-if="ringSize !== null">
        <p>Your ring size is {{ ringSize }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    head: {
        title: 'Ring size | gkalmoukis',
        meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        {
            hid: 'description',
            name: 'description',
            content: 'This page provides a percentage change calculator.'
        }
    ]},
    data() {
      return {
        circumference: null,
        diameter: null,
        ringSize: null
      };
    },
    methods: {
      calculateRingSize() {
        const circumferenceInMM = this.circumference;
        const diameterInMM = this.diameter;
        
        // Ring size calculation
        // This is just an example calculation, adjust based on your own requirements
        this.ringSize = (circumferenceInMM / 3.14) - 4;
      }
    }
  };
  </script>

  <style>
.contains-table {
    display: flex;
  align-items: center;
  justify-content: center;
}
</style>