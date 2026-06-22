# legal — tüm app'lerin yasal sayfaları

Tek bir GitHub Pages sitesi; her uygulamanın gizlilik politikası burada barınır.
Ücretsiz, sürüm kontrollü, sonsuz ölçeklenir. App Store, app içi gizlilik linki
için **gerçek ve erişilebilir bir URL** ister — bu repo onu sağlar.

## Yapı
```
legal/
  index.html                      # landing (app listesi)
  template/privacy-template.html  # yeni app için şablon
  habitora/privacy/index.html     # → /legal/habitora/privacy/
```

## Canlı URL kalıbı
`https://<github-kullanıcı-adı>.github.io/legal/<app>/privacy/`

Örn. Habitora: `https://<kullanıcı>.github.io/legal/habitora/privacy/`

## Yeni app eklemek (1 dakika)
1. `cp template/privacy-template.html <app>/privacy/index.html`
2. `{{APP_NAME}}`, `{{LAST_UPDATED}}`, `{{CONTACT_EMAIL}}` yerlerini doldur; veri
   bölümünü app'in App Store "App Privacy" beyanıyla **birebir** eşle.
3. `index.html`'e bir satır ekle, commit & push. URL anında canlı olur.

## İlk yayınlama
```
gh repo create legal --public --source=. --remote=origin --push
gh api -X POST repos/<kullanıcı>/legal/pages -f source.branch=main -f source.path=/
```
(veya repo → Settings → Pages → Branch: main /root). Birkaç dakikada yayında olur.
