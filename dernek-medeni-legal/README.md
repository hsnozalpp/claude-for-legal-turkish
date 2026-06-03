# dernek-medeni-legal

Türk **dernekler hukuku**, **vakıflar** ve **Medeni Kanun kişiler hukuku** için taslak ve araştırma desteği. `claude-for-legal-turkish` marketplace'inin bir parçasıdır ve aynı plugin/skill iskeletini kullanır.

> **Uyarı:** Bu plugin hukuki danışmanlık vermez. Her çıktı bir taslak, araştırma notu veya karar desteğidir ve avukat/hukukçu incelemesine tabidir. Mevzuat, içtihat, süreler, bildirimler, imza ve resmi kaynak kontrolleri her somut dosya için ayrıca doğrulanmalıdır.

## Kapsam

- **Dernekler hukuku** — Dernekler Kanunu (5253), Dernekler Yönetmeliği, TMK m.56-100
- **Vakıflar** — TMK m.101-117, Vakıflar Kanunu (5737)
- **Kişiler hukuku** — TMK Birinci Kitap (m.8-117): gerçek/tüzel kişi, ehliyet, kişilik hakları, ad, vesayet

## Kurulum

Marketplace eklendikten sonra:

```
/plugin install dernek-medeni-legal
```

İlk iş olarak profili kurun:

```
/dernek-medeni-legal:cold-start-interview
```

## Skill'ler

| Komut | İşlev |
|---|---|
| `/dernek-medeni-legal:cold-start-interview` | Profil kurulumu (diğer skill'ler buna bağımlıdır) |
| `/dernek-medeni-legal:dernek-kurulus` | Dernek kuruluşu kontrol listesi + tüzük iskeleti |
| `/dernek-medeni-legal:tuzuk-review` | Tüzük / vakıf senedi madde madde inceleme |
| `/dernek-medeni-legal:genel-kurul` | Genel kurul çağrı, gündem, karar tutanağı taslakları |
| `/dernek-medeni-legal:yonetim-kurulu-karar` | Yönetim kurulu / vakıf yönetim organı karar taslağı |
| `/dernek-medeni-legal:dernek-uyum-takip` | Beyanname, genel kurul, defter, bildirim uyum takibi |
| `/dernek-medeni-legal:vakif-kurulus` | Vakıf kuruluşu senet iskeleti + tescil süreç listesi |
| `/dernek-medeni-legal:kisiler-hukuku-research` | TMK kişiler hukuku araştırma notu (Yargı MCP içtihat) |
| `/dernek-medeni-legal:customize` | Çıktı/davranış ayarları |

## MCP kaynakları

- **Yargı MCP** — Yargıtay, Danıştay, AYM ve diğer Türk hukuk kaynaklarına filtreli erişim (içtihat araştırması)
- **Google Drive / Box** — tüzük, karar defteri, beyanname, üye kayıtları (KVKK: üye/bağışçı listeleri kişisel veridir)

## Mevzuat referansları

Skill'ler somut madde numaralarına atıf yapar (örn. beyanname 5253 m.19 + Dernekler Yönetmeliği m.83 / EK-21 / Nisan sonu, defterler Yönetmelik m.32, tasdik m.36, organ bildirimi 5253 m.23 / 30 gün, taşınmaz m.22 / 1 ay, dernek tanımı TMK m.56, yön. kurulu TMK m.84). Tam tablo: [`references/mevzuat-haritasi.md`](references/mevzuat-haritasi.md) — TMK (4721), Dernekler Kanunu (5253) ve Dernekler Yönetmeliği (8038) defter/beyanname ayrıntılarını içerir. Numaralar `mevzuat.gov.tr` resmi metinlerinden doğrulanmıştır; parasal hadler ve formlar değişebileceği için her dosyada güncel hâl teyit edilmelidir.

## Güvenlik tasarımı

Her skill: profil kontrolü → reviewer note → kaynak etiketleme (`[resmi kaynak]` / `[içtihat - Yargı MCP]` / `[model bilgisi - doğrula]`) → hukukçu kontrolü kapısı. Süreler ve mevzuat eşikleri resmi kaynak çekilmeden kesinleştirilmez.
