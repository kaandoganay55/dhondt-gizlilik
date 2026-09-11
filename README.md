# D'Hondt Simülatörü — Gizlilik Politikası

Bu depo tek bir iş yapar: **D'Hondt Simülatörü mobil uygulamasının gizlilik
politikası ve KVKK aydınlatma metnini** herkese açık bir adreste yayınlar.
App Store ve Google Play başvurularında "Privacy Policy URL" alanı zorunlu ve
o alana bu deponun GitHub Pages adresi yazılır.

Uygulamanın kaynak kodu burada değil, ayrı (private) bir depoda.

## Neden ayrı bir depo

Uygulama deposu private; GitHub, private depolardan Pages yayınlamak için ücretli
plan istiyor. Metnin kendisi zaten kamuya açık olmak üzere yazıldığı için
yalnızca onu taşıyan bu depo public tutuluyor.

## İçerik nasıl güncellenir

`index.html` **elle düzenlenmez** — üretilen bir dosyadır. Tek kaynağı uygulama
deposundaki `src/content/privacy.ts`. Metin değişince:

```bash
# uygulama deposunda
npm run privacy:page          # docs/index.html'i yeniden üretir

# sonra buraya kopyala
cp docs/index.html ../dhondt-gizlilik/index.html
git -C ../dhondt-gizlilik commit -am "gizlilik metni güncellendi" && git -C ../dhondt-gizlilik push
```

## Dikkat

Bu sayfa **sürekli erişilebilir kalmalı**. Mağazalar yayından sonra da bu adresi
kontrol ediyor; depo silinir ya da private'a çevrilirse sayfa ölür ve uygulama
mağazadan kaldırılabilir.
