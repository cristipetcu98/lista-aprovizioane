MATI MARKET – SMART RETAIL V4.8
================================

NOUTATI V4.8
------------
- Buton separat „PRODUSE COMANDATE RECENT” in fila COMANDA.
- Lista foloseste comenzile finalizate din istoric, inclusiv comenzile vechi care nu au toate campurile noi.
- Produsele sunt unice si ordonate dupa cea mai recenta comanda.
- Fiecare produs poate fi adaugat direct in comanda curenta; duplicatele sunt blocate.
- Eliminata categoria defectuoasa „COMANDATE RECURENT” din catalog.
- PDF REAL generat local in format A4, nu pagina HTML de imprimare.
- Pe dispozitivele compatibile, PDF-ul poate fi trimis prin meniul nativ de partajare iOS; din acel meniu se poate alege Print sau Save to Files.
- Daca partajarea fisierelor nu este disponibila, aplicatia afiseaza un link pentru deschiderea/descarcarea PDF-ului.
- Produsele, categoriile si furnizorii existenti sunt standardizati cu LITERE MARI si FARA DIACRITICE.
- La normalizare, duplicatele identice dupa denumire + categorie + furnizor sunt consolidate, iar referintele din comanda curenta si istoric sunt remapate.
- Cache-ul Service Worker a fost actualizat.

FISIERE
-------
- index.html
- sw.js
- manifest.webmanifest
- icon-192.png
- icon-512.png
- README-RO.txt

DATE SI COMPATIBILITATE
-----------------------
Cheile localStorage existente sunt pastrate:
- lista-aprovizionare-db
- lista-aprovizionare-history
- lista-aprovizionare-draft-v2

Nu schimba adresa GitHub Pages (domeniu si cale). Nu sterge datele Safari.
Inainte de actualizare, este recomandat sa faci un Backup JSON din Setari.
Datele raman locale dispozitivului; aceasta versiune nu adauga sincronizare intre dispozitive.

PDF PE IPHONE
-------------
Butonul „Distribuie PDF / Imprima” genereaza un fisier PDF real si incearca sa il trimita prin Web Share API, daca browserul permite partajarea fisierelor.
In foaia de partajare iOS, alege Print pentru imprimare sau Save to Files pentru salvare.
Daca iOS/browserul nu permite partajarea fisierelor, apare linkul „Descarca / Deschide PDF”.
Comportamentul exact al foii de partajare si al imprimantei trebuie verificat pe iPhone-ul real. Testele locale nu pot certifica dialogurile native iOS.

FORMAT PDF
----------
- A4 portret.
- Titlu si data/ora emiterii.
- Produse grupate pe furnizori.
- Numerotare continua.
- Produsele sunt afisate pe un singur rand.
- Furnizorii neasociati sunt grupati separat.
- 50 de produse de test in 5 grupe de furnizori au incaput pe o pagina A4.
- Un test cu 130 de produse a generat 3 pagini A4.

TESTE EFECTUATE
---------------
- Sintaxa JavaScript: verificata cu node --check.
- ID-uri HTML duplicate: niciunul identificat.
- ID-uri necesare pentru functiile noi: prezente.
- Cheile localStorage cerute: pastrate.
- Implementarea veche bazata pe window.open()/window.print(): eliminata din fluxul PDF.
- PDF valid, deschis si verificat cu instrumente PDF locale.
- Test PDF 50 produse: 1 pagina A4.
- Test PDF 130 produse: 3 pagini A4.
- Logica produselor recente: verificata cu set de date de test.
- Nu a fost disponibil un iPhone fizic pentru testarea finala a meniului nativ Share/Print.

PUBLICARE
---------
Inlocuieste cele 6 fisiere in radacina aceluiasi repository GitHub Pages.
Pastreaza aceeasi adresa a aplicatiei.
Dupa publicare, inchide complet aplicatia instalata si redeschide-o pentru a prelua noul Service Worker.
Nu sterge datele Safari.


VERSIUNEA PREMIUM MOBILE
- Interfață simplificată pentru iPhone.
- Acțiunile principale sunt prioritizate; acțiunile secundare sunt grupate.
- Catalogul, comenzile, istoricul, vocea, exporturile și backupurile rămân disponibile.
- Cheile de stocare locală au fost păstrate pentru compatibilitate cu datele existente.
