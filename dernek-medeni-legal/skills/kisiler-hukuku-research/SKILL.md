---
name: kisiler-hukuku-research
description: >
  Türk Medeni Kanunu Birinci Kitap (kişiler hukuku, m.8-117) konularında
  araştırma notu üretir: gerçek/tüzel kişi, hak ve fiil ehliyeti, kişilik
  haklarının korunması, ad, vesayet/kayyımlık, dernek ve vakıf tüzel kişiliği.
  Yargı MCP üzerinden içtihat çeker. Çıktı araştırma notudur, hukuki görüş değil.
argument-hint: "[hukuki soru veya konu]"
---

# /kisiler-hukuku-research

## İş akışı

1. Profili oku. Soruyu netleştir: somut olay mı, soyut araştırma mı?
2. İlgili TMK maddelerini ve konuyu çerçevele (aşağıdaki harita).
3. Yargı MCP varsa ilgili içtihatı (Yargıtay/AYM/Danıştay) çek; çektiğini `[içtihat - Yargı MCP]`, çekemediğini açıkça belirt.
4. Yapılandırılmış araştırma notu üret.

## Kapsam haritası (TMK Birinci Kitap) — doğrulanmış madde anahtarları

- **Gerçek kişiler** — hak ehliyeti (m.8), fiil ehliyeti (m.9), erginlik 18 yaş (m.11), ergin kılınma (m.12), ayırt etme gücü (m.13), fiil ehliyetsizliği/sınırlı ehliyetsizler (m.14-16), kişiliğin başlangıcı ve sonu — sağ ve tam doğum (m.28), gaiplik (m.32-35).
- **Kişilik hakları** — vazgeçme/aşırı sınırlama yasağı (m.23), saldırıya karşı hâkimden koruma (m.24), davalar: önleme/durdurma/tespit + maddi-manevi tazminat (m.25), ad üzerindeki hakkın korunması (m.26), adın değiştirilmesi — haklı sebep/hâkim (m.27).
- **Kişisel durum** — yerleşim yeri (m.19-21), kişisel durum sicili (m.39-46).
- **Tüzel kişiler — genel** — m.47-52 (tanım, ehliyet, organlar, yerleşim yeri, sona erme).
- **Tüzel kişiler — dernekler** — m.56-100: tanım/en az 7 kişi (m.56), kurma hakkı (m.57), tüzel kişilik (m.59-60), üyelik (m.64-66, m.80, m.82), organlar (m.72, yön. kurulu m.84, denetim m.86), sona erme (m.87-89).
- **Tüzel kişiler — vakıflar** — m.101-117: tanım (m.101), kurma iradesi (m.102), senet (m.107), yönetim (m.109), denetim/değişiklik (m.111-112), sona erme (m.116).
- **Vesayet/kayyımlık** — TMK İkinci Kitap bağlantısı; kişiler hukuku bağlamında sınırlı.

> Tam tablo: `references/mevzuat-haritasi.md`. Madde numaraları resmi metinden doğrulanmıştır; yine de güncel hâli teyit et ve içtihatı Yargı MCP'den çek.

## Araştırma notu formatı

```text
KİŞİLER HUKUKU ARAŞTIRMA NOTU — [konu]

Reviewer note
- Kaynaklar: [model bilgisi - doğrula / içtihat - Yargı MCP / kullanıcı sağladı]
- Kapsam: [TMK m. ...]
- Sınır: Bu bir araştırma notudur; somut olaya uygulama ve dava stratejisi avukat işidir.

1. Soru / olay özeti
2. İlgili mevzuat (TMK maddeleri + varsa özel kanun)
3. Hukuki çerçeve / kurallar
4. İçtihat (varsa) — [içtihat - Yargı MCP] etiketli; daire, esas/karar no, özet
5. Değerlendirme / olası yaklaşımlar (kesin sonuç değil)
6. Açık sorular ve doğrulanması gerekenler
```

## Kurallar

- Güncel mevzuat ve içtihat çekilmeden kesin sonuç ("kazanırsınız", "geçerlidir") yazma.
- İçtihatı uydurma; Yargı MCP'den gerçekten gelmeyen karar numarası verme.
- Süreye bağlı (hak düşürücü/zamanaşımı) konularda mutlaka "süreyi avukatla doğrulayın" uyarısı koy.

## Bu skill ne yapmaz

- Hukuki görüş veya dava tahmini vermez.
- Avukat yerine somut dava/başvuru kararı almaz.
- İçtihat ve mevzuatı resmi kaynak olmadan kesinleştirmez.
