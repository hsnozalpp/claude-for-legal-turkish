<!--
CONFIGURATION LOCATION

User-specific configuration for this plugin lives at:

  ~/.claude/plugins/config/claude-for-legal/dernek-medeni-legal/CLAUDE.md

Rules for every skill, command, and agent in this plugin:
1. READ configuration from that path. Not from this template.
2. If that file does not exist or still contains [PLACEHOLDER] markers, STOP before substantive work and ask the user to run `/dernek-medeni-legal:cold-start-interview`.
3. Setup and cold-start-interview WRITE to that path, creating parent directories as needed.
4. This file is the template shipped with the plugin. It may be replaced by plugin updates. Do not write user data here.

Shared facts live one level above this profile at:

  ~/.claude/plugins/config/claude-for-legal/company-profile.md
-->

# Dernek / Vakıf / Kişiler Hukuku Profili - Türk Hukuku
*Cold-start tarafından [DATE] tarihinde yazıldı. Aktif modüller: [Dernek | Vakıf | Kişiler Hukuku]*
*`[PLACEHOLDER]` görüyorsanız `/dernek-medeni-legal:cold-start-interview` çalıştırın.*

---

## Kuruluş profili

**Tüzel kişi adı:** [PLACEHOLDER]
**Tür:** [PLACEHOLDER - dernek / federasyon / konfederasyon / vakıf / dernek şubesi / temsilcilik / henüz kurulmadı]
**Faaliyet alanı / amaç:** [PLACEHOLDER]
**Kütük / sicil no:** [PLACEHOLDER - dernek kütük no / vakıf sicil no]
**Merkez (il/ilçe):** [PLACEHOLDER]
**İlgili idare:** [PLACEHOLDER - İl/İlçe Sivil Toplumla İlişkiler Müdürlüğü (eski Dernekler Müdürlüğü) / Vakıflar Genel Müdürlüğü bölge müdürlüğü]
**Kuruluş tarihi:** [PLACEHOLDER]
**Vergi dairesi / vergi no:** [PLACEHOLDER]
**Kamu yararına dernek / vergi muafiyetli vakıf statüsü:** [PLACEHOLDER - var / yok / başvuru aşamasında]
**Yurt dışı bağlantı / yardım / üyelik:** [PLACEHOLDER - yok / var (Bakanlık izni boyutu)]
**Yetkili organlar:** [PLACEHOLDER - genel kurul, yönetim kurulu, denetim kurulu / vakıf yönetim organı, mütevelli heyeti]
**Eskalasyon:** [PLACEHOLDER - sorumlu avukat / yönetim kurulu başkanı / dış danışman]

**Çalışma bağlamı:** [PLACEHOLDER - dernek/vakıf içi gönüllü-yönetici / hukuk müşaviri / avukat / hukuk bürosu / danışman]

---

## Kullanıcı rolü

**Rol:** [PLACEHOLDER - Avukat / hukuk müşaviri / yönetim kurulu üyesi / gönüllü / hukukçu olmayan kullanıcı]
**Sorumlu avukat veya hukukçu:** [PLACEHOLDER]

Skill'ler bu bölümü okuyarak çıktı dilini ve işlem kapılarını belirler. Hukukçu olmayan kullanıcılar için her çıktı "araştırma ve taslak" olarak verilir; imza, beyanname verme, sicile bildirim, tescil veya bağlayıcı işlem öncesinde avukat/hukukçu kontrolü istenir.

---

## Çıktı kuralları

Her tüzük taslağı, karar metni, beyanname kontrol notu, araştırma notu veya takip tablosu şu çerçeveyle üretilir:

```text
GİZLİ HUKUKİ ÇALIŞMA TASLAĞI - AVUKAT/HUKUKÇU İNCELEMESİNE TABİDİR
Bu çıktı hukuki görüş, imza onayı, sicil/beyanname talimatı veya resmi başvuru yerine geçmez.
```

Harici olarak imzalanacak, sicile/idareye verilecek, genel kurula sunulacak veya resmi makama gönderilecek metinlerde bu başlık nihai metnin içinde bırakılmaz. Başlık yalnızca hazırlık notları ve inceleme çıktıları içindir.

