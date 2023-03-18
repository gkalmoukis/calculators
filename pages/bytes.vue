<template>
    <div>
      <h1>Byte Converter</h1>
      <div>
        <label>Bytes:</label>
        <input type="number" v-model="bytes" @input="convert">
      </div>
      <div>
        <label>Bits:</label>
        <input type="number" v-model="bits" @input="convert">
      </div>
      <div>
        <label>Kilobytes:</label>
        <input type="number" v-model="kilobytes" @input="convert">
      </div>
      <div>
        <label>Megabytes:</label>
        <input type="number" v-model="megabytes" @input="convert">
      </div>
      <div>
        <label>Gigabytes:</label>
        <input type="number" v-model="gigabytes" @input="convert">
      </div>
      <div>
        <label>Terabytes:</label>
        <input type="number" v-model="terabytes" @input="convert">
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        bytes: 0,
        bits: 0,
        kilobytes: 0,
        megabytes: 0,
        gigabytes: 0,
        terabytes: 0,
      }
    },
    methods: {
      convert() {
        this.bits = this.bytes * 8
        this.kilobytes = this.bytes / 1024
        this.megabytes = this.bytes / 1024 / 1024
        this.gigabytes = this.bytes / 1024 / 1024 / 1024
        this.terabytes = this.bytes / 1024 / 1024 / 1024 / 1024
        
        if (this.bits > 0) {
          this.bytes = this.bits / 8
        } else if (this.kilobytes > 0) {
          this.bytes = this.kilobytes * 1024
        } else if (this.megabytes > 0) {
          this.bytes = this.megabytes * 1024 * 1024
        } else if (this.gigabytes > 0) {
          this.bytes = this.gigabytes * 1024 * 1024 * 1024
        } else if (this.terabytes > 0) {
          this.bytes = this.terabytes * 1024 * 1024 * 1024 * 1024
        }
      },
    },
  }
  </script>