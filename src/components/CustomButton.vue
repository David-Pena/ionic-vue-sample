<template>
  <div class="custom-button" @click="handleClick">
    {{ buttonText }}
  </div>
</template>

<script setup lang="ts">
defineProps(["buttonText"]);

const handleClick = () => {
  console.log("Clicked...");
};
</script>

<style scoped>
.custom-button {
  /* Your custom button styles */
  background-color: #007bff;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

/* Additional styles can be added for hover, active, etc. states */
.custom-button:hover {
  background-color: #0056b3;
}
</style>
