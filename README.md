https://biedronm.github.io/rivalcore/#konkurencja
# RivalCore 31.7

RivalCore to wewnętrzne narzędzie BeDigital do analizy reklam marki i jej konkurencji. Zbiera publiczne dane z bibliotek reklam (Meta, Google, TikTok, LinkedIn), liczy z nich aktywność, przekaz, oferty, odbiorców i szacowany koszt, a potem składa wszystko w raport dla klienta (HTML, PDF, PowerPoint, Excel, plik dla AI).

To jeden plik `index.html`. Nie ma serwera ani instalacji. Otwierasz go w przeglądarce, łączysz źródła, wpisujesz marki i klikasz „Analizuj”.

- Wersja: **31.7** (27.11.2026), w kodzie `RCV = "31.7"`.
- Testy: 54/54 w 31.4. Zmiany 31.5–31.7 są naniesione na zbudowany `index.html`, nie na źródła; sprawdzone w przeglądarce na danych testowych (rozdział 13, „Wersje 31.5–31.7 a źródła”). Pełny zestaw testów trzeba uruchomić po przeniesieniu ich do `src/`.
- Wdrożenie docelowe: `index.html` w repozytorium `biedronm/rivalcore`, adres `https://biedronm.github.io/rivalcore/`.
- **Stan wdrożenia:** na GitHub Pages nadal jest 29.1 (bez TikToka i LinkedIna). Wersje 30.0–31.7 są gotowe w paczkach i czekają na zgodę BeDi na wypchnięcie.

## Spis treści

