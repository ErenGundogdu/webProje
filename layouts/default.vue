<template>
  <div class="layout-container">
    <!-- Sol Menü -->
    <nav class="nav-bar">
      <button
        v-for="(item, index) in components"
        :key="index"
        @click="setActiveComponent(item.component)"
      >
        {{ item.label }}
      </button>
    </nav>

    <!-- Sağ Alan: Dinamik Bileşen -->
    <main class="main-content">
      <component
        v-if="activeComponent"
        :is="activeComponent"
      />
      <div v-else class="placeholder">
        <h2>Hoş Geldiniz!</h2>
        <p>Soldaki menüden bir seçenek seçerek devam edebilirsiniz.</p>
      </div>
    </main>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Component1 from "~/components/Component1.vue";
import Component2 from "~/components/Component2.vue";
import Component3 from "~/components/Component3.vue";
import Component4 from "~/components/Component4.vue";
import Component5 from "~/components/Component5.vue";
import Component6 from "~/components/Component6.vue";
import Component7 from "~/components/Component7.vue";
import Component8 from "~/components/Component8.vue";
import Component9 from "~/components/Component9.vue";
import Component10 from "~/components/Component10.vue";

// Bileşen Listesi
const components = [
  { label: "Ana Ekran Üst Kısmı", component: Component1 },
  { label: "Slider", component: Component2 },
  { label: "Giriş yap/Üye ol", component: Component3 },
  { label: "Sepetim", component: Component4 },
  { label: "Ürün Listeleme", component: Component5 },
  { label: "Favorilerim", component: Component6 },
  { label: "İletişim Formu", component: Component7 },
  { label: "Arama Çubuğu", component: Component8 },
  { label: "Mağazalar", component: Component9 },
  { label: "Sayfa Sonu", component: Component10 },
];

// Aktif bileşen
const activeComponent = ref(null);

// Bileşeni aktif hale getiren fonksiyon
const setActiveComponent = (component) => {
  activeComponent.value = component;
};
</script>

<style scoped>
.layout-container {
  display: flex;
  height: 100vh;
  position: relative;
}

/* Sol Menü */
.nav-bar {
  width: 20%;
  background-color: #f5f5f5;
  padding: 20px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.nav-bar button {
  padding: 10px;
  font-size: 16px;
  cursor: pointer;
  border: none;
  background-color: blue;
  color:white;
  border-radius: 4px;
  transition: background-color 0.3s ease;
}

.nav-bar button:hover {
  background-color: #0056b3;
}

/* Sağ Alan */
.main-content {
  flex-grow: 1;
  padding: 20px;
  display: flex;
  justify-content: center; /* Merkezleme */
  align-items: center; /* Dikey merkezleme */
  background-color: #ffffff;
}

.placeholder {
  text-align: center;
  color: #555;
}

.placeholder h2 {
  font-size: 24px;
  margin-bottom: 10px;
}

.placeholder p {
  font-size: 18px;
}
</style>
