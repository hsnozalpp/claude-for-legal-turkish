---
name: tuzuk-review
description: >
  Mevcut bir dernek tüzüğünü veya vakıf senedini madde madde inceler; zorunlu
  unsurların eksikliğini, iç tutarsızlıkları, mevzuata aykırı olabilecek
  hükümleri ve riskli/boşluk bırakan maddeleri işaretler. Çıktı hukukçu
  incelemesine tabi bir not + madde tablosudur.
argument-hint: "[tüzük/senet dosyası veya metin]"
---

# /tuzuk-review

## İş akışı

1. Profili oku. Tüzük/senet metnini kullanıcıdan al (dosya, yapıştırılan metin veya bağlı arşivden).
2. Metni gerçekten oku; okumadığın bölümü "incelendi" sayma. Okuma kapsamını reviewer note'ta belirt.
3. Madde madde analiz et ve aşağıdaki tabloyu üret.

## Reviewer note (zorunlu)

```text
Reviewer note
- Kaynaklar: [kullanıcı sağladı / belge kaynağı]
- Okuma kapsamı: [tüm tüzük / madde X-Y]
- Doğrulanması gerekenler: Dernekler Kanunu (5253), Dernekler Yönetmeliği, TMK m.56-100; vakıfsa TMK m.101-117 ve Vakıflar Kanunu (5737)
- Aksiyon öncesi: genel kurul onayı / sicil tescili / idare bildirimi
```

## Zorunlu unsur kontrolü

Derneklerde **Dernekler Kanunu m.4**'teki (a-l) zorunlu hususların hepsini denetle: ad/merkez *(m.4/a)*, amaç ve faaliyet alanı *(m.4/b)*, üyelik *(m.4/c)*, genel kurul toplanma/çağrı *(m.4/d)* ve yetki/oy/karar usulü *(m.4/e)*, yönetim ve denetim kurulu oluşum/görev/sayı *(m.4/f)*, şube *(m.4/g)*, aidat *(m.4/h)*, borçlanma *(m.4/ı)*, iç denetim *(m.4/j)*, tüzük değişikliği *(m.4/k)*, fesih/tasfiye *(m.4/l)*.

Mevzuata uygunluk anahtarları:
- Yönetim kurulu **en az 5 asıl + 5 yedek** (TMK m.84); denetim kurulu **en az 3 asıl + 3 yedek** (TMK m.86). Tüzük bunların altında sayı öngörüyorsa bayrakla.
- Üyelikten çıkarmada son karar genel kurulda (TMK m.80); menfaat çatışması (TMK m.82).
- Ad, 5253 m.28'deki izne/yasağa tabi ibareleri içeriyorsa bayrakla.
- Fesih ve tasfiye hükmü TMK m.87-89 ile uyumlu mu?

Vakıflarda *(TMK m.101 vd.)*: amaç ve özgülenen mal/hak *(m.107)*, yönetim organı *(m.109 — zorunlu)*, senet değişikliği/denetim *(m.111-112)*, sona erme *(m.116)*.

## Çıktı: madde inceleme tablosu

| Madde | Konu | Bulgu | Risk | Öneri (taslak) |
|---|---|---|---|---|
| m.X | [konu] | [eksik / belirsiz / mevzuata aykırı olabilir / tutarsız / iyi] | [yüksek/orta/düşük] | [düzeltme önerisi] |

## Bayrak kategorileri

- **Eksik zorunlu unsur** — yönetmeliğin aradığı bir başlık hiç yok.
- **Mevzuata aykırı olabilir** — nisap, organ yapısı veya yasak hüküm şüphesi → hukukçu kontrolü.
- **İç tutarsızlık** — maddeler birbiriyle çelişiyor (örn. farklı genel kurul nisapları).
- **Boşluk/risk** — uygulamada uyuşmazlık doğurabilecek belirsizlik (örn. çıkarılma usulü, fesih sonrası mal varlığı).
- **Güncellik** — eski mevzuata atıf veya değişmiş eşik/süre şüphesi.

## Kapı

Tüzük değişikliği genel kurul kararı + nisap + (gerekiyorsa) idare bildirimi/tescil ister. Çıktının başında: "Bu inceleme bir taslak nottur; değişiklik metni ve onay usulü sorumlu hukukçu tarafından kesinleştirilmelidir."

## Bu skill ne yapmaz

- Tüzüğün hukuken geçerli olduğuna kesin hüküm vermez.
- Değişikliği genel kurul onayı yerine geçecek şekilde "yürürlüğe koymaz".
- Mevzuat eşik/sürelerini resmi kaynak çekmeden kesinleştirmez.
