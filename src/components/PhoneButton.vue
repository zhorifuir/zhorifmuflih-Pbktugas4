<template>
    <div>
      <button @click="sendPhoneInfo">Klik untuk Menampilkan Info HP</button>
    </div>
  </template>
  
  <script>
  export default {
    name: "PhoneButton",
    data() {
      return {
        phoneInfo: {
          brand: "Iphone ",
          model: "15 Pro Max",
          price: "Rp 30.000.000"
        }
        
      };
    },
    methods: {
      sendPhoneInfo() {
        this.$emit('phone-selected', this.phoneInfo);
      }
    }
  };
  </script>
  
  <style scoped>
  button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #45a049;
  }
  </style>
  