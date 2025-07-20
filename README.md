# 🍽️ Restaurant Management System

A comprehensive restaurant management system with modern web technologies, featuring real-time ordering, admin dashboard, and microservices architecture.

## 🚀 Features

### Customer Features
- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Real-time Ordering**: Live order tracking with Socket.IO
- **Menu Management**: Dynamic menu with categories and search
- **Shopping Cart**: Persistent cart with Redis
- **User Authentication**: Secure login/register with Supabase
- **Order History**: Complete order tracking and history
- **Payment Integration**: Stripe payment processing
- **Profile Management**: User profile and preferences
- **Interactive UI**: Smooth animations with Framer Motion

### Admin Features
- **Dashboard**: Real-time analytics and statistics
- **Order Management**: Live order monitoring and status updates
- **Menu Management**: Add, edit, delete menu items with image upload
- **User Management**: Customer account management
- **Report Generation**: PDF reports with charts
- **Inventory Tracking**: Product stock management
- **Sales Analytics**: Revenue and performance metrics

### Technical Features
- **Microservices Architecture**: Kafka-based event-driven system
- **Real-time Notifications**: WebSocket integration
- **File Upload**: Cloudinary image management
- **Caching**: Redis for session and data caching
- **Logging**: Winston logger with file rotation
- **Docker Support**: Containerized deployment
- **API Documentation**: RESTful API endpoints

## 🛠️ Technology Stack

### Frontend
- **Next.js 14**: React framework with App Router
- **React 18**: Modern React with hooks
- **Tailwind CSS**: Utility-first CSS framework
- **Framer Motion**: Animation library
- **Ant Design**: UI component library
- **Socket.IO Client**: Real-time communication
- **Axios**: HTTP client
- **React Icons**: Icon library
- **Chart.js**: Data visualization
- **React PDF**: PDF generation

### Backend
- **Node.js**: JavaScript runtime
- **Express.js**: Web framework
- **Supabase**: PostgreSQL database and auth
- **Redis**: In-memory data store
- **Kafka**: Event streaming platform
- **Socket.IO**: Real-time bidirectional communication
- **Cloudinary**: Cloud image management
- **Stripe**: Payment processing
- **Nodemailer**: Email service
- **Winston**: Logging framework
- **JWT**: Authentication tokens

### Microservices
- **Invoice Service**: PDF generation with Kafka
- **Event Streaming**: Kafka for service communication

### DevOps
- **Docker**: Containerization
- **Docker Compose**: Multi-container orchestration
- **Concurrently**: Parallel script execution

## 📁 Project Structure

```
restaurant-website/
├── frontend/                 # Next.js frontend application
│   ├── src/
│   │   ├── app/             # App Router pages
│   │   │   ├── admin/       # Admin dashboard
│   │   │   ├── auth/        # Authentication pages
│   │   │   ├── menu/        # Menu pages
│   │   │   ├── sepetim/     # Shopping cart
│   │   │   ├── siparislerim/ # Order history
│   │   │   └── ...
│   │   ├── components/      # Reusable components
│   │   └── contexts/        # React contexts
│   └── public/              # Static assets
├── backend/                  # Express.js API server
│   ├── controllers/         # Route controllers
│   ├── middleware/          # Custom middleware
│   ├── routes/              # API routes
│   ├── services/            # Business logic
│   ├── utils/               # Utility functions
│   └── config/              # Configuration files
├── microservices/           # Microservices
│   └── faturaKafka/         # Invoice generation service
└── docker-compose.yml       # Docker orchestration
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ 
- Docker and Docker Compose
- Redis
- Kafka (via Docker)

### Installation

1. **Clone the repository**
```bash
git clone <repository-url>
cd restaurant-website
```

2. **Install dependencies**
```bash
npm run install-all
```

3. **Environment Setup**
Create `.env` files in frontend and backend directories:

**Backend (.env)**
```env
DATABASE_URL=your_supabase_database_url
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_anon_key
CLOUD_NAME=your_cloudinary_cloud_name
CLOUD_API_KEY=your_cloudinary_api_key
CLOUD_API_SECRET=your_cloudinary_api_secret
STRIPE_SECRET_KEY=your_stripe_secret_key
FRONTEND_URL=http://localhost:5173
```

**Frontend (.env.local)**
```env
NEXT_PUBLIC_BACKEND_URL=http://localhost:3000
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
```

4. **Start with Docker**
```bash
docker-compose up -d
```

5. **Start development servers**
```bash
npm run dev
```

The application will be available at:
- Frontend: http://localhost:5173
- Backend API: http://localhost:3000
- Admin Dashboard: http://localhost:5173/admin

## 📚 API Endpoints

### Authentication
- `POST /auth/register` - User registration
- `POST /auth/login` - User login
- `POST /auth/logout` - User logout

### Products
- `GET /products` - Get all products
- `GET /products/popular` - Get popular products
- `POST /products` - Create product (admin)
- `PUT /products/:id` - Update product (admin)
- `DELETE /products/:id` - Delete product (admin)

### Orders
- `GET /orders` - Get user orders
- `POST /orders` - Create new order
- `PUT /orders/:id/status` - Update order status
- `GET /orders/admin` - Get all orders (admin)

### Basket
- `GET /basket` - Get user basket
- `POST /basket/add` - Add item to basket
- `PUT /basket/update` - Update basket item
- `DELETE /basket/remove/:id` - Remove item from basket

### Checkout
- `POST /checkout/create-payment-intent` - Create Stripe payment
- `POST /checkout/confirm` - Confirm order

## 🔧 Development

### Available Scripts

```bash
# Install all dependencies
npm run install-all

