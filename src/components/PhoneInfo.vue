<template>
    <div class="phone-info">
      <PhoneDisplay @phone-selected="displayPhoneInfo" />
      <div v-if="selectedPhone" class="phone-details">
        <h2>Info HP Terpilih:</h2>
        <p>Merk: {{ selectedPhone.brand }}</p>
        <p>Model: {{ selectedPhone.model }}</p>
        <p>Harga: {{ selectedPhone.price }}</p>
      </div>
      <slot></slot>
    </div>
  </template>
  
  <script>
  import PhoneDisplay from './PhoneDisplay.vue';
  
  export default {
    name: "PhoneInfo",
    components: {
      PhoneDisplay
    },
    data() {
      return {
        selectedPhone: null
      };
    },
    methods: {
      displayPhoneInfo(phoneInfo) {
        this.selectedPhone = phoneInfo;
      }
    }
  };
  </script>
  
  <style scoped>
  .phone-info {
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 5px;
    background-color: #f9f9f9;
  }
  
  .phone-details {
    margin-top: 20px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #fff;
  }
  
  h2 {
    margin-bottom: 10px;
  }
  
  p {
    margin: 5px 0;
  }
  </style>
  