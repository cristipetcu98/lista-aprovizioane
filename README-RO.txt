MATI MARKET – SMART RETAIL V4
============================

CONCEPT
Aplicație PWA pentru aprovizionare rapidă: cauți produsul, îl adaugi o singură dată, iar lista se grupează automat după furnizor. Nu există cantități în comanda standard.

FIȘIERE
- index.html – aplicația completă
- sw.js – cache și funcționare offline
- manifest.webmanifest – instalare PWA
- icon-192.png / icon-512.png – pictograme

MIGRARE V2/V3
Aplicația folosește aceleași chei de stocare ca versiunea veche:
- lista-aprovizionare-db
- lista-aprovizionare-history
- lista-aprovizionare-draft-v2

Migrarea automată citește catalogul și istoricul vechi de pe aceeași origine și nu șterge cheile vechi. Important: GitHub Pages trebuie să rămână la exact aceeași adresă (domeniu și cale) pentru ca Safari să ofere acces la localStorage-ul vechi. Înainte de actualizare, recomandă-se un Backup JSON din aplicația veche.

VOCE
Dacă browserul oferă SpeechRecognition/webkitSpeechRecognition, butonul microfon pornește recunoașterea în română. Textul este potrivit cu catalogul local și utilizatorul confirmă rezultatele înainte de adăugare. Dacă API-ul nu există, butonul mută cursorul în căutare, unde poate fi folosit microfonul tastaturii iOS.

Limită importantă: această versiune include recunoaștere vocală disponibilă nativ în browser și identificare locală, nu un model AI cloud conversațional. Safari iOS poate să nu ofere Web Speech API. Pentru AI cloud real este necesar un backend securizat și un serviciu de transcriere/înțelegere, cu chei și costuri configurate separat.

PDF
Exportul folosește fereastra nativă de imprimare a browserului și CSS A4. Nu este posibilă certificarea comportamentului pe iPhone Safari din testele locale; trebuie verificat pe dispozitiv. Pe iPhone, în previzualizarea de imprimare, folosește Partajare pentru a salva PDF în Fișiere.

TESTE ȘI LIMITĂRI
JavaScript trebuie verificat cu node --check. Testele de browser pot valida căutarea, stocarea și fluxul local, dar nu pot garanta permisiunile microfonului, recunoașterea vocală sau dialogul nativ de imprimare pe iPhone fără test fizic. Datele sunt locale dispozitivului și nu se sincronizează automat între telefoane.

PUBLICARE
Înlocuiește fișierele la rădăcina aceluiași repository GitHub Pages. Nu șterge datele Safari și nu schimba domeniul/calea aplicației. După actualizare, verifică produsele, furnizorii, istoricul și creează un Backup JSON nou.
