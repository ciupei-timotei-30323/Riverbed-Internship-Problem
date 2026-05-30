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
- **Unde era:**
- **Cum l-am găsit:**
- **Cum l-am fixat:**

---

## 2. Endpoint-ul nou

- **Decizii de design:** (ce-ai considerat? ce ai ales și de ce?)
- **Cazuri edge pe care le-ai acoperit:**
- **Teste adăugate:** (ce verifică fiecare)

---

## 3. Folosirea AI-ului

Fii cinstit. Nu pierzi puncte dacă spui adevărul, dimpotrivă.

- **Ce ai folosit:** (ChatGPT / Cursor / Copilot / altele)
- **Prompturi reprezentative folosite:** (scrie prompturile pe care le consideri relevante + context scurt: la ce te-au ajutat)
- **Unde te-a ajutat cel mai mult:**
- **Unde te-a încurcat sau ți-a dat un răspuns greșit:** (foarte interesant pentru noi!)
- **Cum ai verificat ce-a generat:**
- **Anexă opțională — export chat:** (dacă vrei, poți adăuga un export de chat relevant)

---

## 4. Ce-ai face cu mai mult timp

(Lista scurtă, 3-5 puncte. Arată-ne că ai văzut limitele actuale.)

---

## 5. Întrebări / observații

(Orice nu a fost clar, orice ai vrea să discuți cu noi.)
