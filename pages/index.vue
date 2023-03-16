<template>
    <h1>Hi, </h1>
    <p>
        Welcome to our website! 
        We offer a wide selection of calculators to help you with your everyday tasks. 
        <br>
        Our calculators are designed to save you time and money, and are tailored to meet your specific needs. 
        Our site is optimized for search engines, so you can easily find the calculator you need. 
        <br>
        Thanks for visiting our site and we hope you find it useful!
    </p>
</template>

<script>
export default {
  layout: "default",
  head: {
    title: 'Calculators | gkalmoukis',
    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        hid: 'description',
        name: 'description',
        content: 'We offer a wide selection of calculators to help you with your everyday tasks.'
      }
    ],
    link: [{ rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }]
  }
};
</script>
