
# Survivor API

Bu proje, Survivor yarışmacıları ve kategorileri arasında bir ilişki sağlayan bir Web API uygulaması geliştirmek için yapılmıştır. Bu proje, yarışmacı ve kategori CRUD (Create, Read, Update, Delete) işlemleri yapılmasına olanak tanır.

## Tablolar

- **Bir Category** birden fazla **Competitor**'a sahip olabilir. (Bire çok ilişkisi)
- Her **Competitor** yalnızca bir **Category**'ye ait olacaktır.

## Proje Özellikleri

- ASP.NET Core Web API ile geliştirilmiştir.
- Entity Framework Core kullanılmıştır.
- Bire çok (one-to-many) ilişki yapısı oluşturulmuştur.

### Kullanılan Teknolojiler

- **C#**
- **ASP.NET Core Web API**
- **Entity Framework Core**
- **SQL Server**
- **Swagger** - API dokümantasyonu
- **Postman** - API testi için

## Veritabanı Yapısı

### 1. Category Tablosu

| Sütun Adı | Veri Tipi | Açıklama          |
|-----------|-----------|------------------|
| Id        | int       | Kategori Id      |
| Name      | string    | Kategori Adı     |
| Competitors | List    | Yarışmacılar listesi |

### 2. Competitor Tablosu

| Sütun Adı  | Veri Tipi | Açıklama         |
|------------|-----------|-----------------|
| Id         | int       | Yarışmacı Id     |
| FullName   | string    | Yarışmacı Adı    |
| BirthDate  | DateTime  | Doğum Tarihi     |
| Height     | int       | Boy             |
| Location   | string    | Şehir           |
| CategoryId | int       | Kategori Id     |

## Kurulum

1. **Proje dosyalarını klonlayın:**

   ```bash
   git clone https://github.com/kullaniciadi/survivor-api.git
   cd survivor-api
   ```

2. **Bağımlılıkları yükleyin:**

   ```bash
   dotnet restore
   ```

3. **Veritabanını oluşturun:**

   Entity Framework Core kullanarak veritabanını oluşturun:

   ```bash
   dotnet ef database update
   ```

4. **API'yi başlatın:**

   ```bash
   dotnet run
   ```

5. **Swagger ile API'yi test edin:**

   Tarayıcıdan Swagger arayüzüne ulaşın:

   ```
   https://localhost:5001/swagger/index.html
   ```

## API Endpoint'leri

### CompetitorController

- **GET /api/competitors** - Tüm yarışmacıları listele.
- **GET /api/competitors/{id}** - Belirli bir yarışmacıyı getir.
- **GET /api/competitors/categories/{CategoryId}** - Kategori Id'ye göre yarışmacıları getir.
- **POST /api/competitors** - Yeni bir yarışmacı oluştur.
- **PUT /api/competitors/{id}** - Belirli bir yarışmacıyı güncelle.
- **DELETE /api/competitors/{id}** - Belirli bir yarışmacıyı sil.

### CategoryController

- **GET /api/categories** - Tüm kategorileri listele.
- **GET /api/categories/{id}** - Belirli bir kategoriyi getir.
- **POST /api/categories** - Yeni bir kategori oluştur.
- **PUT /api/categories/{id}** - Belirli bir kategoriyi güncelle.
- **DELETE /api/categories/{id}** - Belirli bir kategoriyi sil.

## Katkıda Bulunma

Projeye katkıda bulunmak isterseniz lütfen aşağıdaki adımları takip edin:

1. **Proje Fork'layın**.
2. **Yeni bir branch oluşturun**: `git checkout -b yeni-ozellik`.
3. **Değişikliklerinizi commit edin**: `git commit -m 'Yeni özellik eklendi'`.
4. **Branch'e push edin**: `git push origin yeni-ozellik`.
5. **Pull Request açın**.

## Lisans

Bu proje MIT lisansı altında lisanslanmıştır.

ASP.NET Core: Backend framework for building RESTful APIs.
Entity Framework Core: ORM for interacting with the database.
SQL Server: (or InMemory for development) Database for storing the data.
Swagger: Integrated for API documentation and testing.
Dependency Injection: Used to manage service lifetimes and scope.
