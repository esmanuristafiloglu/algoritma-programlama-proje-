# Uzay Simülasyonu Uygulaması

Bursa Teknik Üniversitesi Bilgisayar Mühendisliği Bölümü, Algoritmalar ve Programlama dersi kapsamında geliştirilmiş konsol tabanlı bir fizik simülasyonu uygulamasıdır.

## 📋 Proje Hakkında

Bu proje, bir bilim insanının Güneş Sistemindeki farklı gezegenlerde ve uydularda (Merkür, Venüs, Dünya, Ay, Mars, Jüpiter, Satürn, Uranüs, Neptün) temel fizik deneylerini simüle etmesini sağlar. Program tamamen C programlama dili ile geliştirilmiş olup, konsol tabanlı çalışmaktadır.

Program, kullanıcıdan bilim insanının adını alır ve 9 farklı fizik deneyi seçeneği sunar. Her deney, 9 gök cismi için ayrı ayrı hesaplama yaparak sonuçları karşılaştırmalı olarak gösterir.

## 🔬 Deneyler ve Formüller

Program 9 farklı fizik deneyi içermektedir:

1. **Serbest Düşme Deneyi** - `h = (1/2) * g * t²`
   - Düşme süresi girilir, her gök cismi için düşme mesafesi hesaplanır.

2. **Yukarı Atış Deneyi** - `h_max = v₀² / (2*g)`
   - Başlangıç hızı girilir, her gök cismi için maksimum yükseklik hesaplanır.

3. **Ağırlık Deneyi** - `G = m * g`
   - Kütle girilir, her gök cismi için ağırlık hesaplanır.

4. **Kütleçekimsel Potansiyel Enerji Deneyi** - `Ep = m * g * h`
   - Kütle ve yükseklik girilir, her gök cismi için potansiyel enerji hesaplanır.

5. **Hidrostatik Basınç Deneyi** - `P = ρ * g * h`
   - Sıvı yoğunluğu ve derinlik girilir, her gök cismi için basınç hesaplanır.

6. **Arşimet Kaldırma Kuvveti Deneyi** - `Fk = ρ * g * V`
   - Sıvı yoğunluğu ve batan hacim girilir, her gök cismi için kaldırma kuvveti hesaplanır.

7. **Basit Sarkaç Periyodu Deneyi** - `T = 2π * √(L/g)`
   - İp uzunluğu girilir, her gök cismi için sarkaç periyodu hesaplanır.

8. **Sabit İp Gerilmesi Deneyi** - `T = m * g`
   - Kütle girilir, her gök cismi için ip gerilmesi hesaplanır.

9. **Asansör Deneyi** - `F = m * (g ± a)`
   - Kütle, asansör ivmesi ve hareket yönü girilir, her gök cismi için etkin ağırlık hesaplanır.

## 🪐 Gök Cisimleri ve Yerçekimi İvmeleri

Program aşağıdaki gök cisimlerinin gerçek yerçekimi ivme değerlerini kullanır:

| Gök Cismi | Yerçekimi İvmesi (m/s²) |
|-----------|------------------------|
| Merkür    | 3.703                  |
| Venüs     | 8.872                  |
| Dünya     | 9.8067                 |
| Ay        | 1.625                  |
| Mars      | 3.728                  |
| Jüpiter   | 25.93                  |
| Satürn    | 11.19                  |
| Uranüs    | 9.01                   |
| Neptün    | 11.28                  |

## 🚀 Kullanım

### Derleme

Programı derlemek için:

```bash
gcc main.c -o uzay_simulasyonu -lm
```

**Not:** `-lm` parametresi matematik kütüphanesini (math.h) bağlamak için gereklidir.

### Çalıştırma

```bash
./uzay_simulasyonu
```

### Program Akışı

1. Program başladığında bilim insanının adı istenir.
2. Deney menüsü gösterilir (1-9 arası deneyler).
3. Kullanıcı bir deney numarası seçer (çıkış için -1).
4. Seçilen deneye göre gerekli parametreler istenir.
5. Tüm gök cisimleri için sonuçlar hesaplanır ve listelenir.
6. Program sonlandırılana kadar (kullanıcı -1 tuşlayana kadar) döngü devam eder.

## 💻 Teknik Detaylar

### Programlama Özellikleri

- **Dil:** C
- **Derleyici:** GCC
- **Kütüphaneler:** 
  - `stdio.h` - Girdi/çıktı işlemleri
  - `stdlib.h` - Standart kütüphane
  - `math.h` - Matematiksel fonksiyonlar (sqrt)

### Kullanılan Programlama Teknikleri

- **Pointer Aritmetiği:** Tüm dizi erişimlerinde pointer aritmetiği kullanılmıştır (`*(ptr + i)` formatında)
- **Pointer Parametreleri:** Fonksiyonlara pointer ile parametre geçirimi
- **Modüler Programlama:** Her deney ayrı bir fonksiyon olarak tasarlanmış
- **Girdi Doğrulama:** Negatif değer kontrolü ternary operatör ile yapılmış (`deger = (deger < 0) ? -deger : deger`)
- **Fonksiyon Prototipleri:** Kod organizasyonu için önceden tanımlama

### Önemli Fonksiyonlar

- `deneyler()` - Deney menüsünü gösterir
- `secim()` - Kullanıcıdan deney numarası alır
- `serbest_dusme()` - Serbest düşme hesaplaması yapar
- `yukari_atis()` - Yukarı atış hesaplaması yapar
- `agirlik()` - Ağırlık hesaplaması yapar
- `potansiyel()` - Potansiyel enerji hesaplaması yapar
- `hidrostatik()` - Hidrostatik basınç hesaplaması yapar
- `kaldirma_kuvveti()` - Kaldırma kuvveti hesaplaması yapar
- `periyod()` - Sarkaç periyodu hesaplaması yapar
- `ip_gerilmesi()` - İp gerilmesi hesaplaması yapar
- `asansor()` - Asansör deneyi hesaplaması yapar

### Kod Özellikleri

- Tüm dizi erişimleri pointer aritmetiği ile yapılmıştır
- Negatif değer kontrolü ternary operatör ile gerçekleştirilmiştir
- Fonksiyonlar pointer parametreleri kullanarak çağrılmaktadır
- Program `do-while` döngüsü ile sürekli çalışır, kullanıcı -1 tuşlayana kadar devam eder

## 📝 Özellikler

- ✅ 9 farklı gök cismi için karşılaştırmalı hesaplama
- ✅ 9 farklı fizik deneyi
- ✅ Kullanıcı dostu menü sistemi
- ✅ Negatif değer kontrolü (ternary operatör ile)
- ✅ Pointer aritmetiği kullanımı
- ✅ Modüler ve okunabilir kod yapısı

## 🔧 Gereksinimler

- GCC derleyici
- C standart kütüphaneleri
- Math kütüphanesi (libm)

## 📄 Lisans

Bu proje eğitim amaçlı geliştirilmiştir.

---

*Bu proje bireysel olarak geliştirilmiştir.*
