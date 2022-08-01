<template>
  <p class="absolute text-center top-0 left-1/2 -translate-x-1/2 translate-y-1/2 text-grayish-blue">Click on card to open input for generate qr code</p>

  <div class="h-screen flex justify-center items-center">
    <QRCodeCard :qrCode="textToQrCode" @click="generateInputShow = !generateInputShow" />
  </div>

  <div class="absolute inset-0 bg-gray-400 bg-opacity-70 z-50 w-full h-screen" v-show="generateInputShow">
    <p class="text-white absolute z-50 -mt-14 -ml-32 top-1/2 left-1/2 -translate-x-1/2 translate-y-1/2">Press Enter or Shift + Space on input to close this window</p>

    <input type="text" placeholder="Enter text to generate qr code"
      @keydown.shift.space="generateInputShow = !generateInputShow"
      @keydown.enter="generateInputShow = !generateInputShow"
      v-model="textToQrCode"
      class="w-2/5 p-2 outline-none rounded-lg shadow absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 focus:border-2 focus:border-light-blue duration-150">
  </div>

  <div class="attribution">
    Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
    Coded by <a href="#">Denis Ostrovsky</a>.
  </div>
</template>

<script lang="ts">
  import { defineComponent } from 'vue';
  import QRCodeCard from '@/components/QRCodeCard.vue'

  export default defineComponent({
    name: 'App',
    components: {
      QRCodeCard
    },

    data() {
      return {
        generateInputShow: false,
        textToQrCode: ''
      }
    },
  });
</script>

<style>
  .attribution {
    font-size: 11px;
    text-align: center;

    width: 100%;
    position: absolute;
    bottom: 0;
    left: 50%;
    right: 50%;
    transform: translate(-50%, -50%);
  }

  .attribution a {
    color: hsl(228, 45%, 44%);
  }
</style>