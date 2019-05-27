# veb2_projekat
1. Opis zadatka

Realizovati aplikaciju za digitalizaciju gradskog saobraćaja. Aplikacija treba da pojednostavi:
  
  ● Evidenciju linija gradskog prevoza. Svaka linija sadrži stanice.
  ● Evidenciju karata i putnika. Evidentirati podatke neophodne za evidenciju prodaje karata, pri čemu postoje različiti tipovi karata. Evidentirati korišćenja karata od strane putnika.
  ● Evidenciju reda vožnje i lokacija vozila. Predvideti izmene reda vožnje, kao i dinamičko praćenje pozicije vozila. Prikupljanje pozicije može biti realizovano putem podsistema koji isporučuje test podatke o poziciji.

Postoje četiri vrste korisnika ovog sistema:
1. Neregistrovani korisnik
2. Putnik
3. Kontrolor
4. Administrator

2. Funkcije sistema

2.1 Prikaz informacija neregistrovanim korisnicima

Prva stranica koju (neregistrovan) korisnik vidi je početna stranica aplikacije na kojoj se mogu
odabrati prikaz reda vožnje, mreže linija, trenutne lokacije vozila, cenovnika i preći na stranicu
za registraciju/prijavu na sistem.
  ● Red vožnje: prikazuje se forma sa mogućnošću za odabir gradskog ili prigradskog reda vožnje, dana i linije;
  ● Mreža linija [jedna]: prikazuje se mreža postojećih linija gradskog i/ili prigradskog saobraćaja, pri čemu je neopodno iscrtati mrežu linija sa postojećim stanicama na mapi.
Klikom na stanicu korisnik dobija dodatne informacije o stanici;
  ● Trenutna lokacija vozila: prikazuju se sva vozila odabrane linije i njihove trenutne lokacije na mapi;
  ● Cenovnik: prikazuje se cena karte za odabrani tip karte (vremenska , dnevna, mesečna i godišnja) i odabranu vrstu putnika (đačka, penzionerske, regularna).
1 Kupljena karta je vazeca u narednih sat vremena za bilo koju liniju

2.2 Registracija korisnka prijavljivanje na sistem

Na stranici za registraciju/prijavu na sistem pomoću korisnikove email adrese i lozinke može se
izvršiti prijava.
Ukoliko korisnik još uvek nije registrovan na sistem, a želi da koristi napredne funkcije aplikacije,
mora prvo da se registruje na odgovarajućoj stranici. Registracija obuhvata unos email adrese,
lozinke, imena, prezimena, datuma rođenja i adrese. Lozinka se unosi u dva polja da bi se
otežalo pravljenje grešaka prilikom odabira nove lozinke.
Prilikom registracije takođe je neohodno i da se definiše tip korisnika (đak, penzioner, regularni
putnik). Ukolko se korisnik izjasni da je đak (učenik ili student), neophodno je da sistemu za to
dostavi i dokaz u vidu fotografije indeksa, dok sa druge strane, ukoliko se izjasni da je
penzioner, neopodno je da dostavi penzioni ček. Korisnici koji se ne izjasne ili se izjasne da su
regularni korisnici, ne dostavljaju dokument. Prilikom registracije korisniku je omogućeno da
preskoči deo za dostavljanje dokumenta i da ga dostavi kasnije tokom korišćenja aplikacije.
Napomena: potrebno je obezbediti mehanizam za autentifikaciju i autorizaciju korisnika na
serverskoj strani.

2.3 Profil korisnika
Registrovani korisnik je u mogućnosti da ažurira svoje lične podatke na stranici za prikaz svog
profila, kao i da pregleda ili ponovo dostavlja dokumenta.

2.4 Postupak kupovine karte
Korisniku je omogućeno da kupi neke od sledećih vrsta karata:

1. Vremenska karta - kupljena karta je vazeca u narednih sat vremena za bilo koju
liniju;
2. Dnevna karta - važi za bilo koju liniju prevoza tokom dana kupovine (ne 24 sata);
3. Mesečna karta - važi tokom tekućeg meseca;
4. Godišnja karta - važi tokom tekuće godine.

Korisnik čiji profil nije verifikovan od strane kontrolera ili koji nije dostavio odgovarajući
dokument (sliku đačke knjižice, indeksa ili penzionog čeka) nema mogućnost kupovine karte.

2.5 Postupak verifikovanja profila putnika
Kontrolor ima mogućnost pregledanja podataka i dokumenata koje su priložili putnici, pri čemu
određeni zahtev može da prihvati ili odbije. Nakon prihvatanja, profil putnika postaje aktivan i
dozvoljenja mu je kupovna karata.
Putnik na svom profilu ima indikaciju o statusu procesa verifikacije (zahtev se procesira, zahtev
je prihvaćen ili je odbijen). Poslati email kao notifikaciju.

2.6 Postupak validiranja karte putnika
Postoji zasebna stranica za kontrolu karata. Kontrolor unosi ID karte i sistem odredjuje na
osnovu tipa karte validnost po sledećim pravilima:
- Za vremensku kartu, u odnosu na čekirano vreme i trenutno vreme
- Za ostale karte po definisanim pravilima

2.7 Upravljanje linijama i stanicama (mrežom linija)

Administrator sistema može da uređuje linije koje sadrže:
1. Redni broj
2. Stanice

Administrator sistema može da uređuje stanice koje sadrže:
1. Naziv
2. Adresu
3. Geografske koordinate
4. Linije

2.8 Upravljanje redom vožnje

Administrator sistema može da uređuje red vožnje koji sadrži:
1. Dan u nedelji
2. Polaske
3. Liniju

2.9 Upravljanje cenovnikom
Administrator sistema može da uređuje cenovnik.

3. Implementacija sistema
Aplikaciju realizovati kao klijent-server aplikaciju. Serverski deo aplikacije treba da bude
realizovan korišćenjem C# programskog jezika (.NET WebApi). Klijentsku aplikaciju realizovati
korišćenjem Angular radnog okvira.
