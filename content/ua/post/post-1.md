---
title: Terraform DNS провайдер для керування FreeIPA
url: '/ua/blog/2022-07-01-terraform-provider-for-freeipa-dns-management'
omit_header_text: false
featured_image: '/blog-images/post-1-banner.jpg'
summary_image: '/blog-images/post-1-short.jpg'
date_prefix: 'Опубліковано #'
date: 2022-07-01
read_more_copy: 'Детальніше ->'


---

[Terraform DNS провайдер](https://registry.terraform.io/providers/rework-space-com/freeipa/latest/docs) 
для керування FreeIPA розроблено та запропоновано командою Rework-Space Infrastructure.

Перевірено на FreeIPA версії 4.9.1

#### Вимоги:
- [Terraform](https://www.terraform.io/) 1.0.x
- Go 1.18 (для створення плагіна провайдера)

#### Ресурси:
- freeipa_dns_record
- freeipa_dns_zone
- freeipa_group
- freeipa_user

[FreeIPA](https://www.freeipa.org/page/Leaflet) — це інтегроване рішення ідентифікації та автентифікації для мережевих 
середовищ Linux/UNIX. Сервер FreeIPA централізовано забезпечує автентифікацію, авторизацію та систему облікових записів, 
зберігаючи дані про користувачів, групи, хости та інші об’єкти, які є необхідними для керування аспектами безпеки 
мережі комп’ютерів.

Ми віддаємо перевагу використанню IaC для керування конфігурацією та інтеграцією FreeIPA. Команда Rework-Space пропонує 
Terraform DNS провайдер для керування FreeIPA на розгляд спільноти відповідно до ліцензії
[GNU GENERAL PUBLIC LICENSE](https://github.com/rework-space-com/terraform-provider-freeipa/blob/main/LICENSE).
