<template>
  <div class="component1">
    <!-- Üst Bar -->
    <div class="top-bar">
      <p>
        Mobil Uygulamada Özel Fiyatlar Hariç LC Waikiki Ürünlerine Özel İlk Siparişte %25+Kargo Ücretsiz!
      </p>
    </div>
    <!-- Ana Bar -->
    <div class="main-bar">
      <div class="logo">
        <img src="public/Ekran görüntüsü 2024-12-03 171130.png" alt="LC Waikiki Logo" />
      </div>
      <div class="search-bar">
        <input type="text" placeholder="Ürün, kategori veya marka ara" />
        <button>ARA</button>
      </div>
      <div class="menu">
        <a href="#"><i class="fa-regular fa-user"></i><span>Giriş Yap</span></a>
        <a href="#"><i class="fa-regular fa-heart"></i><span>Favorilerim</span></a>
        <a href="#"><i class="fa-solid fa-bag-shopping"></i><span>Sepetim</span></a>
      </div>
    </div>
    <!-- Alt Navigasyon Linkleri -->
    <div class="nav-links">
      <a href="#">KADIN</a>
      <a href="#">ERKEK</a>
      <a href="#">ÇOCUK & BEBEK</a>
      <a href="#">AYAKKABI</a>
      <a href="#">AKSESUAR</a>
      <a href="#">EV & YAŞAM</a>
      <div class="kozmetik">
        <a href="#">KOZMETİK</a>
        <!-- Açılır Menü -->
        <div class="dropdown-menu">
          <div>
            <h4>KİŞİSEL BAKIM</h4>
            <p>Banyo ve Duş</p>
            <p>El-Ayak Bakımı</p>
            <p>Ağda ve Epilasyon</p>
            <p>Tıraş Ürünleri</p>
            <p>Makyaş Aksesuarları</p>
            <p>Saç Bakım</p>
            <p>Ağız Bakım</p>
          </div>
          <div>
            <h4>PARFÜM VE DEODORANT</h4>
            <p>Parfüm</p>
            <p>Deodorant</p>
            <h4>MAKYAJ</h4>
            <p>Ruj</p>
            <p>Far</p>
          </div>
          <div>
            <h4>YÜZ BAKIMI</h4>
            <p>Yüz Maskesi</p>
            <p>Yüz Serumu</p>
            <p>Yüz Kremi</p>
            <p>Göz Kremi</p>
            <p>Tonik</p>
            <p>Peeling</p>
          </div>
          <div>
            <h4>VÜCUT BAKIMI</h4>
            <p>Güneş Kremi</p>
            <p>Vücut Losyonu</p>
            <p>Vücut Kremi</p>
          </div>
        </div>
      </div>
      <a href="#">TÜM KATEGORİLER</a>
      <a href="#">YENİ YIL</a>
      <a href="#">WAIKIKILAND</a>
      <a href="#" class="outlet">OUTLET</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Component1",
};
</script>

<style scoped>
/* Genel Navbar Stilleri */
.component1 {
  position: fixed;
  top: 0;
  right: 0;
  width: 80%;
  max-width: 1150px;
  z-index: 1000;
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin: 0 auto;
}

body {
  margin: 0;
  padding: 0;
}

/* Üst Bar */
.top-bar {
  background-color: #f7f7f7;
  padding: 3px 10px;
  text-align: left;
  font-size: 11px;
  color: #555;
}

/* Ana Bar */
.main-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 8px 15px;
}

.logo img {
  height: 50px;
}

/* Arama Çubuğu */
.search-bar {
  display: flex;
  align-items: center;
  flex: 1;
  margin: 0 15px;
}

.search-bar input {
  width: 100%;
  padding: 6px;
  border: 1px solid #ccc;
  border-radius: 4px;
  margin-right: 5px;
}

.search-bar button {
  padding: 6px 10px;
  border: none;
  background-color: #0073e6;
  color: white;
  border-radius: 4px;
  cursor: pointer;
}

.search-bar button:hover {
  background-color: #005bb5;
}

/* Menü */
.menu {
  display: flex;
  align-items: center;
}

.menu a {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-decoration: none;
  color: #0073e6;
  font-size: 13px;
  margin-left: 20px;
}

.menu a i {
  font-size: 20px;
  margin-bottom: 5px;
  display: block;
}

.menu a span {
  font-size: 12px;
  text-align: center;
}

/* Alt Navigasyon Linkleri */
.nav-links {
  display: flex;
  justify-content: center;
  padding: 8px 0;
}

.nav-links a {
  margin: 0 13px;
  text-decoration: none;
  font-size: 13px;
  color: #333;
  font-weight: bold;
}

.nav-links .outlet {
  color: #ff4500;
}

/* Açılır Menü */
.kozmetik {
  position: relative;
}

.dropdown-menu {
  display: none;
  position: absolute;
  top: 100%;
  left: 0;
  background-color: white;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  padding: 15px;
  gap: 20px;
  z-index: 1000;
}

.dropdown-menu div h4 {
  font-size: 14px;
  font-weight: bold;
  margin-bottom: 5px;
}

.dropdown-menu div p {
  margin: 0;
  font-size: 13px;
  line-height: 1.5;
  cursor: pointer;
}

.dropdown-menu div p:hover {
  color: #0073e6;
}

.kozmetik:hover .dropdown-menu {
  display: flex;
}

</style>
