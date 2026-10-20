# Hotelska oprema — B2B partner portal

Prilagođeni prototip za razgovor sa Dejanom Savićem. Fokus je na ponovljenim nabavkama uniformi kod stalnih hotelskih i ugostiteljskih kupaca, uz odvojene naloge kupaca i administraciju.

## Brzo pokretanje

Raspakujte ZIP u nov, prazan folder. Otvorite folder `Hotelska-Oprema-Demo`, pa `index.html` u modernom pregledaču. Nisu potrebni instalacija, build, server ni registracija. Za najbolji pregled preporučen je Chrome, Edge ili Firefox.

Portal prvo prikazuje demo prijavu. Unesite **bilo koje neprazno korisničko ime i lozinku**. Unos se ne šalje i ne čuva. Zatim izaberite bilo kog od pet kupaca ili administraciju. Svaki kupac je aktivan i ima primer porudžbine. **Odjavite se** pri dnu levog menija vraća ekran za prijavu. Korpe različitih kupaca se čuvaju odvojeno. Dugme **Promeni nalog** u levom meniju prikazuje druge kupce. Dugme **Administracija** u gornjem desnom uglu otvara Dejanov prikaz. Na telefonu je levi meni dostupan kroz dugme sa tri linije.

## GitHub Pages

1. Napravite novi GitHub repozitorijum, npr. `Hotelska-Oprema-B2B-Demo`.
2. Otvorite folder `Hotelska-Oprema-Demo` unutar ZIP-a i ubacite **njegov sadržaj** u koren repozitorijuma. `index.html` mora biti direktno u korenu, uz `app.js`, `data.js`, `styles.css` i folder `assets`.
3. Otvorite **Settings → Pages**.
4. Za Source izaberite **Deploy from a branch**.
5. Izaberite granu **main**, folder **/(root)** i kliknite Save.
6. Kada GitHub završi objavu, otvorite link koji se pojavi na toj stranici.

Sve putanje su relativne i rade i kada je demo u podfolderu GitHub Pages sajta. Fotografije su uključene u ZIP i dodatno ugrađene u `data.js`, zajedno sa logotipom. Zato prikaz slika ne zavisi od toga da li je `assets/` folder prenesen u potpunosti. Portal ih ne učitava sa tuđeg sajta. Aplikacija nema CDN ili druge spoljne programske zavisnosti.

## Predlog demonstracije za Dejana — 5 minuta

1. **Kupac → Naše uniforme:** pokažite odobrene modele, oznaku personalizacije i ugovorenu demo cenu. Za recepcijski model unesite, na primer, 4 komada M i 6 komada L.
2. **Korpa:** izaberite lokaciju isporuke, unesite referencu, potvrdite specifikaciju i pošaljite demo porudžbinu.
3. **Administracija → Porudžbine:** otvorite novu porudžbinu, proverite veličine, promenite status u Potvrđena i sačuvajte.
4. **Prikaz kupca → Moje porudžbine:** pogledajte promenjeni status. Otvorite detalje porudžbine; dugme **Ponovi porudžbinu** vraća stavke u korpu po aktuelnim demo cenama.
5. **Odjavite se → nova demo prijava:** unesite bilo koje ime i lozinku, pa izaberite drugi hotel, restoran ili wellness centar. Pokažite njegove modele, cene, istoriju nabavke i zasebnu korpu.

Za drugi scenario otvorite **Ponude i zahtevi**: kupac sačuva zahtev, administrator pripremi cenu i pošalje demo ponudu, a kupac je prihvati i kreira porudžbinu.

## Funkcionalnosti

