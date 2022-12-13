---
title: DDoS attack mitigation for Canadian Bayraktar crowdfunding initiative
url: '/blog/DDoS-attack-mitigation-for-Canadian-Bayraktar-crowdfunding-initiative'
omit_header_text: false
featured_image: '/blog-images/post-2-banner-5.png'
summary_image: '/blog-images/post-2-short.jpeg'
date_prefix: 'Published #'
date: 2022-08-01
read_more_copy: 'Read more ->'

---

#### Introduction

To endure in a heroic battle defending the civilized world from russian aggression, Ukraine urgently and absolutely 
needs more equipment to protect the sky. One of the most popular and efficient unmanned aerial vehicles is Turkish 
medium-altitude long-endurance Baykar Bayraktar TBx UAV.

Aware of the global scale of russian threat, our friends in Lithuania, Ukraine, and Poland have raised millions of 
dollars across the globe through grassroots fundraisers to ensure and conduct purchases of the famous Bayraktar drone.

[UHelpUkraine](https://uhelpukraine.org/) is a registered non-profit organization (REG. #1000182616, Canada) of proud 
Ukrainian-Canadian volunteers. An initiative [#BuyaBayraktar](https://www.facebook.com/hashtag/BuyaBayraktar/)
was started by UHelpUkraine on Jul 20, 2022 and attracted 
[a lot of attention](https://www.einnews.com/pr_news/582045288/canadian-non-profit-uhelpukraine-raising-funds-for-crucial-drone-needed-in-ongoing-fight-against-russia),
both anticipated and unwanted one.


#### Attack signature detection and response

Rework-Space team was involved in the project since Jul 23, 2022 to resolve issues with suspicious traffic activity 
that caused poor performance of [uhelpukraine.org](https://uhelpukraine.org/) site.

First, we have done some hosting audits and research which enabled us to configure AWS Web Application Firewall 
([WAF](https://docs.aws.amazon.com/waf/latest/developerguide/waf-chapter.html)).
As a result, we have protected the web application [uhelpukraine.org](https://uhelpukraine.org/) from common web 
exploits and also researched the traffic in detail. In less than 2 days, 140 000 000 illegitimate requests were blocked.

{{< figure src="/blog-images/post-2-image-1.png" alt="WAF requests visualization" title="Figure 1. WAF requests visualization">}}

CPU utilization improved considerably.

{{< figure src="/blog-images/post-2-image-2.png" alt="EC2 instance CPU utilization" title="Figure 2. EC2 instance CPU utilization">}}

However, we discovered that there were short time intervals when WAF rules were not efficient and CPU utilization was 
still high (Figure 2). Generally, AWS [proposes](https://docs.aws.amazon.com/waf/latest/developerguide/ddos-responding.html#ddos-responding-manual) 
two kinds of  response to DDoS attacks (the 7-layer OSI Model), namely:
1. Provide your own mitigations;
2. Contact support – If you're a Shield Advanced customer.

Option 1 is not acceptable in this case of more than 60M blocked requests with geographically distributed origins. 
The daily budget of our customer was about $50, and you pay for each 1M of blocked requests. Option 2 is good but 
starts from $3000 for a monthly subscription. Obviously, it would not be the best solution for our customer, a 
non-profit organization with a very limited budget.

So, we have conducted research on projects and companies that support open society initiatives and help people feel 
safe when using information technologies. As a result, we have chosen [Jigsaw](https://jigsaw.google.com/), which is 
a unit within Google that explores threats to open information systems and creates technology that enables scalable 
solutions.

You can see the result in Figure 2, presenting the new solution implemented on Jul 25, 2022. Noteworthy, for non-profit 
organizations and other eligible clients [Jigsaw](https://jigsaw.google.com/) proposes CDN cache (Google infrastructure), 
[reCAPTCHA](https://www.google.com/recaptcha/about/) (should be enabled explicitly), metrics in a single dashboard at 
no cost at all, [as a basic option](https://www.pcmag.com/opinions/inside-project-shield-jigsaws-anti-ddos-machine).

{{< figure src="/blog-images/post-2-image-3.png" alt="Cost dynamics for uhelpukraine.org" title="Figure 3. Cost dynamics for uhelpukraine.org">}}

In conclusion, we got rid of expenses on the AWS side. Now [UHelpUkraine](https://uhelpukraine.org/) team pays just for 
AWS hosting services and focuses on volunteer activities. Rework-Space team continues to provide cyber-security 
services to our new partner [UHelpUkraine](https://uhelpukraine.org/) and will do so till our people prevails.

All materials are published with the consent of [UHelpUkraine](https://uhelpukraine.org/) team.
