MATI MARKET – APROVIZIONARE RAPIDĂ 2.0
======================================

CONȚINUT
- index.html: aplicația
- sw.js: cache și funcționare offline pentru fișierele aplicației
- manifest.webmanifest: instalare ca aplicație web pe telefon
- icon-192.png și icon-512.png: pictograme

CE S-A ÎMBUNĂTĂȚIT
- Selectarea produsului printr-o singură atingere pe întregul rând.
- A doua atingere elimină produsul din selecție.
- Căutare instantanee și filtre după categorie/furnizor.
- Favorite persistente.
- Filtre pentru comenzi recente și produse comandate frecvent.
- Buton pentru repetarea ultimei comenzi.
- Salvarea automată a selecției curente.
- Comandă vocală acolo unde browserul oferă Speech Recognition.
- Administrare produse, categorii și furnizori.
- Import/export catalog CSV (fișier compatibil cu Excel).
- Export comandă CSV (compatibil cu Excel), PDF, copiere și distribuire WhatsApp.
- Backup/restaurare JSON pentru catalog, istoric și selecția curentă.
- Istoric de comenzi.

MIGRARE FĂRĂ PIERDEREA CATALOGULUI EXISTENT
Aplicația păstrează cheile localStorage din V4:
- lista-aprovizionare-db
- lista-aprovizionare-history

Pentru ca aplicația nouă să poată citi datele deja salvate pe iPhone:
1. Înlocuiește fișierele din același repository GitHub Pages.
2. Păstrează exact aceeași adresă GitHub Pages (același domeniu și aceeași cale).
3. Nu șterge datele site-ului din Safari și nu dezinstala/șterge datele aplicației înainte de verificare.
4. Deschide adresa existentă în Safari, reîncarcă pagina și verifică dacă produsele și furnizorii apar.
5. După confirmarea catalogului, intră la Administrare și creează un Backup JSON.

IMPORTANT DESPRE DATE
Catalogul și istoricul sunt stocate local pe dispozitiv/browser. Nu există sincronizare între iPhone-uri sau între utilizatori. Ștergerea datelor site-ului din Safari poate șterge catalogul local. Fă periodic Backup JSON și păstrează fișierul într-un loc sigur.

LIMITĂRI DE COMPATIBILITATE
- Dictarea vocală directă depinde de suportul browserului. Dacă Safari pe iPhone nu oferă Speech Recognition, folosește microfonul tastaturii iOS pentru dictarea în căutare.
- Exportul Excel este CSV cu separator și codare compatibile cu Excel; nu este un fișier .xlsx nativ.
- Generarea PDF folosește o bibliotecă externă atunci când există conexiune. Fără aceasta, aplicația oferă imprimare/Salvare ca PDF din browser.
- Funcțiile de catalog, selecție, istoric și export CSV sunt locale. Sincronizarea cloud și integrarea cu casa de marcat nu sunt incluse.


VERSIUNEA V2.3 – EXPORT PDF
Butonul PDF folosește fereastra nativă de imprimare Safari, cu o pagină separată pentru tipărire. Pe iPhone: apasă PDF, în previzualizarea de imprimare mărește previzualizarea cu două degete, apoi folosește Partajare > Salvează în Fișiere pentru a salva PDF-ul. Cache-ul Service Worker a fost actualizat la v4.


VERSIUNEA V2.5 – VERIFICARE RAPIDA
A fost adăugat modul „Începe verificarea rafturilor”. Produsele sunt parcurse pe rând, grupate după categoriile existente. Pentru fiecare produs se poate marca AVEM, COMANDĂ sau MAI TÂRZIU. Starea verificării se salvează separat în localStorage, fără modificarea catalogului, istoricului, cheilor existente sau funcției PDF. Produsele marcate COMANDĂ intră în selecția normală a comenzii. Categoriile sunt folosite momentan ca zone de verificare; ordinea lor trebuie adaptată ulterior la traseul fizic real al magazinului.


VERSIUNEA V3 – VERIFICARE PE CATEGORII
Verificarea se face acum prin alegerea unei categorii și afișarea simultană a produselor acesteia. Fiecare produs poate fi marcat AVEM, STOC MIC sau LIPSEȘTE. Pentru ultimele două stări se poate introduce cantitatea. Produsele intră în selecția de aprovizionare fără duplicate, păstrând furnizorul. Progresul este salvat separat în localStorage.

PDF: mecanismul nativ de imprimare Safari din versiunea anterioară a fost păstrat; lista include cantitatea și starea pentru produsele care au fost verificate. Compatibilitatea reală cu Safari pe iPhone trebuie confirmată pe dispozitiv. Testele automate de aici nu pot garanta comportamentul ferestrei native de imprimare iOS.
