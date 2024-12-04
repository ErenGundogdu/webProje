<template>
  <div class="component2">
    <h2 class="form-title">İnternet Mağazası İletişim Formu</h2>
    <p class="form-description">
      LC Waikiki internet mağazası ile ilgili aşağıdaki iletişim formunu doldurunuz.
    </p>

    <form>
      <div class="form-group">
        <select class="form-select">
          <option>Konu Başlığı Seçiniz</option>
        </select>
      </div>
      <div class="form-group">
        <select class="form-select">
          <option>Konu Başlığı Seçiniz</option>
        </select>
      </div>
      <div class="form-group">
        <select class="form-select">
          <option>Konu Başlığı Seçiniz</option>
        </select>
      </div>
      <div class="form-group">
        <input type="text" class="form-input" placeholder="Sipariş Numaranız (Eğer Varsa)" />
      </div>
      <div class="form-group">
        <textarea class="form-textarea" placeholder="Mesajınız"></textarea>
      </div>
      <p class="character-count">Kalan karakter sayısı: 2048</p>
      <div class="form-group checkbox-group">
        <input type="checkbox" id="not-robot" />
        <label for="not-robot">Ben robot değilim</label>
      </div>
      <div class="form-group">
        <button type="button" class="upload-btn">Dosya Yükle</button>
        <p class="file-info">
          Dosya boyutu en fazla 10 mb boyutunda (.jpg, .pdf, .docx, .xlsx, .bmp, .png formatında) olmalıdır.
        </p>
      </div>
      <p class="privacy-info">
        Kişisel verileriniz, <a href="#">Aydınlatma Metni</a> kapsamında işlenmektedir.
      </p>
      <button type="submit" class="submit-btn">GÖNDER</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "Component2",
};
</script>

<style scoped>
.contact-form {
  font-family: Arial, sans-serif;
  padding: 20px;
  max-width: 600px;
  margin: 0 auto;
  text-align: left;
}

.form-title {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 10px;
  color: #333;
}

.form-description {
  font-size: 14px;
  margin-bottom: 20px;
  color: #555;
}

.form-group {
  margin-bottom: 15px;
  display: flex;
  flex-direction: column;
  align-items: left; /* Form elemanlarını ortalar */
}

.form-select,
.form-input,
.form-textarea {
  width: 70%; /* Daha dar genişlik */
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 14px;
}

.form-textarea {
  resize: none;
  height: 80px;
}

.character-count {
  font-size: 12px;
  color: #888;
  margin-bottom: 10px;
}

.checkbox-group {
  display: flex;  /* Flexbox düzeni ile hizalama */
  align-items: center;  /* Dikey olarak ortalar */
  gap: 10px;  /* Checkbox ile metin arasındaki boşluk */
}

.checkbox-group input[type="checkbox"] {
  margin: 0;  /* Checkbox'ın etrafındaki boşluğu kaldır */
}

.upload-btn {
  padding: 10px 15px;
  background-color: #f1f1f1;
  border: 1px solid #ddd;
  border-radius: 4px;
  cursor: pointer;
}

.upload-btn:hover {
  background-color: #e0e0e0;
}

.file-info {
  font-size: 12px;
  color: #888;
}

.privacy-info {
  font-size: 12px;
  color: #888;
  margin-bottom: 20px;
}

.privacy-info a {
  color: #007bff;
  text-decoration: none;
}

.submit-btn {
  background-color: #007bff;
  color: #fff;
  border: none;
  padding: 10px;
  border-radius: 4px;
  font-size: 14px;
  cursor: pointer;
}

.submit-btn:hover {
  background-color: #0056b3;
}
</style>