- 20 stvarnih proizvoda sa lokalnim fotografijama: 14 modela uniformi i 6 artikala hotelskog tekstila.
- Katalog sa pretragom, kategorijama, grupama osoblja, dostupnošću, omiljenim artiklima i sortiranjem.
- Detalji proizvoda sa linkom na izvorni proizvod.
- Odobreni modeli po kupcu, raspodela količina po veličinama i sačuvana oznaka personalizacije.
- Korpa, obračun osnovice i ilustrativnog PDV-a, lokacije isporuke i napomene.
- Probne porudžbine, detalji, statusi, ponovno poručivanje i izvoz CSV pregleda.
- Zahtevi za ponudu, administratorska priprema ponude i prihvatanje na nalogu kupca.
- Uvoz CSV, TXT, XML i jednostavnog XLSX spiska sa pregledom i validacijom pre dodavanja u korpu.
- Pregled dokumenta porudžbine u portalu, sa dugmetom Štampaj / Sačuvaj kao PDF i izvozom stavki u CSV.
- Administracija porudžbina, demo kupaca, ukupnih zaliha, rabata i rokova plaćanja.
- Demo prijava sa proizvoljnim korisničkim imenom i lozinkom, izbor pet aktivnih kupaca i odjava. Svaki nalog ima primer porudžbine.
- Prikaz za računar i telefon, tastaturna navigacija, fokus u dijalozima i lokalno čuvanje demo izmena.

## Uvoz podataka

U folderu `templates` su primeri za CSV, XML i XLSX. Koristite demo šifre iz kataloga (`DEMO-001` itd.).

CSV/TXT kolone su `sifra`, `velicina`, `kolicina`. Podržani su tačka-zarez, zarez i tab kao separator. Uniforme imaju ilustrativni izbor XS–XXL, tekstil oznaku UNI.

XML primer:

```xml
<porudzbina>
  <artikal>
    <sifra>DEMO-001</sifra>
    <velicina>M</velicina>
    <kolicina>5</kolicina>
  </artikal>
</porudzbina>
```

XLSX čita prvi radni list `sheet1.xml`, tekstualne i numeričke ćelije, bez evaluacije formula. Šifrovani dokumenti, `.xls`, složeni radni listovi i fajlovi veći od 5 MB nisu podržani. Kod nepodržanog XLSX fajla koristite CSV šablon. Maksimalno 1.000 redova po uvozu i 999 komada po redu.

## Stvarni izvori i demo podaci

Nazivi, fotografije i kratki opisi proizvoda preuzeti su sa **hotelskaoprema.rs** 20.10.2026. Kratki opisi su preformulisani za prikaz. Izvori su u `SOURCES.csv`, a originalni link je dostupan i u detaljima proizvoda. Originalni logo je uključen.

**Cene u portalu, demo šifre, izbor veličina, raspoložive količine, rabati, odobrenja, personalizacija, kontakt osobe, kupci i poslovni dokumenti su ilustrativni.** Uniforme na javnom sajtu uglavnom nemaju izloženu cenu. Portal ne prikazuje potvrđenu komercijalnu ponudu dobavljača. Za papuče Basic u demou se poštuje javno navedena minimalna porudžbina od 200 pari.

Portal je prototip: nema stvarne autentifikacije, finansijske obaveze, naplate, slanja email poruka, ERP veze, rezervacije zaliha ni rada više stvarnih korisnika. Dugmad za „slanje” čuvaju demo podatke samo u pregledaču. Administracija je javno otvorena radi prezentacije i ne predstavlja produkcionu kontrolu pristupa.

Izmene se čuvaju u `localStorage` istog pregledača, pod ključem `hotelska-oprema-partner-v4`. Sesija demo prijave čuva se u `sessionStorage`; korisničko ime i lozinka se ne čuvaju. Ova verzija započinje sopstveni skup početnih demo podataka. Ne sinhronizuju se između uređaja ili pregledača. Ako pregledač zabrani lokalno čuvanje, demo radi do zatvaranja stranice i prikazuje obaveštenje. Za početno stanje otvorite **Pomoć i podrška → Vrati početni demo**.

## Fajlovi

- `index.html` — početna stranica.
- `styles.css` — responzivan vizuelni sistem.
- `data.js` — katalog, početni demo podaci i ugrađene fotografije/logotip.
- `app.js` — funkcionalnosti portala i administracije.
- `assets/` — originalni logo i lokalne fotografije.
- `templates/` — primeri uvoza.
- `SOURCES.csv` — izvori proizvoda i fotografija.
- `.nojekyll` — pomoćni fajl za statički GitHub Pages prikaz.

## Provereno

U pregledaču su provereni izbor količina po veličinama, kreiranje porudžbine, promena statusa u administraciji, administratorska priprema i kupčevo prihvatanje ponude, kao i uvoz jednostavnog XLSX spiska. Izgled je pregledan na desktop širini i mobilnom prikazu od 390 px.
