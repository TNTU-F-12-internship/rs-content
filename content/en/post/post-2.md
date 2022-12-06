---
title: Стримування DDoS атак для краудфандингової ініціативи Canadian Bayraktar
url: '/ua/blog/DDoS-attack-mitigation-for-Canadian-Bayraktar-crowdfunding-initiative'
omit_header_text: false
featured_image: '/image/post-2-banner.png'
summary_image: '/image/post-2-short.jpeg'
date_prefix: 'Опубліковано #'
date: 2022-08-01
read_more_copy: 'Детальніше ->'
identifier: ua-post-DDoS-attack-mitigation
parent: ua-blog

---

#### Опис
Щоб вистояти в героїчній битві, захищаючи цивілізований світ від російської агресії, Україні терміново і вкрай 
необхідно більше обладнання для захисту неба. Одним із найпопулярніших і найефективніших безпілотників є турецький 
середньовисотний довготривалий БПЛА Baykar Bayraktar TBx.

Усвідомлюючи глобальний масштаб російської загрози, наші друзі в Литві, Україні та Польщі зібрали мільйони доларів по 
всьому світу через масові збори коштів, щоб забезпечити та провести закупівлі знаменитого безпілотника Bayraktar.

[UHelpUkraine](https://uhelpukraine.org/) є зареєстрованою неприбутковою організацією (REG. #1000182616, Канада) 
завзятих українсько-канадських волонтерів. Ініціатива [#BuyaBayraktar](https://www.facebook.com/hashtag/BuyaBayraktar/) 
започаткована UHelpUkraine 20 липня 2022 року, привернула 
[чимало уваги](https://www.einnews.com/pr_news/582045288/canadian-non-profit-uhelpukraine-raising-funds-for-crucial-drone-needed-in-ongoing-fight-against-russia), 
як очікуваної, так і небажаної.


#### Виявлення сигнатури атак та вжиті заходи
Команда Rework-Space була залучена до проєкту Canadian Bayraktar з 23 липня 2022 року для вирішення проблем із 
підозрілою активністю трафіку, що спричинило низьку доступність сайту [uhelpukraine.org](https://uhelpukraine.org/) 
для користувачів.

Для початку, ми провели деякі перевірки та дослідження хостингу, що дозволило нам налаштувати правила 
AWS Web Application Firewall (WAF). У результаті ми захистили веб-сайт [uhelpukraine.org](https://uhelpukraine.org/) 
від поширених експлойтів, а також детально дослідили трафік. Менш ніж за 2 дні було заблоковано 140 000 000 
нелегітимних запитів.