### Reviewer note

Her önemli çıktıdan önce tek bir inceleme notu ver:

```text
Reviewer note
- Kaynaklar: [okunan belgeler / resmi kaynak / kullanıcı beyanı / doğrulanamadı]
- Okuma kapsamı: [tamamı / seçili dosyalar / madde aralığı]
- Doğrulanması gerekenler: [Dernekler Kanunu (5253), Dernekler Yönetmeliği, Türk Medeni Kanunu (4721), Vakıflar Kanunu (5737) ve Yönetmeliği, tüzük/vakıf senedi, genel kurul/karar defteri, beyanname süreleri]
- Aksiyon öncesi: [imza / beyanname / sicil bildirimi / tescil / genel kurul / denetim için kontrol]
```

Kaynak etiketi gerçekten ne yapıldıysa onu gösterir:

- `[resmi kaynak]` yalnızca mevzuat, DERBİS, vakıf sicili, idare duyurusu veya benzeri resmi kayıt bu oturumda kontrol edildiyse.
- `[kullanıcı sağladı]` kullanıcı belgeyi, kaydı veya ekran çıktısını verdiyse.
- `[model bilgisi - doğrula]` herhangi bir kaynak çekilmeden hatırlanan genel bilgi için.
- `[içtihat - Yargı MCP]` Yargıtay/Danıştay/AYM kararı bu oturumda gerçekten çekildiyse.
- `[belge kaynağı]` tüzük, vakıf senedi, karar defteri, üye kaydı, beyanname, e-posta veya arşiv belgesi için.

Güncelliği önemli olan süre, eşik, mevzuat veya idari uygulama konusunda güncel resmi kaynak kontrol edilmeden kesin ifade kurma. Dernek/vakıf mevzuatı ve yönetmelik sık değişir; süreleri (örn. genel kurul, beyanname, bildirim süreleri) varsayımla yazma.

---

## Yapısal veri standardı

Tracker, YAML, JSON, CSV export şeması, alan adı ve otomasyon anahtarlarında canonical standart: ASCII `english_snake_case`.

- YAML/JSON anahtarları İngilizce `snake_case` yazılır: `legal_name`, `registry_no`, `due_date`, `meeting_type`.
- Kontrol edilen enum değerleri ASCII makine token'ı olarak yazılır: `not_started`, `in_progress`, `verify`, `done`.
- Kullanıcıya görünen raporlar, Markdown tabloları, karar taslakları ve durum özetleri Türkçe yazılır.
- Türk hukukuna özgü kavramlar insan-facing etiketlerde korunur: `dernek`, `tüzük`, `genel kurul`, `mütevelli heyeti`, `DERBİS`, `beyanname`, `TMK m.56`, `Vakıflar Genel Müdürlüğü`.

---

## Entegrasyonlar

| Entegrasyon / kaynak | Durum | Yoksa uygulanacak yöntem |
|---|---|---|
| Belge arşivi (Drive, Box, klasör) | [✓ / ✗] | Kullanıcı yerel klasör veya belge yükler |
| DERBİS / dernek sicili kaynağı | [✓ / ✗ / manuel] | Kullanıcı kayıt, link veya ekran çıktısı sağlar |
| Vakıf sicili / VGM kaydı | [✓ / ✗ / manuel] | Kullanıcı güncel kayıt veya belge sağlar |
| Yargı MCP (içtihat) | [✓ / ✗] | Araştırmada içtihat çekilemezse açıkça belirtilir |
| Üye / bağışçı kayıtları | [✓ / ✗ / manuel] | KVKK kapsamında dikkatle; kullanıcı sağlar |

Connector yapılandırması tek başına "bağlı" sayılmaz. Skill bir kaynağı kullandığını söyleyecekse ya kaynağı gerçekten okur ya da manuel/user-provided olarak etiketler.

---

## Aktif modüller

Yalnızca aktif modüller doldurulur. Kullanılmayan modüller config'te boş bırakılabilir.

---

## Dernek modülü

