# Hastane Randevu Sistemi

Bu proje, Java Swing kullanılarak geliştirilmiş ve MySQL veritabanı ile çalışan masaüstü tabanlı bir Hastane Randevu Yönetim Sistemidir. Sistem; Hasta ve Doktor kullanıcı rollerini destekler ve randevu alma, yönetme ve muayene süreçlerini kapsar.

Bu proje eğitim / akademik amaçlı olarak geliştirilmiştir.

## Proje Özellikleri

### Kullanıcı Rolleri
- Hasta
- Doktor

### Hasta Paneli
- Kayıt olma ve giriş yapma
- Branşa göre doktor listeleme
- Doktorun çalışma saatlerine göre randevu alma
- Aynı gün içinde yalnızca 1 randevu alma kuralı
- Randevu iptal etme
- Randevu tarih ve saat güncelleme
- Randevu geçmişini görüntüleme
- Doktor arama (Ad, Soyad, Branş)
- Profil bilgilerini güncelleme (iletişim, şifre)

### Doktor Paneli
- Günlük / haftalık / tarih aralığına göre randevu listeleme
- Randevu durumlarını güncelleme:
  - AKTIF
  - TAMAMLANDI
  - GELMEDI
  - IPTAL
- Muayene notu ve reçete girme
- Hasta arama (TC / Ad Soyad)
- Seçilen hastanın randevu geçmişini görüntüleme
- Çalışma saatlerini belirleme
- Profil bilgilerini güncelleme

## Kullanılan Tasarım Desenleri

### Zorunlu Tasarım Desenleri
- Factory Pattern – UserFactory
- State Pattern – AppointmentState, AktifState, IptalState, TamamlandiState, GelmediState
- Observer Pattern – AppointmentObserver, AppointmentSubject
- Abstract Class – User, BaseDashboard

### Ek Tasarım Desenleri
- Template Method Pattern – AbstractViewTemplate
- Strategy Pattern – WorkingHourStrategy, HourlyWorkingHourStrategy

## Kullanılan Teknolojiler
- Java (JDK 17+)
- Java Swing
- MySQL
- JDBC
- LocalDate / LocalTime API

## Veritabanı Yapısı

### Tablolar
- users
- patients
- doctors
- appointments

## İş Kuralları
- Aynı doktor, aynı gün ve aynı saat için birden fazla randevu alınamaz
- Hasta aynı gün içinde birden fazla randevu alamaz
- Doktor çalışma saatleri saatlik slotlara bölünür
- Örnek çalışma saati formatı: 09:00-12:00,13:00-17:00

## Kurulum

### Veritabanını Oluşturma
```sql
CREATE DATABASE hospital_randevu;
Tabloların oluşturulması için uygun SQL scriptlerinin çalıştırılması gerekir.

Veritabanı Bağlantı Ayarları
DatabaseManager sınıfı içinde kendi MySQL bilgilerinizi giriniz.

URL: jdbc:mysql://localhost:3306/hospital_randevu
USER: root
PASS: 1234

Uygulamayı Çalıştırma
bash
Kodu kopyala
javac HastaneSistemi.java
java HastaneSistemi
veya IDE üzerinden main metodu çalıştırılabilir.

Uygulama Başlangıç Noktası
Uygulamanın giriş noktası HastaneSistemi sınıfı içindeki main metodudur.

Güvenlik Notu
Şifreler eğitim amacıyla düz metin olarak saklanmaktadır. Gerçek sistemlerde şifrelerin hashlenmesi önerilir (BCrypt vb.).

Geliştirilebilir Özellikler
Şifre hashleme

Bildirim sistemi

PDF reçete çıktısı

Web veya mobil arayüz

REST API entegrasyonu

Diyagramlar
Sınıf Diyagramı


Sequence Diyagramı


ER Diyagramı


Use Case Diyagramı


Tasarım Desenleri Diyagramı


Geliştiriciler
Alp Erin Şenel (1220505066)
https://github.com/KLU1220505066/hastaneRandevu/tree/main

Kerem Yalın Taşkın (5210505028)
https://github.com/keremyalintaskin/hastahane_randevu_sistemi

Arda Işık (5210505058)
https://github.com/5210505058/hastane_randevu_sistemi

Lisans
Bu proje eğitim amaçlıdır ve serbestçe geliştirilebilir.

markdown
Kodu kopyala

Artık bu **%100 doğru GitHub README.md formatı**.  
İstersen bir sonraki adımda repo için **LICENSE**, **.gitignore**, **SQL script**, ya da **PDF rapor** da hazırlarım.
