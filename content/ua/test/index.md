---
title: Тест
description: "Тестування оптимізації зображень"

---

#### мій img код

rs-content static/general-images/ - дає помилку

{{/* < img src="/general-images/background_photo.jpg" title="rs-content static/general-images/" > */}}

rs-content content/ua/test/ - дає помилку

{{/* < img src="backgroun.jpg" title="rs-content content/ua/test/" > */}}

{{< img src="images/backg.jpg" alt="rs-content assets/images/" >}}
{{< img src="images/mem.jpg" alt="rs-theme assets/images/" >}}



#### figure від hugo
{{< figure src="backgroun.jpg" title="rs-content content/ua/test/" >}}
{{< figure src="/general-images/background_photo.jpg" title="rs-content static/general-images/" >}}
{{< figure src="image/background_ph.jpg" title="rs-content assets/image/" >}}
{{< figure src="images/mem.jpg" alt="rs-theme assets/images/" >}}

Контент сторінки
