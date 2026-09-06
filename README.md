# BIST algoritmik işlem araştırması

İlişkili hisselerde geride kalanı spot alma, VİOP çift işlemi ve spot–vadeli taşıma yaklaşımlarını karşılaştıran araştırma çalışması. Canlı emir gönderen bir uygulama içermez.

## Güncel sonuç

İlk spot deneyi, 2024-01-02–2026-09-04 döneminde her ekonomik gruba 25.000 TL sanal başlangıç sermayesi ve alış/satışın her birine %0,15 değişken maliyet varsayımıyla:

| Ekonomik grup | Tamamlanan işlem | Değişken gider sonrası sonuç | Dönemin toplam getirisi |
|---|---:|---:|---:|
| AKBNK / GARAN | 11 | −3.978,49 TL | −%15,91 |
| TCELL / TTKOM | 9 | +1.959,43 TL | +%7,84 |
| Birleşik portföy | 20 | −2.019,06 TL | −%4,04 |

Her grupta sinyal oluştuğunda yalnız geride kalıp toparlanma işareti veren hisse alınır; iki hisse aynı anda alınıp satılan korunmuş çift değildir. Sonuçlar yıllıklandırılmamıştır. Sabit veri/yazılım giderleri, vergi ve nakit faizi tablodaki sonuçlara dahil değildir. Aylık 500 TL sabit gider senaryosunda birleşik dönem sonucu −18.068,67 TL olur; bu bir kurum tarifesi değil, sonradan uygulanan gider hassasiyeti hesabıdır.

Bu kuralla banka grubu seçilmez. Telekom grubundaki dokuz işlemlik pozitif sonuç, kalıcı avantaj veya canlıya geçiş için yeterli kanıt değildir. Birleşik portföyün günlük kapanışlara göre en büyük zirveden düşüşü %20,11 olmuştur; başlangıç sermayesine göre zarar ile aynı ölçü değildir.

## Sonuçların sınırı

Yahoo Finance'tan indirilen 2021-09-01–2026-09-04 verisi dört hisse için 1.264 ham, 1.259 ortak geçerli günlük kayıt içeriyor. Beş ortak boş tarihten 9 Nisan 2024 gerçek bir yarım seans olduğu halde eksiktir. Boş fiyatlar doldurulmadı. Bu bilinen eksikle üretilen sonuçlar keşif amaçlıdır; temiz veriyle doğrulanmış kârlılık kanıtı değildir.

Bugün seçilmiş dört yaşayan şirketin geçmişi kullanıldığı için seçim/sağkalım yanlılığı vardır. Sonraki tarihsel dönem gerçek zamanlı bağımsız ileri test değildir. Düzeltilmiş fiyatlardan kesirli toplam getiri birimleri kullanılır; gerçek lotlar, kotasyonlar, açılışta gerçekleşme ve temettü ödeme zamanlaması modellenmez. %5 kapanış zarar eşiği kesin zarar tavanı sağlamaz.

## Tekrar çalıştırma

Python 3.10 veya üzeri yeterlidir; ek paket gerekmez. Depo kökünde:

```bash
python3 research/spot_historical_test.py
```

Windows'ta Python kurulumuna göre:

```powershell
py -3 research/spot_historical_test.py
```

Komut JSON sonuçlarını, CSV işlem kayıtlarını ve Markdown raporunu yeniden üretir. Nakit/pozisyon, sinyal ve işlem tarihleri, eğitim dönemi ve kâr/zarar mutabakatı kontrolleri içerir. Veri dosyaları sabit anlık görüntüdür; kaynak adresleri ve SHA-256 özetleri aynı dizinde kayıtlıdır. Sağlayıcının veriyi sonradan düzeltmesi bu anlık görüntüyü değiştirmez.

## Dosyalar

- [Deney kuralları ve önkayıt](research/spot-deney-onkayit.md)
- [Ayrıntılı test raporu](research/spot-ilk-test-raporu.md)
- [İşlem kayıtları](research/spot-test-islemler.csv)
- [Makine tarafından okunabilir sonuçlar](research/spot-test-sonuclari.json)
- [Veri kaynakları](research/data/spot-yahoo-2026-09-06/manifest.json)
- [Spot strateji taslağı](research/spot-geride-kalan-stratejisi.md)
- [VİOP kazanç hipotezi](research/ilk-kazanc-hipotezi.md)
- [Wayfinder karar haritası](.scratch/arbitraj/map.md)
- [Kavramlar](CONTEXT.md)

Araştırma notları kurum/platform karşılaştırmalarını ve çalışma bütçesini de içerir. Güncel ücretler veya erişim olanakları, ilgili notta belirtilen doğrulama tarihine göre okunmalıdır.
