<p align="center">
  <img src="[https://github.com/user-attachments/assets/50fe082c-141a-42a5-92d0-089bad5a0e1b](https://github.com/user-attachments/assets/50fe082c-141a-42a5-92d0-089bad5a0e1b)" alt="BRIQ Logo" width="150"/>
</p>

<h1 align="center">⚡️ ExeQ Thinker</h1>

<p align="center">
  <strong><i>“Bırakın, görünmeyen desenler gerçeği ortaya çıkarsın.”</i></strong>
  <br />
  <br />
  Karmaşık analiz, stratejik planlama ve güvenilir sonuçlar için tasarlanmış, derinlemesine düşünen bir bilişsel mimari.
</p>

<p align="center">
    <a href="#"><img src="[https://img.shields.io/badge/Python-3.11+-blue?logo=python&logoColor=white](https://img.shields.io/badge/Python-3.11+-blue?logo=python&logoColor=white)" alt="Python Version"></a>
    <a href="#"><img src="[https://img.shields.io/badge/License-MIT-green.svg](https://img.shields.io/badge/License-MIT-green.svg)" alt="License"></a>
    <a href="#"><img src="[https://img.shields.io/badge/Status-Aktif-brightgreen](https://img.shields.io/badge/Status-Aktif-brightgreen)" alt="Project Status"></a>
    <a href="#"><img src="[https://img.shields.io/github/stars/your-org/exeq-thinker?style=social](https://img.shields.io/github/stars/your-org/exeq-thinker?style=social)" alt="GitHub Stars"></a>
</p>

---

## 🎯 Neden ExeQ Thinker?

Standart Dil Modelleri (LLM), tek adımlık görevlerde harikalar yaratır ancak karmaşık, çok aşamalı ve belirsiz problemler karşısında yetersiz kalır. Cevapları yüzeysel olabilir, kritik detayları gözden kaçırabilir ve tutarsız sonuçlar üretebilirler.

**ExeQ Thinker** ise bu sorunu çözmek için geliştirilmiş bir **bilişsel mimaridir (cognitive architecture)**. Basit bir "soru-cevap" mekanizması yerine, problemi alt görevlere ayıran, her adımı eleştirel bir süzgeçten geçiren ve araçları (tool) akıllıca kullanarak en doğru sonuca ulaşan **planlayıcı-eleştirmen (planner-critic)** döngülerini kullanır.

Bu yapı, onu aşağıdakiler için vazgeçilmez kılar:
- 🧠 **Araştırmacılar:** Kanıta dayalı, denetlenebilir ve tekrarlanabilir analiz zincirleri oluşturmak için.
- ⚙️ **Mühendisler:** Güvenilir araç kullanımı (tool-use), yapılandırılmış veri (JSON) çıktısı ve otomasyon süreçleri için.
- 🏢 **Kurumlar:** Üretim ortamına hazır, denetim kayıtları (audit logs) tutan ve öngörülebilir yapay zeka kararları için.

---

## ✨ Temel Özellikler

- 🧭 **Derinlemesine ve Çok Adımlı Akıl Yürütme:** Bir problemi atomik parçalarına ayırır, her birini analiz eder ve sonuçları sentezleyerek yüksek güvenilirlikli çıktılar üretir. Bu, "Chain of Thought" mekanizmasının çok daha gelişmiş bir versiyonudur.

- 🚀 **Optimize Edilmiş Performans:** **Flash Attention 2** gibi en son GPU optimizasyonları sayesinde, dikkat mekanizmasının karesel ($O(N^2)$) karmaşıklığını çizgisel ($O(N)$) seviyesine indirir. Bu, daha az VRAM kullanımı ve çok daha yüksek çıkarım (inference) hızları anlamına gelir.

- 🛠️ **Genişletilebilir Araç (Tool) Ekosistemi:** RAG (Retrieval-Augmented Generation) pipeline'ları, harici API'lar, veritabanları veya özel veri kaynakları gibi herhangi bir aracı sisteme kolayca entegre edin.

