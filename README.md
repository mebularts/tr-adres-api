# tr-adres-api

Statik JSON adres verisi (il → ilçe → mahalle → yol). GitHub Pages veya herhangi bir statik sunucudan servis edilebilir.

Varsayılan yayın adresi: `https://mebularts.github.io/tr-adres-api` (kaynak klasör: `docs/`).

## Endpointler (v1)
- `/v1/meta.json`
- `/v1/iller.json`
- `/v1/ilceler/by-il/{IL_ID}.json`
- `/v1/mahalleler/by-ilce/{ILCE_ID}.json`
- `/v1/yollar/by-ilce/{ILCE_ID}.json` (mahalle bazlı filtre kütüphane tarafından yapılır)

JSON’lar titlecase döner; tüketici kütüphane `case=upper` ile TR uyumlu üst metin üretebilir.

## GitHub Pages
1) Repo Settings → Pages → Source: `Deploy from branch`
2) Branch: `main` (veya kullandığınız), Folder: `/docs`
3) Kaydet, birkaç dakika sonra Pages URL aktif olur.

## Self-host
- `docs/v1` klasörünü doğrudan CDN / statik sunucunuza koyun.
- CORS açıksa front-end uygulamalar doğrudan çağırabilir; kapalıysa gereken başlıkları kendi sunucunuzda ekleyin.

## Veri Üretimi
`tools/generate_api.py` (ana repoda) SQL dump’lardan bu klasör yapısını üretir. Bu repo örnek veri içerir; tam veri için script’i kendi dump’larınızla çalıştırın.

Geliştirici: **@mebularts**
