---
published: true
tags: google translate api free js javascript
---
The official Google Translate API is not awailable for free but there is a way around which you can use without having to pay the enterprise license fee.

The text can be translated from one language to another using the secret translate.googleapis.com API that is internally used by the Google Translate extension for Chrome and requires no authentication.


The actual API url is (example):

[https://translate.googleapis.com/translate_a/single?client=gtx&sl=**auto**&tl=**en**&dt=t&q=**hola**]()

This call will translate "hola" word from autodetected language (**auto**) to english (**en**)

All language codes can be found [here](https://cloud.google.com/translate/docs/languages)

Let's write a simple example in javascript:

{% gist e7acd93721843bbd3af4e0cfdd29e0b0 %}

Or for those who prefer async/await syntax:

{% gist ae70886b759cc52fdb0a1efca82136ab %}

As you can see it's a simple GET request, thus is easily implementable in your favourite language
