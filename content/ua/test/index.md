---
title: Тест
description: "Тестування оптимізації зображень"
url: '/ua/test'

---

#### мій img код



rs-content static/general-images/ - дає помилку

{{/* < img src="/general-images/background_photo.jpg" title="rs-content static/general-images/" > */}}

rs-content content/ua/test/ - дає помилку

{{/* < img src="backgroun.jpg" title="rs-content content/ua/test/" > */}}

{{< img src="images/background_cut.jpg" alt="rs-content assets/images/" >}}
{{< img src="images/mem.jpg" alt="rs-theme assets/images/" >}}



#### figure від hugo
{{< figure src="post-1.jpg" title="rs-content content/ua/test/" >}}
{{< figure src="/general-images/background_photo_test_2.jpg" title="rs-content static/general-images/" >}}
{{< figure src="images/post-1.jpg" title="rs-content assets/images/" >}}
{{< figure src="images/mem.jpg" alt="rs-theme assets/images/" >}}

Контент сторінки
