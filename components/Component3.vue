<template>
  <div class="auth-container">
    <!-- Sekme Butonları -->
    <div class="tabs">
      <button
        :class="{ active: activeTab === 'login' }"
        @click="setActiveTab('login')"
      >
        GİRİŞ YAP
      </button>
      <button
        :class="{ active: activeTab === 'signup' }"
        @click="setActiveTab('signup')"
      >
        ÜYE OL
      </button>
    </div>

    <!-- Üye Ol Formu -->
    <div v-if="activeTab === 'signup'" class="form-container">
      <div class="reasons">
        <div class="reason">
          <img
            src="https://img.lcwstatic.com/Resource/Images/Banner/customer-kargo-bedava-d.png"
            alt="Kargo"
          />
        </div>
        <div class="reason">
          <img
            src="https://img.lcwstatic.com/Resource/Images/Banner/customer-kapida-odeme-d.png"
            alt="Ödeme"
          />
        </div>
        <div class="reason">
          <img
            src="https://img.lcwstatic.com/Resource/Images/Banner/customer-indirim-haber-d.png"
            alt="Bildirim"
          />
        </div>
      </div>

      <form class="signup-form">
        <input type="email" placeholder="E-Posta Adresin" />

        <!-- Şifre Girişi ve Göster Butonu -->
        <div class="password-container">
          <input type="password" placeholder="Şifreniz" />
        </div>

        <!-- Telefon Numarası -->
        <input type="tel" placeholder="0 (5__) ___ __ __" />

        <!-- İletişim İzni -->
        <p class="communication-title">
          Aşağıdaki yöntemlerden birkaçını seçerek bize iletişim izni vermek ister misiniz?
        </p>
        <div class="communication-options">
          <label><input type="checkbox" /> E-Posta</label>
          <label><input type="checkbox" /> Arama</label>
          <label><input type="checkbox" /> SMS</label>
        </div>

        <!-- Gizlilik Sözleşmesi -->
        <div class="agreement">
          <label>
            <input type="checkbox" />
            Kullanım ve Gizlilik Sözleşmesini okudum, onaylıyorum.
          </label>
        </div>
        <p>Kişisel verileriniz,  Aydınlatma Metinleri  kapsamında işlenmektedir.</p>

        <button type="submit" class="signup-button">ÜYE OL</button>
        <p class="or">veya</p>
        <button type="button" class="login-button">GİRİŞ YAP</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: "signup", // Varsayılan olarak Üye Ol sekmesi açık
    };
  },
  methods: {
    setActiveTab(tab) {
      this.activeTab = tab;
    },
  },
};
</script>

<style scoped>
/* Genel Düzen */
.auth-container {
  width: 500px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

/* Sekmeler */
.tabs {
  display: flex;
  margin-bottom: 20px;
  border-bottom: 2px solid #ddd;
}

.tabs button {
  flex: 1;
  padding: 15px 0;
  font-size: 16px;
  font-weight: bold;
  background-color: transparent;
  border: none;
  border-bottom: 3px solid transparent;
  color: #888;
  cursor: pointer;
  transition: all 0.3s ease;
}

.tabs button.active {
  border-bottom: 3px solid #007bff;
  color: #007bff;
}

/* Form İçeriği */
.form-container {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.reasons {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}

.reason {
  text-align: center;
}

.reason img {
  width: 150px;
  height: 130px;
}

/* Form Girdi Alanları */
.signup-form input {
  width: 100%;
  padding: 12px;
  font-size: 14px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
} 

/* Şifre Girişi ve Göster Butonu */
.password-container {
  display: flex;
  align-items: center;
  width: 100%;
}

.password-container input {
  flex-grow: 1;
  padding: 12px;
  font-size: 14px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

/* Telefon Numarası */
.signup-form input[type="tel"],
.signup-form input[type="email"] {
  width: 100%;
  padding: 12px;
  font-size: 14px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

/* İletişim Seçenekleri */
.communication-options {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
}

.communication-options label {
  display: inline-flex;
  align-items: center;
  font-size: 14px;
  cursor: pointer;
  gap: 8px;
}

/* Gizlilik Sözleşmesi */
.agreement label {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  font-size: 10px;
  cursor: pointer;
}

.agreement {
  margin-top: 15px;
}

/* Butonlar ve "veya" metni */
.signup-button,
.login-button {
  width: 100%;
  max-width: 300px;
  background-color: #007bff;
  color: white;
  padding: 12px;
  font-size: 16px;
  font-weight: bold;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin: 5px 0;
}

.login-button {
  background-color: gray;
}

.or {
  text-align: center;
  font-size: 14px;
  color: black;
  margin: 10px 0;
}

/* Orta Kısım */
.signup-form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.signup-form button {
  width: 100%;
  max-width: 300px;
}
</style>  