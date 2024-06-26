<template>
  <div class="container" :style="{ backgroundColor: backgroundColor }">
    <h1 :class="{ 'text-red': isRed }">Contoh Halaman Web</h1>
    <p :style="{ 'font-size': fontSize + 'px' }">Ini adalah halaman web sederhana dengan gaya.</p>
    <div class="buttons">
      <button @click="toggleRed">Toggle Warna</button>
      <button @click="increaseFontSize">Perbesar Ukuran Font</button>
      <p class="total-clicks">Total Klik: {{ totalClicks }}</p>
    <button @click="incrementTotalClicks">Tambah Klik</button> 
    </div>
    
    
    <input 
      type="text" 
      v-model="inputText" 
      placeholder="Masukkan teks"
      @keyup.enter="saveText"
    >

    <!-- Output yang menampilkan teks yang tersimpan -->
    <div v-if="savedTexts.length > 0" class="saved-texts">
      <h2>Teks yang tersimpan:</h2>
      <div v-for="(text, index) in savedTexts" :key="index" class="saved-text">
        <p>{{ text }}</p>
        <button @click="deleteText(index)">Delete</button>
      </div>
    </div>
    
    <!-- Output yang menampilkan teks yang sedang diketik secara real-time -->
    <div v-if="inputText" class="real-time-text">
      <h2>Teks yang sedang ditulis:</h2>
      <p>{{ inputText }}</p>
    </div>
  
  </div>
</template>

<script>
export default {
  data() {
    return {
      isRed: false,
      fontSize: 16,
      totalClicks: 0,
      inputText: '',
      savedTexts: [],
      backgroundColor: 'rgb(240, 240, 240)' // Ubah nilai background ke RGB
    };
  },
  methods: {
    toggleRed() {
      this.isRed = !this.isRed;
    },
    increaseFontSize() {
      this.fontSize += 2;
    },
    incrementTotalClicks() {
      this.totalClicks++;
    },
    saveText() {
      if (this.inputText.trim() !== '') { // Menyimpan teks hanya jika tidak kosong
        this.savedTexts.push(this.inputText);
        this.inputText = ''; // Bersihkan input setelah disimpan
      }
    },
    deleteText(index) {
      this.savedTexts.splice(index, 1); // Menghapus teks dari array berdasarkan index
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.text-red {
<<<<<<< HEAD
  color: blue
=======
  color: yellow
>>>>>>> 818a2e682e534eee423cb7f4f0b098622c94f11b
}

.buttons {
  margin-bottom: 20px;
}

.buttons button {
  padding: 10px 20px;
  margin-right: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.buttons button:hover {
  background-color: #0056b3;
}

.total-clicks {
  font-weight: bold;
  margin-bottom: 10px;
}

input[type="text"] {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.saved-texts {
  margin-bottom: 20px;
}

.saved-text {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.saved-text button {
  padding: 5px 10px;
  background-color: #dc3545;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.saved-text button:hover {
  background-color: #c82333;
}

.real-time-text {
  padding: 10px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 4px;
}
.container {
  text-align: center;
}

.quick-count-button {
  padding: 10px 20px;
  background-color: rgb(65, 105, 225); /* Warna latar belakang */
  color: white; /* Warna teks */
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s ease;
}

.quick-count-button:hover {
  background-color: rgb(30, 70, 170); /* Warna latar belakang saat dihover */
}
</style>
