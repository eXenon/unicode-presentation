---
title: Unicode
revealOptions:
    transition: 'none'
    slideNumber: true
---
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.0.13/css/all.css" integrity="sha384-DNOHZ68U8hZfKXOrtjWvjxusGo9WQnrNx2sqG0tfsghAvtVlRW3tvkXWZh58N9jp" crossorigin="anonymous">
<h1>Unicode</h1>

---

Unicode is a standard maintained by the *Unicode Consortium*. The lastest version, Unicode 13, has been published in March 2020.
<br>
<img src="assets/unicode.svg.png" height="150px">
<br>
Unicode 13 contains 143.924 caracters.

---

Unicode defines a list of caracters, but it can be encoded in several ways :
- __UTF-8__, __UTF-16__ : two variable width encodings
- __UTF-32__ : fixed width encoding
- __GB18030__ : official encoding of the CCP
- __BOCU__, __UTF-7__, ...

---

<h3>UTF-8</h3>
<img src="assets/utf8.png" height="300px">

---

The Unicode character space is broken up into planes :
```
- 0x0000  - 0xFFFF   : Basic Multilingual Plane
- 0x10000 - 0x1FFFF  : Supplementary Multilingual Plane
- 0x20000 - 0x2FFFF  : Supplementary Ideographic Plane
- 0x30000 - 0x3FFFF  : Tertiary Ideographic Plane
- 0x40000 - 0xDFFFF  : Unassigned planes
- 0xE0000 - 0xEFFFF  : Supplementary Special Purpose Plane
- 0xF0000 - 0x10FFFF : Supplementary Private Use Area planes
```

---

<img src="assets/utf8-planes.png" height="300px">


---

<small>
The BMP is split into 163 blocks which cover a vide variety of languages.
<br><br>
Latin with extensions, covers from 0x0000 to 0x024F (591). From 592 to 65535, it covers other languages, with some symbols and control caracters.
<br><br>
The ideographic planes mainly cover CJK (Chinese - Japanese - Korean), since they share the same origins. The largest block covers 42.711 caracters.
</small>

---

The official scripts reference list :

https://unicode.org/charts/

---

Scripts

<img src="assets/ethiopic.png" height="400px">

---

<small>
With so many different languages everything becomes difficult :

<ul>
    <li>17 characters marked as "Space separator" in Unicode</li>
    <li>4 different markers for "Left-to-Right" text (and 4 more for "Right-to-Left")</li>
    <li>Some languages have different letters based on position in word or surrouding letters</li>
    <li>Lower / Uppercasing</li>
    <li>Character counting</li>
    <li>Word separation</li>
    <li>Regexes</li>
    <li>Accents and accented letters</li>
    <li>Normalization</li>
</ul>


Other languages conceive of writing very differently than we do.
<small>

---

Normalization

http://unicode.org/reports/tr15/

---

<small>4 different normalizations are defined by Unicode.
They are used to normalize the way diacriticts are encoded, but also as a projection of UTF-8 in general.</small>

<img src="assets/normalization.jpg" height="300px">

---

Character counting

---

How many characters are there in :
क्षि♊🅱️

- 25 bytes
- 8 code points
- 3 graphemes
- Python len : 7
- JS len : 8

<small>(also editing this string broke my terminal and vim undo)</small>

---

Gives rise to ugly algorithms :<br>
<img src="assets/segmentation.png" height="500px">

---

Unicode oddities

---

<table style="font-size: 0.6em;">
  <tr>
    <td>Ogham</td>
    <td>᚛ᚈᚑᚋ ᚄᚉᚑᚈᚈ᚜</td>
    <td>An old irish script that used to be carved in stones. The space is :  </td>
  </tr>
  <tr>
    <td>Alchemy</td>
    <td>🜢🜵  🜶  🜷  🜸  🜹  🜺  🜻  🜼</td>
    <td></td>
  </tr>
  <tr>
    <td>Hieroglyphs</td>
    <td>𓀉𓀁𓀅</td>
    <td></td>
  </tr>
  <tr>
    <td>Mahjong and chess pieces</td>
    <td>🀃🀇🀘 🨮🨰</td>
    <td></td>
  </tr>
  <tr>
    <td>Linear A</td>
    <td>𐘃𐘈𐘔𐘘</td>
    <td>An old minoan writing system that never was deciphered !</td>
  </tr>
</table>

---

Unicode tries to encode all of written language.

> "The deepest philosophical knowledge lies already prepared in language." - Nietzsche

---

Part 2 : Emojis & Fonts
