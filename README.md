# Şehir İçi Şikayet ve Talep Yönetim Sistemi — Backend & Web Admin

Vatandaşların şehir içi altyapı, çevre ve temizlik gibi sorunlarını yerel yönetimlere hızlıca iletebildiği; yetkililerin ise bu talepleri tek bir merkezden yönetip sahadaki personellere atayabildiği **uçtan uca entegre bir akıllı şehir çözümüdür.**

Bu repo, projenin **Laravel tabanlı REST API ve Web Yönetim Paneli** bileşenini içerir. Mobil uygulama ayrı bir repoda geliştirilmektedir.

---

## Ekran Görüntüleri

### Mobil Uygulama
<p align="center">
  <img src="https://github.com/user-attachments/assets/704e4bdf-b1df-427a-bddb-12cc64804a7c" width="270" alt="Ana Sayfa Harita" />
  <img src="https://github.com/user-attachments/assets/f98a3d75-fb77-474a-8e22-9f5067158946" width="270" alt="Şikayet Oluşturma" />
  <img src="https://github.com/user-attachments/assets/1076d0d1-87a8-4097-9cf7-3f9a3bfdd6e5" width="270" alt="Şikayet Detay" />
</p>

#### Rol Bazlı Şikayet Yönetimi ve İstatistikler
<p align="center">
  <img src="https://github.com/user-attachments/assets/42e292f7-8bd3-4636-8426-fa63da61d206" width="380" alt="Vatandaş Görünümü" />
  <img src="https://github.com/user-attachments/assets/019edf1a-9fd6-4c9d-9951-0d230c388c54" width="380" alt="Yönetici Görünümü" />
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/caa1293a-faee-43ef-b7dd-65984f6c6c04" width="380" alt="Yönetim" />
  <img src="https://github.com/user-attachments/assets/fe48860c-8eb6-4af1-86a4-71311f24a353" width="380" alt="Profil" />
</p>

### Web Yönetim Paneli (Admin Dashboard)

<p align="center">
  <img src="docs/images/web-admin/dashboard.png" width="800" alt="Web Admin Dashboard - Kontrol Paneli" />
</p>
<p align="center">
  <img src="docs/images/web-admin/sikayet-listesi.png" width="400" alt="Web Şikayet Listesi" />
  <img src="docs/images/web-admin/sikayet-detay.png" width="400" alt="Şikayet Detayı" />
</p>
<p align="center">
  <img src="docs/images/web-admin/personel-ata.png" width="400" alt="Web Görev Atama" />
  <img src="docs/images/web-admin/durum-guncelle.png" width="400" alt="Şikayet Durum Güncelleme" />
</p>

#### Kullanıcı ve Yetki Yönetimi
<p align="center">
  <img src="docs/images/web-admin/yonetici-listesi.png" width="400" alt="Yönetici Listesi" />
  <img src="docs/images/web-admin/calisan-listesi.png" width="400" alt="Çalışan Listesi" />
</p>
<p align="center">
  <img src="docs/images/web-admin/personel-profili.png" width="400" alt="Personel Profili ve Atandığı Şikayetler" />
  <img src="docs/images/web-admin/yetki-yonetimi.png" width="400" alt="Rol Bazlı Yetki Yönetimi" />
</p>

---

## Temel Özellikler

Sistem, 4 farklı kullanıcı rolü (`Vatandaş`, `Personel`, `Sorumlu`, `Sistem Yöneticisi`) üzerinden yetkilendirilmiş dinamik bir mimariye sahiptir.

### Web Yönetim Paneli (Admin & Managing)
Yetkililerin şehre dair tüm verileri kuşbakışı incelediği ve operasyonu yönettiği merkezdir.
* **Merkezi Dashboard:** Şehir genelindeki şikayetlerin kategorilere ve aylara göre dağılımını gösteren detaylı istatistik paneli.
* **Görev Atama:** Bekleyen şikayetleri sahadaki uygun personellere atama ve süreç takibi.
* **Durum ve Çözüm Yönetimi:** Şikayetlerin durumlarını güncelleme ve vatandaşa gösterilecek "Çözüm Notları" ekleme.
* **Kullanıcı ve Rol Yönetimi:** Sistemdeki vatandaş, personel ve yöneticilerin hesap/yetki kontrolleri (rol ve izin bazlı, granüler yetkilendirme).