1. [Co narzędzie robi](#1-co-narzędzie-robi)
2. [Źródła danych](#2-źródła-danych)
3. [Uruchomienie i wdrożenie](#3-uruchomienie-i-wdrożenie)
4. [Połączenia: jednorazowa konfiguracja](#4-połączenia-jednorazowa-konfiguracja)
5. [Ekran startowy: pięć kroków](#5-ekran-startowy-pięć-kroków)
6. [Wyniki](#6-wyniki)
7. [Raporty i eksporty](#7-raporty-i-eksporty)
8. [Jak liczymy](#8-jak-liczymy)
8a. [Kategoria produktu](#8a-kategoria-produktu)
8b. [Gotowe do wysłania](#8b-gotowe-do-wysłania)
8c. [Komentarze, kolejność sekcji, raport danych](#8c-komentarze-kolejność-sekcji-raport-danych)
9. [Stany źródeł: BŁĄD, BRAK DANYCH, NIEPEŁNE DANE, BRAK DOSTĘPU](#9-stany-źródeł)
10. [Prywatność i klucze](#10-prywatność-i-klucze)
11. [Znane ograniczenia: BŁĄD vs BRAK FUNKCJI](#11-znane-ograniczenia-błąd-vs-brak-funkcji)
12. [Rozwiązywanie problemów](#12-rozwiązywanie-problemów)
13. [Kod źródłowy, budowanie i testy](#13-kod-źródłowy-budowanie-i-testy)
14. [Historia wersji (skrót)](#14-historia-wersji-skrót)

---

## 1. Co narzędzie robi

RivalCore odpowiada na pytania, które zadaje klient agencji: kto z konkurencji reklamuje się najmocniej, gdzie, czym i za ile.

- **Porównanie z konkurencją** albo **raport jednej marki** (wybór w kroku 3).
- **Kategoria produktu** (od 31.5): analiza tylko reklam jednej kategorii, np. telewizorów u marek, które reklamują 50 produktów. Rozdział 8a.
- **Aktywność:** liczba reklam, aktywne, nowe, długość życia, evergreeny, tempo testowania, fale startów, kampanie.
- **Przekaz i oferty:** argumenty reklam, rabaty i fale rabatów, ceny, CTA, ton, najczęstsze słowa (tylko z tekstów Mety, bo Google tekstów nie publikuje).
- **Odbiorcy:** wiek, płeć, kraje, targetowanie, luki demograficzne i mapa wolnych pól.
- **Szacowany koszt i udział w głosie:** w każdym kanale osobno i we wszystkich kanałach razem, z widełkami i przedziałami pewności.
- **Strategia:** zmiany strategii w czasie, indeks testowania, „dokłada czy wymienia”, rozjazd Meta–Google, rekomendacje w formacie obserwacja → działanie → efekt → jak zmierzyć za 30 dni, brief kreatywny.
- **Reklamy:** galeria z filtrami, porównanie do 4 reklam obok siebie, oś czasu emisji (Gantt).
- **Wyniki kont Google Ads klientów** (skrypt MCC + arkusz Google), osobny moduł „Wyniki”.

Narzędzie pokazuje, co i jak intensywnie reklamuje konkurencja. Nie pokazuje, jak skuteczne są te reklamy (CTR, sprzedaż, ROAS), bo żadna biblioteka tego nie publikuje.

## 2. Źródła danych

Każda platforma działa samodzielnie. Można analizować np. sam LinkedIn.

- **Meta** (Facebook, Instagram, Messenger, Audience Network): oficjalne Meta Ad Library API (`graph.facebook.com`). Daje reklamy, daty, teksty, platformy, a dla emisji w UE zasięg, wiek i płeć, kraje, płatnika. Wydatków reklam komercyjnych nie daje.
- **Google** (Search, YouTube, sieć reklamowa): publiczny zbiór Google Ads Transparency Center w BigQuery (`bigquery-public-data.google_ads_transparency_center`). Daje kreacje, formaty, powierzchnie, kraje i zakresy wyświetleń w EOG i Turcji od 1.03.2023. Tekstów reklam i wydatków nie daje.
- **TikTok:** Commercial Content API (biblioteka reklam TikToka), przez pośrednika. Tylko reklamy emitowane w UE/EOG, Wielkiej Brytanii i Szwajcarii. Zasięg w przedziałach.
- **LinkedIn:** Ad Library API, przez tego samego pośrednika. Wymaga zatwierdzenia aplikacji przez LinkedIna. Wyświetlenia w przedziałach, tylko dla emisji w UE.
- **Konta Google Ads klientów:** skrypt Google Ads w koncie MCC zapisuje dane do arkusza Google, RivalCore czyta arkusz (albo plik .xlsx/.csv).

Obszar dla Google: Centrum przejrzystości nie ma dowolnych zestawów krajów. Jeśli wśród wybranych krajów jest Polska, Google bierze Polskę; przy jednym kraju EOG ten kraj; przy kilku krajach albo „Cały świat” cały EOG. Narzędzie pokazuje to pod wyborem krajów i ostrzega, gdy obszar Google różni się od Mety.

## 3. Uruchomienie i wdrożenie

### Skąd otwierać

- **Docelowo:** `https://biedronm.github.io/rivalcore/` (GitHub Pages).
- **Lokalnie** (dopóki 31.7 nie jest w repo): w folderze z `index.html` uruchom `python3 -m http.server 8000` i otwórz `http://localhost:8000`.
- **Nie z dysku** (`file://`): logowanie Google nie działa, a pośrednik TikToka i LinkedIna odrzuca takie zapytania. Sama Meta i wczytana analiza z pliku działają.

Przeglądarka: Chrome albo Edge.

### Wdrożenie na GitHub Pages

1. Zbuduj `dist/index.html` (rozdział 13) albo weź gotowy `index.html` z paczki.
2. Podmień `index.html` w katalogu głównym repo `biedronm/rivalcore`. Źródła mogą leżeć obok, np. w folderze `app/`.
3. Settings → Pages → branch `main`, katalog główny.
4. Sprawdź, że `https://biedronm.github.io` jest w „Autoryzowanych źródłach JavaScript” klienta OAuth Google i w `ALLOWED_ORIGINS` pośrednika.

Do repo trafia tylko `index.html` (i ewentualnie źródła). Żadnych kluczy, tokenów ani ID kont.

### Zawartość paczki 31.7

- `index.html`: gotowe narzędzie 31.7 (31.4 + kategoria produktu + nowy raport, lista „Gotowe do wysłania”, komentarze, kolejność sekcji, raport danych).
- `kategoria-31.5.js`, `apply-31.5.py`, `raport-31.6.js`, `apply-31.6.py`, `komentarze-kolejnosc-31.7.js`, `apply-31.7.py`: moduły i listy miejsc wpięcia, do przeniesienia do źródeł (rozdział 13). Nakłada się je po kolei: 31.5 → 31.6 → 31.7.

Pozostałe pliki pochodzą z paczki 31.4:

- `rivalcore-31.4-zrodla.zip`: kod źródłowy z testami.
- `worker/rivalcore-proxy.js`: pośrednik TikTok + LinkedIn (Cloudflare Worker). `worker/tiktok-proxy.js` to starszy pośrednik tylko dla TikToka, działa dalej.
- `test-linkedin.mjs`: skrypt do sprawdzenia parametrów LinkedIna na prawdziwym tokenie.
- `INSTRUKCJA-TikTok-LinkedIn.md`: instrukcja krok po kroku dla pośrednika, TikToka i LinkedIna.
- `przyklad-raportu-31.4.html`: przykładowy raport HTML na danych testowych.
- `zrzuty/przed`, `zrzuty/po`: ekrany przed i po zmianach 31.4 (ciemny, jasny, telefon).
- `README-archiwum-do-31.4.md`: poprzednie README z pełnym dziennikiem zmian.

## 4. Połączenia: jednorazowa konfiguracja

### Meta (token)

1. Potwierdź tożsamość na `facebook.com/ID`. Bez tego API zwraca błąd 10.
2. Zaakceptuj dostęp na `facebook.com/ads/library/api`.
3. Na `developers.facebook.com` utwórz aplikację (typ „Inne” / „Firma”), niczego w niej nie konfigurujesz.
4. W Graph API Explorer wygeneruj User Token, a w Access Token Debugger przedłuż go do ok. 60 dni.
5. W RivalCore, krok 2, wklej token i kliknij „Sprawdź połączenie”.

Weryfikacja, aplikacja i token muszą być z tego samego konta. Token zapisuje się w przeglądarce tylko po zaznaczeniu „Zapamiętaj token”.

### Google (BigQuery i logowanie)

1. Projekt Google Cloud z włączonym **BigQuery API** i **Google Sheets API**. Zapisz ID projektu (nie nazwę).
2. Bez karty działa piaskownica BigQuery: 1 TB zapytań miesięcznie za darmo. Jedna analiza przetwarza ok. 30–40 GB, czyli ok. 25 analiz miesięcznie.
3. Ekran zgody OAuth (Google Auth Platform → Branding) i konta zespołu jako użytkownicy testowi.
4. Klient OAuth typu **Aplikacja internetowa**. Autoryzowane źródła JavaScript: `https://biedronm.github.io` i `http://localhost:8000` (bez ścieżki i ukośnika). Przekierowania puste. Sekretu klienta nie używamy nigdzie.
5. W RivalCore wpisz ID projektu i ID klienta, „Połącz z Google”, potem „Test BigQuery”. Logowanie trwa godzinę i nie zapisuje się.
6. Każda osoba potrzebuje roli **Użytkownik zadań BigQuery** (`roles/bigquery.jobUser`).

Developer tokena Google Ads nie potrzeba. Bezpośrednie Google Ads API wymagałoby zatwierdzonego tokena i serwera (brak CORS), dlatego wyniki kont idą przez skrypt.

### Konta Google Ads klientów (skrypt MCC)

1. Utwórz pusty arkusz Google i udostępnij go zespołowi.
2. Google Ads → konto MCC → Narzędzia → Działania zbiorcze → Skrypty → nowy skrypt.
3. W RivalCore → Wyniki skopiuj „Skrypt Google Ads”, wklej, podmień `SHEET_URL` (opcjonalnie `ACCOUNT_LABEL`, `DAYS`, domyślnie 90).
4. Uruchom i ustaw harmonogram dzienny. Skrypt zapisuje zakładki `RC_dane`, `RC_frazy`, `RC_info`.
5. W RivalCore → Wyniki wklej link do arkusza i kliknij „Wczytaj z arkusza”.

Limit skryptu to 30 minut, co wystarcza na kilkadziesiąt kont. Przy dużym MCC podziel konta etykietą na dwa skrypty.

### Pośrednik dla TikToka i LinkedIna (Cloudflare Worker)

TikTok i LinkedIn nie przyjmują zapytań prosto ze strony na innej domenie (brak CORS), więc idą przez mały pośrednik.

1. `dash.cloudflare.com` → Workers & Pages → Create → Worker, np. `rivalcore-proxy` → Deploy.
2. Edit code → wklej cały `worker/rivalcore-proxy.js` → Deploy. Jeśli masz pośrednika z 30.0, podmień kod, adres zostaje.
3. Settings → Variables and Secrets → `ALLOWED_ORIGINS` = `https://biedronm.github.io` (lokalnie dopisz po przecinku `http://localhost:8000`) → Deploy.
4. Adres Workera wklej w RivalCore w polu „Adres pośrednika” (zapamiętuje się).

Co pośrednik robi i czego nie robi:

- przepuszcza tylko ścieżki biblioteki reklam TikToka (POST) i `GET /rest/adLibrary` LinkedIna,
- tylko ze stron z `ALLOWED_ORIGINS`, inne dostają 403,
- **nie ma w sobie żadnych kluczy** i niczego nie zapisuje; klucze przychodzą z karty przeglądarki przy każdym zapytaniu.

Sekret TikToka przechodzi przez pośrednika w drodze do TikToka, dlatego Worker ma stać na koncie agencji, nie na cudzym.

### TikTok

Aplikacja w TikTok for Developers z produktem Commercial Content API (zakres `research.adlib.basic`). Client key i Client secret wklejasz w kroku 2 przy każdej sesji. Limit to ok. 1000 zapytań dziennie, licznik widać pod ustawieniami TikToka. Po testach warto wygenerować nowy Client secret.

### LinkedIn

Aplikacja w LinkedIn Developers powiązana ze stroną firmy BeDigital, z zatwierdzonym produktem Ad Library API. W RivalCore wpisujesz **token OAuth** (nie Client ID ani Client Secret), wygenerowany w Auth → OAuth 2.0 tools → Token generator. Ważny ok. 60 dni. Pole „Wersja API” zostaw puste (domyślnie 202510).

Do czasu zatwierdzenia LinkedIn pokazuje stan BRAK DOSTĘPU, a pozostałe platformy liczą się normalnie. Pełna instrukcja wniosku: `INSTRUKCJA-TikTok-LinkedIn.md`.

## 5. Ekran startowy: pięć kroków

Pasek kroków u góry, do każdego kroku wracasz jednym kliknięciem.

### Krok 1. Co analizujemy

Zaznaczasz platformy: Meta, Google, TikTok, LinkedIn. Każda działa samodzielnie. Znaki platform to proste piktogramy.

### Krok 2. Połączenia

Pola tylko dla wybranych platform, przy każdej „Sprawdź połączenie”. Klucze i tokeny zostają w pamięci karty i nie trafiają do zestawów ani plików.

### Krok 3. Marki, kraje, okres

- **Rodzaj raportu:** „Porównanie z konkurencją” albo „Raport jednej marki”. W raporcie jednej marki znikają pola konkurentów i porównania. Wpisani konkurenci wracają po przełączeniu z powrotem.
- **Twoja marka** jest wyróżnionym polem, konkurenci są w osobnych polach (same nazwy). Przy każdej marce link „Znajdź w Bibliotece Reklam” i linki do bibliotek pozostałych platform.
- „Wklej listę” przyjmuje konkurentów z Excela. „Odkryj konkurentów po frazie” jest zwinięte przy polach konkurentów.
- **Kraje:** duży przycisk „Polska” (domyślnie), potem „UE + UK”, „Cały świat”, „Wyczyść”. Reszta krajów w zwijanej sekcji „Inne kraje”.
- **Okres:** przyciski „Ostatnie 12 miesięcy”, „Ostatnie pół roku” (domyślnie), „Ostatnie 3 miesiące”, „Ostatni miesiąc”, „Bieżący rok”, „Bieżący kwartał”. Pozostałe okresy w liście. 7 i 14 dni są oznaczone „tylko Meta” i nie ma ich w okresie Google.
- Objaśnienia są w ikonach (i) przy polach, nie w długich podpisach.
- **„Zawęź do kategorii produktu”** (zwinięte, od 31.5): gotowa lista albo własne słowa kategorii. Rozdział 8a.

Kraje i okres są wspólne dla wszystkich platform, żeby porównanie było uczciwe.

### Krok 4. Ustawienia platform

Platforma po platformie („Dalej: Google”, „Dalej: LinkedIn”…). Każda ma dwie części.

- **A. Ustawienia ogólne platformy:** okres platformy, stawki, limity pobierania.
- **B. Marka po marce:** konta na tej platformie i zwinięte „Własne ustawienia tej marki”. Puste pole = ustawienie ogólne (na szaro), zmienione pola są oznaczone „zmienione”, „Przywróć ogólne” czyści markę.

**Meta w 31.4:**

- na wierzchu **branża** (stawki przeliczają się od razu),
- pod nią pole **„Raport z estymacjami i modelowaniem wydatków”**. Dopiero ono odsłania CPM, częstotliwość, sezon, stawki formatów i marek oraz kalibrację,
- bez zaznaczenia szacunek kosztu nadal się liczy, ze stawek wybranej branży (pola są tylko schowane),
- „Od ilu dni aktywności reklamę uznajemy za stałą (evergreen)?”, domyślnie 30 dni,
- limit reklam i „Tendencje i porównania” z objaśnieniem przy samym polu,
- wersja Graph API jest w „Więcej ustawień pobierania Mety”.

Co marka może nadpisać (reszta jest wspólna dla platformy):

- Meta: okres, limit reklam, CPM min/max, częstotliwość min/max,
- Google: CPM min/max osobno dla tekstu, grafiki i wideo (okres jeden dla całego Google, bo to jedno zapytanie do BigQuery),
- TikTok: strony wyników, CPM, częstotliwość,
- LinkedIn: strony wyników, CPM.

Zmiana stawki jednej marki przelicza tylko tę markę, bez ponownego pobierania.

### Krok 5. Podsumowanie

Co zostanie pobrane, z jakim okresem, które połączenia są gotowe i czy analiza jest zawężona do kategorii. Tu jest przycisk „Analizuj”. Pod nim pasek postępu dla każdego źródła i zużycie dziennego limitu TikToka.

### Zestawy klientów

Zestaw zapamiętuje klienta, marki, okres, kraje, włączone źródła, ustawienia, nadpisania marek i kategorię produktu (zestaw bez kategorii ją wyłącza). Przyciski zestawów są pogrupowane po klientach i wczytują zestaw jednym kliknięciem. „Eksport / Import” przenosi zestawy między komputerami. Klucze nigdy nie trafiają do zestawu.

### Zapis i wczytanie analizy

„Zapisz analizę” zapisuje dane, ustawienia, ręczne korekty, kategorię produktu i ręczne przypisania reklam do grup do pliku `.json`. „Wczytaj analizę” otwiera go później bez tokenów i bez pobierania, z banerem „stan danych na …”.

## 6. Wyniki

Na górze poziomy kanałów (Meta, Google, TikTok, LinkedIn, „Kanały razem”), niżej Porównanie albo konkretna marka i zakładki tematyczne. Wstążkę zakładek przewija się w bok kółkiem myszy albo strzałkami po bokach. Każda zakładka zaczyna się od najważniejszego wniosku.

- **Zakładki marki:** Przegląd, Oś czasu, Prawdopodobny budżet, Kreacje i testy, Kampanie, Strategia i testy, Przekaz, Co przeżywa, Brief kreatywny, Oferty i ceny, Odbiorcy, Kalendarz, Zmiany, Społeczne i polityczne.
- **Zakładki porównania:** Wnioski i rekomendacje, Udział w głosie (z symulatorem budżetu), Prawdopodobny budżet, Kreacje i testy, Strategia i testy, Przekaz i oferty, Odbiorcy, Kalendarz, Co przeżywa, Wojna rabatowa, Mapa wolnych pól, Brief kreatywny, Rankingi i indeks.
- **Google:** udział w wyświetleniach, budżet, formaty, powierzchnie, odbiorcy, kraje, kreacje, kalendarz, dla porównania i dla każdej marki.
- **Kanały razem:** udział w głosie ze wszystkich kanałów, tabela marek w kanałach, wspólna oś czasu, rozjazd Meta–Google.
- **Reklamy:** galeria z filtrami (platforma, format, kraj, aktywne / zakończone, marka), wyszukiwarka, porównanie do 4 reklam, oś czasu emisji.

Narzędzia obok wyników:

- **Filtry wyników** (okres emisji, platforma, format, tylko aktywne, próg evergreen) przeliczają wszystko bez pobierania.
- **Kategoria produktu** (karta pod filtrami, w widoku Meta i LinkedIn): ustawienia kategorii, tabela marek (ile reklam w każdej grupie, ile w analizie) i lista reklam do ręcznego przypisania. Rozdział 8a.
- **Sandbox korekt:** podmieniasz CPM, częstotliwość, korektę zasięgu albo wpisujesz realny budżet marki i klikasz „Przelicz”. Póki korekty są włączone, narzędzie i każdy eksport mówią o tym w ramce.
- **Ręczne korekty:** lista wykrytych rabatów do odrzucenia lub uznania, lista argumentów do poprawy, słownik branżowy z własnymi frazami. Korekty wchodzą do wszystkich wyników i eksportów.
- **Źródła raportów i analiz** (dawniej „Lupa detektywa”): oznacza bloki jako czyste dane, obliczenia, poszlaki albo dedukcję. Domyślnie włączone, definicje w rozwijanej sekcji. Dymki „Skąd to?” przy liczbach pokazują rachunek na danych tej analizy.
- **Migawki:** zapisują się po każdej analizie, zakładka „Zmiany” pokazuje różnice przy kolejnej (najwcześniej następnego dnia).
- **Tryb „dla klienta”:** ukrywa klucze, pośredników, oznaczenia źródeł i metodologię, zostawia wyniki i wnioski.

## 7. Raporty i eksporty

Wszystko jest w menu „Eksport i zapis” przy nagłówku „Wyniki”. Pozycja bez danych w sesji jest wyszarzona i mówi, czego brakuje.

- **Raport HTML:** jeden samodzielny plik do wysłania klientowi. Wygląd „jak aplikacja” (domyślny) albo „jak wydruk” (kartki A4). Od 31.6:
  - **okładka** to odpowiedź w jednym zdaniu i cztery kafelki „W 5 sekund”: udział w głosie, pozycja w wydatkach, luka do lidera (albo przewaga nad nr 2) i tempo nowych kreacji, z kolorowym statusem. Uwaga o zasięgu w obszarze jest zwinięta pod jednym przyciskiem,
  - raport **otwiera się na „Raporcie w skrócie”**, połączonym z „Najważniejszymi wnioskami” (bez powtórki kafelków z okładki). Spis treści jest tylko w menu bocznym,
  - **kolejność jak historia:** 1 · Gdzie jesteś (skrót, udział w głosie, budżet, rankingi), 2 · Co robi konkurencja (kreacje, strategia, przekaz, rabaty, odbiorcy, kalendarz, galeria), 3 · Co z tym zrobić (rekomendacje, brief), potem Profile marek i O raporcie („Jak czytać ten raport”, metodologia),
  - **profil marki** to jedna sekcja na markę z zakładkami (Przegląd, Oś czasu, Budżet…) zamiast 12 osobnych sekcji. Stare linki do tematów (np. `#b-2-budget`) otwierają profil na właściwej zakładce,
  - **nagłówki sekcji to wnioski** z danych analizy, np. „LG Electronics wydaje ~22 tys. zł/mies. więcej niż Samsung Polska”; nazwa sekcji jest nad nimi małym drukiem,
  - pasek ma jeden przełącznik **„Skrót dla zarządu / Pełny raport”**. Skrót prowadzi krok po kroku przyciskiem „Dalej” (dawne „Obejrzyj w 5 minut”),
  - rekomendacje są kartami na całą szerokość, a przyciski paska mają czytelny tekst także po najechaniu i w jasnym motywie,
  - zostają: sortowanie tabel, „Kopiuj link” (klawisz L), wyszukiwarka, motyw jasny/ciemny, symulator budżetu, dymki „skąd ta liczba”, hasło (AES-256-GCM) i przypomnienie o aktualności danych.
- **Komentarze, kolejność sekcji, pełny raport HTML i raport danych (bez wniosków):** rozdział 8c.
- **Raport PDF:** przez okno drukowania („Zapisz jako PDF”, skala 100%, „Grafika tła”). **Domyślnie skrót dla klienta** (ok. 15–20 stron przy 2 markach); „Pełny raport” i „Dla zarządu” to jedno kliknięcie. Od 31.6: okładka z kafelkami „W 5 sekund”, bez osobnej strony wniosków przy stronie „Raport w skrócie”, porównania w kolejności historii z nagłówkami-wnioskami, rekomendacje po dowodach i na całą szerokość strony, rodzaj danych jako mała etykieta w rogu bloku zamiast kolorowej ramki. Strona „Co jest w raporcie” tylko przy zaznaczonej opcji w „Dodatkowe”. Działa bez internetu.
- **Prezentacja PPTX:** do 15 edytowalnych slajdów (natywne tabele i wykresy), presety, motyw ciemny lub jasny, notatki prelegenta z zastrzeżeniami. Slajd bez danych sam się pomija.
- **Excel:** ponad 20 arkuszy, same wartości, **bez formuł**. Nagłówki w stylu BeDigital (#0B0B0B / #EEEEEE), przypięty pierwszy wiersz. Osobno Meta, Google i oba kanały.
- **Plik dla AI (.md):** prompt i dane do wklejenia w Claude albo ChatGPT. Prompt każe opierać się wyłącznie na danych z pliku i odróżniać dane od szacunków.
- **Pakiet do strategii (.zip):** wykresy PNG z logo, `fakty-do-strategii.csv`, pełny Excel, `CZYTAJ-MNIE.md`.

Kiedy co: HTML do czytania na ekranie i telefonie, PDF do archiwum i druku, PPTX na spotkanie.

## 8. Jak liczymy

Wszystkie kwoty to **szacunki**. Żadna biblioteka reklam nie publikuje wydatków reklam komercyjnych. Szacunki służą do porównania marek między sobą, wszystkie marki liczymy tą samą metodą.

### Środek widełek: średnia geometryczna, we wszystkich kanałach

Stawki podajemy jako widełki (min–max). Środek widełek to średnia geometryczna: √(min × max).

- Przykład: CPM 10–25 zł daje środek 15,81 zł (średnia arytmetyczna dałaby 17,50 zł).
- Od 30.0 tak samo liczy Google (wcześniej brał średnią arytmetyczną). To zmiana celowa: szacowany koszt środkowy Google spadł przez nią o kilka do kilkunastu procent, dolne i górne widełki się nie zmieniły. Powód: jeden wzór dla wszystkich kanałów i lepsze dopasowanie do szerokich widełek.
- Widełki kosztu: dolne końce danych razy dolne stawki i górne razy górne.

### Meta

- **Koszt = zasięg × częstotliwość × CPM ÷ 1000.** Domyślnie CPM 10–25 zł i częstotliwość 1,3–2,0 (albo stawki wybranej branży).
- **Zasięg z wybranego obszaru:** Meta podaje zasięg łącznie dla całej UE, więc mnożymy go przez udział wybranych krajów w odbiorcach reklamy. Reklama bez rozbicia krajów dostaje udział całej marki. Marka bez żadnego rozbicia zostaje nieprzeskalowana i jest oznaczona.
- **Dwie liczby budżetu, obie poprawne:**
  - prognoza (zakładka Meta): dzisiejszy zasięg dzienny aktywnych reklam × 30 dni × częstotliwość × CPM ÷ 1000, czyli „ile wyda w najbliższym miesiącu, jeśli nic nie zmieni”,
  - średnia z okresu (Kanały razem, okładka raportu): koszt całego okresu ÷ liczba dni × 30, czyli „ile wydawała w okresie”. To jedyna baza wspólna z Google, bo dla Google prognozy policzyć się nie da.
- **Kolejność stawek:** CPM formatu marki → CPM marki → stawki ogólne platformy (branża albo kalibracja). Puste pole dziedziczy wyżej, błędne pole jest pomijane i oznaczone na czerwono.
- **Kalibracja:** wpisujesz realny wydatek znanej marki, narzędzie liczy efektywny CPM = wydatek ÷ (szacowane wyświetlenia ÷ 1000) i ustawia CPM ±15% dla wszystkich marek. Rejestr trafności od 3 kont w branży mierzy błąd szacunku.
- **Okres:** liczą się reklamy emitowane choć jeden dzień w okresie. Meta usuwa reklamy komercyjne ok. rok po końcu emisji, więc okres starszy niż ok. 12 miesięcy jest zaniżony i nie liczymy dla niego zmian procentowych.

### Google

- **Koszt = wyświetlenia ÷ 1000 × CPM formatu.** Domyślnie tekst 40–120 zł, grafika 4–14 zł, wideo 10–30 zł. Wyświetlenia to zakresy Google; kreacje z otwartym górnym zakresem liczymy dolną wartością.
- **Horyzont kompletnych danych** (skala dni): Google dosyła statystyki partiami, więc liczymy do najpóźniejszego dnia, do którego sięga co najmniej połowa ostatnio aktywnych kreacji. Ma wyłącznik w ustawieniach Google.
- **Granica danych** (skala tygodni): ostatni tydzień, w którym suma wyświetleń wszystkich analizowanych marek sięga co najmniej 15% mediany tygodnia. Po nim linia Google jest urwana, a odcinek zakreskowany jako „brak danych, nie zero”. Nie ma wyłącznika, bo to fakt o zbiorze.

### TikTok

- Zasięg w przedziałach (np. „1M-5M”). Środek przedziału to średnia geometryczna końców; przy „0-1K” połowa górnej granicy; przy „100K+” dolna granica.
- Zasięg reklamy rozkładamy równo na dni emisji i bierzemy część z okresu analizy.
- **Koszt = zasięg × częstotliwość × CPM ÷ 1000**, domyślnie CPM 8–22 zł i częstotliwość 1,5–3.
- API nie filtruje po ID reklamodawcy, więc szukamy po nazwie i zostawiamy reklamy z wybranych kont.
- Domyślnie 20 stron po 10 reklam i 10 zapytań o szczegóły na markę. Dane od 2 dni wstecz do roku wstecz.

### LinkedIn

- Wyświetlenia w przedziale za cały czas emisji. Rozkładamy je równo na dni emisji, bierzemy dni z okresu, przy wybranych krajach mnożymy przez udział tych krajów.
- **Koszt = wyświetlenia × CPM ÷ 1000**, przeliczony na miesiąc. Domyślnie CPM 40–120 zł.
- Reklama jest „aktywna”, gdy ostatnie wyświetlenie było najwyżej 3 dni przed datą danych (LinkedIn nie podaje statusu).
- 25 reklam na stronę wyników.

### Udział w głosie

- W kanale: udział marki w sumie szacowanych wydatków, aktywnych reklam albo zasięgu wszystkich analizowanych marek.
- **Wszystkie kanały razem:** dla każdej marki sumujemy szacowany miesięczny koszt (średnia z okresu) ze wszystkich kanałów, a udział = suma marki ÷ suma wszystkich marek. Kanał, w którym rynek wydaje więcej, waży więcej; wagi kanałów są pokazane. Obok wariant z równymi wagami kanałów.
- Wymaga co najmniej dwóch kanałów.

### Inne wskaźniki

- **Evergreen:** reklama emitowana co najmniej X dni (domyślnie 30).
- **Wyłączane ≤ 7 dni:** odsetek zakończonych reklam, które działały najwyżej 7 dni. Miara intensywności testów.
- **Indeks aktywności 0–100** (tylko Meta): skala 25%, zasięg 25%, świeżość 15%, testowanie 15%, regularność 10%, różnorodność 10%.
- **Argumenty, rabaty, ceny, ton:** reguły słownikowe, bez AI. Dlatego są listy do ręcznej korekty.
- **Test A/B:** ten sam tekst albo nagłówek i domena, start w odstępie do 7 dni. To poszlaka, nie pewność.
- **Wolne pole:** grupa wieku i płci od 5% zasięgu, w której argument używany w kategorii (od 8%) pojawia się co najmniej o połowę rzadziej.

## 8a. Kategoria produktu

Do analizy marek, które reklamują wiele produktów, a klienta interesuje jedna kategoria (np. telewizory u Samsunga, LG i Philipsa). Zawężenie działa po pobraniu, więc można je włączyć, zmienić albo wyłączyć w wynikach bez ponownego pobierania.

### Ustawienie

W kroku 3 („Zawęź do kategorii produktu”) albo w wynikach, w karcie „Kategoria produktu”:

1. Zaznacz „Analizuj tylko reklamy jednej kategorii produktu”.
2. Wybierz gotową listę (Telewizory, Smartfony, Pralki i suszarki, Lodówki, Laptopy, Odkurzacze) albo wpisz własne słowa.
3. **Słowa kategorii**, po przecinku:
   - `telewizor*` = dowolna końcówka (telewizora, telewizorów),
   - pojedyncze słowo od 6 liter dostaje końcówkę samo: `pralka` łapie też „pralki” i „pralkę”,
   - krótkie słowa (`tv`, `oled`, `4k`) liczą się tylko jako całe słowo,
   - wielkość liter i polskie znaki nie mają znaczenia, frazy wielowyrazowe działają (`smart tv`, `uchwyt* na telewizor*`).
4. **Słowa innych produktów (wykluczające):** produkty, których nie analizujesz, i frazy, które tylko wyglądają na kategorię (`uchwyt* na telewizor*`, `tv plus`, `apple tv`). Wykluczenie „zjada” swój fragment tekstu, więc „Samsung TV Plus” nie liczy się jako „tv”.
5. Wybierz, co wchodzi do analizy: zawsze „dotyczy”, opcjonalnie „wspomina” i „trudne do określenia”.

### Cztery grupy

Każda reklama dostaje jedną grupę (reguły słownikowe, bez AI):

- **Dotyczy kategorii:** są słowa kategorii, a słów innych produktów nie ma albo jest ich co najmniej dwa razy mniej.
- **Wspomina kategorię:** kategoria obok innych produktów, np. „Black Friday: telewizory, pralki, lodówki”, „soundbar do Twojego telewizora”.
- **Trudne do określenia:** reklama bez tekstu (sama grafika albo wideo), reklama katalogowa z szablonem `{{product.name}}`, tekst krótszy niż ok. 15 liter albo tekst, który nie wymienia żadnego produktu (np. reklama wizerunkowa).
- **Nie dotyczy:** brak słów kategorii, a tekst wymienia inne produkty.

Słowo liczy się najwyżej 3 razy w jednej reklamie.

### Ręczne przypisanie

Karta „Kategoria produktu” w wynikach:

- **tabela marek:** ile reklam marki jest w każdej grupie i ile weszło do analizy,
- **lista reklam** z zakładkami grup. Domyślnie otwiera się „Trudne do określenia”, bo tam są decyzje do podjęcia,
- przy każdej reklamie tekst z podświetlonymi słowami kategorii, link do biblioteki reklam, powód decyzji automatu i cztery przyciski grup. Przerywana ramka oznacza przypisanie ręczne, „Cofnij” przywraca automat,
- **przypisanie hurtowe:** „Wszystkie widoczne teksty przypisz do…”. Działa na to, co jest na liście po filtrze marki i wyszukiwarce,
- reklamy z tym samym tekstem są w jednym wierszu, a decyzja obejmuje wszystkie, także u innych marek,
- przypisania zapisują się w przeglądarce osobno dla każdej kategorii (według nazwy) i w pliku „Zapisz analizę”.

Każda zmiana od razu przelicza wszystkie zakładki, udział w głosie i eksporty.

### Gdzie działa, a gdzie nie

- **Meta:** zawężenie po tekście reklamy, nagłówku, opisie linku i ścieżce linku.
- **LinkedIn:** po tekście i nagłówku reklamy.
- **Google:** bez zawężenia. Zbiór w BigQuery nie ma tekstów reklam.
- **TikTok:** bez zawężenia. Biblioteka podaje co najwyżej tytuł, i to tylko dla reklam pobranych ze szczegółami.
- **Kanały razem:** udział w głosie zestawia Metę zawężoną do kategorii z Google dla całej marki. Narzędzie ostrzega o tym ramką.

### Jak to widać w raportach

- Ramka „Zawężone do kategorii: …” w wynikach, w raporcie HTML/PDF (okładka i metodologia) i w „Kanałach razem”.
- Nagłówek marki ma linię „w analizie X z Y reklam marki”, a podpis filtra „kategoria: …”. Ten podpis trafia też do Excela, pliku dla AI i pakietu do strategii.
- W Excelu jest arkusz „Kategoria produktu”: każda reklama z grupą, powodem, trafionymi słowami i informacją, czy przypisano ją ręcznie.
- Plik dla AI mówi wprost, że liczby dotyczą jednej kategorii, a nie całej komunikacji marki.

### Czego zawężenie nie zmienia

- **Kalibracji i rejestru trafności.** Realny wydatek konta dotyczy całej marki, więc kalibracja liczy wszystkie reklamy.
- **Migawek i zakładki „Zmiany”.** Migawka zapisuje całą markę, żeby porównania między dniami nie zależały od ustawień kategorii.

## 8b. Gotowe do wysłania

Karta nad filtrami wyników zbiera w jednym miejscu wszystko, co trzeba sprawdzić przed wysłaniem raportu klientowi. Zastępuje czytanie tego README przed każdą wysyłką.

- **BŁĄD:** awaria źródła, pobieranie zatrzymane na limicie bezpieczeństwa Mety.
- **UWAGA:** analiza wczytana z pliku, próba (limit reklam), marka bez reklam, zasięg nieprzeskalowany do wybranych krajów, marki liczone na różnych podstawach zasięgu, okres starszy niż ok. 12 miesięcy, włączony sandbox, reklamy „trudne do określenia” przy kategorii produktu.
- **INFO** (do wiadomości, bez odhaczania): brak formatów, nieskalibrowany szacunek kosztu, zawężenie do kategorii, interpretacje jako poszlaki.

Każdy punkt UWAGA i BŁĄD odhaczasz, gdy go sprawdzisz albo świadomie zostawiasz. Przy części punktów jest przycisk do miejsca, w którym się to naprawia (sandbox, lista kategorii). Pasek postępu i nagłówek mówią, ile zostało. Panel „Raport (PDF / HTML)” pokazuje ramkę z liczbą niesprawdzonych punktów. Lista zeruje się po nowej analizie.

## 8c. Komentarze, kolejność sekcji, raport danych

### Komentarze analityka

Nad treścią każdej zakładki wyników Mety (porównanie i każda marka) jest pole „+ Dodaj komentarz do raportu”.

- Komentarz trafia na początek tej samej sekcji w raporcie HTML i PDF, w wyróżnionej ramce „Komentarz analityka”. Komentarz z zakładki „Wnioski i rekomendacje” trafia do „Raportu w skrócie”, a komentarz z zakładki marki do jej profilu, na właściwą zakładkę (w PDF: na stronę tematu).
- Zakładka z komentarzem ma niebieską kropkę.
- Komentarz pojawi się tylko wtedy, gdy jego sekcja jest zaznaczona w panelu raportu. Lista „Gotowe do wysłania” podaje, ile sekcji ma komentarz.
- Komentarze zapisują się same w przeglądarce, osobno dla każdego zestawu marek (nie przechodzą na analizę innego klienta), i w pliku „Zapisz analizę”.
- Nie dotyczy to zakładek Google, TikToka i LinkedIna. Ogólny komentarz do całego raportu nadal wpisujesz w „Dodatkowe → Komentarz analityka”.

### Kolejność sekcji (PDF i HTML)

W panelu „Raport (PDF / HTML)” lista „Kolejność sekcji w raporcie” pokazuje zaznaczone sekcje: skrót, porównania, Google, TikTok, rekomendacje, brief, profile marek (każda marka osobno), metodologię i sekcje tylko dla HTML (galeria, oś czasu, LinkedIn, wszystkie kanały).

- Kolejność zmieniasz przeciągnięciem albo strzałkami ↑ ↓. „Przywróć domyślną” wraca do kolejności historii (rozdział 7).
- Okładka jest zawsze pierwsza, a w PDF zaraz po niej strona „Co jest w raporcie” (jeśli zaznaczona). W HTML „Jak czytać ten raport” i metodologia są zawsze na końcu, w „O raporcie”.
- Przy własnej kolejności menu raportu HTML ma grupę „Sekcje raportu” w Twojej kolejności i osobno „Profile marek”.
- Kolejność zapisuje się w przeglądarce. Sekcja odznaczona i zaznaczona ponownie wraca na swoje miejsce.

### Pełny raport HTML

Przycisk „Pełny raport HTML (wszystko)” zaznacza wszystkie sekcje i marki z panelu i od razu zapisuje raport HTML w wyglądzie aplikacji. Kolejność z listy obowiązuje też tu.

### Raport danych (bez wniosków)

Pole „Tylko dane i wyliczenia” w panelu raportu działa dla PDF i HTML:

- pomija sekcje będące w całości zaleceniami: rekomendacje, brief kreatywny (porównanie i marki),
- usuwa z pozostałych sekcji wszystko oznaczone jako dedukcja: zdania-wnioski na początku zakładek, plan „Co zrobić najpierw”, rekomendacje, wolne pola, zdanie-podsumowanie na okładce i komentarze analityka,
- nagłówki sekcji to zwykłe nazwy, nie wnioski,
- zostają czyste dane i obliczenia, w tym szacunki kosztu i udziałów (to wyliczenia, nie interpretacje). Ramka „Raport danych” na okładce i w metodologii mówi, co pominięto.

## 9. Stany źródeł

Każde źródło pokazuje jeden z czterech stanów. Nie mylimy usterki z wynikiem.

- **BŁĄD:** awaria (złe klucze, limit API, brak połączenia). Wynik nic nie mówi o konkurencji, trzeba naprawić przyczynę.
- **BRAK DANYCH:** źródło odpowiedziało poprawnie, ale marka nie ma reklam w tym okresie i obszarze. To wynik.
- **NIEPEŁNE DANE:** pobieranie zatrzymane przed końcem (limit stron, limit bezpieczeństwa Mety ok. 100 tys. reklam). Podajemy liczbę pobranych reklam.
- **BRAK DOSTĘPU:** źródło działa, ale aplikacja nie ma jeszcze zgody na dane (LinkedIn przed zatwierdzeniem Ad Library API, odpowiedź 403).

## 10. Prywatność i klucze

- Narzędzie działa w całości w przeglądarce. Dane idą tylko między przeglądarką a Metą, Google oraz TikTokiem i LinkedInem przez pośrednika.
- **Pośrednik nie ma kluczy.** Klucze TikToka i token LinkedIna są tylko w pamięci otwartej karty. Nie trafiają do localStorage, zestawów, zapisanych analiz, raportów, Excela ani pliku dla AI (sprawdza to test).
- Logowanie Google daje token na godzinę, trzymany w pamięci karty. ID projektu i klienta OAuth nie są tajne, ale nie wpisujemy ich do plików narzędzia; każdy uzupełnia własne.
- Token Meta zapisuje się lokalnie tylko po zaznaczeniu „Zapamiętaj token”.
- Z internetu dociągane są tylko biblioteki open source (xlsx, pptxgenjs, jszip, html-to-image z jsDelivr, cdnjs albo unpkg) i czcionki Google Fonts. Żadna nie dostaje danych.
- Zestawy, migawki, ustawienia, korekty i słownik są w localStorage tej przeglądarki.
- Nigdy nie wklejaj kluczy ani tokenów do czatu, maila ani plików projektu.

## 11. Znane ograniczenia: BŁĄD vs BRAK FUNKCJI

### Otwarte błędy

- Brak znanych otwartych błędów w 31.4 (54/54 testów). Ostatni naprawiony: wstążka zakładek wyników przyklejała się 48 px poniżej góry ekranu (naprawione w 31.4).

### BRAK FUNKCJI (świadomie nie ma, albo jeszcze nie ma)

- **Automatyczne dopasowanie stawek do sezonu.** Stawki to średnia z całego roku. Korektę sezonu (Q4 / Black Friday / Święta +25%, lato −10%) włączasz ręcznie w zaawansowanych.
- **Wyłączenie sekcji wydatków przy odznaczonych estymacjach.** Odznaczone pole „Raport z estymacjami…” tylko chowa stawki; raport dalej pokazuje szacunek ze stawek branży. Do decyzji BeDi, czy ma raczej wyłączać sekcje wydatków.
- **Logotypy platform.** W krokach są proste piktogramy SVG, nie oficjalne logotypy.
- **Prognoza kosztu dla Google.** Centrum przejrzystości podaje wyświetlenia narastająco, bez dziennego tempa, więc w Google liczymy tylko średnią z okresu.
- **Teksty reklam Google.** Zbiór ich nie ma, więc argumenty, rabaty, brief i mapa wolnych pól liczą tylko Metę i są tak podpisane.
- **Wyniki reklam konkurencji** (CTR, konwersje, ROAS): nie publikuje ich żadna biblioteka.

- **Rozpoznawanie kategorii z obrazu lub wideo.** Kategoria jest rozpoznawana tylko po tekście reklamy. Reklamy bez tekstu i katalogowe trafiają do „trudne do określenia” i trzeba je przypisać ręcznie (podgląd kreacji przez link do biblioteki).
- **Zawężenie kategorii dla Google i TikToka.** Brak tekstu reklam w ich bibliotekach.

### Do potwierdzenia

- **LinkedIn:** nazwy parametrów filtrów (kraje, zakres dat) i stronicowania są wzięte z publicznych opisów API. Trzeba je potwierdzić skryptem `test-linkedin.mjs` na prawdziwym tokenie:
  `read -s LI_TOKEN && export LI_TOKEN && node test-linkedin.mjs "Nazwa firmy"`
  Skrypt nie wypisuje tokenu. Poprawki pójdą w `src/linkedin/client.js`.

### Ograniczenia danych

Te ograniczenia narzędzie pokazuje też na liście „Gotowe do wysłania” (rozdział 8b), dopasowane do bieżącej analizy.


- Meta: tylko reklamy, które dotarły do UE; opóźnienie 1–2 dni; zasięg nie jest unikalny między reklamami; udział obszaru to przybliżenie; brak identyfikatora grafiki, więc test kreacji to poszlaka.
- Google: tylko EOG i Turcja, od 1.03.2023; zbiór bywa niepełny względem strony `adstransparency.google.com` (sprawdź 1–2 marki); nazwy reklamodawców się powtarzają, najpewniej wpisz ID `AR…`.
- TikTok: tylko UE/EOG, UK i Szwajcaria; limit ok. 1000 zapytań dziennie.
- LinkedIn: statystyki tylko dla emisji w UE; dostęp po zatwierdzeniu aplikacji.
- Interpretacje: długa emisja to poszlaka, nie dowód skuteczności; krótka emisja nie znaczy słabej reklamy; „kto zaczął, kto dołączył” to zbieżność w czasie; demografia pokazuje, do kogo reklama dotarła, nie jak była targetowana; rekomendacje i brief są regułowe.

Przy kwotach w materiałach dla klienta zawsze podawaj przedział i dopisek „szacunek na podstawie bibliotek reklam”.

## 12. Rozwiązywanie problemów

Meta:

- **Błąd 10:** dokończ weryfikację tożsamości i akceptację API, potem nowy token tym samym kontem.
- **Błąd 190:** token wygasł, wygeneruj i przedłuż nowy.
- **„Limit zapytań API, czekam…”:** normalne przy wielu markach, narzędzie samo odczeka.
- **Zła strona marki:** podaj ID strony albo link z Biblioteki Reklam.
- **Marka międzynarodowa ma podejrzanie wysoki budżet:** sprawdź pasek „Zasięg przeskalowany do obszaru”; marka „bez przeskalowania” potrzebuje włączonego pobierania demografii.

Google:

- **Logowanie nie działa:** plik otwarty z dysku. Otwórz z GitHub Pages albo `http://localhost:8000`.
- **`origin_mismatch`:** adres narzędzia nie jest w autoryzowanych źródłach klienta OAuth.
- **„Brak uprawnienia do uruchamiania zapytań”:** sprawdź ID projektu albo nadaj rolę `roles/bigquery.jobUser`.
- **Wykres Google spada do zera:** to granica danych, nie koniec emisji.

TikTok i LinkedIn:

- **403 / „Ta strona nie jest na liście ALLOWED_ORIGINS”:** dopisz adres, z którego otwierasz RivalCore (uwaga na `http`/`https` i ukośnik na końcu). `file://` jest zawsze odrzucany.
- **„Pośrednik nie ma ustawionej zmiennej ALLOWED_ORIGINS”:** brakuje zmiennej albo nie kliknięto Deploy.
- **TikTok: złe klucze albo wyczerpany limit:** sprawdź klucze; przy limicie poczekaj do jutra albo zmniejsz liczbę stron.
- **LinkedIn: BRAK DOSTĘPU:** Ad Library API nie jest jeszcze zatwierdzone albo token jest z innej aplikacji. **LinkedIn 401:** token wygasł.

Liczby i eksporty:

- **Inna kwota na zakładce Meta i w „Kanałach razem”:** prognoza kontra średnia z okresu (rozdział 8).
- **Excel pobrał się jako .csv:** biblioteka Excela nie wczytała się z żadnego adresu; dane są te same.
- **PDF bez teł:** zaznacz „Grafika tła” w oknie drukowania.
- **Zniknęły korekty:** są w tej przeglądarce; między komputerami przenoś je przez „Zapisz analizę”.

## 13. Kod źródłowy, budowanie i testy

Źródła są w `rivalcore-31.4-zrodla.zip`. Budowanie: Vite + `vite-plugin-singlefile`, wynik to jeden plik `dist/index.html` ze wszystkim w środku.

### Budowanie

- Raz: `npm install` (Node 18+).
- Praca na żywo: `npm run dev` → `http://localhost:5173`.
- Budowanie: `npm run build` (najpierw ESLint, nieznana nazwa = błąd budowania, potem `dist/index.html`).

### Najważniejsze katalogi

- `src/main.js`: kolejność uruchamiania modułów.
- `src/meta/`: moduł Meta (`app.js` i wydzielone: api, loader, analyze, budget, recs, promo, xlsx, pptx, report-pdf, ai-export, strategy-pack, sets, wizard i inne).
- `src/google/app.js`: BigQuery, logowanie, zakładki Google, kalibracja Google.
- `src/tiktok/`, `src/linkedin/`: klienci API, analizy, panele.
- `src/adapters/` + `src/model/ad.js`: wspólny model reklamy dla wszystkich źródeł.
- `src/sov/`: udział w głosie ze wszystkich kanałów. `src/explorer/`: galeria, filtry, oś czasu.
- `src/ui/layout.js`: ekran startowy w pięciu krokach. `src/ui/scope.js`: nadpisania marka → platforma. `src/ui/panel314.js`: panel 31.4 (rodzaj raportu, kraje, okresy, estymacje, (i), wstążka wyników).
- `src/report/runtime.js`, `src/styles/report.css`: raport HTML.
- `src/core/`: wersja, formatowanie, daty, stany źródeł, styl Excela.
- `worker/`: pośrednicy Cloudflare (wdrażani osobno).

Klucze w localStorage dodane w 31.7: `rc31.comments` (komentarze analityka, według zestawu marek), `rc31.pdfOrder` (kolejność sekcji raportu), `rc31.facts` (raport danych). Klucz w localStorage dodany w 31.6: `rc31.ready` (odhaczone punkty listy „Gotowe do wysłania” dla bieżącej analizy).

Klucze w localStorage dodane w 31.5: `rc31.cat` (ustawienia kategorii), `rc31.catOv` (ręczne przypisania reklam do grup, osobno dla każdej kategorii).

Klucze w localStorage dodane w 31.4: `rc31.mode` (porównanie / jedna marka), `rc31.compStash` (schowani konkurenci), `rc31.est` (estymacje).

### Wersje 31.5–31.6 a źródła

Kategoria produktu (31.5) i zmiany raportu (31.6) są naniesione na zbudowany `index.html` z 31.4 (źródeł nie było pod ręką). Żeby nie zginęły przy następnym `npm run build`, trzeba je przenieść do `src/`. 31.5:

- `kategoria-31.5.js`: cały moduł (np. jako `src/category/index.js`). Korzysta z `results`, `rerender`, `periodCtx`, `rowIn`, `esc`, `fmt`, `iso`, `tipI` oraz z `LI` i `RZ`.
- `apply-31.5.py`: lista miejsc, w które moduł jest wpięty (każde wpięcie to para „było → jest”). Najważniejsze: `reanalyze` (filtr wierszy Meta i `ctx.hist`), `filterLabel`, `brandHead`, karta wyników, raport HTML (okładka i metodologia), `RZ.render`, `exportXlsx` (arkusz), `buildAiMd`, `saveAnalysis` / `loadAnalysis`, `currentSet` / `applySet`, `LI.analyze`, `renderAllBase`, przełącznik kanałów, podsumowanie kroku 5, `init`, CSS i `window.RC` (`catOf`, `catRule`, `catStats`, `catApply`, `CAT`, `CAT_OV`).

31.6:

- `raport-31.6.js`: nagłówki-wnioski (`rcHead`), okładka „W 5 sekund” (`rcHeroX5`), kolejność jak historia (`RC_STORY`, `rcStoryOrder`), zakładki profilu marki w raporcie HTML (`RC_PT_JS`), CSS raportu (`RC316_CSS`), przycinanie pustych miesięcy na wykresach (`rcTrimMonths`) i lista „Gotowe do wysłania” (`readyItems`, `readyCardRender`, `readyBanner`). Najlepiej jako `src/report/story.js` i `src/ui/ready.js`.
- `apply-31.6.py`: miejsca wpięcia. Najważniejsze: `appReportSections` (skrót + wnioski, profile marek), `appReportShell` (okładka, pasek, nagłówki, „Jak czytać” na końcu, bez spisu jako sekcji), literał `REPORT_RUNTIME` (przycisk „Skrót” uruchamia ścieżkę krok po kroku), `buildReport` (okładka PDF, kolejność stron), `openPdfPanel` (domyślny skrót, ramka listy), galeria (reklamy katalogowe), `renderAllBase`, CSS druku.
- **Odmiana „1 dzień”:** skrypt zamienia każde `${wyrażenie} dni` w kodzie na `${__dn(wyrażenie)}` (67 miejsc). W źródłach lepiej dodać pomocnik do `src/core/format.js` i użyć go w tych miejscach.

31.7:

- `komentarze-kolejnosc-31.7.js`: komentarze (`commBox`, `commHtml`, `commGet`, `commSet`), kolejność sekcji (`pdfUnits`, `pordMount`, `rcOrderPages`, `rcOrderSections`, `rcUnitOf`) i raport danych (`RC_FACT_SKIP_SECS`, `rcFactStrip`). Najlepiej jako `src/report/comments.js`, `src/report/order.js` i `src/report/facts.js`.
- `apply-31.7.py`: miejsca wpięcia. Najważniejsze: pole komentarza w karcie wyników (`renderAllBase`), `appReportSections` i `buildReport` (komentarze, `has()` z pominięciem sekcji, oznaczanie stron kluczem `PGK` i układanie ich na końcu), `pdfOpts` (`o.order`, `o.facts`), zapis i wczytanie analizy (`comm`).

Przy wyłączonej kategorii liczby są identyczne jak w 31.4 (sprawdzone na danych testowych), więc złoty wzorzec nie powinien się zmienić. Po przeniesieniu do `src/` warto dopisać testy: klasyfikacja przykładowych tekstów (dotyczy / wspomina / trudne / nie dotyczy), ręczne przypisanie i cofnięcie, zapis i wczytanie analizy z kategorią.

### Testy

- `npm test`: budowanie, testy jednostkowe (`unit.mjs`, `unit_tiktok.mjs`, `unit_worker.mjs`, `unit_proxy.mjs`, `unit_v31.mjs`) i testy w przeglądarce (`python3 -I tests/run_all.py`, Playwright + openpyxl).
- `npm run test:unit`: same testy jednostkowe.
- Testy w przeglądarce sprawdzają m.in. wszystkie zakładki, TikTok i LinkedIn na atrapie API, brak kluczy w plikach, Excel, plik dla AI, raport HTML, PPTX, 5 szerokości ekranu bez przewijania w poziomie.
- **Złoty wzorzec** (`tests/golden.json`): liczby marek, rekomendacje, plik dla AI i arkusze Excela muszą wyjść identycznie. Celowa zmiana liczb wymaga `python3 -I tests/run_all.py --write-golden` i opisu w historii wersji.
- Dostęp testów do wnętrza aplikacji (`window.RC`) włącza tylko adres z `?test`.

## 14. Historia wersji (skrót)

Pełny dziennik zmian jest w `README-archiwum-do-31.4.md`.

- **31.7** (27.11.2026): komentarze analityka przy zakładkach wyników, widoczne w raporcie HTML i PDF; własna kolejność sekcji dla PDF i HTML; przycisk „Pełny raport HTML (wszystko)”; raport danych bez wniosków, interpretacji i zaleceń.
- **31.6** (27.11.2026): raport po uwagach. Lista „Gotowe do wysłania”; raport HTML z okładką „W 5 sekund”, startem na „Raporcie w skrócie” (połączonym z wnioskami), kolejnością jak historia, profilami marek z zakładkami, nagłówkami-wnioskami i jednym przełącznikiem „Skrót / Pełny raport”; PDF domyślnie jako skrót, z rekomendacjami na całą szerokość i etykietami zamiast kolorowych ramek. Poprawki: nieczytelny aktywny przycisk paska, „1 dni” → „1 dzień”, szablon `{{product.name}}` w galerii, puste miesiące na początku wykresów, ucięty tytuł w pasku.
- **31.5** (27.11.2026): kategoria produktu. Zawężenie analizy Mety i LinkedIna do reklam jednej kategorii po tekście reklamy, cztery grupy (dotyczy, wspomina, trudne do określenia, nie dotyczy), ręczne i hurtowe przypisanie reklam do grup, gotowe listy słów, ramki w raportach, arkusz w Excelu, kategoria w zestawach i zapisanej analizie.
- **31.4** (26.11.2026): panel startowy po uwagach BeDi. Rodzaj raportu (porównanie / jedna marka), Polska domyślnie, przyciski okresów, domyślny okres pół roku zamiast całej historii, estymacje Mety za polem wyboru, (i) zamiast podpisów, „Źródła raportów i analiz”, prostsza nota o zasięgu, uporządkowany panel PDF/HTML. Naprawiona wstążka wyników (top: 0, przewijanie w bok).
- **31.3** (25.11.2026): raport HTML w stylu BeDigital: pasek z logo w jednym rzędzie, menu „Więcej”, panele, kopiowanie linku do sekcji, sortowanie tabel, pasek postępu, ↑.
- **31.2** (24.11.2026): ekran startowy w pięciu krokach, ustawienia platforma po platformie i marka po marce.
- **31.1** (24.11.2026): wspólne ustawienia + źródła + konta. Odrzucona, zastąpiona przez 31.2.
- **31.0** (24.11.2026): LinkedIn, udział w głosie ze wszystkich kanałów, galeria i oś czasu, zestawy klientów, tryb dla klienta, stany źródeł, styl Excela, podział `src/meta/app.js`.
- **30.0** (23.11.2026): TikTok jako trzeci kanał, pośrednik Cloudflare bez kluczy, środek CPM Google jako średnia geometryczna.
- **29.1:** formularz Meta | Google, raport „historia, potem aneks”, ostrzeżenie o różnym obszarze Meta i Google. **Wersja obecnie na GitHub Pages.**
- **29.0:** kod w modułach (Vite), jedna biblioteka wykresów, wspólny model reklamy.
- **28.x:** strategia i testy, kampanie, rekomendacje z pomiarem, rejestr trafności, zasięg z wybranego obszaru, sandbox korekt, hasło do raportu.
- **25–27:** raport HTML jako aplikacja, podsumowania obu kanałów, warstwa „co z tego wynika”, detektor rabatów, korekty ręczne.
- **20–24:** Google jako drugi kanał, wyniki kont Google Ads, pierwsze raporty i eksporty.
