---
name: cold-start-interview
description: >
  Dernek/vakıf/kişiler hukuku profilini ilk kez kuran veya güncelleyen kurulum
  görüşmesi. Kullanıcının tüzel kişi türünü, organlarını, sicil/beyanname
  durumunu ve rolünü sorar; sonucu
  ~/.claude/plugins/config/claude-for-legal/dernek-medeni-legal/CLAUDE.md
  dosyasına yazar. Diğer tüm skill'ler bu profile bağımlıdır.
argument-hint: "[--redo | --module dernek|vakif|kisiler]"
---

# /cold-start-interview

Bu skill, plugin'in profilini kurar. Diğer skill'ler çalışmadan önce bu profil dolu olmalıdır.

## İş akışı

1. `~/.claude/plugins/config/claude-for-legal/dernek-medeni-legal/CLAUDE.md` dosyasının var olup olmadığına bak.
   - Yoksa, plugin kökündeki `CLAUDE.md` şablonunu temel al ve parent dizinleri oluştur.
   - Varsa ve `--redo` verilmediyse, eksik/`[PLACEHOLDER]` alanları tamamlamaya odaklan.
2. Aşağıdaki blokları sırayla sor. Her turda en fazla 2-3 soru sor; kullanıcıyı boğma.
3. Cevapları şablondaki ilgili `[PLACEHOLDER]` alanlarına yazıp dosyayı kaydet.
4. Hangi modüllerin aktif olduğunu `## Aktif modüller` altında işaretle.

## Sorulacaklar

### Blok 1 — Temel kimlik
- Bir dernek mi, vakıf mı, yoksa henüz kurulmamış bir yapı için mi çalışıyoruz?
- Adı, faaliyet alanı/amacı, merkezi (il/ilçe) nedir?
- Kütük/sicil no ve kuruluş tarihi var mı?

### Blok 2 — Kullanıcı rolü
- Avukat mısınız, hukuk müşaviri mi, yönetim kurulu üyesi/gönüllü mü, yoksa hukukçu olmayan bir kullanıcı mı?
- Sorumlu avukat veya hukukçu kim?

### Blok 3 — Organlar ve uyum (dernek)
- Yönetim kurulu ve denetim kurulu yapısı (asıl/yedek üye sayısı)?
- Son olağan genel kurul ne zaman yapıldı?
- Hangi defterler tutuluyor? İşletme hesabı mı, bilanço esası mı?
- Yıllık beyanname durumu nedir?

### Blok 4 — Vakıf (varsa)
- Vakıf senedi tescil edildi mi? Mütevelli heyeti/yönetim organı yapısı?
- VGM denetimi/beyanname durumu, vergi muafiyeti var mı?

### Blok 5 — Kişiler hukuku (varsa)
- Hangi kişiler hukuku konularıyla ilgileniyorsunuz (tüzel kişilik, ehliyet, kişilik hakları, vesayet, ad)?

### Blok 6 — Entegrasyonlar
- Belge arşivi (Drive/Box/klasör) var mı? DERBİS/vakıf sicili erişimi manuel mi?
- Yargı MCP içtihat araştırması için kullanılacak mı?

## Yazma kuralları

- Yalnızca config yolundaki dosyaya yaz; plugin kökündeki şablona ASLA kullanıcı verisi yazma.
- `[DATE]` alanını bugünün tarihiyle doldur.
- Aktif olmayan modülleri boş bırakabilirsin; ama hangi modüllerin aktif olduğunu açıkça işaretle.
- Bitince kısa bir özet ver ve hangi skill'lerin artık kullanılabilir olduğunu söyle.

## Bu skill ne yapmaz

- Hukuki görüş vermez; sadece profili kurar.
- Sicile/idareye otomatik kayıt yapmaz.
