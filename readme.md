Swag Labs E-Ticaret Otomasyon Test Projesi
Bu proje, popüler test sitesi Swag Labs (Saucedemo) üzerinde uçtan uca (End-to-End) bir e-ticaret satın alma sürecini otomatize etmek amacıyla Python ve Playwright kullanılarak geliştirilmiştir.

Proje, modern web otomasyonu tekniklerini, dinamik sayfa etkileşimlerini, form doldurma, filtreleme ve doğrulama (assertion) süreçlerini uygulamalı olarak göstermektedir.

🚀 Projenin İşlevi ve Test Senaryosu Adımları
Yazılan test senaryosu, gerçek bir kullanıcının alışveriş deneyimini simüle eder ve sırasıyla şu adımları gerçekleştirir:

Giriş Sayfası: [https://www.saucedemo.com/](https://www.saucedemo.com/) adresine gidilir.

Kullanıcı Girişi: Geçerli kullanıcı adı (standard_user) ve şifre (secret_sauce) alanları doldurularak sisteme giriş yapılır. Girişin başarılı olduğu URL doğrulaması ile kontrol edilir.

Filtreleme: Ürün listesi sayfasında, ürünler "Pahalıdan Ucuza" (Price: High to Low) olacak şekilde sıralanır.

Sepete Ekleme: Listenin en pahalı ilk iki ürünü (Fleece Jacket ve Backpack) sepete eklenir. Sağ üstteki sepet rozetinde "2" sayısının belirdiği doğrulanır.

Sepet Kontrolü: Sepet sayfasına geçilir ve ödeme (Checkout) süreci başlatılır.

Form Doldurma: Müşteri bilgileri (Ad, Soyad, Posta Kodu) dinamik olarak form alanlarına yazılır ve ilerlenir.

Sipariş Onayı: Sipariş özet sayfası aşağı kaydırılarak (scroll) kontrol edilir ve "Finish" butonu ile alışveriş tamamlanır.

Başarı Doğrulaması & Raporlama: Ekranda "Thank you for your order!" mesajının çıktığı doğrulanır. Testin başarıyla bittiğini kanıtlamak adına ekran görüntüsü (final_projesi_basari_raporu.png) alınır ve tarayıcı kapatılır.

🛠️ Teknik Altyapı ve Çalışma Şekli
Dil: Python 3.x

Kütüphane: Playwright (Python Sync API)

Tarayıcı Modu: Chromium (Headless: False - Testin gözle görülmesi için tarayıcı açık çalışır)

Yavaşlatma (Slow Mo): Adımların insan gözüyle takip edilebilmesi için slow_mo=500 (her adım arası 500ms bekleme) parametresi eklenmiştir.

Doğrulama (Assertions): expect() metotları kullanılarak sayfa URL'leri ve metin içerikleri otomatik olarak kontrol edilir. Beklenen durum oluşmazsa test hata verir (Fail olur).

💻 Kurulum ve Çalıştırma Talimatları
Projeyi kendi yerel bilgisayarınızda çalıştırmak için aşağıdaki adımları takip edebilirsiniz:

1. Gerekli Kütüphanelerin Kurulumu
Öncelikle terminal veya komut satırını açarak Python için Playwright kütüphanesini yükleyin:

Bash
pip install playwright
Ardından Playwright'ın ihtiyaç duyduğu tarayıcı motorlarını indirmek için şu komutu çalıştırın:

Bash
playwright install
2. Projeyi Çalıştırma
Kodların bulunduğu Python dosyasını (örneğin main.py) çalıştırmak için:

Bash
python main.py
📊 Test Çıktıları ve Raporlama
Test başarıyla tamamlandığında konsolda adım adım bilgilendirme mesajları görünecektir:

Swag Labs e-ticaret sitesine giriş yapılıyor...

Kullanıcı bilgileri dolduruluyor ve sisteme giriliyor...

Ürünler 'Pahalıdan Ucuza' doğru sıralanıyor...
...
