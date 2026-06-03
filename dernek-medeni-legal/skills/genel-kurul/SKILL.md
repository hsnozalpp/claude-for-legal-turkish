---
name: genel-kurul
description: >
  Dernek genel kurulu (olağan/olağanüstü) için çağrı, gündem, hazirun ve karar
  tutanağı taslakları ile toplantı öncesi/sonrası formalite kontrol listesi
  üretir. Tüzük + Dernekler Kanunu/Yönetmeliği esas alınır; vakıf mütevelli
  heyeti toplantıları için de uyarlanabilir. Çıktı hukukçu incelemesine tabidir.
argument-hint: "[olağan / olağanüstü / gündem konusu]"
---

# /genel-kurul

## İş akışı

1. Profili oku; tüzükteki genel kurul hükümlerini (çağrı usulü, toplantı/karar nisabı, gündem bağlılığı, organ seçimi) öğren. Tüzük yoksa kullanıcıdan ilgili maddeleri iste.
2. Toplantı türünü (olağan/olağanüstü) ve gündemi netleştir.
3. İstenen belgeleri üret: çağrı metni, gündem, hazirun cetveli iskeleti, karar tutanağı taslağı, formalite listesi.

## Intake

- Olağan mı olağanüstü mü? Olağansa son genel kurul tarihi nedir?
- Gündem maddeleri neler? (organ seçimi, faaliyet/denetim raporu, bütçe, tüzük değişikliği, fesih vb.)
- Tüzükteki çağrı usulü ve süresi nedir? İlk/ikinci toplantı nisabı?
- Toplantı yeri/şekli (fiziki/elektronik) ve tarih?
- İdareye/sicile bildirim ve DERBİS girişi bekleniyor mu?

## Nisap ve çağrı kapısı

Toplantı ve karar nisapları ile çağrı süreleri **tüzük + mevzuata** göre doğrulanmadan "geçerli" yazma. Tüzük değişikliği ve fesih gibi konular ağırlaştırılmış nisap gerektirir; bunu ayrıca işaretle ve hukukçu kontrolü iste.

## Mevzuat referansları

- **Genel kurul (zorunlu organ):** TMK m.72; oluşum, çağrı, toplantı/karar usulü ve yetkiler TMK m.73-77. Çağrı usulü ve nisaplar **önce tüzüğe**, sonra bu maddelere göre kontrol edilir.
- **Üyeliğe kabul/çıkarmada son karar:** TMK m.80. **Menfaat çatışması** (üye; eşi, üstsoy, altsoy ile işlem): TMK m.82 — ilgili üye o kararda oy kullanamaz.
- **Fesih:** genel kurul kararıyla TMK m.88 (ağırlaştırılmış nisap — tüzük + mevzuat).
- **Bildirim (m.23):** Genel kurulu izleyen **30 gün** içinde seçilen yönetim/denetim kurulu asıl-yedek üyeleri dernekler birimine bildirilir; üyeliğe kabul/sona erme **45 gün** içinde bildirilir *(5253 m.23)*. Bunu formalite listesine ekle.

## Çıktı iskeletleri

### Çağrı metni (taslak)
```text
[DERNEK ADI]
[OLAĞAN/OLAĞANÜSTÜ] GENEL KURUL TOPLANTISI ÇAĞRISI

Toplantı Tarihi/Saati: [ ]   Yer: [ ]   Şekil: [fiziki/elektronik]
Çoğunluk sağlanamazsa ikinci toplantı: Tarih/Saat: [ ]   Yer: [ ]
Gündem:
1. Açılış ve yoklama, divan oluşumu
2. [ ]
...
Yönetim Kurulu adına
[Ad / unvan]
```

### Karar tutanağı (taslak)
```text
[DERNEK ADI] GENEL KURUL TOPLANTI TUTANAĞI
Tarih: [ ]   Yer: [ ]   Toplantı no: [ ]
Hazirun: [katılan üye sayısı] / [toplam üye]  (hazirun cetveli ektedir)
Divan: Başkan [ ], Yazman [ ], Sayman [ ]

Reviewer note: [nisap kontrolü / tüzük maddesi / bildirim ihtiyacı]

GÜNDEM VE KARARLAR
1. ...
2. [Organ seçimi yapıldıysa: seçilen yönetim/denetim kurulu asıl ve yedek üyeleri]
...

İmzalar: Divan heyeti
```

## Formalite kontrol listesi

```text
□ Çağrı tüzükteki usul ve süreyle yapıldı mı?
□ Gündem önceden duyuruldu mu, toplantı gündeme bağlı kaldı mı?
□ İlk/ikinci toplantı nisabı doğru uygulandı mı?
□ Hazirun cetveli imzalandı mı?
□ Tüzük değişikliği/fesih için ağırlaştırılmış nisap sağlandı mı?
□ Organ seçimi sonuçları doğru kaydedildi mi?
□ İdareye bildirim / DERBİS girişi / sicil işlemi gerekiyor mu? (5253 m.23: organlar 30 gün, üyelik 45 gün)
□ Yeni yönetim kurulunun görev dağılımı ayrı kararla yapılacak mı? (→ /dernek-medeni-legal:yonetim-kurulu-karar)
```

## Bu skill ne yapmaz

- Toplantının/kararın geçerliliğine kesin hüküm vermez.
- İdareye/DERBİS'e otomatik bildirim yapmaz.
- Nisap ve süreleri resmi kaynak/tüzük kontrolü olmadan kesinleştirmez.
