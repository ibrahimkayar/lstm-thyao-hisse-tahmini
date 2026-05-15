# LSTM ile THYAO Hisse Senedi Kapanış Fiyatı Tahmini

Bu projede, Borsa İstanbul’da işlem gören Türk Hava Yolları A.O. (THYAO) hisse senedinin kapanış fiyatı LSTM yapay sinir ağı modeli ile tahmin edilmiştir.

## Proje Hakkında

Çalışmada 2016-2025 dönemine ait günlük THYAO hisse senedi verileri kullanılmıştır. Modelde açılış fiyatı, en yüksek fiyat, en düşük fiyat, kapanış fiyatı ve işlem hacmi değişkenleri girdi olarak alınmış; hedef değişken olarak bir sonraki günün kapanış fiyatı belirlenmiştir.

## Kullanılan Yöntem

- Yapay Sinir Ağları
- LSTM modeli
- Zaman serisi tahmini
- Min-Max ölçeklendirme
- 60 günlük zaman penceresi

## Kullanılan Değişkenler

- Open
- High
- Low
- Close
- Volume

## Model Performansı

Model performansı aşağıdaki ölçütlerle değerlendirilmiştir:

- MAE: 15.36
- MSE: 289.27
- RMSE: 17.01
- R-kare: 0.138

## Sonuç

LSTM modeli genel fiyat eğilimini takip edebilmiş, ancak yüksek oynaklık dönemlerinde tahmin hataları artmıştır. R-kare değerinin düşük olması, modelin test dönemindeki fiyat değişimlerini sınırlı düzeyde açıklayabildiğini göstermektedir.

## Rapor

Proje raporuna aşağıdaki dosyadan ulaşabilirsiniz:

[LSTM_THYAO_Rapor.pdf](LSTM_THYAO_Rapor.pdf)
