<template>
  <div id="app" class="app-container">
    <PhoneInfo>
      <template #default>
        <p class="slot-content">Ini informasi Hp.</p>
      </template>
    </PhoneInfo>
  </div>
</template>

<script>
import PhoneInfo from './components/PhoneInfo.vue';

export default {
  name: 'App',
  components: {
    PhoneInfo
  }
};
</script>

<style scoped>
.app-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

.slot-content {
  margin-top: 20px;
  padding: 10px;
  border: 1px dashed #bbb;
  border-radius: 5px;
  background-color: #f0f0f0;
  text-align: center;
}
</style>
