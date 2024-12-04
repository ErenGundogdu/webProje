<template>
  <div class="favorites">
    <!-- Filtreler -->
    <div class="filters">
      <button class="filter-btn active">Tümü</button>
      <button class="filter-btn"><i class="fa-regular fa-heart"></i> En Çok Beğenilenler</button>
      <button class="filter-btn"><i class="fa-solid fa-fire"></i> En Çok Satanlar</button>
      <button class="filter-btn"><i class="fa-regular fa-star"></i> En Çok Değerlendirilenler</button>
    </div>

    <!-- Ürün Sayısı -->
    <p class="product-count">5 ürün listelendi.</p>

    <!-- Ürün Listesi -->
    <div class="product-list">
      <div class="product-card" v-for="(product, index) in products" :key="index">
        <!-- Ürün Görseli -->
        <div class="product-image-wrapper">
          <img :src="product.image" alt="Ürün resmi" class="product-image" />
          <button class="remove-btn">🗑️</button>
        </div>

        <!-- Ürün Bilgileri -->
        <div class="product-info">
          <h3 class="product-title">{{ product.title }}</h3>
          <p class="product-desc">{{ product.description }}</p>
          <p class="product-color">Renk: <span>{{ product.color }}</span></p>
          <p class="product-price">{{ product.price }} TL</p>
          <div class="product-actions">
            <select class="size-select">
              <option>Beden</option>
            </select>
            <button class="add-to-cart-btn">SEPETE EKLE</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Favorites",
  data() {
    return {
      products: [
        {
          image:
            "https://img-lcwaikiki.mncdn.com/mnpadding/600/800/ffffff/pim/productimages/20242/7330160/v1/l_20242-w4cm22z4-m0t_a.jpg",
          title: "LCW ACCESSORIES",
          description: "Spiderman Baskılı Dijital Kol Saati",
          color: "KARIŞIK",
          price: "229,99",
        },
        {
          image:
            "https://img-lcwaikiki.mncdn.com/mnpadding/600/800/ffffff/mpsellerportal/v0/img_034606996v0_01ce374e-346e-44a7-b333-ea1f23f87f03.jpg",
          title: "Esem",
          description: "JEAN Kadın Terlik Siyah",
          color: "BEJ",
          price: "359,90",
        },
        {
          image:
            "https://img-lcwaikiki.mncdn.com/mnpadding/600/800/ffffff/mpsellerportal/v0/img_033235983v0_a0975f0e-7242-4892-aac6-24a72cd0929e.jpg",
          title: "Bargello",
          description: "134 Kadın 50 Ml Parfüm Edp Oriental",
          color: "RENKSİZ",
          price: "340,00",
        },
        {
          image:
            "https://img-lcwaikiki.mncdn.com/mnpadding/600/800/ffffff/pim/productimages/20242/7696807/v1/l_20242-w4jf70z4-cvl_a.jpg",
          title: "LCW ACCESSORIES",
          description: "Batman Baskılı Erkek Çocuk Okul Çantası",
          color: "SİYAH",
          price: "499,99",
        },
        {
          image:
            "https://img-lcwaikiki.mncdn.com/mnpadding/600/800/ffffff/pim/productimages/20242/7183958/v1/l_20242-w44391z1-lt4_a.jpg",
          title: "LCW Baby",
          description: "Kapüşonlu Baskılı Kız Bebek Astronot Mont",
          color: "PEMBE",
          price: "1.299,99",
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Genel */
.favorites {
  padding: 20px;
  font-family: Arial, sans-serif;
}

/* Filtre Bölümü */
.filters {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

.filter-btn {
  padding: 10px 15px;
  border: 1px solid #ddd;
  border-radius: 20px;
  background-color: #fff;
  cursor: pointer;
}

.filter-btn.active {
  background-color: #007bff;
  color: white;
}

/* Ürün Sayısı */
.product-count {
  font-size: 16px;
  color: #555;
  margin-bottom: 20px;
}

/* Ürün Listesi */
.product-list {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 20px;
}

/* Ürün Kartı */
.product-card {
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 15px;
  position: relative;
}

.product-image-wrapper {
  position: relative;
}

.product-image {
  width: 100%;
  border-radius: 8px;
  margin-bottom: 10px;
}

.remove-btn {
  position: absolute;
  top: 5px;
  right: 5px;
  background-color: transparent;
  border: none;
  cursor: pointer;
}

/* Ürün Bilgileri */
.product-info {
  text-align: left;
}

.product-title {
  font-size: 14px;
  font-weight: bold;
  margin-bottom: 5px;
}

.product-desc {
  font-size: 12px;
  margin-bottom: 10px;
}

.product-color {
  font-size: 12px;
  color: #555;
  margin-bottom: 5px;
}

.product-price {
  font-size: 16px;
  font-weight: bold;
  color: #333;
  margin-bottom: 10px;
}

/* Sepet Ekle */
.product-actions {
  display: flex;
  gap: 10px;
  align-items: center;
}

.size-select {
  flex: 1;
  padding: 5px;
}

.add-to-cart-btn {
  flex: 2;
  background-color: #007bff;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.add-to-cart-btn:hover {
  background-color: #0056b3;
}
</style>
