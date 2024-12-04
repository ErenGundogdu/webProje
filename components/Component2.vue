<template>
  <div class="carousel-container">
    <!-- Slider İçeriği -->
    <div class="carousel-slide" :style="{ transform: `translateX(-${currentIndex * 100}%)`, transition: 'transform 0.5s ease-in-out' }">
      <div v-for="(slide, index) in slides" :key="index" class="slide">
        <img :src="slide.image" :alt="'Sayfa ' + (index + 1)" class="slide-image" />
      </div>
    </div>

    <!-- Navigasyon Butonları -->
    <button class="carousel-button prev" @click="prevSlide">←</button>
    <button class="carousel-button next" @click="nextSlide">→</button>

    <!-- Sayfa Göstergeleri -->
    <div class="carousel-dots">
      <span
        v-for="(slide, index) in slides"
        :key="index"
        class="dot"
        :class="{ active: index === currentIndex }"
        @click="goToSlide(index)"
      ></span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Component2",
  data() {
    return {
      currentIndex: 0, // Aktif slaytın indeksi
      slides: [
        { image: "https://img-lcwaikiki.mncdn.com/Resource/Images/Banner/151124-YENIYIL-YENIYIL-KOLEKSIYON.JPG" },
        { image: "https://img-lcwaikiki.mncdn.com/Resource/Images/Banner/181124-YILBASI-HOME.JPG" },
        { image: "https://img-lcwaikiki.mncdn.com/Resource/Images/Banner/151124-YENIYIL-YETISKIN-GIYIM-2.JPG" },
        { image: "https://img-lcwaikiki.mncdn.com/Resource/Images/Banner/151124-YENIYIL-CCK-SIK-SECIMLER.JPG" },
        { image: "https://img-lcwaikiki.mncdn.com/Resource/Images/Banner/151124-YENIYIL-PIJAMA.JPG" },
        { image: "https://img-lcwaikiki.mncdn.com/Resource/Images/Banner/151124-YENIYIL-COK-ARANALAR.JPG" },
      ], // 5 sayfa için resim ekledik
    };
  },
  methods: {
    nextSlide() {
      this.currentIndex =
        (this.currentIndex + 1) % this.slides.length; // Sonraki slayta geç
    },
    prevSlide() {
      this.currentIndex =
        (this.currentIndex - 1 + this.slides.length) % this.slides.length; // Önceki slayta geç
    },
    goToSlide(index) {
      this.currentIndex = index; // Belirli slayta git
    },
  },
};
</script>

<style scoped>
.carousel-container {
  position: relative;
  width: 100%;
  max-width: 100%;
  margin: 0 auto;
  overflow: hidden;
  border-radius: 8px;
}

.carousel-slide {
  display: flex;
  height: auto; /* Otomatik yüksekliği destekle */
}

.slide {
  min-width: 100%;
  height: auto; /* Otomatik yüksekliği destekle */
}

.slide-image {
  width: 100%;
  height: auto; /* Resim oranını koruyarak genişlik ve yükseklik ayarı */
  object-fit: cover;
  border-radius: 8px;
}

.carousel-button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: white;
  color: black;
  border: 1px solid black;
  padding: 10px;
  cursor: pointer;
  border-radius: 50%;
  font-size: 20px;
  z-index: 2;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.carousel-button.prev {
  left: 15px;
}

.carousel-button.next {
  right: 15px;
}

.carousel-dots {
  position: absolute;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 5px;
}

.dot {
  width: 10px;
  height: 10px;
  background-color: white;
  border-radius: 50%;
  cursor: pointer;
  opacity: 0.5;
  transition: opacity 0.3s ease;
}

.dot.active {
  opacity: 1;
  background-color: white;
}

</style>
