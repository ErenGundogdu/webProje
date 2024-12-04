<template>
  <div class="product-list">
    <div class="product" v-for="(product, index) in products" :key="index">
      <!-- İndirim Etiketi -->
      <div v-if="product.discount" class="discount-tag">
        {{ product.discount }}
      </div>

      <!-- Ürün Görseli -->
      <img :src="product.image" :alt="product.name" class="product-image" />

      <!-- Ürün Bilgileri -->
      <div class="product-info">
        <h3 class="product-brand">{{ product.brand }}</h3>
        <p class="product-name">{{ product.name }}</p>
        
        <!-- Yıldızlar -->
        <div class="rating">
          <span class="stars">
            <span v-for="i in 5" :key="i" :class="{'filled': i <= product.rating}">
              &#9733; <!-- Yıldız karakteri -->
            </span>
          </span>
          <span class="rating-number">({{ product.rating }})</span>
        </div>

        <p class="price">{{ formatPrice(product.price) }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductList",
  data() {
    return {
      products: [
        {
          brand: "LCW Vision",
          name: "Slim Fit Dik Yaka Erkek Deri Görünümlü Mont",
          rating: 24,
          price: 1799.99,
          discount: "150 TL Özel %10 İndirim",
          image: "https://img-lcwaikiki.mncdn.com/mnpadding/600/800/ffffff/pim/productimages/20242/7100842/v1/l_20242-w40231z8-cvl-97-74-94-188_a.jpg",
        },
        {
          brand: "LCW Jeans",
          name: "779 Regular Fit İçi Polar Erkek Jean Pantolon",
          rating: 11,
          price: 899.99,
          discount: "250 TL Özel %15 İndirim",
          image: "https://img-lcwaikiki.mncdn.com/mnpadding/600/800/ffffff/pim/productimages/20242/7263414/v1/l_20242-w4ae94z8-309-93-78-93-187_a.jpg",
        },
        {
          brand: "LC Waikiki",
          name: "Standart Kalıp Erkek Pijama Takımı",
          rating: 1,
          price: 699.99,
          discount: null,
          image: "https://img-lcwaikiki.mncdn.com/mnpadding/600/800/ffffff/pim/productimages/20242/7448975/v2/l_20242-w4g416z8-jc7_u.jpg",
        },
        {
          brand: "LCW Vision",
          name: "Standart Kalıp Gömlek Yaka Süet Erkek Mont",
          rating: 24,
          price: 1999.99,
          discount: "150 TL Özel %10 İndirim",
          image: "https://img-lcwaikiki.mncdn.com/mnpadding/600/800/ffffff/pim/productimages/20242/7138031/v1/l_20242-w41099z8-yct-97-74-94-188_a.jpg",
        },
      ],
    };
  },
  methods: {
    formatPrice(price) {
      return price.toFixed(2) + " TL";
    },
  },
};
</script>

<style scoped>
.product-list {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
}

.product {
  width: 22%;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 10px;
  background-color: #fff;
  text-align: left;
  position: relative;
}

.discount-tag {
  position: absolute;
  top: 10px;
  left: 10px;
  background-color: red;
  color: white;
  padding: 5px;
  font-size: 12px;
  font-weight: bold;
  border-radius: 5px;
}

.product-image {
  width: 100%;
  height: auto;
  border-bottom: 1px solid #ddd;
  margin-bottom: 10px;
}

.product-brand {
  font-size: 14px;
  font-weight: bold;
  color: #444;
}

.product-name {
  font-size: 12px;
  color: #777;
}

.rating {
  margin: 5px 0;
  font-size: 14px;
  color: #f39c12;
}

.stars {
  font-size: 16px;
}

.stars span {
  color: #ddd; /* Boş yıldız */
}

.stars .filled {
  color: #f39c12; /* Doldurulmuş yıldız */
}

.rating-number {
  font-size: 12px;
  color: #777;
  margin-left: 5px;
}

.price {
  font-size: 16px;
  font-weight: bold;
  color: #2c3e50;
}
</style>
