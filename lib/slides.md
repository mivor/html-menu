# HTML

## Frame-uri si  meniuri



## Frame-uri

Frame-urile sunt folosite pentru a afisa mai multe documente .html intro fereastra.

Aceata inseamna ca vei avea o pagina fara continut, care va avea rolul de a indica browser-ului ce pagini trebuie sa afiseze. Fiecare document HTML deschis in fereastra browser-ului seme numeste fra, iar fiecare frame se comporta independent fata de celelalte frame-uri.

Odata cu introducerea PHP si CSS aceasta tehnica a fost inlaturata putin cate putin, ajungand sa se foloseasca foarte putin.

Dezavantajele utilizarii frame-urilor sunt: dezvoltatorul Web trebuie sa aiba in vedere mai multe documente HTML iar printarea intregii pagini este relativ dificila.



## Pagina Generica

In general frame-urile se folosesc pentru a afisa un meniu pe de o parte iar continutul pe de o alta parte. Atunci cand cineva da un clik pe un link din meniu se va deschide o alta pagina in partea de continut. Vom exempifica toate acestea cu ajutorul codului urmator:

```html
<!DOCTYPE html>
<html>
<head></head>
<frameset cols="30%,*">
  <frame src="menu.html">
  <frame src="content.html">
</frameset>
</html>
```

- `<frameset>` &ndash; Este tagul care stabileste caracteristicile frame-ului. Frame-urile individuale vor fi definite inauntrul lui.

- `<frameset cols="#%, *">` &ndash; `Cols` stabileste inaltimea pe care fiecare frame o va avea. In exemplul anterior am stabilit ca primul frame (meniul) va ocupa 30% din suprafata afisata, si am folosit semnul " * " pentru a indica browser-ului ca in restul paginii ramase se va afisa continutul paginii.

- `<frame src="">` &ndash; adresa fisierelor care vor fi afisate ca meniu si respectiv continut.



## Adaugarea unui banner

```
<!DOCTYPE html>
<html>
<head>
</head>
<frameset rows="20%,*">
  <frame src="title.html">
  <frameset cols="30%,*">
    <frame src="menu.html">
    <frame src="content.html">
</frameset>
</html>
```

- `<frameset rows="#%, *">` &ndash; "rows" stabileste inaltimea fiecarui frame care va fi afisat. In exemplul anterior am ales ca primul frame va fi 20% iar restul de spatiu ramas va fi impartit intre menu.html si content.html.



## Margine si Spatiere

Probabil ati observat ca intre frame-uri raman niste linii gri care de multe ori nu sunt dorite. Inlaturarea lor este posibila cu ajutorul `frameborder` si `framespacing`. Aceste atribute vor fi introduse inauntrul tag-ului frameset.

**Nota:** In realitate frameset si frameborder este acelasi atribut. Exista insa browsere care nu recunosc decat unul dintre cele doua. De aceea, sfatul nostru, este sa le folositi pe amandoua pentru mai multa siguranta.

- `frameborder="#"` &ndash; Valoarea 0 nu reproduce margine.

- `border="#"` &ndash; modifica grosimea marginii. (folosit de netscape)

- `framespacing="#"` &ndash; modifica grosimea marginii (folosit de Internet Explorer)

###Iata si un exemplu practic:

```
<html>
<head></head>
<frameset border="0" frameborder="0" framespacing="0" rows="20%,*">
  <frame src="title.html">
  <frameset border="0" frameborder="0" framespacing="0" cols="30%,*">
    <frame src="menu.html">
    <frame src="content.html">
</frameset>
</html>
```



## frame name si frame target

Pentru a menitine meniul in pozitia actuala iar cand executam click pe pagina de contact de exemplu sa se deschida in locul pagini de continut, vom da un nume fiecarui frame si vom preciza locul unde se va deschide cu ajutorul base target.

Iata si codul pentru pagina noastra

```
<html>
<head>
  <base target="content">
</head>
<frameset rows="20%,*">
  <frame name="title" src="title.html">
  <frameset cols="30%,*">
  <frame name="menu" src="menu.html">
  <frame name="content" src="content.html">
</frameset>
</html>
```



## Noresize si scrolling

Frame-ul se mai poate personaliza inca putin folosind atributele `noresize` si `scrolling`.

```
<html>
<head></head>
<frameset border="2" frameborder="1" framespacing="2" rows="20%,*">
  <frame src="title.html" noresize scrolling="no">
  <frameset border="4" frameborder="1" framespacing="4" cols="30%,*">
  <frame src="menu.html" scrolling="auto" noresize>
  <frame src="content.html" scrolling="yes" noresize>
</frameset>
</html>
```

- `noresize` &ndash; nu lasa ca framul sa se redimensioneze in functie de monutorul vizitatorului

- `scrolling="(yes/no)"` &ndash; permite sau nu sroll-ul intr-un frame

