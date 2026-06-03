---
name: vakif-kurulus
description: >
  Yeni (TMK) vakfı kuruluşu için resmi senet iskeleti, mahkeme tescili ve VGM
  süreçleri kontrol listesi üretir. TMK m.101-117 ve Vakıflar Kanunu (5737)
  esas alınır. Senet ve tescil mahkeme + noter boyutuyla hukukçu kontrolü
  gerektirir; çıktı taslaktır.
argument-hint: "[vakfın amacı]"
---

# /vakif-kurulus

## İş akışı

1. Profili oku. Vakfın amacını, özgülenecek mal/hakkı ve yönetim yapısını öğren.
2. Senet iskeleti + kuruluş süreç kontrol listesi üret. Mahkeme/noter boyutunu açıkça hukukçu kontrolüne bırak.

## Intake

- Vakfın amacı nedir ve hukuka/ahlaka uygun, belirli mi?
- Özgülenecek mal varlığı/hak nedir, amaca yeterli mi?
- Yönetim organı/mütevelli yapısı nasıl planlanıyor?
- Vergi muafiyeti hedefleniyor mu?
- Kurucu(lar) gerçek/tüzel kişi mi, ehliyet durumu?

## Kuruluş süreç kontrol listesi (taslak)

```text
VAKIF KURULUŞ KONTROL LİSTESİ
□ Amaç belirli, sürekli ve hukuka/ahlaka uygun mu? (TMK m.101)
□ Özgülenen mal/hak amacı gerçekleştirmeye yeterli mi? (yeterli mal varlığı)
□ Resmi vakıf senedi içeriği hazır mı? (amaç, mal varlığı, yönetim, denetim, senet değişikliği usulü)
□ Senet noterde resmi senet olarak düzenlenecek mi / ölüme bağlı tasarrufla mı?
□ Yerleşim yeri mahkemesinde tescil davası/başvurusu planlandı mı?
□ Vakıflar Genel Müdürlüğü'ne tescil ve sicile kayıt süreci not edildi mi?
□ Resmi Gazete ilanı boyutu işaretlendi mi?
□ Vergi muafiyeti hedefleniyorsa ayrı başvuru koşulları not edildi mi?
□ Tüm mahkeme/noter adımları için sorumlu hukukçu atandı mı?
```

> Vakıf kuruluşu resmi senet + mahkeme tescili ister. Senet içeriği, mal varlığının yeterliliği ve tescil usulü için TMK m.101-117 ve Vakıflar mevzuatını doğrula; bu adımlar avukat/noter/mahkeme boyutuyla yürütülür.

## Mevzuat referansları

- **Vakıf tanımı:** TMK m.101 — gerçek/tüzel kişilerin yeterli mal ve hakları belirli ve sürekli bir amaca özgülemesi; vakfın üyesi olmaz.
- **Kurma iradesi:** TMK m.102 — resmî senetle veya ölüme bağlı tasarrufla.
- **Senet içeriği:** TMK m.107 — amaç + özgülenen mal ve haklar.
- **Yönetim organı:** TMK m.109 — zorunlu.
- **Denetim (VGM) ve haklı sebeple değişiklik:** TMK m.111-112.
- **Amacın değiştirilmesi / sona erme:** TMK m.116.
- Tescil ve VGM süreçleri ayrıca **Vakıflar Kanunu (5737)** kapsamındadır; ilgili madde numaraları bu plugin'de doğrulanmadı — kullanılacaksa teyit et.

## Senet iskeleti (referans başlıklar)

1. Vakfın adı ve merkezi
2. Amaç ve bu amaca özgülenen mal ve haklar
3. Vakfın organları, yönetim ve temsil
4. Denetim ve hesap düzeni
5. Vakıf senedinin değiştirilmesi usulü
6. Vakfın sona ermesi ve mal varlığının akıbeti

## Kapı

Çıktının başında: "Bu bir taslak iskelettir. Vakıf senedinin resmi düzenlenmesi, mal varlığının yeterliliği ve mahkeme tescili sorumlu avukat/noter tarafından yürütülmelidir."

## Bu skill ne yapmaz

- Resmi senet düzenlemez, noter/mahkeme işlemi yapmaz.
- Mal varlığının "yeterli" olduğuna kesin hüküm vermez.
- Vergi muafiyeti koşullarını uzman kontrolü olmadan kesinleştirmez.
