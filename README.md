![starkbucks](https://user-images.githubusercontent.com/110226567/213872431-77b95d8d-bcec-45fb-9b31-4dc01f166d40.png)

# โญ Starbucks

Starbucks PWA ์ฌ์ดํธ ๐ [Demo](https://imjone.github.io/starbucks/)

<br />

## ๐ข ํ๋ก์ ํธ ๊ฐ์

PWA(Progressive Web Application)๋ฅผ ๋ฉ์ธ ์ปจ์์ผ๋ก ์ก๊ณ  ์งํํ ํ๋ก์ ํธ์๋๋ค.<br />
๋ํ์ ์ธ ์๊ฐ ์๋ ์คํ๋ฒ์ค๋ฅผ ์ฃผ์ ๋ก ์ก์์ ์ฌ์ดํธ ์ ์ฒด์ ์ผ๋ก ๋ฆฌ๋ด์ผํ์์ผ๋ฉฐ,<br />
๋ฉ์ธ ํ์ด์ง์ ์๋ธ ํ์ด์ง ์ ๋ถ ๋น ์ง ์์ด ๋์ํ๋๋ก ์ ์ํ์์ต๋๋ค.

<br />

## ๐จ๏ธ ์ฌ์ฉ ๊ธฐ์ 

<p>
  <img src="https://img.shields.io/badge/HTML-e34f26?style=flat-square&logo=HTML5&logoColor=white" />
  <img src="https://img.shields.io/badge/CSS-1572b6?style=flat-square&logo=CSS3&logoColor=white" />
  <img src="https://img.shields.io/badge/JavaScript-f7df1e?style=flat-square&logo=JavaScript&logoColor=white" />
  <img src="https://img.shields.io/badge/Google Maps API-4285F4?style=flat-square&logo=Google&logoColor=white" />
</p>

<br />

## ๐ ์ฃผ์ ๊ธฐ๋ฅ

- ๋ค์ํ ์ํฉ์ ๋ง๋ ํ์์ฐฝ ๋ธ์ถ
- ๋ฉ๋ด๋ช ์ด์ฑ ๊ฒ์ ์นดํ๊ณ ๋ฆฌ ํํฐ๋ง
- ๋ฉ๋ด ์์ธ ์ ๋ณด ๋ฐ ์ฃผ๋ฌธ ์ต์ ํ์์ฐฝ
- Google Maps API๋ฅผ ํ์ฉํ ๋งค์ฅ ์ง๋
- ๋ฉค๋ฒ์ญ ์นด๋ ์ด๋ฏธ์ง ์ฌ๋ผ์ด๋

<br />

## ๐ป ์์ค ์ฝ๋

์ ์ฒด ์ฝ๋ ๋ณด๋ฌ ๊ฐ๊ธฐ ๐ [Notion](https://imjone.notion.site/Starbucks-68398a8c085f4045bc1da00a6173849e)

### ๐ ๋งค๋ํ์คํธ ํ์ผ ์ธํ

PWA ์ค์น ๋ฐ ์ฑ์ ๊ตฌ์ฑ ์ ๋ณด๋ฅผ ๋ด๊ณ  ์๋`manifest.json` ํ์ผ์ ์ค์ ํด์ฃผ์์ต๋๋ค.<br />

```json
{
  "dir": "auto",
  "lang": "ko",
  "name": "Starbucks Korea",
  "short_name": "Starbucks",
  "background_color": "#00704a",
  "theme_color": "#00704a",
  "description": "Starbucks PWA site",
  "display": "standalone",
  "orientation": "any",
  "scope": "https://imjone.github.io/starbucks/",
  "start_url": "https://imjone.github.io/starbucks/",
  "categories": ["coffee", "dessert", "cafe"],
}
```

### ๐ ๋ฉ๋ด ์นดํ๊ณ ๋ฆฌ ํํฐ๋ง

๊ฐ๊ฐ์ ์นดํ๊ณ ๋ฆฌ์ ๋ฉ๋ด ๋ฆฌ์คํธ์๋ `data-` ์์ฑ์ด ์ ์๋์ด ์์ผ๋ฉฐ,<br />
์นดํ๊ณ ๋ฆฌ ๋ฒํผ ํด๋ฆญ ์ ํด๋น ์์ฑ๊ณผ ์ผ์นํ๋ ๊ฐ์ ์ง๋ ๋ฉ๋ด๋ง ํํฐ๋ง๋ฉ๋๋ค.

```html
<!-- Category -->
<div class="menu__categories">
  <button data-filter="all">์ ์ฒด ๋ณด๊ธฐ</button>
  <button data-filter="promotion">ํ๋ก๋ชจ์</button>
  <button data-filter="beverage">์๋ฃ</button>
  <button data-filter="dessert">๋์ ํธ</button>
</div>

<!-- Menu List -->
<article id="beverage" data-type="beverage"></article>
<article id="dessert" data-type="dessert"></article>
<article id="promotion" data-type="promotion"></article>
```
```javascript
const menuCategories = document.querySelector('.menu__categories');
const articleOfMenu = document.querySelectorAll('.menu__article');

menuCategories.addEventListener('click', e => {
  articleOfMenu.forEach(article => {
    if (filter === 'all' || filter === article.dataset.type) {
      article.style.display = 'block';
    } else {
      article.style.display = 'none';
    }
  });
});
```

### ๐ ๊ตฌ๊ธ ์ง๋

์ง๋์ ์ค์ฌ์ ์ ์ค์ ํด์ฃผ๊ณ , ๋งค์ฅ ์ ๋ณด๋ฅผ ์ ๊ณตํ  ์ ์๋ `infowindow` ์์๋ฅผ ์ ์ํฉ๋๋ค.<br />
๋ฏธ๋ฆฌ ์ค๋นํด๋ ๋งค์ฅ ๋ฆฌ์คํธ ๋ฐฐ์ด์ ์์ ๊ฐ์๋งํผ ๋ฐ๋ณต๋ฌธ์ ๋๋ฉฐ `marker`๊ฐ ์์ฑ๋๊ณ ,<br />
๋ง์ปค๋ฅผ ํด๋ฆญํ๋ฉด ์ ๋ณด์ฐฝ์ด ๋ธ์ถ๋๋ฉฐ ํด๋น ๋งค์ฅ์ ์์น๋ก ์ง๋๊ฐ ํ๋ ๋ฐ ์ด๋๋ฉ๋๋ค.

```javascript
const map = new google.maps.Map(document.getElementById('map'), {
  zoom: 12,
  center: { lat: 37.5001276, lng: 127.0290304 },
  disableDefaultUI: true,
  scrollwheel: true,
});

const infowindow = new google.maps.InfoWindow();
const bounds = new google.maps.LatLngBounds();

for (let i = 0; i < stores.length; i++) {
  const store = stores[i];
  const marker = new google.maps.Marker({
    position: { lat: store.lat, lng: store.lng },
    map,
    address: store.address,
    title: store.name,
    icon: {
      url: 'img/coffee/reserve/map_marker.png', // change marker icon image
    },
  });
  bounds.extend(marker.position);
  
  marker.addListener('click', () => {
    infowindow.open(map, marker);
    infowindow.setContent(reserveStoreInfo);
    map.panTo(marker.position);
    map.setZoom(15);
  });
}
```

<br />

## ๐ ๋ฐฐ์ด ์  ๋ฐ ๋๋ ์ 

- ๊ตฌ๊ธ ์ง๋๋ฅผ ์ปค์คํํ๋ ๊ณผ์ ์์ API ํ์ฉ ๋ฅ๋ ฅ์ ์ค์์ฑ์ ๋๊ผ์ต๋๋ค.
- ์ํ๋ ์ ๋ณด๋ฅผ ๋น ๋ฅด๊ฒ ์ฐพ์๋๊ฐ ์ ์๋ ์ ๋ณด ํ์ ๋ฅ๋ ฅ์ ๊ธฐ๋ฅผ ์ ์์์ต๋๋ค.
- ๊ธฐ๋ฅ ๊ตฌํ์ ์์ด ๋ ์์ ์ ๋ถ์กฑํจ์ ๋๋ผ๋ฉฐ, ๋์ฑ ์ด์ฌํ ํด์ผ๊ฒ ๋ค๋ ์๊ทน์ ๋ฐ์์ต๋๋ค.
