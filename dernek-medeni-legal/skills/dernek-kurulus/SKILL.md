---
name: dernek-kurulus
description: >
  Dernek kuruluşu için taslak ve kontrol listesi üretir: kurucu listesi, tüzük
  taslağı iskeleti, kuruluş bildirimi ve ilk genel kurula kadar yapılması
  gerekenler. Dernekler Kanunu (5253) ve Dernekler Yönetmeliği esas alınır;
  çıktı hukukçu incelemesine tabi taslaktır.
argument-hint: "[derneğin amacı / faaliyet alanı]"
---

# /dernek-kurulus

## İş akışı

1. `~/.claude/plugins/config/claude-for-legal/dernek-medeni-legal/CLAUDE.md` profilini oku. `[PLACEHOLDER]` doluysa `/dernek-medeni-legal:cold-start-interview` çalıştırılmasını iste.
2. Amaç/faaliyet alanını, merkez ilini ve kurucu sayısını öğren.
3. Aşağıdaki çıktıları üret: kuruluş kontrol listesi + tüzük iskeleti referansı + bildirim/sicil adımları.

## Intake

- Derneğin amacı tek cümleyle nedir?
- Faaliyet alanı (kültür, spor, yardım, mesleki vb.)?
- Merkez il/ilçe?
- Kurucu sayısı ve niteliği (gerçek/tüzel kişi, fiil ehliyeti)?
- Yurt dışı bağlantı, yardım alma/verme veya yabancı kurucu var mı? (Ek izin boyutu)
- İktisadi işletme veya yardım toplama planı var mı?

## Kuruluş kontrol listesi (taslak)

```text
DERNEK KURULUŞ KONTROL LİSTESİ
□ En az kurucu sayısı sağlandı mı? (gerçek/tüzel kişi ehliyeti kontrol edilmeli)
□ Dernek adı mevzuata ve mevcut kayıtlara uygun mu? (yasak/karıştırıcı ad kontrolü)
□ Amaç ve faaliyet alanı tüzükte açık ve hukuka uygun mu?
□ Tüzük, Dernekler Yönetmeliği'ndeki zorunlu unsurları içeriyor mu? (→ /dernek-medeni-legal:tuzuk-review)
□ Yerleşim yeri (merkez) ve geçici yönetim kurulu belirlendi mi?
□ Kuruluş bildirimi ve ekleri hazır mı? (tüzük + kurucu bilgileri)
□ İlgili mülki idare amirliğine (valilik/kaymakamlık) bildirim yapılacak mı?
□ İlk olağan genel kurul için yasal süre takvime alındı mı?
□ Tutulacak defterler ve onay (noter/DERBİS) planlandı mı?
□ Vergi dairesi / potansiyel vergi no işlemleri not edildi mi?
□ Yurt dışı/yabancı unsuru varsa ek izin gerekliliği işaretlendi mi?
```

> Süreler, kurucu sayısı ve bildirim detayları için güncel Dernekler Kanunu ve Yönetmeliği'ni doğrula. Yargı MCP veya resmi kaynak çekmeden kesin gün/sayı yazma; çektiğinde `[resmi kaynak]` etiketle.

## Tüzük iskeleti (zorunlu maddeler — referans)

Dernekler Kanunu **m.4**'e göre tüzükte bulunması zorunlu hususlar (somut içerik tüzük-review ile ayrıntılandırılır):

1. Derneğin adı ve merkezi *(5253 m.4/a; yasak/izne tabi adlar: m.28)*
2. Amaç ve bu amacı gerçekleştirmek için sürdürülecek çalışma konuları/biçimleri ve faaliyet alanı *(m.4/b)*
3. Üye olma, üyelikten çıkma ve çıkarılma şart ve şekilleri *(m.4/c; TMK m.64-66)*
4. Genel kurulun toplanma şekli ve zamanı *(m.4/d; TMK m.73-77)*
5. Genel kurulun görev ve yetkileri, oy kullanma ve karar alma usul ve şekilleri *(m.4/e)*
6. Yönetim ve denetim kurullarının görev, yetki ve oluşumu, asıl/yedek üye sayısı *(m.4/f; TMK m.84 yön. kurulu en az 5+5, m.86 denetim en az 3+3)*
7. Şube hükümleri *(m.4/g)*; giriş/yıllık aidat *(m.4/h)*; borçlanma usulleri *(m.4/ı)*; iç denetim *(m.4/j; 5253 m.9)*
8. Tüzüğün ne şekilde değiştirileceği *(m.4/k)*
9. Derneğin feshi halinde mal varlığının tasfiye şekli *(m.4/l; TMK m.87-89)*

## Mevzuat referansları

- **Dernek tanımı / kurucu sayısı:** TMK m.56 — en az 7 gerçek/tüzel kişi, kazanç paylaşma dışı amaç. Kurma hakkı: TMK m.57, 5253 m.3 (önceden izinsiz).
- **Tüzel kişiliğin kazanılması / inceleme:** TMK m.59-60.
- **Zorunlu organlar:** TMK m.72.
- **Yabancı/uluslararası unsur:** 5253 m.5 (yabancı dernek için Dışişleri görüşü + İçişleri Bakanlığı izni).
- **Kuruluş incelemesi:** Kuruluş bildirimi ve tüzük, **alındı belgesi tarihinden itibaren 60 gün** içinde mülkî idare amirliğince incelenir *(Dernekler Yönetmeliği m.5 vd.)*. Bu sürede eksiklik/aykırılık bildirilebilir.
- **İlk defterler:** Kuruluşta tutulacak defterler kullanmadan önce il müdürlüğü/notere tasdik ettirilir *(Yönetmelik m.32, m.36)* — bkz. `/dernek-medeni-legal:dernek-uyum-takip`.
- Ayrıntı için: `references/mevzuat-haritasi.md`.

## Bu skill ne yapmaz

- Bağlayıcı kuruluş başvurusu yapmaz; sicile/idareye gönderim yapmaz.
- Kurucu ehliyeti, ad uygunluğu ve süreleri kesinleştirmez — bunlar hukukçu/idare kontrolüdür.
- Yabancı unsur, izin ve vergi boyutunu uzman kontrolü olmadan tamamlanmış saymaz.
