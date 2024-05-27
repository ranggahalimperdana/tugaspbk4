<template>
  <div>
    <button @click="fetchImage('image1')">Di Ambil Dari File Image 1</button>
    <button @click="fetchImage('image2')">Di Ambil Dari File Image 2 </button>
  </div>
</template>

<script>
export default {
  methods: {
    fetchImage(imageType) {
      this.$emit('fetch-image', imageType);
    }
  }
};
</script>

<style scoped>
button {
  background-color: #28a745;
  color: white;
  border: none;
  padding: 10px 15px;
  margin: 5px;
  border-radius: 4px;
  cursor: pointer;
  font-family:Georgia, 'Times New Roman', Times, serif;
}

button:hover {
  background-color: #218838;

}
</style>