**Tüzük durumu:** [PLACEHOLDER - taslak / yürürlükte / değişiklik aşamasında / yok]
**Organlar:** [PLACEHOLDER - genel kurul, yönetim kurulu (asıl/yedek üye sayısı), denetim kurulu]
**Genel kurul periyodu:** [PLACEHOLDER - olağan genel kurul dönemi (tüzükte belirtilen, en geç 3 yıl)]
**Son olağan genel kurul:** [PLACEHOLDER - tarih veya yok]
**Tutulan defterler:** [PLACEHOLDER - üye kayıt, karar, evrak kayıt, işletme hesabı / bilanço, alındı belgesi kayıt, demirbaş]
**Beyanname yükümlülüğü:** [PLACEHOLDER - yıllık beyanname durumu / son verilen]
**Şube / temsilcilik:** [PLACEHOLDER]
**İktisadi işletme:** [PLACEHOLDER - var / yok]

### Dernek ilkeleri

- Her karar/tüzük taslağı önce tüzükteki özel hükmü, organı ve nisabı kontrol eder.
- Genel kurul çağrı usulü, toplantı/karar nisabı ve gündem bağlılığı tüzük + Dernekler Kanunu/Yönetmeliği'ne göre doğrulanmadan "geçerli" denmez.
- İl/İlçe müdürlüğüne bildirim, DERBİS girişi, beyanname süresi ve defter onayı ayrıca işaretlenir.
- Tüzük değişikliği, organ değişikliği, taşınmaz edinimi, yurt dışı yardım, platform/üst kuruluş üyeliği, fesih/tasfiye gibi konularda eskalasyon yapılır.

---

## Vakıf modülü

**Vakıf senedi durumu:** [PLACEHOLDER - taslak / tescil edildi / değişiklik aşamasında]
**Vakıf türü:** [PLACEHOLDER - yeni (TMK) vakfı / mazbut / mülhak / cemaat / esnaf vakfı]
**Yönetim organı / mütevelli heyeti:** [PLACEHOLDER]
**VGM denetimi / beyanname:** [PLACEHOLDER]
**Vergi muafiyeti:** [PLACEHOLDER - var / yok / başvuru]
**Mal varlığı / amaca özgülenen değer:** [PLACEHOLDER]

### Vakıf ilkeleri

- Vakıf kuruluşu TMK m.101 vd. uyarınca resmi senet + mahkeme tescili ister; bu süreç noter ve mahkeme boyutuyla hukukçu kontrolü gerektirir.
- Senet değişikliği, amaç/mal varlığı değişikliği mahkeme kararına tabidir; otomatik geçerli sayılmaz.
- VGM denetimi, beyanname ve şube/temsilcilik işlemleri ayrıca işaretlenir.

---

## Kişiler hukuku modülü

**Tipik konular:** [PLACEHOLDER - tüzel kişilik, ehliyet, kişilik hakları, ad, vesayet/kayyım, dernek-vakıf tüzel kişiliği]
**Bağlam:** [PLACEHOLDER - dernek/vakıf tüzel kişiliği odaklı / bireysel danışmanlık / akademik]

### Kişiler hukuku ilkeleri

- TMK Birinci Kitap (m.8-117) kapsamı: gerçek kişiler, ehliyet, kişilik hakları, kişisel durum sicili, tüzel kişiler (dernekler m.56-100, vakıflar m.101-117).
- Kişilik haklarının korunması, ad üzerindeki hak, hak ve fiil ehliyeti, vesayet ve kayyımlık konularında somut olay + güncel içtihat kontrolü esastır.
- Bu modül araştırma ve taslak üretir; dava, başvuru ve süreye bağlı işlemler avukat tarafından yürütülür.

---

## Hukukçu olmayan kullanıcı kapısı

Profilde kullanıcı hukukçu değilse, sonucu bağlayıcı olabilecek (sicile/idareye verilecek, genel kurula sunulacak, mahkemeye gidecek) metin üretmeden önce sorumlu avukat/hukukçu kontrolü iste. Üretilen her şey "taslak — hukukçu inceleyecek" çerçevesinde kalır.

---

*Tam kurulum için: `/dernek-medeni-legal:cold-start-interview --redo`*
*Modül eklemek için: `/dernek-medeni-legal:cold-start-interview --module [dernek | vakif | kisiler]`*
