<template>
  <div class="shopping-cart-container">
    <!-- Sol Kısım: Sepetim -->
    <div class="cart-section">
      <h2>Sepetim ({{ cartItems.length }} Ürün)</h2>

      <!-- Tümünü Seç -->
      <div class="select-all">
        <input type="checkbox" id="selectAll" v-model="selectAll" @change="toggleSelectAll" />
        <label for="selectAll">Tümünü Seç</label>
      </div>

      <!-- Ürün Listesi -->
      <div v-for="(item, index) in cartItems" :key="index" class="cart-item">
        <div class="item-header">
          <input type="checkbox" v-model="item.selected" />
          <span>{{ item.seller }} tarafından gönderilecek ürünler</span>
        </div>

        <div class="item-body">
          <div class="product-details">
            <img :src="item.image" alt="Ürün Görseli" class="product-image" />
            <div class="product-info">
              <h3>{{ item.name }}</h3>
              <p>Beden: {{ item.size }}</p>
              <p>Renk: {{ item.color }}</p>
            </div>
          </div>
          <div class="product-actions">
            <div class="quantity">
              <button @click="decreaseQuantity(index)">-</button>
              <input type="number" v-model="item.quantity" min="1" />
              <button @click="increaseQuantity(index)">+</button>
            </div>
            <div class="price">{{ formatPrice(item.price) }} TL</div>
            <button class="delete-button" @click="removeItem(index)">🗑</button>
          </div>
        </div>
      </div>
    </div>

    <!-- Sağ Kısım: Sipariş Özeti -->
    <div class="summary-section">
      <h3>Sipariş Özeti</h3>
      <div class="summary-details">
        <p>Ürün Toplam: <span>{{ formatPrice(totalPrice) }} TL</span></p>
        <p>İndirimler: <span>-{{ formatPrice(discount) }} TL</span></p>
        <p>Ara Toplam: <span>{{ formatPrice(totalPrice - discount) }} TL</span></p>
        <p>Kargo Ücreti: <span>{{ shippingFee }}</span></p>
      </div>
      <h4>Genel Toplam: <span>{{ formatPrice(totalPrice - discount + shippingFeeNumeric) }} TL</span></h4>
      <div class="extra-options">
        <input type="checkbox" id="giftWrap" v-model="giftWrap" />
        <label for="giftWrap">Hediye Paketi İstiyorum</label>
      </div>
      <button class="checkout-button">Ödeme Adımına Geç</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ShoppingCart",
  data() {
    return {
      cartItems: [
        {
          seller: "LC Waikiki",
          name: "Trekking Bot",
          size: 39,
          color: "Bej",
          quantity: 1,
          price: 719.99,
          selected: false,
          image: "https://img-lcwaikiki.mncdn.com/mnpadding/230/306/ffffff/pim/productimages/20242/7382636/v1/l_20242-w4eg93z4-cr8_a.jpg",
        },
        {
          seller: "LC Waikiki",
          name: "Sweatshirt",
          size: "M",
          color: "Açık Gri",
          quantity: 1,
          price: 449.99,
          selected: false,
          image: "https://img-lcwaikiki.mncdn.com/mnpadding/230/306/ffffff/pim/productimages/20242/7128381/v1/l_20242-w40850z8-yeg-102-88-96-190_a.jpg",
        },
      ],
      discount: 80.0,
      shippingFee: "BEDAVA",
      giftWrap: false,
      selectAll: false,
    };
  },
  computed: {
    totalPrice() {
      return this.cartItems.reduce((sum, item) => sum + item.price * item.quantity, 0);
    },
    shippingFeeNumeric() {
      return this.shippingFee === "BEDAVA" ? 0 : parseFloat(this.shippingFee);
    },
  },
  methods: {
    formatPrice(price) {
      return price.toFixed(2);
    },
    removeItem(index) {
      this.cartItems.splice(index, 1);
    },
    increaseQuantity(index) {
      this.cartItems[index].quantity++;
    },
    decreaseQuantity(index) {
      if (this.cartItems[index].quantity > 1) {
        this.cartItems[index].quantity--;
      }
    },
    toggleSelectAll() {
      this.cartItems.forEach((item) => {
        item.selected = this.selectAll;
      });
    },
  },
};
</script>

<style scoped>
.shopping-cart-container {
  display: flex;
  gap: 20px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
}

.cart-section {
  flex: 3;
  padding: 20px;
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 8px;
}

.select-all {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 20px;
}

.cart-item {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 10px;
  margin-bottom: 10px;
}

.item-header {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 14px;
  font-weight: bold;
  margin-bottom: 10px;
}

.item-body {
  display: flex;
  justify-content: space-between;
}

.product-details {
  display: flex;
  align-items: center;
  gap: 20px;
}

.product-image {
  width: 100px;
  height: 100px;
  object-fit: cover;
}

.product-info h3 {
  margin: 0;
}

.product-actions {
  display: flex;
  align-items: center;
  gap: 20px;
}

.quantity {
  display: flex;
  align-items: center;
  gap: 5px;
}

.quantity button {
  padding: 5px 10px;
  border: none;
  background-color: #007bff;
  color: white;
  cursor: pointer;
  border-radius: 4px;
}

.price {
  font-weight: bold;
}

.delete-button {
  background-color: transparent;
  border: none;
  font-size: 16px;
  cursor: pointer;
}

.summary-section {
  flex: 1;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #fff;
}

.summary-details {
  margin-bottom: 20px;
}

.summary-details p {
  display: flex;
  justify-content: space-between;
  margin: 5px 0;
}

.extra-options {
  margin-bottom: 20px;
}

.checkout-button {
  width: 100%;
  padding: 12px;
  font-size: 16px;
  font-weight: bold;
  background-color: #28a745;
  color: #fff;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  text-align: center;
}

.checkout-button:hover {
  background-color: #218838;
}
</style>
