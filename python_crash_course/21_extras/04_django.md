# `render(request, template_name, context)` Mein `request` Kyun Dete Hain?

* Django ko batana padta hai ki ye kis HTTP request ka response 
  hai.
* Taki Django response object ko properly return kar sake.
* Isme user session, authentication, aur cookies jaise features 
  properly kaam kar sakein.

Without `request`, Django ye nahi samajh paayega ki kis user ke liye 
ya kis request ke context mein template render karna hai.

## TL;DR

`request` object ek container hai jisme user, session, method, aur 
form data hota hai. Jab `render()` function mein pass kiya jaata hai, 
toh Django use karta hai proper response generate karne ke liye.
