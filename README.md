# 🎭 StagePass - Tiyatro Bilet Rezervasyon Sistemi

[![Java](https://img.shields.io/badge/Java-17-orange.svg)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.5.7-brightgreen.svg)](https://spring.io/projects/spring-boot)
[![Maven](https://img.shields.io/badge/Maven-3.6+-blue.svg)](https://maven.apache.org/)
[![License](https://img.shields.io/badge/License-Demo-yellow.svg)](https://github.com/enginakts/stage-pass)

> StagePass, tiyatro gösterileri için bilet rezervasyonu ve ödeme işlemlerini yöneten modern bir web uygulamasıdır. Spring Boot framework'ü kullanılarak geliştirilmiştir.

**🔗 Repository**: [https://github.com/enginakts/stage-pass](https://github.com/enginakts/stage-pass)

## 📋 İçindekiler

- [Özellikler](#özellikler)
- [Teknolojiler](#teknolojiler)
- [Gereksinimler](#gereksinimler)
- [Kurulum](#kurulum)
- [Kullanım](#kullanım)
- [Proje Yapısı](#proje-yapısı)
- [Veritabanı](#veritabanı)
- [Güvenlik](#güvenlik)
- [API Endpoints](#api-endpoints)

## ✨ Özellikler

### Kullanıcı Özellikleri
- **Kullanıcı Yönetimi**: Kayıt olma, giriş yapma ve oturum yönetimi
- **Gösteri Arama**: Şehir, tiyatro ve tarih bazlı gösteri arama
- **Koltuk Seçimi**: İnteraktif koltuk haritası ile koltuk seçimi
- **Bilet Rezervasyonu**: Gösteri ve koltuk seçimine göre bilet rezervasyonu
- **Ödeme İşlemleri**: Kredi kartı ile güvenli ödeme
- **Bilet Yönetimi**: Rezerve edilen biletleri görüntüleme ve yönetme
- **Ödül Sistemi**: Gösterilere katılım sonrası puan kazanma

### Admin Özellikleri
- **Dashboard**: Sistem istatistikleri ve genel bakış
- **Şehir Yönetimi**: Şehir ekleme, düzenleme ve yönetme
- **Tiyatro Yönetimi**: Tiyatro ekleme, görsel yükleme ve yönetme
- **Gösteri Yönetimi**: Gösteri oluşturma ve yönetme
- **Kullanıcı İstatistikleri**: Kullanıcı, bilet ve ödeme istatistikleri

## 🛠 Teknolojiler

| Kategori | Teknoloji |
|----------|-----------|
| **Backend Framework** | Spring Boot 3.5.7 |
| **Java Version** | 17 |
| **Veritabanı** | SQLite |
| **ORM** | Hibernate / JPA |
| **Template Engine** | Thymeleaf |
| **Güvenlik** | Spring Security |
| **Build Tool** | Maven |
| **Diğer** | Lombok, WebSocket, Spring Mail |

## 📦 Gereksinimler

- ☕ Java 17 veya üzeri
- 📦 Maven 3.6+
- 💾 En az 500MB boş disk alanı
- 🌐 Modern bir web tarayıcısı (Chrome, Firefox, Edge, Safari)

## 🚀 Hızlı Başlangıç

```bash
# Repository'yi klonlayın
git clone https://github.com/enginakts/stage-pass.git
cd stage-pass

# Bağımlılıkları yükleyin ve uygulamayı çalıştırın
mvn clean install
mvn spring-boot:run
```

Uygulama `http://localhost:8082` adresinde çalışacaktır. 🎉

## 🚀 Detaylı Kurulum

### 1. Projeyi Klonlayın

```bash
git clone https://github.com/enginakts/stage-pass.git
cd stage-pass
```

### 2. Bağımlılıkları Yükleyin

```bash
mvn clean install
```

### 3. Uygulamayı Çalıştırın

```bash
mvn spring-boot:run
```

veya

```bash
java -jar target/stagepass-0.0.1-SNAPSHOT.jar
```

### 4. Uygulamaya Erişin

Uygulama varsayılan olarak **`http://localhost:8082`** adresinde çalışacaktır.

> 💡 **İpucu**: İlk çalıştırmada veritabanı otomatik olarak oluşturulacak ve test verileri yüklenecektir.

## 📖 Kullanım

### İlk Çalıştırma

Uygulama ilk çalıştırıldığında otomatik olarak test verileri yüklenir:

- **3 Şehir**: İstanbul, Ankara, İzmir
- **4 Tiyatro**: Her şehirde farklı tiyatrolar
- **20 Gösteri**: Her tiyatro için 5 gösteri
- **Test Kullanıcıları**: Admin ve 5 test kullanıcısı

### Varsayılan Giriş Bilgileri

#### Admin Kullanıcı
- **Email**: `admin@stagepass.com`
- **Şifre**: `admin123`

#### Test Kullanıcıları
- **Email**: `user1@test.com` - `user5@test.com`
- **Şifre**: `password123`

### Kullanıcı Akışı

1. **Kayıt/Giriş**: Yeni kullanıcı kaydı veya mevcut kullanıcı girişi
2. **Gösteri Arama**: Ana sayfada popüler gösterileri görüntüleme veya arama yapma
3. **Koltuk Seçimi**: Gösteri detayından koltuk seçim sayfasına geçiş
4. **Rezervasyon**: Koltuk seçimi ve rezervasyon oluşturma
5. **Ödeme**: Kredi kartı bilgileri ile ödeme işlemi
6. **Bilet Görüntüleme**: Biletlerim sayfasından rezerve edilen biletleri görüntüleme

### Admin Akışı

1. **Admin Girişi**: Admin hesabı ile giriş yapma
2. **Dashboard**: Sistem istatistiklerini görüntüleme
3. **Şehir Yönetimi**: `/admin/cities` - Yeni şehir ekleme
4. **Tiyatro Yönetimi**: `/admin/theaters` - Tiyatro ekleme ve görsel yükleme
5. **Gösteri Yönetimi**: Gösterileri oluşturma ve yönetme

## 📁 Proje Yapısı

```
stage-pass/
├── src/
│   ├── main/
│   │   ├── java/com/stagepass/stagepass/
│   │   │   ├── config/          # Yapılandırma sınıfları
│   │   │   │   ├── DataInitializer.java
│   │   │   │   ├── SecurityConfig.java
│   │   │   │   ├── TestDataLoader.java
│   │   │   │   └── WebConfig.java
│   │   │   ├── controller/      # MVC Controller'lar
│   │   │   │   ├── AdminController.java
│   │   │   │   ├── AuthController.java
│   │   │   │   ├── HomeController.java
│   │   │   │   ├── PaymentController.java
│   │   │   │   ├── ShowBookingController.java
│   │   │   │   ├── TicketController.java
│   │   │   │   └── TestController.java
│   │   │   ├── model/           # Entity sınıfları
│   │   │   │   ├── City.java
│   │   │   │   ├── Payment.java
│   │   │   │   ├── Seat.java
│   │   │   │   ├── Show.java
│   │   │   │   ├── Theater.java
│   │   │   │   ├── Ticket.java
│   │   │   │   ├── User.java
│   │   │   │   └── UserReward.java
│   │   │   ├── repository/      # JPA Repository'ler
│   │   │   ├── service/         # İş mantığı servisleri
│   │   │   │   ├── BookingService.java
│   │   │   │   ├── PaymentService.java
│   │   │   │   └── UserService.java
│   │   │   ├── util/            # Yardımcı sınıflar
│   │   │   │   └── ImageUrlProvider.java
│   │   │   └── StagepassApplication.java
│   │   └── resources/
│   │       ├── application.properties
│   │       ├── static/          # CSS, JS dosyaları
│   │       └── templates/       # Thymeleaf şablonları
│   └── test/                    # Test sınıfları
├── pom.xml                      # Maven yapılandırması
├── README.md                    # Proje dokümantasyonu
├── stagepass.db                 # SQLite veritabanı (otomatik oluşturulur)
└── uploads/                     # Yüklenen görseller (otomatik oluşturulur)
```

## 🗄 Veritabanı

### Veritabanı Yapısı

Proje SQLite veritabanı kullanmaktadır. Veritabanı dosyası `stagepass.db` olarak proje kök dizininde oluşturulur.

### Entity İlişkileri

- **User** (Kullanıcı)
  - `OneToMany` → Ticket
  - Roller: USER, ADMIN

- **City** (Şehir)
  - `OneToMany` → Theater

- **Theater** (Tiyatro)
  - `ManyToOne` → City
  - `OneToMany` → Show
  - `OneToMany` → Seat

- **Show** (Gösteri)
  - `ManyToOne` → Theater
  - `OneToMany` → Ticket
  - Durumlar: ACTIVE, CANCELLED, COMPLETED, POSTPONED

- **Seat** (Koltuk)
  - `ManyToOne` → Theater
  - Tipler: VIP, PREMIUM, STANDARD

- **Ticket** (Bilet)
  - `ManyToOne` → User
  - `ManyToOne` → Show
  - `OneToOne` → Seat
  - `OneToMany` → Payment
  - Durumlar: ACTIVE, CANCELLED, USED, EXPIRED, REFUNDED

- **Payment** (Ödeme)
  - `ManyToOne` → Ticket
  - Yöntemler: CREDIT_CARD
  - Durumlar: PENDING, COMPLETED, FAILED, REFUNDED

### Veritabanı Yönetimi

- Hibernate DDL Auto: `update` (otomatik şema güncelleme)
- SQL Logging: Aktif (geliştirme ortamı için)

## 🔒 Güvenlik

- **Spring Security**: Web güvenliği için yapılandırılmış
- **Password Encoding**: BCrypt ile şifre hashleme
- **Session Management**: HTTP Session tabanlı kimlik doğrulama
- **Role-Based Access**: Admin ve User rolleri

### Güvenlik Notları

- CSRF koruması şu anda devre dışı (geliştirme amaçlı)
- Üretim ortamında güvenlik ayarlarının gözden geçirilmesi önerilir

## 🌐 API Endpoints

Aşağıda uygulamanın tüm endpoint'leri listelenmiştir:

### Kimlik Doğrulama
- `GET /login` - Giriş sayfası
- `POST /login` - Giriş işlemi
- `GET /register` - Kayıt sayfası
- `POST /register` - Kayıt işlemi
- `GET /logout` - Çıkış işlemi

### Ana Sayfa ve Arama
- `GET /` - Ana sayfa (giriş gerekli)
- `GET /search` - Gösteri arama
- `GET /dashboard` - Kullanıcı dashboard'u

### Gösteri ve Rezervasyon
- `GET /shows/{showId}/seats` - Koltuk seçim sayfası
- `POST /shows/{showId}/seats/book` - Koltuk rezervasyonu

### Ödeme
- `GET /payments/{ticketId}` - Ödeme sayfası
- `POST /payments/{ticketId}/process` - Ödeme işlemi

### Biletler
- `GET /tickets` - Kullanıcının biletleri

### Admin
- `GET /admin` - Admin dashboard
- `GET /admin/cities` - Şehir yönetimi
- `POST /admin/cities` - Şehir ekleme
- `GET /admin/theaters` - Tiyatro yönetimi
- `POST /admin/theaters` - Tiyatro ekleme

## ⚙️ Yapılandırma

### application.properties

Ana yapılandırma dosyası `src/main/resources/application.properties` içinde bulunur:

```properties
# Server Configuration
server.port=8082
spring.application.name=stagepass

# Database Configuration
spring.datasource.url=jdbc:sqlite:stagepass.db
spring.datasource.driver-class-name=org.sqlite.JDBC
spring.jpa.database-platform=org.hibernate.community.dialect.SQLiteDialect
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# Upload Directory
stagepass.upload-dir=uploads

# Security (Development)
spring.security.user.name=admin
spring.security.user.password=admin123
```

### Port Değiştirme

Port numarasını değiştirmek için `src/main/resources/application.properties` dosyasındaki `server.port` değerini düzenleyin.

### Veritabanı Yolu

Veritabanı dosyasının konumunu değiştirmek için `spring.datasource.url` değerini düzenleyin.

## 📝 Geliştirme Notları

- Proje Spring Boot 3.5.7 kullanmaktadır
- Lombok kullanıldığı için IDE'nizde Lombok eklentisinin yüklü olması gerekir
- SQLite veritabanı dosyası proje kök dizininde oluşturulur
- Yüklenen görseller `uploads/` dizininde saklanır

## 🐛 Bilinen Sorunlar

- CSRF koruması şu anda devre dışı
- Üretim ortamı için güvenlik ayarlarının gözden geçirilmesi gerekmektedir

## 📸 Ekran Görüntüleri

> **Not**: Ekran görüntüleri yakında eklenecektir.

## 🤝 Katkıda Bulunma

Katkılarınızı bekliyoruz! Projeyi geliştirmek için:

1. Bu repository'yi fork edin
2. Feature branch oluşturun (`git checkout -b feature/AmazingFeature`)
3. Değişikliklerinizi commit edin (`git commit -m 'Add some AmazingFeature'`)
4. Branch'inizi push edin (`git push origin feature/AmazingFeature`)
5. Bir Pull Request oluşturun

### Katkıda Bulunma Kuralları

- Pull request göndermeden önce değişikliklerinizi test edin
- Kod standartlarına uyun
- Açıklayıcı commit mesajları yazın
- Yeni özellikler için dokümantasyon ekleyin

## 🐛 Hata Bildirimi

Bir hata bulduysanız, lütfen [Issues](https://github.com/enginakts/stage-pass/issues) sayfasında yeni bir issue oluşturun. Hata bildirirken:

- Hatanın açıklamasını ekleyin
- Hatanın nasıl tekrarlanabileceğini belirtin
- Beklenen davranışı açıklayın
- Ekran görüntüleri ekleyin (varsa)

## 💡 Özellik İstekleri

Yeni özellik önerileriniz için [Issues](https://github.com/enginakts/stage-pass/issues) sayfasında yeni bir issue oluşturabilirsiniz.

## 📄 Lisans

Bu proje demo amaçlı geliştirilmiştir. Eğitim ve öğrenme amaçlı kullanılabilir.

## 👤 Geliştirici

**Engin Aktaş**

- GitHub: [@enginakts](https://github.com/enginakts)
- Repository: [stage-pass](https://github.com/enginakts/stage-pass)

## 🙏 Teşekkürler

- Spring Boot ekibine harika framework için
- Tüm açık kaynak topluluğuna katkıları için

## 📊 Proje İstatistikleri

- ⭐ Stars: [![GitHub stars](https://img.shields.io/github/stars/enginakts/stage-pass.svg?style=social&label=Star)](https://github.com/enginakts/stage-pass)
- 🍴 Forks: [![GitHub forks](https://img.shields.io/github/forks/enginakts/stage-pass.svg?style=social&label=Fork)](https://github.com/enginakts/stage-pass/fork)
- 👀 Watchers: [![GitHub watchers](https://img.shields.io/github/watchers/enginakts/stage-pass.svg?style=social&label=Watch)](https://github.com/enginakts/stage-pass)

---

⭐ Bu projeyi beğendiyseniz, yıldız vermeyi unutmayın!

**Not**: Bu README dosyası projenin mevcut durumunu yansıtmaktadır. Güncellemeler için projeyi takip etmeye devam edin.

