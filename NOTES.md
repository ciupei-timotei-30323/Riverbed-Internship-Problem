# NOTES — Ciupei Timotei

---

## 1. Bug-urile găsite

Pentru fiecare bug, scrie 2-3 propoziții:

### Bug #1
- Locatie: _main.py_,  linia 32
- L-am gasit examinand testul _test_create_event_returns_201_ si _main.py_
- Am adaugat `status_code=201` la linia 32.

### Bug #2
- Locatie: _storage.py_, linia 51
- L-am gasit apeland endpointul dupa care am observat ca primul event nu aparea
- niciodata in lista evenimentelor. Dupa care, pornind de la testul _test_list_events_includes_created_items_ am 
- examinat fiecare endpoint apelat si functiile din spate (din _storage.py_). Astfel am observat doi `+ 1`
- de care nu era nevoie.
- Am sters `+ 1` si am lasata linia ca `return all_events[offset : offset + limit]`.

### Bug #3
- Locatie: _storage.py_, functiile : _soft_delete_event_ , _list_events_
- Am testat endpointul de delete si am observat ca nu si ascundea event-urile sterse
- asa ca am inspectat mai indeaproape functiile folosite de acest endpoint si am constatat ca
- nu se verifica daca eventul are atributul de `deleted_at` sau nu.
- Am introdus un check in functia _soft_delete_event_ si _list_events_ pentru a verifica daca eventul are
- atributul `deleted_at` sau nu. In caz ca acesta e prezent, eventul este ignorat.

---

## 2. Endpoint-ul nou

- **Decizii de design:** (ce-ai considerat? ce ai ales și de ce?)
- **Cazuri edge pe care le-ai acoperit:**
- **Teste adăugate:** (ce verifică fiecare)

---

## 3. Folosirea AI-ului

Fii cinstit. Nu pierzi puncte dacă spui adevărul, dimpotrivă.

- **Ce ai folosit:** Gemini
- **Prompturi reprezentative folosite:** 
  1. _Should I add another list of deleted events or should I check for deleted events when fetching events from the memory?_
     - Context: Ma gandeam la o strategie pentru a gestiona evenimentele sterse.
     - M-a ajutat in strategia de gestionare a evenimentelor sterse.
  2. _how can I rewrite this so that if the id of the event doesn't exist, None is returned [Regarding the function soft_delete_event()]_
     - Context: Incercam sa rezolv un warning din partea IDE-ului 
     - Mi-a dat codul necesar pentru a scapa de eroarea respectiva.
  3. _In this method, what do those Query() calls do? Are they necesary?_
     - Context: Incercam sa inteleg unele metode si sintaxa fastapi
     - M-a lamurit de ce am nevoie si ce face `Query()`
- **Unde te-a ajutat cel mai mult:**
  - In a ajunge la curent cu sintaxa si mecanismele fastapi.
- **Unde te-a încurcat sau ți-a dat un răspuns greșit:** (foarte interesant pentru noi!)
- **Cum ai verificat ce-a generat:**
  - Fie am rulat API-ul si am verificat endpointurile ori am rulat testele.
- **Anexă opțională — export chat:** (dacă vrei, poți adăuga un export de chat relevant)

---

## 4. Ce-ai face cu mai mult timp

(Lista scurtă, 3-5 puncte. Arată-ne că ai văzut limitele actuale.)

---

## 5. Întrebări / observații

(Orice nu a fost clar, orice ai vrea să discuți cu noi.)
