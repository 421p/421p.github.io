---
published: true
---
## Google Translate free API

The official Google Translate API is available for businesses only but there is a way around which you can use without having to pay the enterprise license fee.

The text can be translated from one language to another using the secret translate.googleapis.com API that is internally used by the Google Translate extension for Chrome and requires no authentication.


The actual API url is (example):

[https://translate.googleapis.com/translate_a/single?client=gtx&sl=**auto**&tl=**en**&dt=t&q=**hola**]()

This call will translate "hola" word from **auto**detected language t **en**glish

Let's write a simple example in javascript:

{% gist e7acd93721843bbd3af4e0cfdd29e0b0 %}
