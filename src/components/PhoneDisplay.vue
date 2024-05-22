<template>
    <div class="phone-display">
      <PhoneButton @phone-selected="handlePhoneSelected" />
      <form @submit.prevent="submitCustomPhone">
        <h3>Tambahkan Informasi HP</h3>
        <label>
          Merk:
          <input type="text" v-model="customPhone.brand" required>
        </label>
        <label>
          Model:
          <input type="text" v-model="customPhone.model" required>
        </label>
        <label>
          Harga:
          <input type="text" v-model="customPhone.price" required>
        </label>
        <button type="submit">Tambahkan HP</button>
      </form>
    </div>
  </template>
  
  <script>
  import PhoneButton from './PhoneButton.vue';
  
  export default {
    name: "PhoneDisplay",
    components: {
      PhoneButton
    },
    data() {
      return {
        customPhone: {
          brand: '',
          model: '',
          price: ''
        }
      };
    },
    methods: {
      handlePhoneSelected(phoneInfo) {
        this.$emit('phone-selected', phoneInfo);
      },
      submitCustomPhone() {
        this.$emit('phone-selected', this.customPhone);
        this.customPhone = { brand: '', model: '', price: '' }; // Reset the form
      }
    }
  };
  </script>
  
  <style scoped>
  .phone-display {
    margin: 20px 0;
  }
  
  form {
    margin-top: 20px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #f9f9f9;
  }
  
  form h3 {
    margin-bottom: 10px;
  }
  
  label {
    display: block;
    margin-bottom: 10px;
  }
  
  input {
    padding: 5px;
    font-size: 14px;
    margin-left: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
  }
  
  button {
    padding: 5px 10px;
    font-size: 14px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 3px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #45a049;
  }
  </style>
  