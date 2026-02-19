# 🔥 İtki Sistemleri (Propulsion Systems)

<div align="center">

  ![OpenRocket](https://img.shields.io/badge/OpenRocket-Simülasyon-blue?style=for-the-badge&logo=rocket)
  ![Cesaroni](https://img.shields.io/badge/Cesaroni-Motor_Tedariği-red?style=for-the-badge&logo=fire)
  ![SolidWorks](https://img.shields.io/badge/SolidWorks-CAD_Tasarım-orange?style=for-the-badge&logo=dassaultsystèmes)

</div>

## 🎯 Hedef ve Gereksinimler
**Görev:** Faydalı yük ile birlikte roketi **10.000 feet (3.048m)** irtifaya taşımak.
**Kısıt:** Ses hızını (Mach 1.2) aşmamak ve stabil bir uçuş profili sağlamak.

---

## 🚀 Motor Seçimi ve Analizi

Yüksek irtifa kategorisi için **L Sınıfı** katı yakıtlı motorlar veya özgün **Hibrit Motor** tasarımı değerlendirilmektedir.

### 📊 Motor Performans Tablosu

| Parametre | Cesaroni L1115 (Katı) | Özgün Hibrit (N2O + Parafin) |
| :--- | :--- | :--- |
| **Toplam İtki (Total Impulse)** | 3.650 Ns | 4.200 Ns (Hedef) |
| **Ortalama İtki (Avg Thrust)** | 1.115 N | 950 N |
| **Yanma Süresi (Burn Time)** | 3.9 sn | 5.5 sn |
| **Özgül İtki (Isp)** | 210 sn | 240 sn |
| **Toplam Ağırlık** | 2.8 kg | 4.1 kg (Tank dahil) |

> [!NOTE]
> **Karar:** Güvenilirlik ve yarışma takvimi göz önüne alınarak, ilk uçuş için **Cesaroni L1115** ticari motoru tercih edilmiştir. AR-GE çalışmaları hibrit motor üzerine devam edecektir.

---

## 📐 Teknik Tasarım Detayları

### 1. Katı Yakıt Geometrisi (Grain Geometry)
Motor performansını belirleyen temel faktör yanma yüzey alanıdır.
*   **Bates Grain:** Silindirik, ortası delik yakıt blokları. Nötr (sabit) itki profili sağlar.
*   **Finocyl:** Yıldız geometrisi. Yüksek başlangıç itkisi (High Kick-off) sağlar, rampadan çıkış hızını artırır.

### 2. Lüle Tasarımı (Nozzle Design)
Süpersonik egzoz çıkışı için **De Laval (Yakınsak-Iraksak)** lüle kullanılır.

$$ \frac{A_e}{A_t} = \frac{1}{M_e} \left[ \left( \frac{2}{\gamma + 1} \right) \left( 1 + \frac{\gamma - 1}{2} M_e^2 \right) \right]^{\frac{\gamma + 1}{2(\gamma - 1)}} $$

*   **Boğaz Alanı ($A_t$):** Yanma odası basıncını (Chamber Pressure) belirler.
*   **Çıkış Alanı ($A_e$):** İdeal genişleme (Optimum Expansion) için dış basınca göre ayarlanır.

---

## 🛠️ Hibrit Motor AR-GE (Future Work)

Kendi geliştirdiğimiz hibrit motor tasarımı, güvenlik ve performans avantajları sunar.

```mermaid
graph LR
    Oxidizer[Oksitleyici Tankı<br>(N2O - Azot Protoksit)] -->|Selenoid Valf| Injector[Enjektör Plakası]
    Injector -->|Atomize Gaz| CC[Yanma Odası<br>(Parafin/Mum Yakıt)]
    Igniter[Ateşleyici] --> CC
    CC -->|Yüksek Basınç| Nozzle[De Laval Lüle]
    Nozzle --> Exhaust[Egzoz Gazı]
    
    style Oxidizer fill:#e1f5fe,stroke:#01579b
    style CC fill:#fff3e0,stroke:#e65100
```

### Avantajlar
1.  **Durdurulabilir:** Vana kapatılarak motor susturulabilir.
2.  **Güvenli:** Yakıt ve oksitleyici ayrı depolandığı için patlama riski düşüktür.
3.  **Çevreci:** Toksik olmayan yakıtlar kullanılır.

---

## ⚙️ Montaj ve Entegrasyon
İtki kuvvetinin gövdeye aktarımı kritiktir. 

*   **Motor Kundağı:** 75mm çapında Isıya Dayanıklı Fenolik Tüp.
*   **Merkezleme Halkaları (Centering Rings):** 3 adet, Birch Plywood (6mm).
*   **Thrust Plate:** Motorun geri tepme kuvvetini doğrudan gövdeye ileten Alüminyum 6061 plaka.
*   **Retainer:** Motorun uçuş sonrası düşmesini engelleyen vidalı kapak sistemi.

---

## ⚠️ Güvenlik Prosedürleri
*   **Depolama:** Motorlar kuru ve serin yerde saklanmalıdır.
*   **Statik Test:** Her yeni tasarım önce yer test standında (Static Fire Test) denenir.
*   **Güvenli Mesafe:** L sınıfı motor ateşlemelerinde en az **100 metre** mesafede bulunulmalıdır.
