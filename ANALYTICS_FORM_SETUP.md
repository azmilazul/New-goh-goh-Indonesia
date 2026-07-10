# goh-goh Website Analytics + Form Setup

File utama: `index.html`

## 1. GA4

Di `index.html`, cari:

```js
const SITE_INTEGRATIONS={
  ga4MeasurementId:"G-XXXXXXXXXX",
  formEndpoint:"",
  formProvider:"formspree"
};
```

Ganti `G-XXXXXXXXXX` dengan Measurement ID GA4 asli, contoh:

```js
ga4MeasurementId:"G-ABC123DEF4"
```

Event yang sudah dikirim ke GA4:
- `page_view`
- `view_item`
- `add_to_cart`
- `view_cart`
- `begin_checkout`
- `generate_lead`
- `select_language`
- `quiz_answer`
- `quiz_result`

## 2. Formspree

Buat form baru di Formspree, lalu ganti:

```js
formEndpoint:""
formProvider:"formspree"
```

Menjadi:

```js
formEndpoint:"https://formspree.io/f/FORM_ID_ANDA",
formProvider:"formspree"
```

## 3. Google Sheets

Jika memakai Google Apps Script yang menulis ke Google Sheets, ganti menjadi:

```js
formEndpoint:"https://script.google.com/macros/s/DEPLOYMENT_ID_ANDA/exec",
formProvider:"google-sheets"
```

Payload yang dikirim:
- `name`
- `email`
- `message`
- `source`
- `page`
- `submittedAt`

## 4. Catatan

Saat `formEndpoint` masih kosong, form tidak akan mengirim data dan akan menampilkan pesan konfigurasi.
