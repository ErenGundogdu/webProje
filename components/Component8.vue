<template>
  <div class="component8">
    <!-- Arama Kutusu -->
    <div class="search-input-wrapper">
      <span class="search-icon">🔍</span>
      <input
        type="text"
        class="search-input"
        placeholder="Ürün, kategori veya marka ara"
        v-model="searchQuery"
        @focus="showDropdown = true"
        @blur="hideDropdown"
      />
      <span 
        class="clear-icon" 
        v-if="searchQuery" 
        @click="clearSearch"
      >✖</span>
      <button class="search-button" @click="performSearch">Ara</button>
    </div>
    
    <!-- Dropdown Menüsü -->
    <div class="dropdown" v-if="showDropdown">
      <!-- Trend Aramalar -->
      <div class="trend-aramalar">
        <h3>Trend Aramalar</h3>
        <div class="chip-container">
          <span class="chip" v-for="item in trendAramalar" :key="item">
            <i class="fa-regular fa-star"></i> {{ item }}
          </span>
        </div>
      </div>

      <!-- Popüler Kategoriler -->
      <div class="populer-kategoriler">
        <h3>Popüler Kategoriler</h3>
        <div class="chip-container">
          <span class="chip" v-for="item in populerKategoriler" :key="item">{{ item }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Component8",
  data() {
    return {
      showDropdown: false,
      searchQuery: "",
      trendAramalar: ["Pijama Takımı", "Mont ve Kaban", "Deri Ceket", "Tesettür Elbise", "Hoodie"],
      populerKategoriler: ["Mont ve Kaban", "Pantolon", "Tişört", "Elbise", "Ceket", "Kazak", "Sweatshirt", "Hırka", "Pijama", "Gömlek", "Takım"],
    };
  },
  methods: {
    hideDropdown() {
      setTimeout(() => {
        this.showDropdown = false;
      }, 200); // Tıklama sorununu önlemek için küçük gecikme
    },
    clearSearch() {
      this.searchQuery = "";
    },
    performSearch() {
      alert(`Arama yapılıyor: ${this.searchQuery}`);
    },
  },
};
</script>

<style scoped>
/* Genel Arama Barı Stilleri */
.component8 {
  position: relative; /* Arama çubuğunu bağlama konteksine sokar */
  width: 100%;
  max-width: 600px; /* Arama çubuğu genişliği */
  margin: 10px auto; /* Ortalamak için (yukarı taşındı) */
}

.search-input-wrapper {
  position: relative; /* Dropdown menüsü bu konteks içinde konumlanır */
  display: flex;
  align-items: center;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 10px 15px;
  gap: 10px; /* Öğeler arası boşluk */
}

.search-icon {
  font-size: 18px;
  color: #aaa;
}

.search-input {
  flex: 1;
  border: none;
  outline: none;
  font-size: 16px;
  color: #333;
}

.search-input::placeholder {
  color: #aaa;
  font-size: 16px;
}

.clear-icon {
  font-size: 16px;
  color: #aaa;
  cursor: pointer;
  transition: color 0.2s ease;
}

.clear-icon:hover {
  color: #007bff;
}

.search-button {
  padding: 8px 20px;
  font-size: 14px;
  color: #fff;
  background-color: #007bff;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.search-button:hover {
  background-color: #0056b3;
}

/* Dropdown Menüsü */
.dropdown {
  position: absolute;
  top: calc(100% + 8px); /* Arama kutusunun hemen altında */
  left: 0;
  width: 100%;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 8px;
  margin-top: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  z-index: 10;
  padding: 15px;
  overflow: hidden; /* Taşmayı engeller */
}

/* Başlıklar */
.dropdown h3 {
  font-size: 14px;
  color: #333;
  margin-bottom: 10px;
  font-weight: 600;
}

/* Chip Container */
.chip-container {
  display: flex;
  flex-wrap: wrap;
  gap: 8px; /* Chipler arası boşluk */
}

/* Chip Stilleri */
.chip {
  display: inline-block;
  padding: 8px 15px; /* Resimdeki gibi daha geniş */
  background-color: #f1f1f1;
  color: #555;
  font-size: 14px;
  border-radius: 20px; /* Daha yuvarlak */
  cursor: pointer;
  transition: background-color 0.2s ease, color 0.2s ease;
  white-space: nowrap; /* Taşmayı engeller */
}

.chip i {
  margin-right: 5px; /* İkon ile metin arası boşluk */
}

.chip:hover {
  background-color: #007bff;
  color: #fff;
}
</style>
