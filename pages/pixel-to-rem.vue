<template>
    <div>
      <h1>Pixel to Rem Converter</h1>
    <p>This tool converts pixels to rems and vice versa.</p>
    <h2>Instructions:</h2>
    <ol>
      <li>Enter a value in pixels in the first input field labeled "Pixels".</li>
      <li>Click the "Convert to Rem" button to convert the value to rems.</li>
      <li>The converted value will be displayed in the second input field labeled "Rems".</li>
      <li>To convert a value from rems to pixels, enter a value in rems in the second input field labeled "Rems".</li>
      <li>Click the "Convert to Pixels" button to convert the value to pixels.</li>
      <li>The converted value will be displayed in the first input field labeled "Pixels".</li>
    </ol>
    <h2>Example:</h2>
    <p>If you enter the value "16" in the "Pixels" input field and click the "Convert to Rem" button, the tool will calculate that 16 pixels is equal to 1 rem and display the value "1.00" in the "Rems" input field.</p>
      <div>
        <label for="pxInput">Pixels:</label>
        <input id="pxInput" v-model="pxValue" type="number" step="0.01">
        <button @click="convertPxToRem">Convert to Rem</button>
      </div>
      <div>
        <label for="remInput">Rems:</label>
        <input id="remInput" v-model="remValue" type="number" step="0.01">
        <button @click="convertRemToPx">Convert to Pixels</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    head: {
        title: 'Pixel to Rem Converter | gkalmoukis',
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
        pxValue: '',
        remValue: ''
      };
    },
    methods: {
      convertPxToRem() {
        if (this.pxValue !== '') {
          this.remValue = (this.pxValue / 16).toFixed(2);
        } else {
          this.remValue = '';
        }
      },
      convertRemToPx() {
        if (this.remValue !== '') {
          this.pxValue = (this.remValue * 16).toFixed(2);
        } else {
          this.pxValue = '';
        }
      }
    }
  };
  </script>