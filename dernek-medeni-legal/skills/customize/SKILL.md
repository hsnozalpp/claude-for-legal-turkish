---
name: customize
description: >
  Bu plugin'in çıktı biçimini, dil tercihlerini, takip tablosu alanlarını ve
  hatırlatma davranışını kullanıcının çalışma tarzına göre ayarlar. Değişiklikleri
  ~/.claude/plugins/config/claude-for-legal/dernek-medeni-legal/CLAUDE.md
  profiline yazar.
argument-hint: "[ayarlamak istediğin davranış]"
---

# /customize

## İş akışı

1. Config yolundaki `CLAUDE.md` profilini oku.
2. Kullanıcının ayarlamak istediği davranışı belirle:
   - Çıktı dili ve ton (resmi/sade)
   - Reviewer note ayrıntı düzeyi
   - Takip tablosu (uyum-tracker) ek alanları
   - Hangi konularda otomatik "hukukçu kontrolü" kapısı isteneceği
   - Varsayılan organ/şirket türü
3. İlgili bölümü profile yaz ve özetle.

## Kurallar

- Yalnızca config yolundaki profile yaz; plugin şablonuna yazma.
- Güvenlik kapılarını (hukukçu olmayan kullanıcı kapısı, büyük işlem kapısı) tamamen kaldırma; sadece eşiklerini ayarla.
- Yapısal veri standardını (`english_snake_case`) bozma.

## Bu skill ne yapmaz

- Hukuki içerik üretmez; yalnızca davranışı yapılandırır.
