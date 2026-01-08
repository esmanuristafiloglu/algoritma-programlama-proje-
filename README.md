# Uzay Simülasyonu Uygulaması

Algoritmalar ve Programlama dersi için yaptığım konsol tabanlı fizik simülasyonu projesi.

## Proje Hakkında

Bu program, farklı gezegenlerde ve uydularda (Merkür, Venüs, Dünya, Ay, Mars, Jüpiter, Satürn, Uranüs, Neptün) fizik deneyleri yapmamıza olanak sağlıyor. C dili ile yazıldı ve konsol üzerinden çalışıyor.

Program başladığında isminizi giriyorsunuz, sonra 9 farklı deneyden birini seçip parametreleri giriyorsunuz. Program tüm gök cisimleri için sonuçları hesaplayıp gösteriyor.

## Deneyler

1. Serbest Düşme Deneyi - `h = (1/2) * g * t²`
2. Yukarı Atış Deneyi - `h_max = v₀² / (2*g)`
3. Ağırlık Deneyi - `G = m * g`
4. Potansiyel Enerji Deneyi - `Ep = m * g * h`
5. Hidrostatik Basınç Deneyi - `P = ρ * g * h`
6. Arşimet Kaldırma Kuvveti - `Fk = ρ * g * V`
7. Basit Sarkaç Periyodu - `T = 2π * √(L/g)`
8. Sabit İp Gerilmesi - `T = m * g`
9. Asansör Deneyi - `F = m * (g ± a)`

## Gök Cisimleri

Program 9 gök cisminin yerçekimi ivmelerini kullanıyor:
- Merkür: 3.703 m/s²
- Venüs: 8.872 m/s²
- Dünya: 9.8067 m/s²
- Ay: 1.625 m/s²
- Mars: 3.728 m/s²
- Jüpiter: 25.93 m/s²
- Satürn: 11.19 m/s²
- Uranüs: 9.01 m/s²
- Neptün: 11.28 m/s²

## Nasıl Çalıştırılır

Derleme:
```bash
gcc main.c -o uzay_simulasyonu -lm
```

Çalıştırma:
```bash
./uzay_simulasyonu
```

Program çalıştığında:
1. İsminizi girin
2. Deney numarasını seçin (1-9, çıkmak için -1)
3. İstenen parametreleri girin
4. Sonuçları görün

## Teknik Özellikler

- C programlama dili
- Pointer aritmetiği kullanımı (`*(ptr + i)`)
- Ternary operatör ile negatif değer kontrolü
- Modüler yapı (her deney ayrı fonksiyon)
- Pointer parametreleri

## Kullanılan Kütüphaneler

- `stdio.h` - Girdi/çıktı
- `stdlib.h` - Standart kütüphane
- `math.h` - Matematiksel işlemler
