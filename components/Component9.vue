<template>
  <div class="lc-waikiki">
    <header>
      <h1>LC Waikiki</h1>
      <nav>
        <ul>
          <li><a href="#">Kurumsal</a></li>
          <li><a href="#">İnsan Kaynakları</a></li>
          <li><a href="#">Mağazalar</a></li>
          <li><a href="#">Kurumsal Satış</a></li>
          <li><a href="#">Sürdürülebilirlik</a></li>
          <li><a href="#">İletişim</a></li>
        </ul>
      </nav>
    </header>
    <main>
      <div class="store-filter">
        <label>
          Ülke:
          <select v-model="selectedCountry">
            <option v-for="country in countries" :key="country" :value="country">
              {{ country }}
            </option>
          </select>
        </label>
        <label>
          İl:
          <select v-model="selectedCity">
            <option v-for="city in cities" :key="city" :value="city">
              {{ city }}
            </option>
          </select>
        </label>
        <label>
          İlçe:
          <select v-model="selectedDistrict">
            <option v-for="district in districts" :key="district" :value="district">
              {{ district }}
            </option>
          </select>
        </label>
        <label>
          Tüm Mağazalar:
          <select v-model="selectedStore">
            <option v-for="store in stores" :key="store" :value="store">
              {{ store }}
            </option>
          </select>
        </label>
      </div>
    </main>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "LcWaikiki",
  setup() {
    const selectedCountry = ref("");
    const selectedCity = ref("");
    const selectedDistrict = ref("");
    const selectedStore = ref("");

    const countries = ref(["Türkiye", "Almanya", "Fransa"]); // Örnek ülkeler
    const cities = ref(["İstanbul", "Ankara", "İzmir"]); // Örnek iller
    const districts = ref(["Kadıköy", "Beşiktaş", "Şişli"]); // Örnek ilçeler
    const stores = ref(["Mağaza 1", "Mağaza 2", "Mağaza 3"]); // Örnek mağazalar

    return {
      selectedCountry,
      selectedCity,
      selectedDistrict,
      selectedStore,
      countries,
      cities,
      districts,
      stores,
    };
  },
});
</script>

<style scoped>
.lc-waikiki {
  font-family: Arial, sans-serif;
}

header {
  display: flex;
  flex-direction: column; /* Flex yönü kolon yapıldı */
  align-items: flex-start;
  background-color: #0056a6;
  color: white;
  padding: 10px 20px;
}

header h1 {
  margin: 0;
  margin-bottom: 10px; /* LC Waikiki ile Kurumsal arasında mesafe */
}

nav ul {
  list-style: none;
  display: flex;
  gap: 20px;
  margin: 0;
  padding: 0;
}

nav a {
  color: white;
  text-decoration: none;
}

.store-filter {
  display: flex;
  gap: 20px;
  margin: 20px;
}

label {
  display: flex;
  flex-direction: column;
  font-weight: bold;
}

select {
  padding: 5px;
  border: 1px solid #ddd;
  border-radius: 4px;
}
</style>
