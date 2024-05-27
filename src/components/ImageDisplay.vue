<template>
  <div class="image-container">
    <img :src="imageUrl" alt="Random Image">
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  props: {
    imageUrl: String,
    message: String
  }
};
</script>

<style scoped>
.image-container {
  margin-top: 20px;
}

img {
  max-width: 100%;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

p {
  margin-top: 10px;
  color: #666;
}
</style>
