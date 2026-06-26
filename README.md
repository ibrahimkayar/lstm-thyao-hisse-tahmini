# LSTM ile THYAO Hisse Senedi Kapanış Fiyatı Tahmini

Bu projede Borsa İstanbul'da işlem gören Türk Hava Yolları A.O. (THYAO) hisse senedinin kapanış fiyatı, Uzun Kısa Süreli Bellek Ağı (Long Short-Term Memory - LSTM) kullanılarak tahmin edilmiştir.

Çalışma kapsamında yapay sinir ağlarının teorik altyapısı incelenmiş ve zaman serisi tahmin problemlerinde yaygın olarak kullanılan LSTM mimarisi finansal veriler üzerinde uygulanmıştır.

---

## Proje Amacı

Bu çalışmanın amacı, geçmiş dönem finansal verileri kullanarak THYAO hisse senedinin bir sonraki güne ait kapanış fiyatını tahmin etmektir.

Finansal zaman serileri doğrusal olmayan ve yüksek oynaklığa sahip yapılar olduğundan klasik regresyon yöntemleri yerine derin öğrenme tabanlı LSTM modeli tercih edilmiştir.

---

## Veri Seti

Projede 2023-2025 dönemine ait günlük THYAO verileri kullanılmıştır.

Veri setinde aşağıdaki değişkenler bulunmaktadır:

- Open (Açılış Fiyatı)
- High (En Yüksek Fiyat)
- Low (En Düşük Fiyat)
- Close (Kapanış Fiyatı)
- Volume (İşlem Hacmi)

Başlangıçta 749 gözlem bulunan veri seti, veri temizleme ve özellik mühendisliği işlemlerinden sonra 730 gözleme düşürülmüştür.

---

## Özellik Mühendisliği

Model performansını artırmak amacıyla aşağıdaki ek değişkenler oluşturulmuştur:

### Lag Değişkenleri
- Close_lag_1
- Close_lag_3
- Close_lag_5
- Close_lag_10

### Hareketli Ortalamalar
- MA_5
- MA_10
- MA_20

### Teknik Özellikler
- Return (Günlük Getiri)

Tüm değişkenler `MinMaxScaler` kullanılarak normalize edilmiştir.

---

## Model Mimarisi

Model aşağıdaki mimariden oluşmaktadır:

- LSTM (64 nöron)
- Dropout
- LSTM (32 nöron)
- Dropout
- Dense (1)

Toplam eğitilebilir parametre sayısı:

```text
32,417
