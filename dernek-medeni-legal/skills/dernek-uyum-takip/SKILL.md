---
name: dernek-uyum-takip
description: >
  Derneğin/vakfın yıllık uyum yükümlülüklerini izleyen takip tablosu kurar ve
  günceller: beyanname, defter onayları, olağan genel kurul dönemi, denetim,
  bildirimler (taşınmaz, yardım, organ değişikliği). YAML tracker üretir ve
  yaklaşan/eksik yükümlülükleri raporlar. Süreler resmi kaynaktan doğrulanır.
argument-hint: "[durum raporu | yeni yükümlülük ekle]"
---

# /dernek-uyum-takip

## İş akışı

1. Profili oku. Tracker dosyası:
   `~/.claude/plugins/config/claude-for-legal/dernek-medeni-legal/uyum-tracker.yaml`
2. Tracker yoksa kullanıcının yükümlülüklerini sorarak oluştur. Varsa oku, güncelle ve durum raporu üret.
3. Yaklaşan ve eksik (gecikmiş) yükümlülükleri öne çıkar.

## Takip edilen yükümlülük kategorileri

- **Yıllık beyanname** — Dernek YK başkanları **her takvim yılının ilk dört ayı içinde (≈ Nisan sonu)** bir önceki yıla ait **Dernek Beyannamesini (EK-21)** mülkî idare amirliğine verir *(5253 m.19; Dernekler Yönetmeliği m.83)*. Şubeler örneğini bağlı derneğe de verir; temsilcilikler ayrı beyanname vermez.
- **Olağan genel kurul** — tüzükte belirtilen dönem; mevzuat azami dönem öngörür (tüzük daha sık öngörebilir). Sonrası **30 gün** içinde organ bildirimi *(5253 m.23)*.
- **Üyelik bildirimleri** — üyeliğe kabul/sona erme **45 gün** içinde dernekler birimine *(5253 m.23)*.
- **Defter tasdiki** — defterler **kullanmadan önce** il müdürlüğüne veya notere tasdik ettirilir; sayfalar bitene kadar kullanılır, ara tasdik yok. **Yevmiye Defteri her yıl** (önceki yılın son ayında) yeniden tasdik; **Büyük Defter tasdiki zorunlu değil** *(Yönetmelik m.36)*.
- **Defter esası kontrolü** — işletme hesabı esası geneldir; kamu yararına dernekler ve **yıllık brüt geliri 1.500.000 TL'yi aşan** dernekler bilanço esasına geçer *(Yönetmelik m.31 — güncel hadleri teyit et)*.
- **Denetim** — iç denetim esastır *(5253 m.9)*; idari denetim risk değerlendirmesine göre üç yılı geçmeyecek şekilde yapılabilir *(5253 m.19)*.
- **Olaya bağlı bildirimler** — taşınmaz edinimi: tapu tescilinden **1 ay** içinde *(5253 m.22)*; yurt dışı yardım: önceden bildirim *(m.21)*; temsilcilik/organ/adres değişikliği *(m.23-24)*.
- **Mali uyum** — gelir alındı belgesi ile tahsil (banka dekontu geçerli), ayni bağış EK-15 *(Yönetmelik m.38)*; vergi/SGK boyutu (varsa iktisadi işletme).

## Tutulacak defterler (Yönetmelik m.32)

```text
İşletme hesabı esası:
  □ Karar Defteri
  □ Üye Kayıt Defteri
  □ Evrak Kayıt Defteri
  □ İşletme Hesabı Defteri

Bilanço esası:
  □ Karar Defteri
  □ Üye Kayıt Defteri
  □ Evrak Kayıt Defteri
  □ Yevmiye Defteri
  □ Büyük Defter
```

Hesap dönemi takvim yılıdır (1 Ocak – 31 Aralık) *(Yönetmelik m.35)*; kayıt ve defterler Türkçe tutulur *(m.33; 5253 m.31)*.

> Gün sayıları ve hadler 5253 + Dernekler Yönetmeliği (mevzuat no 8038) metninden alınmıştır `[resmi kaynak]`. Parasal had ve form numaraları değişebilir — her dönemde güncel mevzuatı teyit et; değişmişse `verify` durumunda bırak, varsayımla `done` yapma. Ayrıntı: `references/mevzuat-haritasi.md`.

## Tracker şeması (YAML, english_snake_case)

```yaml
entity:
  legal_name: ""
  type: "dernek"        # dernek | vakif
  registry_no: ""
obligations:
  - key: "annual_declaration"
    label: "Yıllık beyanname"
    period: "yearly"
    due_date: ""        # 5253 m.19: Nisan ayı sonu — yıla göre teyit et
    legal_basis: "5253 m.19"
    status: "verify"    # not_started | in_progress | done | verify | overdue
    notes: ""
  - key: "ordinary_general_assembly"
    label: "Olağan genel kurul"
    period: ""          # tüzük dönemi
    last_done: ""
    next_due: ""
    status: "verify"
  - key: "book_certification"
    label: "Defter tasdiki"
    period: "as_needed"   # Yevmiye Defteri yıllık; diğerleri sayfa bitince
    legal_basis: "Dernekler Yönetmeliği m.36"
    due_date: ""
    status: "verify"
    notes: "Yevmiye Defteri her yıl yeniden tasdik; Büyük Defter tasdiki zorunlu değil"
  - key: "book_basis"
    label: "Defter esası"
    value: ""             # isletme_hesabi | bilanco
    legal_basis: "Dernekler Yönetmeliği m.31"
    status: "verify"
    notes: "Kamu yararına dernek veya yıllık brüt gelir 1.500.000 TL üstü ise bilanço esası"
  - key: "annual_general_assembly_notice"
    label: "Genel kurul sonuç bildirimi"
    period: "after_assembly"
    legal_basis: "5253 m.23"
    due_date: ""          # genel kurulu izleyen 30 gün
    status: "verify"
```

## Durum raporu (kullanıcıya, Türkçe)

```text
DERNEK/VAKIF UYUM DURUMU — [tarih]

Gecikmiş / acil:
- [yükümlülük] — son tarih [ ] — durum [overdue]  ⚠️ doğrula

Yaklaşan:
- [yükümlülük] — hedef [ ] — durum [ ]

Doğrulanması gereken süreler:
- [...]  (resmi kaynak kontrolü gerekli)
```

## Bu skill ne yapmaz

- Beyanname/bildirimi sizin yerinize vermez.
- Süreleri resmi kaynak çekmeden kesinleştirmez; "verify" durumunu keyfi "done" yapmaz.
- Mali/vergi yükümlülüğünü uzman kontrolü olmadan tamamlanmış saymaz.
