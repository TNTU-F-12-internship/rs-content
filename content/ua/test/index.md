---
title: Тест
description: "Тестовий опис"
featured_image: '/image/background_photo.jpg'

---

мій img код

rs-content static/image/ - дає помилку

rs-content content/ua/about/ - дає помилку
{{< img src="/image/background_ph.jpg" alt="rs-content assets/image/" >}}
{{< img src="images/mem.jpg" alt="rs-theme assets/images/" >}}

figure від hugo
{{< figure src="backgroun.jpg" title="rs-content content/ua/about/" >}}
{{< figure src="/image/background_photo.jpg" title="rs-content static/image/" >}}
{{< figure src="image/background_ph.jpg" title="rs-content assets/image/" >}}
{{< figure src="images/mem.jpg" alt="rs-theme assets/images/" >}}

Контент сторінки
