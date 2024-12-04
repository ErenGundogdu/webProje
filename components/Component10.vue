<template>
  <div class="component10">
   
    <!-- Footer -->
    <footer class="footer">
      <div class="footer-container">
        <!-- Sol Taraf -->
        <div class="footer-left">
          <h2>LC Waikiki</h2>
          <p>
            <i class="fas fa-phone"></i> 444 9 924
          </p>
          <p>LCW.COM'da Engelsiz İletişim!</p>
          <p>
            <i class="fas fa-sign-language"></i> İşaret Dili Hizmeti
          </p>
        </div>

        <!-- Orta ve Sağ Taraf -->
        <div class="footer-sections">
          <div class="footer-section">
            <h3>Destek</h3>
            <ul>
              <li><button><i class="fas fa-envelope"></i> İletişim Formu</button></li>
              <li><button><i class="fas fa-phone-alt"></i> 444 4 529</button></li>
              <li><button><i class="fab fa-whatsapp"></i> Whatsapp Destek</button></li>
              <li><button><i class="fas fa-video"></i> Görüntülü Destek</button></li>
              <li><button><i class="fas fa-box-open"></i> Sipariş Takip</button></li>
            </ul>
          </div>
          <div class="footer-section">
            <h3>Yardım</h3>
            <ul>
              <li><button> Sıkça Sorulan Sorular</button></li>
              <li><button> İade ve Değişim</button></li>
              <li><button> Kullanım Koşulları</button></li>
              <li><button> Site Haritası</button></li>
              <li><button> İşlem Rehberi</button></li>
            </ul>
          </div>
          <div class="footer-section">
            <h3>Kurumsal</h3>
            <ul>
              <li><button> Hakkımızda</button></li>
              <li><button> Mağazalarımız</button></li>
              <li><button> Kurumsal</button></li>
              <li><button> Kariyer Fırsatları</button></li>
              <li><button> Hediye Kart</button></li>
            </ul>
          </div>
          <div class="footer-section">
            <h3>Politikalar</h3>
            <ul>
              <li><button> Aydınlatma Metni</button></li>
              <li><button> Aydınlatma Metni / Pazaryeri</button></li>
              <li><button> Veri Gizliliği ve Güvenliği Politikası</button></li>
            </ul>
          </div>
        </div>
      </div>

      <!-- Alt Kısım: Sosyal Medya -->
      <div class="footer-social">
        <h4>Bizi Takip Edin</h4>
        <div class="social-icons">
          <button><i class="fab fa-instagram"></i></button>
          <button><i class="fab fa-tiktok"></i></button>
          <button><i class="fab fa-whatsapp"></i></button>
          <button><i class="fab fa-youtube"></i></button>
          <button><i class="fab fa-facebook"></i></button>
          <button><i class="fab fa-solid fa-x"></i></button>
          <button><i class="fab fa-linkedin"></i></button>
        </div>
      </div>
    </footer>
  </div>
</template>

<script lang="ts" setup>
// Ek fonksiyonlar buraya eklenebilir.
</script>

<style scoped>
/* Genel Component Stilleri */
.component10 {
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #f9f9f9;
}

/* Footer Stilleri */
.footer {
  background-color: #f9f9f9;
  padding: 40px 0;
  font-family: Arial, sans-serif;
  color: #333;
  max-width: 1600px;  /* Genişlik arttırıldı */
  margin: 0 auto;
}

.footer-container {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 40px;
}

.footer-left {
  flex: 2;  /* Sol tarafa daha fazla alan verildi */
}

.footer-left h2 {
  font-size: 24px;
  margin-bottom: 20px;
}

.footer-sections {
  display: flex;
  flex: 5;  /* Sağ ve orta taraflara daha fazla alan verildi */
  justify-content: space-between;
  gap: 20px; /* Sıraları daha fazla aralıklı yapıldı */
}

.footer-section {
  margin: 0 20px;
  flex: 1;  /* Her bölüm eşit şekilde genişletildi */
}

.footer-section h3 {
  font-size: 18px;
  margin-bottom: 20px;
}

.footer-section ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-section li {
  margin-bottom: 15px;
}

button {
  background: none;
  border: none;
  color: #333;
  font-size: 14px; /* Font boyutu küçültüldü */
  text-align: left;
  padding: 5px 0;
  cursor: pointer;
  transition: color 0.3s ease, text-decoration 0.3s ease;
  display: inline-flex; /* Metin ve ikonları aynı satıra yerleştirmek için inline-flex kullanıldı */
  align-items: center;  /* İkon ve metni dikeyde ortalamak için align-items kullanıldı */
  gap: 8px; /* İkon ile metin arasındaki boşluğu düzenledik */
}

button:hover {
  color: #007bff;
  text-decoration: underline;
}

/* Sosyal Medya İkonları */
.footer-social {
  text-align: center;
  margin-top: 40px;
}

.footer-social h4 {
  margin-bottom: 20px;
  font-size: 18px;
}

.social-icons button {
  background: none;
  border: none;
  cursor: pointer;
  margin: 0 10px;
}

.social-icons i {
  font-size: 24px;
}

/* Mobil Uyumluluk */
@media screen and (max-width: 1024px) {
  .footer-container {
    flex-direction: column;
  }
  .footer-sections {
    flex-direction: column;
    gap: 20px;
  }
}
</style>


