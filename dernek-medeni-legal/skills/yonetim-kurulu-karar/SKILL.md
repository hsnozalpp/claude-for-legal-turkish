---
name: yonetim-kurulu-karar
description: >
  Dernek yönetim kurulu (veya vakıf yönetim organı) karar taslağı üretir: görev
  dağılımı, üye kabul/çıkarma, harcama/yetki, temsil, banka/imza, taşınmaz,
  yardım toplama gibi konularda karar metni + nisap ve defter kontrol listesi.
  Tüzük esas alınır; çıktı hukukçu incelemesine tabidir.
argument-hint: "[karar konusu]"
---

# /yonetim-kurulu-karar

## İş akışı

1. Profili oku; tüzükteki yönetim kurulu yapısı, toplantı/karar nisabı ve temsil yetkisini al.
2. Karar konusunu sınıflandır: rutin / inceleme gerektiren / hukukçu kontrolü zorunlu.
3. Karar defteri formatına uygun taslak + nisap/defter kontrol listesi üret.

## Intake

- Karar organı: dernek yönetim kurulu mu, vakıf yönetim organı mı?
- Karar konusu tek cümleyle nedir?
- Dayanak: tüzük maddesi, genel kurul kararı, sözleşme, harcama belgesi?
- Toplantıya katılan üye sayısı ve nisap?
- İmza/temsil yetkisi, banka, taşınmaz veya bildirim boyutu var mı?

## Sınıflandırma

**Rutin adaylar:** görev dağılımı, rutin üye kabulü, olağan harcama onayı, banka talimatı güncelleme, etkinlik kararı.

**İnceleme bayrağı:** taşınmaz edinimi/satışı *(5253 m.22 — genel kurul yetkisi gerekir; tapu tescilinden itibaren 1 ay içinde bildirim)*, yurt dışına yardım *(5253 m.21 — önceden bildirim)*, üst kuruluş/platform üyeliği *(5253 m.25)*, iktisadi işletme kurma, üyelikten çıkarma *(TMK m.80 — son karar genel kurulda)*, borçlanma/kefalet, tüzük değişikliği önerisi, fesih/tasfiye hazırlığı *(TMK m.87-89)*. Bu konularda taslak başında reviewer note ile bayrağı göster ve hukukçu kontrolü iste.

## Mevzuat referansları

- **Menfaat çatışması:** TMK m.82 — üye, dernekle kendisi/eşi/üstsoyu/altsoyu arasındaki işlem veya uyuşmazlık kararında oy kullanamaz; ilgili üyeyi oylamadan çıkar.
- **Taşınmaz:** 5253 m.22 — yalnızca genel kurulun yetki vermesi üzerine yönetim kurulu kararıyla alınır/satılır; edinim tapu tescilinden itibaren **1 ay** içinde mülkî idare amirliğine bildirilir.
- **Gelir-gider:** 5253 m.11 — gelir alındı belgesi, gider harcama belgesi ile.
- **Bildirim:** organ/yerleşim yeri değişikliği 5253 m.23 usulüne tabidir.

## Karar taslağı iskeleti

```text
[DERNEK / VAKIF ADI]
YÖNETİM KURULU KARARI

Karar No: [ ]   Tarih: [ ]   Toplantıya katılanlar: [ ] / [ ]

Reviewer note:
- Organ ve nisap: [ ]
- Dayanak belgeler: [ ]
- Kontrol: tüzük maddesi, temsil yetkisi, karar defteri, idare/sicil bildirimi

KARAR
1. [Karar açık ve ölçülebilir yazılır; belge varsa ad/tarih/taraf belirtilir.]
2. [Yetkilendirme: kim, neyi imzalamaya/yürütmeye yetkili.]
3. [Bildirim/defter/sicil adımı için yetki.]

İmzalar: [Yönetim kurulu üyeleri]
```

## Nisap ve defter kontrol listesi

```text
□ Toplantı/karar nisabı tüzüğe uygun mu?
□ Karar konusu yönetim kurulu yetkisinde mi, yoksa genel kurul kararı mı gerekir?
□ Menfaat çatışması / ilgili üye oylamaya katılmamalı mı?
□ Karar defterine doğru formatla işlenecek mi?
□ İmza/temsil yetkisi tüzük + karar ile uyumlu mu?
□ İdareye bildirim / DERBİS / sicil / VGM işlemi gerekiyor mu?
□ Taşınmaz, yurt dışı yardım, üst kuruluş üyeliği gibi özel izin/bildirim var mı?
```

## Bu skill ne yapmaz

- Kararın geçerliliğine kesin hüküm vermez.
- Genel kurul yetkisindeki konuyu yönetim kurulu kararıyla "geçerli" kılmaz.
- İdareye/sicile otomatik bildirim yapmaz.