- 🔒 **Üretim Ortamına Hazır (Production-Ready):**
  - **Token Bütçeleme:** Sonsuz döngüleri ve beklenmedik maliyetleri önlemek için her işlemde token kullanımını akıllıca yönetir.
  - **Durum Yönetimi (Stateful Memory):** Konuşma geçmişini ve ara adımları yöneterek bağlamı asla kaybetmez.
  - **Güvenlik Korkulukları (Guardrails):** İstenmeyen veya zararlı içerik üretimini engeller ve sistemin güvenilirliğini artırır.
  - **Detaylı Loglama:** Her bir düşünce adımını, araç çağrısını ve kararını kaydederek tam bir denetlenebilirlik sağlar.

- 🧠 **Özel Olarak İnce Ayarlanmış Model (`gpt-oss:20b-exeq`):**
  - **Temel Model:** Güçlü ve açık kaynaklı `ollama gpt-oss:20b`.
  - **Eğitim Verisi:** Akıl yürütme, planlama ve araç kullanımı üzerine odaklanmış, **1.8 milyon ham örnekten oluşan (toplamda 400 milyar token'dan fazla)** devasa bir veri seti ile ince ayar (fine-tuning) yapılmıştır. Bu, modelin karmaşık talimatları anlama ve uygulama yeteneğini zirveye taşır.

---

## 🏗️ Mimari: ExeQ Nasıl Düşünür?

ExeQ Thinker, insan beyninin bir problemi çözerken izlediği "düşün-eleştir-eyleme geç" döngüsünü taklit eder. Süreç, aşağıdaki adımlarla işler:

```mermaid
graph TD
    subgraph "Kullanıcı Etkileşimi"
        A[👤 Kullanıcı Sorusu]
    end

    subgraph "ExeQ Thinker Çekirdeği"
        B[🧠 Orkestratör]
        C[📝 Planlayıcı]
        D[🔎 Eleştirmen/Sentezleyici]
        E[🛠️ Araç Yönlendirici]
        F[💾 Bellek Yöneticisi]
    end

    subgraph "Hesaplama ve Veri Katmanı"
        G["🚀 GPU ile Hızlandırılmış Model (gpt-oss:20b-exeq)"]
        H["📚 Harici Araçlar (RAG, API'ler, DB)"]
    end

    subgraph "Çıktı"
        I[💬 Anlık Akış (Streaming) Cevap]
    end

    A --> B
    B -- Problem Analizi --> C
    C -- Adım Adım Plan Oluşturur --> B
    B -- Görevi Yönlendirir --> E
    E -- Gerekli Aracı Çağırır --> H
    H -- Sonuçları Döndürür --> D
    C -- Planı Gönderir --> D
    F -- Bağlam ve Geçmişi Sağlar --> D
    D -- Sonuçları ve Planı Değerlendirir, Gerekirse Revize için Planlayıcıya Geri Gönderir --> B
    B -- Nihai Cevap için Sentezlenmiş Veriyi Gönderir --> I
    
    C -- Model Çağrısı --> G
    D -- Model Çağrısı --> G
    E -- Model Çağrısı --> G

    style B fill:#1E90FF,stroke:#333,stroke-width:2px,color:#fff
    style G fill:#FF4500,stroke:#333,stroke-width:2px,color:#fff
```

---

# Clone the repo
```
git clone https://github.com/your-org/exeq-thinker.git
cd exeq-thinker
```

---

# Create environment
```
conda create -n exeq-turbo python=3.11 -y
conda activate exeq-turbo
```

---

# Project environment
```
exeq-turbo/
│── app.py                # FastAPI entrypoint
│── requirements.txt      # Dependencies
│── src/
│   │── core/             # Core engine
│   │── memory/           # History & token budgeting
│   │── tools/            # RAG & external tool router
│   │── models/           # LLM integrations
│── tests/                # Unit & integration tests
│── docs/                 # Documentation
```

---

# Install dependencies
```
pip install -r requirements.txt
```

---

# Running locally
```
python app.py
```

---

# Example curl request
```
curl -X POST http://localhost:5001/chat \
     -H "Content-Type: application/json" \
     -d '{"message": "“At what point is there a non-negotiable difference between Einstein’s theory of general relativity and Stephen Hawking’s studies of black holes?”!"}'
```