# Start development servers
npm run dev

# Build frontend
cd frontend && npm run build

# Start production
cd frontend && npm start
```

### Code Structure
- **Feature-based Architecture**: Organized by business features
- **Service Layer**: Business logic separated from controllers
- **Middleware**: Authentication and validation
- **Error Handling**: Centralized error management
- **Logging**: Structured logging with Winston

## 🐳 Docker Deployment

```bash
# Build and start all services
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down
```

## 📊 Monitoring & Health Checks

- **Health Endpoint**: `GET /health` - System status
- **Redis Status**: Connection monitoring
- **Kafka Status**: Event streaming health
- **API Logging**: Request/response logging

## 🔒 Security Features

- **JWT Authentication**: Secure token-based auth
- **CORS Protection**: Cross-origin request handling
- **Input Validation**: Request data sanitization
- **File Upload Security**: Image validation and processing
- **Environment Variables**: Secure configuration management

## 📱 Responsive Design

- **Mobile-First**: Optimized for mobile devices
- **Tablet Support**: Responsive tablet layouts
- **Desktop Experience**: Enhanced desktop features
- **Touch-Friendly**: Mobile-optimized interactions

## 🎨 UI/UX Features

- **Smooth Animations**: Framer Motion transitions
- **Loading States**: User feedback during operations
- **Error Handling**: User-friendly error messages
- **Toast Notifications**: Success/error feedback
- **Dark/Light Mode**: Theme support (planned)

## 📈 Performance

- **Image Optimization**: Next.js image optimization
- **Code Splitting**: Dynamic imports
- **Caching**: Redis and browser caching
- **CDN**: Cloudinary for image delivery
- **Lazy Loading**: Component and image lazy loading

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the ISC License.

## 👥 Author

- **Ahmet Buğra Kadıoğlu** - Frontend Development

## 🙏 Acknowledgments

- Supabase for database and authentication
- Stripe for payment processing
- Cloudinary for image management
- The open-source community for amazing libraries



# 🍽️ Restoran Yönetim Sistemi

Modern web teknolojileri ile geliştirilmiş, gerçek zamanlı sipariş sistemi, admin paneli ve mikroservis mimarisi içeren kapsamlı bir restoran yönetim sistemi.

## 🚀 Özellikler

### Müşteri Özellikleri
- **Responsive Tasarım**: Tailwind CSS ile mobil öncelikli yaklaşım
- **Gerçek Zamanlı Sipariş**: Socket.IO ile canlı sipariş takibi
- **Menü Yönetimi**: Kategoriler ve arama ile dinamik menü
- **Alışveriş Sepeti**: Redis ile kalıcı sepet
- **Kullanıcı Kimlik Doğrulama**: Supabase ile güvenli giriş/kayıt
- **Sipariş Geçmişi**: Tam sipariş takibi ve geçmişi
- **Ödeme Entegrasyonu**: Stripe ödeme işleme
- **Profil Yönetimi**: Kullanıcı profili ve tercihleri
- **İnteraktif Arayüz**: Framer Motion ile akıcı animasyonlar

### Admin Özellikleri
- **Dashboard**: Gerçek zamanlı analitik ve istatistikler
- **Sipariş Yönetimi**: Canlı sipariş izleme ve durum güncellemeleri
- **Menü Yönetimi**: Resim yükleme ile ürün ekleme, düzenleme, silme
- **Kullanıcı Yönetimi**: Müşteri hesap yönetimi
- **Rapor Oluşturma**: Grafiklerle PDF raporları
- **Stok Takibi**: Ürün stok yönetimi
- **Satış Analitiği**: Gelir ve performans metrikleri

### Teknik Özellikler
- **Mikroservis Mimarisi**: Kafka tabanlı olay odaklı sistem
- **Gerçek Zamanlı Bildirimler**: WebSocket entegrasyonu
- **Dosya Yükleme**: Cloudinary resim yönetimi
- **Önbellekleme**: Oturum ve veri önbellekleme için Redis
- **Loglama**: Dosya rotasyonu ile Winston logger
- **Docker Desteği**: Konteynerli dağıtım
- **API Dokümantasyonu**: RESTful API endpoint'leri

## 🛠️ Teknoloji Yığını

### Frontend
- **Next.js 14**: App Router ile React framework'ü
- **React 18**: Hook'lar ile modern React
- **Tailwind CSS**: Utility-first CSS framework'ü
- **Framer Motion**: Animasyon kütüphanesi
- **Ant Design**: UI bileşen kütüphanesi
- **Socket.IO Client**: Gerçek zamanlı iletişim
- **Axios**: HTTP istemcisi
- **React Icons**: İkon kütüphanesi
- **Chart.js**: Veri görselleştirme
- **React PDF**: PDF oluşturma

### Backend
- **Node.js**: JavaScript runtime
- **Express.js**: Web framework'ü
- **Supabase**: PostgreSQL veritabanı ve kimlik doğrulama
- **Redis**: Bellek içi veri deposu
- **Kafka**: Olay akış platformu
- **Socket.IO**: Gerçek zamanlı çift yönlü iletişim
- **Cloudinary**: Bulut resim yönetimi
- **Stripe**: Ödeme işleme
- **Nodemailer**: E-posta servisi
- **Winston**: Loglama framework'ü
- **JWT**: Kimlik doğrulama token'ları

### Mikroservisler
- **Fatura Servisi**: Kafka ile PDF oluşturma
- **Olay Akışı**: Servis iletişimi için Kafka

### DevOps
- **Docker**: Konteynerleştirme
- **Docker Compose**: Çoklu konteyner orkestrasyonu
- **Concurrently**: Paralel script çalıştırma

## 📁 Proje Yapısı

```
restaurant-website/
├── frontend/                 # Next.js frontend uygulaması
│   ├── src/
│   │   ├── app/             # App Router sayfaları
│   │   │   ├── admin/       # Admin dashboard
│   │   │   ├── auth/        # Kimlik doğrulama sayfaları
│   │   │   ├── menu/        # Menü sayfaları
│   │   │   ├── sepetim/     # Alışveriş sepeti
│   │   │   ├── siparislerim/ # Sipariş geçmişi
│   │   │   └── ...
│   │   ├── components/      # Yeniden kullanılabilir bileşenler
│   │   └── contexts/        # React context'leri
│   └── public/              # Statik dosyalar
├── backend/                  # Express.js API sunucusu
│   ├── controllers/         # Route controller'ları
│   ├── middleware/          # Özel middleware
│   ├── routes/              # API route'ları
│   ├── services/            # İş mantığı
│   ├── utils/               # Yardımcı fonksiyonlar
│   └── config/              # Konfigürasyon dosyaları
├── microservices/           # Mikroservisler
│   └── faturaKafka/         # Fatura oluşturma servisi
└── docker-compose.yml       # Docker orkestrasyonu
```

## 🚀 Başlangıç

### Gereksinimler
- Node.js 18+ 
- Docker ve Docker Compose
- Redis
- Kafka (Docker üzerinden)

### Kurulum

1. **Repository'yi klonlayın**
```bash
git clone <repository-url>
cd restaurant-website
```

2. **Bağımlılıkları yükleyin**
```bash
npm run install-all
```

3. **Ortam Kurulumu**
Frontend ve backend dizinlerinde `.env` dosyaları oluşturun:

**Backend (.env)**
```env
DATABASE_URL=your_supabase_database_url
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_anon_key
CLOUD_NAME=your_cloudinary_cloud_name
CLOUD_API_KEY=your_cloudinary_api_key
CLOUD_API_SECRET=your_cloudinary_api_secret
STRIPE_SECRET_KEY=your_stripe_secret_key
FRONTEND_URL=http://localhost:5173
```

**Frontend (.env.local)**
```env
NEXT_PUBLIC_BACKEND_URL=http://localhost:3000
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
```

4. **Docker ile başlatın**
```bash
docker-compose up -d
```

5. **Geliştirme sunucularını başlatın**
```bash
npm run dev
```

Uygulama şu adreslerde erişilebilir olacak:
- Frontend: http://localhost:5173
- Backend API: http://localhost:3000
- Admin Dashboard: http://localhost:5173/admin

## 📚 API Endpoint'leri

### Kimlik Doğrulama
- `POST /auth/register` - Kullanıcı kaydı
- `POST /auth/login` - Kullanıcı girişi
- `POST /auth/logout` - Kullanıcı çıkışı

### Ürünler
- `GET /products` - Tüm ürünleri getir
- `GET /products/popular` - Popüler ürünleri getir
- `POST /products` - Ürün oluştur (admin)
- `PUT /products/:id` - Ürün güncelle (admin)
- `DELETE /products/:id` - Ürün sil (admin)

### Siparişler
- `GET /orders` - Kullanıcı siparişlerini getir
- `POST /orders` - Yeni sipariş oluştur
- `PUT /orders/:id/status` - Sipariş durumunu güncelle
- `GET /orders/admin` - Tüm siparişleri getir (admin)

### Sepet
- `GET /basket` - Kullanıcı sepetini getir
- `POST /basket/add` - Sepete ürün ekle
- `PUT /basket/update` - Sepet ürününü güncelle
- `DELETE /basket/remove/:id` - Sepetten ürün kaldır

### Ödeme
- `POST /checkout/create-payment-intent` - Stripe ödeme oluştur
- `POST /checkout/confirm` - Siparişi onayla

## 🔧 Geliştirme

### Mevcut Script'ler

```bash
# Tüm bağımlılıkları yükle
npm run install-all

