# 🍳 Bon Appétit: Akıllı Tarif & Dinamik Porsiyon Asistanı

Bu proje, modern web kazıma (Web Scraping) teknikleri, Nesne Yönelimli Programlama (OOP) ve standart veri modelleri (`schema.org/Recipe`) kullanılarak geliştirilmiş, kullanıcıların mutfaktaki en büyük kronik problemlerine akıllı çözümler sunan interaktif bir **Backend-Frontend** web uygulamasıdır.

🌐 **Canlı Demo (Vercel):** [Proje Canlı Linki Buraya Gelecek]

---

## ✨ Projenin Öne Çıkan Özellikleri & Benzersiz Mimari

Piyasadaki standart tarif siteleri statik metinler sunarken, bu proje sahip olduğu algoritmik motorlarla sıyrılmaktadır:

1. **Schema.org/Recipe Standardizasyonu & Otomatik Scraping:**
   * Bon Appétit web sitesinden BeautifulSoup ve Requests kütüphaneleri kullanılarak ham HTML ve JSON-LD (`application/ld+json`) verileri anlık olarak çekilir.
   * Sitelerin CSS class isimleri değişse dahi `schema.org` standartları sayesinde tarif adı, pişirme süresi, porsiyon ve görseller kusursuz bir şekilde yakalanır.

2. **Gelişmiş OOP Mimarisi (`Tarif` Sınıfı):**
   * Çekilen her tarif bellekte `Tarif` sınıfından türetilen nesnelere dönüştürülür. ISO 8601 süre formatları (`PT45M`) otomatik olarak tam sayı dakikalara çevrilir.

3. ⚡ **Benzersiz Özellik: Dinamik Porsiyon Ölçekleyici & Akıllı Kiler Motoru (Smart Pantry):**
   * **Matematiksel Gramaj Ölçekleme:** Tarif 4 kişiliktir ancak evdeki kişi sayısı slider üzerinden örneğin 2 veya 6 kişiye çekildiğinde; sistem metin içindeki kesirli sayıları (`1 1/2 cup`, `3/4 tsp` vb.) `Fraction` modülüyle algılar ve tüm malzeme gramajlarını anlık olarak matematiksel olarak yeniden hesaplar.
   * **Kiler Kontrolü (Eksik Alışveriş Analizi):** Kullanıcı evinde bulunan malzemeleri (`egg, butter, garlic` vb.) araya virgül koyarak yazar; sistem tarifle semantik eşleştirme yaparak bir **Dolap Uyumluluk Yüzdesi (% oran)** hesaplar ve marketten alınması gereken eksik listesini otomatik olarak filtreler.

---

## 🛠️ Kullanılan Teknolojiler

* **Backend:** Python, Flask, BeautifulSoup4, Requests, Isodate, Fractions
* **Frontend:** HTML5, Bootstrap 5, JavaScript (Async Fetch API)
* **Dağıtım (Deployment):** Vercel (Serverless Python Functions)

---

## 📂 Proje Dosya Yapısı

```text
bonappetit-tarif-asistani/
│
├── api/
│   └── index.py            # Flask backend, Scraping modülü ve OOP Tarif sınıfı
├── templates/
│   └── index.html          # Dinamik arayüz, porsiyon slider'ı ve kiler analiz paneli
├── requirements.txt        # Python bağımlılıkları
└── vercel.json             # Vercel serverless yönlendirme konfigürasyonu
