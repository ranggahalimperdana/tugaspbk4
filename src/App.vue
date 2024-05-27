<template>
  <div class="app-container">
    <h1>Data di Ambil Dari Dua File Komponen Yang Saling terhubung</h1>
    <image-button @fetch-image="fetchImage"></image-button>
    <image-display :image-url="imageUrl" :message="message" v-if="imageUrl"></image-display>
  </div>
</template>

<script>
import ImageButton from './components/ImageButton.vue';
import ImageDisplay from './components/ImageDisplay.vue';
import axios from 'axios';

export default {
  components: {
    ImageButton,
    ImageDisplay
  },
  data() {
    return {
      imageUrl: '',
      message: ''
    };
  },
  methods: {
    async fetchImage(imageType) {
      try {
        const response = await axios.get(`https://picsum.photos/200/300?random=${imageType}`, { responseType: 'blob' });
        this.imageUrl = URL.createObjectURL(response.data);
        this.message = `Image fetched from ${imageType}`;
      } catch (error) {
        console.error(error);
      }
    }
  }
};
</script>

<style>
body {
  font-family: 'Space Mono', monospace;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.app-container {
  background: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 600px;
  text-align: center;
}

h1 {
  color: #333;
}

button {
  background-color: #007BFF;
  color: white;
  border: none;
  padding: 10px 15px;
  margin: 10px;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
</style>