# Geliştirme sunucularını başlat
npm run dev

# Frontend'i build et
cd frontend && npm run build

# Production'ı başlat
cd frontend && npm start
```

### Kod Yapısı
- **Özellik Tabanlı Mimari**: İş özelliklerine göre organize edilmiş
- **Servis Katmanı**: İş mantığı controller'lardan ayrılmış
- **Middleware**: Kimlik doğrulama ve doğrulama
- **Hata Yönetimi**: Merkezi hata yönetimi
- **Loglama**: Winston ile yapılandırılmış loglama

## 🐳 Docker Dağıtımı

```bash
# Tüm servisleri build et ve başlat
docker-compose up -d

# Logları görüntüle
docker-compose logs -f

# Servisleri durdur
docker-compose down
```

## 📊 İzleme ve Sağlık Kontrolleri

- **Sağlık Endpoint'i**: `GET /health` - Sistem durumu
- **Redis Durumu**: Bağlantı izleme
- **Kafka Durumu**: Olay akışı sağlığı
- **API Loglama**: İstek/yanıt loglama

## 🔒 Güvenlik Özellikleri

- **JWT Kimlik Doğrulama**: Güvenli token tabanlı kimlik doğrulama
- **CORS Koruması**: Cross-origin istek işleme
- **Girdi Doğrulama**: İstek verisi sanitizasyonu
- **Dosya Yükleme Güvenliği**: Resim doğrulama ve işleme
- **Ortam Değişkenleri**: Güvenli konfigürasyon yönetimi

## 📱 Responsive Tasarım

- **Mobil Öncelikli**: Mobil cihazlar için optimize edilmiş
- **Tablet Desteği**: Responsive tablet düzenleri
- **Masaüstü Deneyimi**: Gelişmiş masaüstü özellikleri
- **Dokunmatik Dostu**: Mobil optimize edilmiş etkileşimler

## 🎨 UI/UX Özellikleri

- **Akıcı Animasyonlar**: Framer Motion geçişleri
- **Yükleme Durumları**: İşlemler sırasında kullanıcı geri bildirimi
- **Hata Yönetimi**: Kullanıcı dostu hata mesajları
- **Toast Bildirimleri**: Başarı/hata geri bildirimi
- **Karanlık/Açık Mod**: Tema desteği (planlanmış)

## 📈 Performans

- **Resim Optimizasyonu**: Next.js resim optimizasyonu
- **Kod Bölme**: Dinamik import'lar
- **Önbellekleme**: Redis ve tarayıcı önbellekleme
- **CDN**: Resim dağıtımı için Cloudinary
- **Lazy Loading**: Bileşen ve resim lazy loading

## 🤝 Katkıda Bulunma

1. Repository'yi fork edin
2. Özellik branch'i oluşturun
3. Değişikliklerinizi yapın
4. Uygunsa test ekleyin
5. Pull request gönderin

## 📄 Lisans

Bu proje ISC Lisansı altında lisanslanmıştır.

## 👥 Yazar
- **Ahmet Buğra Kadıoğlu** - Frontend Geliştirme

## 🙏 Teşekkürler

- Veritabanı ve kimlik doğrulama için Supabase
- Ödeme işleme için Stripe
- Resim yönetimi için Cloudinary
- Harika kütüphaneler için açık kaynak topluluğu 