### Mobil Uygulama
Mobil uygulama, sahada veri girişini ve takibini kolaylaştırmak için tasarlanmıştır.
* **Akıllı Konum Entegrasyonu:** Şikayet oluştururken interaktif harita üzerinden nokta atışı konum seçimi ve otomatik adres (ilçe/mahalle) tespiti.
* **Görsel Kanıt Yükleme:** Kamera veya galeri üzerinden çoklu fotoğraf yükleme (maksimum 3 adet).
* **Anlık Durum Takibi:** İletilen taleplerin durumlarını anlık olarak izleyebilme.
* **Mobil Yönetim Paneli**: Yöneticilerin bilgisayara ihtiyaç duymadan mobilden şikayetleri listeleyebildiği, durum güncelleyebildiği ve sahada görev ataması yapabildiği özel yönetim arayüzü.
* **Kişisel Dashboard:** Kullanıcının rolüne göre (Vatandaş için toplam talep, Personel için atanan işler) özelleştirilmiş istatistik ekranı.
* **Tema Desteği:** Kullanıcı tercihine göre Karanlık (Dark) ve Aydınlık (Light) mod desteği.

---

## Kullanılan Teknolojiler

**Backend & Web**
* **Framework:** Laravel 10 (PHP ^8.1)
* **Kimlik Doğrulama:** Laravel Sanctum (API token tabanlı)
* **Rol & Yetki Yönetimi:** Spatie Laravel-Permission (RBAC)
* **Veritabanı:** MySQL
* **Dosya Yönetimi:** Laravel Filesystem (local storage / genişletilebilir cloud disk desteği)
* **HTTP Client:** Guzzle

**Mobil Mimari**
* **Framework:** Flutter
* **State Management:** Riverpod
* **Ağ İstekleri & API:** Dio (Interceptors & Token Management)
* **Harita ve Konum:** flutter_map, geocoding, latlong2
* **Form & Validasyon:** mask_text_input_formatter, form validation

---

## Backend Kurulumu

Gereksinimler: PHP ^8.1, Composer, MySQL, Node.js (asset build için opsiyonel).

```bash
# 1. Repoyu klonlayın
git clone https://github.com/sikayet-app/report-app-backend.git
cd report-app-backend

# 2. Bağımlılıkları yükleyin
composer install

# 3. Ortam dosyasını oluşturun ve uygulama anahtarını üretin
cp .env.example .env
php artisan key:generate

# 4. .env dosyasında veritabanı bilgilerinizi düzenleyin
#    DB_CONNECTION=mysql
#    DB_HOST=127.0.0.1
#    DB_DATABASE=report_app
#    DB_USERNAME=...
#    DB_PASSWORD=...

# 5. Veritabanı tablolarını oluşturun ve örnek verileri yükleyin
php artisan migrate --seed

# 6. Yüklenen görsellerin (şikayet fotoğrafları vb.) erişilebilir olması için
php artisan storage:link

# 7. Geliştirme sunucusunu başlatın
php artisan serve
```

Uygulama varsayılan olarak `http://127.0.0.1:8000` adresinde çalışır. API uç noktaları ve mobil uygulama bu adres üzerinden Sanctum token'ları ile kimlik doğrulaması yaparak haberleşir.

---

## Organizasyon Repoları

Sistemin kaynak kodlarına aşağıdaki bağlantılardan ulaşabilirsiniz:

* **[Mobil Uygulama Reposu (Flutter)](https://github.com/sikayet-app/sikayet_uygulamasi)**
* **[Backend & Web Admin Reposu (Laravel)](https://github.com/sikayet-app/report-app-backend)**

---

## Lisans

Bu proje [MIT lisansı](https://opensource.org/licenses/MIT) ile lisanslanmıştır.
