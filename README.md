https://biedronm.github.io/rivalcore/#konkurencja

# RivalCore — README

RivalCore to wewnętrzne narzędzie do analizy reklam marek i konkurencji z Biblioteki Reklam Meta (Facebook, Instagram, Messenger, Audience Network) i z Centrum przejrzystości reklam Google (Search, YouTube, sieć reklamowa), a od wersji 20 także wyników kont Google Ads naszych klientów. Jeden plik HTML — bez instalacji, bez serwera, bez opłat. Otwierasz w przeglądarce, wklejasz token, wpisujesz marki i dostajesz analizę z wykresami, raport PDF, prezentację PowerPoint, Excel oraz plik dla AI.

**Aktualna wersja: 25.8 (13 listopada 2026).** Plik narzędzia nazywa się `index.html` (repozytorium `biedronm/rivalcore`, adres `https://biedronm.github.io/rivalcore/`). Wygląd ekranu, raportów PDF, prezentacji i grafik PNG jest zgodny z identyfikacją wizualną BeDigital.

## Spis treści

- [Co nowego? Wersje 25.1–25.8](#co-nowego-wersje-251258)
- [Co nowego? Wersja 25.0 · warstwa „co z tego wynika”](#co-nowego-wersja-250--warstwa-co-z-tego-wynika)
- [Starsze wersje: 20–24](#starsze-wersje-2024)
- [1. Pierwsze uruchomienie (token Meta)](#1-pierwsze-uruchomienie-token-meta)
- [1b. Pierwsze uruchomienie: Google](#1b-pierwsze-uruchomienie-google)
- [2. Jak zrobić analizę](#2-jak-zrobić-analizę)
- [3. Ustawienia](#3-ustawienia)
- [4. Wyniki — zakładki](#4-wyniki--zakładki)
- [5. Dwie liczby budżetu: prognoza i średnia z okresu](#5-dwie-liczby-budżetu-prognoza-i-średnia-z-okresu)
- [6. Dane Google: opóźnienie partii i granica danych](#6-dane-google-opóźnienie-partii-i-granica-danych)
- [7. Co liczy Metę, co liczy oba kanały](#7-co-liczy-metę-co-liczy-oba-kanały)
- [8. Ręczne korekty: rabaty, argumenty, słownik branżowy](#8-ręczne-korekty-rabaty-argumenty-słownik-branżowy)
- [9. Lupa detektywa — skąd pochodzi każda informacja](#9-lupa-detektywa--skąd-pochodzi-każda-informacja)
- [10. Eksporty: PDF, prezentacja PPTX, Excel, plik dla AI, pakiet do strategii](#10-eksporty-pdf-prezentacja-pptx-excel-plik-dla-ai-pakiet-do-strategii)
- [11. Zestawy konkurentów i migawki](#11-zestawy-konkurentów-i-migawki)
- [12. Słowniczek wskaźników](#12-słowniczek-wskaźników)
- [13. Ograniczenia danych — przeczytaj przed wysłaniem raportu klientowi](#13-ograniczenia-danych--przeczytaj-przed-wysłaniem-raportu-klientowi)
- [14. Rozwiązywanie problemów](#14-rozwiązywanie-problemów)
- [15. Prywatność i bezpieczeństwo](#15-prywatność-i-bezpieczeństwo)
- [16. Najczęstsze pytania (FAQ)](#16-najczęstsze-pytania-faq)

## Co nowego? Wersje 25.1–25.8

Seria wydań wokół jednego: **materiał, który idzie do klienta, ma być prawdziwy, czytelny i ma tłumaczyć sam siebie.**

### Raport HTML tłumaczy każdą swoją liczbę (25.8)

Raport z 25.7 wyglądał jak aplikacja, ale miał dwie wady: część tekstu była niewidoczna, a czytelnik nie wiedział, skąd biorą się liczby.

**Niewidoczny tekst.** W przebudowie raportu PDF (24.0) część reguł dostała twardo wpisany czarny kolor zamiast koloru z motywu — i nie były przypięte do wydruku. W ciemnym raporcie HTML dawało to czarny tekst na czarnym tle; metodologia wyglądała na listę pustych myślników. Znalazłem 26 takich reguł; te, które trafiają do raportu, biorą teraz kolor z motywu. Szeroka treść przewija się w swojej sekcji, zamiast uciekać poza prawą krawędź.

**Objaśnienia pochodzenia liczb.** Każdy kafelek i każda liczba nosi w sobie pełny rachunek na danych z tej analizy — to te same dymki „Skąd to?”, które działają w narzędziu. W raporcie były zapisane w pliku, ale nic ich nie pokazywało. Teraz działają: najedź kursorem (na telefonie stuknij), a zobaczysz rachunek z prawdziwymi liczbami, nie ogólny wzór. W pełnym raporcie dla trzech marek jest ich ok. 190.

**Sekcja „Jak czytać ten raport”** otwiera raport: co pokazuje, a czego nie (że kwoty to szacunki, bo ani Meta, ani Google nie publikują wydatków), cztery rodzaje informacji z licznikiem każdego z nich w tym konkretnym raporcie, i od czego zacząć czytanie.

Do tego **wyszukiwarka sekcji** w menu, przycisk **Podświetl objaśnienia** zaznaczający wszystkie miejsca z dymkiem, oraz Esc zamykający dymek.

### Raport HTML w szacie aplikacji (25.7)

Pierwsza wersja raportu HTML (25.5) była wydrukiem wrzuconym do przeglądarki — kartki A4 i nic więcej. Doszedł drugi wygląd, domyślny: raport z menu sekcji, przełącznikiem jasny/ciemny i nawigacją strzałkami, wyglądający jak samo narzędzie. Stary wygląd („jak wydruk”) zostaje do wyboru. Szczegóły w [punkcie 10](#10-eksporty-pdf-prezentacja-pptx-excel-plik-dla-ai-pakiet-do-strategii).

### Raport i prezentacja po ponownej analizie (25.6)

Każda analiza nadaje markom nowe identyfikatory. Panel raportu, prezentacji, pakietu i pliku dla AI budował listę marek w chwili otwarcia, więc panel otwarty przed ponowną analizą wskazywał na marki, których już nie ma — raport wywracał się wtedy na błędzie `Cannot read properties of undefined`, a PDF i HTML w ogóle się nie generowały. Panele pamiętają teraz, dla jakiego zestawu marek powstały, i odświeżają się same.

### Jedno menu eksportu dla wszystkich kanałów (25.4)

Przycisk „Eksport i zapis” wisiał przy wynikach Meta i znikał po przejściu na Google albo Meta + Google — mimo że eksportował wszystkie kanały. Do tego rozwijane menu było ucinane przez kolejne sekcje strony: karta wyników ma `backdrop-filter`, co zamyka kontekst nakładania i czyni ją blokiem zawierającym dla `position:fixed`, więc dymek nie mógł się wydostać.

Teraz menu stoi przy wspólnym nagłówku „Wyniki” i jest widoczne na każdym kanale, a jego zawartość jest pogrupowana po źródle — z pozycjami Google i Meta + Google, których wcześniej tam nie było. Na czas otwarcia dymek przenosi się do `<body>` i sam dobiera miejsce: mieści się w oknie, otwiera w górę, gdy pod przyciskiem jest mało miejsca, a na telefonie staje się panelem przy dolnej krawędzi. Pozycje bez danych są wyszarzone z wyjaśnieniem, a „Wyczyść wyniki” jest na końcu, pod kreską.

### Zerowe ogony Google to brak danych, nie zerowe wydatki

Największa zmiana. Centrum przejrzystości potrafi przestać raportować wyświetlenia marki na długo przed ostatnią datą w zbiorze. Wykresy spadały wtedy do zera i wyglądały, jakby konkurencja wyłączyła reklamy — a pasek podziału kanałów malował te tygodnie na „100% Meta”.

Teraz RivalCore wykrywa **granicę danych** i nigdzie nie rysuje jej jako zera:

- linie Google i „Razem” są **urwane** na ostatnim tygodniu z danymi; linia Meta biegnie dalej, bo jej dane są świeższe;
- odcinek bez danych jest **zakreskowany na szaro** z podpisem „brak danych Google”, a w legendzie stoi „brak danych — nie zero”;
- tygodnie bez danych w pasku podziału kanałów są zakreskowane zamiast malowane na kolor jednego kanału;
- porównanie „pierwsze vs ostatnie 4 tygodnie” liczy się do ostatniego tygodnia z danymi, nie w dziurę;
- miesiące po granicy wypadają z wykresu udziałów zamiast pokazywać fałszywe 0%.

Komunikat idzie wszędzie: ramka ostrzegawcza nad wykresami z datą i liczbą tygodni, wpis w „Najważniejsze w skrócie”, plakietka w pasku stanu, zdanie w podpisie pod wykresem, wiersz w arkuszu „Zakres danych” w Excelu, blok w pliku dla AI, ostrzeżenie na slajdzie „Meta + Google” i punkt w metodologii prezentacji.

Szczegóły działania i różnica względem korekty opóźnienia: [punkt 6](#6-dane-google-opóźnienie-partii-i-granica-danych).

### Ta sama etykieta nie oznacza już dwóch różnych liczb

Zakładka **Meta** pokazywała „szacowany koszt miesięczny” jako **prognozę** (dzisiejsze tempo emisji × 30 dni), a zakładka **Meta + Google** tę samą pozycję jako **średnią z analizowanego okresu**. Obie są poprawne, mierzą co innego — ale nazywały się tak samo, więc marka rosnąca miała w jednym miejscu 4,3 mln zł, a w drugim 2,2 mln zł.

Liczby zostają (średniej z okresu nie da się zastąpić prognozą, bo dla Google prognozy policzyć nie można), zmieniają się podpisy: na zakładce Meta jest teraz „szac. koszt / mies. **(prognoza)**”, na Meta + Google nagłówki kolumn mają wyjaśnienie bazy, a najechanie na wartość w kolumnie Meta pokazuje obie liczby obok siebie. Pod tabelą jest akapit tłumaczący różnicę. Pełne wyjaśnienie: [punkt 5](#5-dwie-liczby-budżetu-prognoza-i-średnia-z-okresu).

### Koniec z pozostałościami po „tylko Meta”

Narzędzie powstawało najpierw dla Mety, więc część elementów liczyła jeden kanał pod ogólną etykietą. Okładka raportu pokazywała sam budżet Meta jako „szacowany koszt miesięczny”, mimo że w raporcie była też sekcja Google.

- **Okładka raportu** bierze liczby z obu kanałów: koszt, aktywne reklamy i wyświetlenia są sumą, a pod każdą liczbą stoi rozbicie („Meta 14 tys. + Google 467 zł”). W stopce doszła baza wyliczenia i data końca danych Google. Bez analizy Google okładka wygląda jak dotąd, bez dopisków.
- **Indeks aktywności** zostaje liczony z Mety i jest tak podpisany — z Google nie da się go policzyć.
- **„Raport w skrócie”** — słupki podziału budżetu szły dotąd z dwóch różnych baz. Teraz obie strony liczone są tak samo, z podpisem przy nagłówku.
- **Prezentacja** — slajd „Najważniejsze liczby” sumuje kanały i pokazuje rozbicie, a slajdy liczone wyłącznie z Mety mają **„· META”** w kickerze: Udział w głosie, Aktywność, Marki w skrócie, Oś czasu, Co przeżywa, Wojna rabatowa, Mapa wolnych pól, Brief kreatywny.
- **Strony PDF** z sekcji Meta i nagłówek porównania na ekranie dostały plakietkę kanału.

Pełna mapa, co liczy który kanał: [punkt 7](#7-co-liczy-metę-co-liczy-oba-kanały).

### Biblioteki zewnętrzne nie wiszą już na jednym CDN-ie

Eksport prezentacji wskazywał na cdnjs, który w ogóle nie hostuje biblioteki pptxgenjs — przycisk kończył się błędem „nie udało się pobrać biblioteki”. Excel ładował się jednym sztywnym tagiem z tego samego hosta, więc przy zablokowanym cdnjs też nie działał, a w zakładce Meta + Google **nie dawał żadnego komunikatu** — klikasz i nic się nie dzieje.

Każda biblioteka ma teraz listę adresów zapasowych i próbuje po kolei; błąd zgłaszany jest dopiero, gdy padną wszystkie:

| Biblioteka | Do czego | Kolejność adresów |
|---|---|---|
| pptxgenjs | prezentacja .pptx | jsDelivr (npm) → jsDelivr (GitHub) → unpkg |
| xlsx | Excel | jsDelivr → cdnjs → unpkg |
| jszip | pakiet do strategii | jsDelivr → cdnjs → unpkg |
| html-to-image | wykresy PNG | jsDelivr → unpkg |

Excel pobiera się w tle 1,2 sekundy po otwarciu strony, więc eksport jest natychmiastowy. Gdy padną wszystkie adresy, każdy przycisk mówi to wprost i podaje listę hostów; eksport Meta sam przełącza się wtedy na CSV. Raport PDF nie potrzebuje żadnej biblioteki zewnętrznej i działa zawsze.

### Drobne, ale istotne dla materiałów klienckich

- **Agenda prezentacji wymienia dokładnie te slajdy, które są w pliku.** Wcześniej obiecywała np. „Mapę wolnych pól”, a slajd nie powstawał, bo przy tych danych nie było czego pokazać. Teraz przed właściwym budowaniem leci próbny przebieg, który sprawdza, co faktycznie powstanie.
- **Niekompletny slajd nie przechodzi po cichu.** Jeśli budowanie któregoś slajdu się wywali, komunikat podaje jego nazwę i każe sprawdzić plik przed wysłaniem.
- **Kafelki na slajdach dobierają wysokość do długości etykiet** — dłuższy podpis wchodził wcześniej na liczbę pod spodem.
- **Nazwy liczebników**: „1 aktywna reklama” zamiast „1 aktywnych reklam”, to samo przy slajdach.

## Co nowego? Wersja 25.0 · warstwa „co z tego wynika”

Wersje 19–24 odpowiadały na pytanie **„co robi konkurencja”**. Wersja 25 odpowiada na **„co z tego wynika dla kreacji i oferty”** — i pozwala ręcznie poprawić to, co automat źle zrozumiał.

### Nowy detektor rabatów

Stary detektor uznawał każdy myślnik przed liczbą za znak minus, więc punktor „- 90% szynki” stawał się rabatem −90%. Teraz:

- każdy procent dostaje punkty za sygnały rabatu: minus przyklejony do liczby, słowo rabatowe tuż przed albo tuż po;
- odpada, gdy po liczbie stoi skład, materiał, statystyka, parametr albo finanse: „90% szynki”, „87% kobiet”, „80% bawełny”, „30% więcej mocy”, „RRSO 9%”, „SPF 30–50%”;
- doszły: zakresy („20–30%”), rabaty „do X%” liczone osobno od stałych, rabat wyliczony z ceny („zamiast 199 zł teraz 149 zł”), rabaty kwotowe, wielosztuki (2+1, 3 za 2, drugi za 1 zł), kody rabatowe z nazwą kodu i próg darmowej dostawy.

Na zestawie 47 zdań testowych (z typowymi pułapkami: skład, statystyki, materiały, finanse) stary detektor trafiał 38 razy, nowy 47. To zestaw autorski, nie próba z prawdziwych reklam — dlatego jest lista do weryfikacji.

### Lista wykrytych rabatów z ręcznym odrzucaniem

Zakładka marki → **Oferty i ceny** → „Wykryte rabaty — lista do weryfikacji”. Każda pozycja ma podświetlony fragment reklamy, decyzję detektora i jej powód, a do tego przyciski **Odrzuć** / **Uznaj za rabat** / **Cofnij decyzję**. Reklamy z identycznym fragmentem są w jednym wierszu — jedna decyzja obejmuje wszystkie. Korekta od razu przelicza statystyki rabatów, „Wojnę rabatową” i „Co przeżywa”, i wchodzi do PDF, prezentacji i Excela.

### Nowe zakładki

| Zakładka | Gdzie | Co pokazuje |
|---|---|---|
| Co przeżywa | marka + porównanie | 12 argumentów reklamy (cena, darmowa dostawa, pilność, dowód społeczny, jakość, nowość…) i odsetek reklam z każdym, które działały co najmniej 30 dni; słowa częstsze w reklamach długo żyjących i w krótkich; reklamy zostawione na długo obok wyłączonych w tydzień; detektor testów A/B |
| Wojna rabatowa | porównanie (siatka też przy marce) | Rabaty tydzień po tygodniu: nasycenie koloru = odsetek aktywnych reklam z rabatem, liczba = najgłębszy rabat; fale promocji z datami („kto zaczął, kto dołączył”); tabela zagrań promocyjnych |
| Mapa wolnych pól | porównanie + „Odbiorcy” marki | Siatka argument × grupa wieku i płci: gdzie konkurencja mówi gęsto, a gdzie nie mówi nic |
| Brief kreatywny | marka + porównanie | „Stawiaj na” i „Uważaj”, język reklam długich i krótkich, oferta, do kogo, trzy koncepty do testu; przycisk „Kopiuj brief” |
| Oś czasu | marka | Jeden wykres: słupki nowych reklam, linia szacowanego budżetu tygodniowego i zacienione fale rabatów, pod spodem ponumerowana lista „Co się działo” |

„Uważaj” zamiast „Nie powielaj” jest celowo: krótka rotacja nie oznacza słabej reklamy. Argumenty oznaczone ⏱ (rabaty, pilność, konkursy, nowości, gratisy) to akcje czasowe i z założenia trwają krótko; kolumna „Obecny w tygodniach” pokazuje, czy marka dany argument stale rotuje, czy go porzuciła.

### Ręczna korekta argumentów i słowniki branżowe

Zakładka marki → **Co przeżywa** → „Argumenty reklam — lista do korekty”: przy każdym tekście reklamy klikasz argument, żeby go zdjąć, albo „+ dodaj argument”, żeby przypisać nowy. Pod listą jest **słownik argumentów**: branża (spożywcza i FMCG, moda, uroda, dom i budowa, motoryzacja, finanse, B2B, elektronika), własne frazy do każdego z 12 argumentów oraz własne argumenty (do 12). Korekty i słownik przeliczają „Co przeżywa”, mapę wolnych pól i brief, zapisują się w przeglądarce i w pliku „Zapisz analizę”, a w PDF widać ich wynik plus linijkę „Słownik argumentów: …”.

### Meta i Google na jednej osi czasu

W zakładce **Meta + Google** doszły dwa bloki: wykres tygodniowego szacowanego kosztu obu kanałów w tych samych tygodniach oraz „Podział budżetu między kanały w czasie” — pasek na markę, gdzie każdy słupek to tydzień, plus zmiana udziału Google między pierwszymi a ostatnimi tygodniami okresu. Przesunięcie o 10 pp lub więcej trafia do „Najważniejsze w skrócie”. W Excelu doszedł arkusz „Kanały tygodniowo”.

### Rozdzielony dostęp Meta i Google

Pole tokenu Meta jest w kafelku Meta (a nie w siatce marek), kafelek Google ma własny blok logowania, a moduł **Połączenia** ma dwie osobne sekcje z własnymi instrukcjami. Meta dostała przycisk „Sprawdź token”, który od razu odpytuje Bibliotekę Reklam. Można skonfigurować tylko jedno źródło — drugie po prostu wyłączasz w formularzu.

### Czytelność

- Tabele z kolumnami na markę nie ucinają się na trzeciej marce: nazwy w nagłówkach są skracane (pełna w podpowiedzi), a pierwsza kolumna zostaje na miejscu przy przewijaniu.
- Tabele, siatka rabatów, oś czasu i pasek zakładek pokazują cień na krawędzi, gdy jest tam dalsza treść; aktywna zakładka sama przewija się w pole widzenia.
- Kolejność kroków w formularzu: źródła → Twoja marka → konkurenci → konta Google → obszar emisji.
- Okno „Wklej listę” otwiera się dopiero po kliknięciu.
- Poprawki na telefonie (nawigacja, wykresy, listy korekt) i w PDF (tabele „Testy w liczbach”, „Rabaty w liczbach” i mapa wolnych pól mieszczą się na kartce).

## Starsze wersje: 20–24

<details>
<summary><b>Wersja 24.0 · nowy raport PDF</b></summary>

- **Raport drukuje się w skali 1:1.** Wcześniej kilka tabel wystawało poza kartkę, przez co przeglądarka pomniejszała cały raport o około jedną trzecią. Teraz nic nie wystaje, a najmniejszy tekst ma 8 pt.
- **Kontrast.** Tekst jest prawie czarny i grubszy (Montserrat 500–700); etykiety na wykresach są ciemne i pogrubione.
- **Czarny pas tytułowy** z logo BeDigital na początku każdej sekcji i każdego tematu marki.
- **Strona „Co jest w raporcie”** po okładce: spis sekcji i trzy zdania o tym, jak czytać szacunki.
- **Kafelki, tabele i karty w jednym stylu:** liczby pogrubione z czarną belką u góry, tabele z czarnym nagłówkiem, rekomendacje z kolorową belką priorytetu.
- **Wykresy na pełną szerokość** tam, gdzie obok siebie były nieczytelne.
- **Okładka** z mocnym tytułem, w wersji ciemnej i jasnej do druku.
- Pełny raport jest długi (dla trzech marek ok. 90 stron). Do wysyłki służą zestawy **Skrót dla klienta** i **Dla zarządu** albo prezentacja PPTX.

</details>

<details>
<summary><b>Wersja 23.0 · wyniki kont i kalibracja Google</b></summary>

- **Moduł „Wyniki kont”** (pasek u góry, adres `#wyniki`). Czyta dane ze skryptu Google Ads zapisane w arkuszu (albo plik CSV / XLSX): kondycja konta 0–100, KPI z deltą do poprzedniego okresu, tabele kont, kampanii, typów kampanii i fraz.
- **„Do sprawdzenia” w układzie Stan → Koszt → Rekomendacja.** Sześć jawnych reguł: kampanie wydające bez konwersji, wzrost CPA o 30%, spadek ROAS o 20%, spadek wydatków o 40%, brak emisji w ostatnim dniu danych, frazy z kosztem od 100 zł bez konwersji.
- **Skrypt Google Ads** kopiuje się przyciskiem w module. Zapisuje zakładki RC_dane, RC_frazy i RC_info; działa w MCC i na pojedynczym koncie.
- **Kalibracja kosztu Google na realnym wydatku** („Google: ustawienia”): wpisujesz prawdziwy miesięczny wydatek marki, a RivalCore przelicza CPM wszystkich formatów (±15%) i stosuje je do wszystkich marek.

</details>

<details>
<summary><b>Wersja 22.0 · warstwa zarządcza</b></summary>

- **„W 5 sekund”** (Porównanie → Wnioski i rekomendacje): werdykt, cztery kafelki ze statusem i trzy ruchy w układzie Stan → Dowód → Ruch.
- **Mapa przewag:** marki × 8 wskaźników z mini-wykresem trendu; ramka = lider kolumny.
- **Kopiuj podsumowanie:** gotowy tekst do maila lub Slacka.
- **Wiarygodność danych:** lista uwag (próba z limitem, strona znaleziona po nazwie, mało reklam, brak formatów lub demografii, stary okres porównawczy).
- **Symulator budżetu** w „Udziale w głosie”, osobno dla Meta i Google.
- **Formularz:** „Wklej listę”, podsumowanie pod konkurentami, skrót Ctrl + Enter (Mac: ⌘ + Enter).

</details>

<details>
<summary><b>Wersja 20.0 · Meta + Google</b></summary>

RivalCore analizuje dwa kanały. Pasek u góry ma trzy moduły:

| Moduł | Adres | Co robi |
|---|---|---|
| Konkurencja · Meta + Google | `#konkurencja` (domyślny) | Formularz z blokiem Źródła danych. Marki wpisujesz raz; jeden przycisk pobiera oba kanały równolegle |
| Wyniki kont · Google Ads | `#wyniki` | Wyniki kont klientów ze skryptu Google Ads |
| Połączenia | `#polaczenia` | Osobno dostęp Meta (token) i dostęp Google (projekt, klient OAuth) |

- Obszar emisji i okres są wspólne dla obu kanałów. Dla Google: jeśli w obszarze jest Polska, bierze PL; jeden kraj EOG — ten kraj; kilka krajów albo „Cały świat” — łącznie EOG.
- Źródło Google: publiczny zbiór `bigquery-public-data.google_ads_transparency_center` (tabela `creative_stats`). Obejmuje reklamodawców z reklamami w EOG i Turcji.

</details>

## 1. Pierwsze uruchomienie (token Meta)

Robisz to raz. Weryfikacja tożsamości może potrwać od kilku godzin do 1–2 dni.

1. **Potwierdź tożsamość** — `facebook.com/ID`, dokument + kraj. Bez tego API zwraca błąd 10, nawet z poprawnym tokenem.
2. **Zaakceptuj dostęp do API** — `facebook.com/ads/library/api` → „Rozpocznij”.
3. **Utwórz aplikację** — `developers.facebook.com` → Moje aplikacje → Utwórz aplikację (typ „Inne” / „Firma”). Nic w niej nie konfigurujesz.
4. **Wygeneruj token** — Graph API Explorer: wybierz aplikację → „User Token” → Generate Access Token. Dodatkowych uprawnień nie trzeba.
5. **Przedłuż token do ~60 dni** — Access Token Debugger → „Przedłuż token dostępu”.
6. **Sprawdź w narzędziu** — Połączenia → sekcja Meta → wklej token → „Sprawdź token”.

Ważne: weryfikacja, aplikacja i token muszą być z tego samego konta Facebook, a token generujesz po zakończeniu weryfikacji.

## 1b. Pierwsze uruchomienie: Google

Robisz to raz na całą agencję. Projekt Google Cloud i klient OAuth mogą być wspólne dla zespołu. **To połączenie nie ma nic wspólnego z tokenem Meta** — możesz mieć tylko jedno z dwóch.

### Czego potrzebujesz

| Element | Do czego | Koszt |
|---|---|---|
| Projekt Google Cloud z BigQuery API i Google Sheets API | zapytania o reklamy konkurencji, odczyt arkusza z wynikami | 0 zł w trybie piaskownicy (1 TB zapytań miesięcznie) |
| Klient OAuth typu „Aplikacja internetowa” | logowanie kontem Google w RivalCore | 0 zł |
| RivalCore otwierany pod adresem `https://` (np. GitHub Pages) | Google nie loguje plików otwartych z dysku | 0 zł |
| Skrypt Google Ads w koncie MCC + arkusz Google | wyniki kont klientów | 0 zł |

Developer tokena Google Ads nie potrzebujesz.

### A. Projekt i BigQuery (ok. 15 minut)

1. Utwórz projekt: `console.cloud.google.com/projectcreate`. Zapisz **ID projektu** (np. `rivalcore-472118`), nie nazwę.
2. Włącz w nim **BigQuery API** i **Google Sheets API**.
3. Rozliczenia: bez karty działa piaskownica BigQuery — 1 TB zapytań miesięcznie za darmo. Jedna analiza Google przetwarza ok. 30–40 GB, czyli ok. 25 analiz miesięcznie. Potem ok. 6,25 USD za TB (ok. 25 gr za analizę).
4. Ekran zgody OAuth: Google Auth Platform → Branding. Nazwa „RivalCore”, e-mail pomocy, odbiorcy Zewnętrzny (albo Wewnętrzny przy Google Workspace). W „Odbiorcy” dodaj konta zespołu jako użytkowników testowych.
5. Klient OAuth: Google Auth Platform → Klienci → Utwórz klienta, typ **Aplikacja internetowa**. W „Autoryzowane źródła JavaScript” dodaj `https://biedronm.github.io` (bez ścieżki i bez ukośnika na końcu) oraz `http://localhost:8000`. Pole przekierowań zostaw puste. Skopiuj **ID klienta**. Sekretu klienta nie wpisuj nigdzie i nie wrzucaj do repozytorium.
6. W RivalCore → Połączenia → sekcja Google wpisz ID projektu i ID klienta (pola są puste, każdy uzupełnia własne), kliknij **Połącz z Google**, zaakceptuj uprawnienia (BigQuery i odczyt arkuszy). W trybie testowym Google pokaże „Aplikacja niezweryfikowana” — kliknij „Kontynuuj”. Na koniec **Test BigQuery**.
7. Logowanie trwa godzinę. ID projektu i klienta zapamiętują się w przeglądarce; token logowania nie zapisuje się nigdzie.

Każda osoba w zespole potrzebuje w tym projekcie roli **Użytkownik zadań BigQuery** (`roles/bigquery.jobUser`).

### B. Skrypt Google Ads (ok. 10 minut)

1. Utwórz pusty arkusz Google, np. „RivalCore · dane Google Ads”, i udostępnij go zespołowi.
2. Google Ads → konto menedżera (MCC) → Narzędzia → Działania zbiorcze → Skrypty → „+” → Nowy skrypt.
3. W RivalCore → Wyniki kliknij **Skrypt Google Ads** (kopiuje się do schowka) i wklej. W pierwszej linii podmień `SHEET_URL`. Opcjonalnie `ACCOUNT_LABEL` (etykieta kont w MCC) i `DAYS` (domyślnie 90).
4. Autoryzuj → Uruchom. Skrypt zapisuje zakładki **RC_dane** (kampania × dzień), **RC_frazy** (wyszukiwane hasła z 30 dni) i **RC_info** (data aktualizacji, liczba kont, błędy).
5. Ustaw harmonogram: codziennie, np. o 6:00.
6. W RivalCore → Wyniki wklej link do arkusza i kliknij **Wczytaj z arkusza**. Bez logowania: pobierz arkusz jako .xlsx i użyj „Wczytaj CSV / XLSX”.

Limit czasu skryptu Google Ads to 30 minut — wystarcza na kilkadziesiąt kont. Przy bardzo dużym MCC użyj `ACCOUNT_LABEL` i dwóch skryptów.

### C. Dlaczego nie bezpośrednio Google Ads API?

Wymaga zatwierdzonego developer tokena i nie da się go wywołać z przeglądarki (brak CORS), więc potrzebny byłby serwer. Skrypt Google Ads daje te same dane bez tokena i bez serwera. Bezpośrednie API ma sens dopiero przy wersji SaaS z backendem.

### Publikacja na GitHub Pages

1. Podmień `index.html` w repozytorium `biedronm/rivalcore` na nową wersję. Bez gałęzi i PR-ów — po prostu podmiana pliku.
2. Settings → Pages → Branch `main` / root. Adres: `https://biedronm.github.io/rivalcore/`.
3. Upewnij się, że `https://biedronm.github.io` jest w „Autoryzowanych źródłach JavaScript” klienta OAuth (krok A5).

## 2. Jak zrobić analizę

1. Otwórz RivalCore w Chrome lub Edge.
2. **Źródła danych** — włącz Metę, Google albo oba. W kafelku Meta wklej token (opcjonalnie „Zapamiętaj token na tym komputerze”); kafelek Google ma własny blok logowania.
3. **Twoja marka** — nazwa, a obok (pewniej) ID strony albo link z Biblioteki Reklam. Marka z kilkoma kontami: „+ konto”, maks. 10 — liczą się razem jako jedna marka. Błędne ID podświetli się na czerwono.
4. **Konkurenci** — każdy w osobnym okienku (nazwa + ID/link). „+ Dodaj konkurenta”, kosz usuwa, „+ konto” dokłada konto tej samej marce. Żeby porównać konta jednej firmy osobno, dodaj je jako osobnych konkurentów. Nie wiesz, kogo wpisać? Rozwiń „Odkryj konkurentów po frazie”. Masz listę w Excelu? „Wklej listę”.
5. **Konta Google** — gdy źródło Google jest włączone, pod konkurentami pojawia się tabela reklamodawców: „Znajdź”, „Wklej ID” (AR… albo link z adstransparency.google.com), „Znajdź wszystkich w Google”. Wybory zapamiętują się dla nazwy marki.
6. **Obszar emisji** — kraje (kafelki) albo „Cały świat”.
7. **Ustawienia zaawansowane** (zwinięty pasek pokazuje aktualne wartości) — pobieranie marek (domyślnie 3 naraz), limity reklam, okres, tendencje i porównania, język, próg evergreen, założenia kosztu.
8. Kliknij **Analizuj**. Pod przyciskiem pojawi się panel postępu dla każdej marki.
9. Jeśli narzędzie trafiło na złą stronę, w zakładce „Przegląd” tej marki są przyciski z innymi znalezionymi stronami.

### Okres i porównania

Okres („Z jakiego okresu”) jest wspólny dla wszystkich kont, żeby porównanie było uczciwe. Liczą się reklamy emitowane choć jeden dzień w okresie — także uruchomione wcześniej. Zasięg i wydatki z API dotyczą całej emisji reklamy, nie samego okresu; narzędzie mówi to w banerze, w PDF, Excelu i pliku dla AI.

Pole „Tendencje i porównania”:

- **porównaj z poprzednim analogicznym okresem** (domyślnie) — pobiera dodatkowo okres tuż przed wybranym; pojawiają się tabele „Porównanie okresów”;
- **porównaj na tle całej historii** — pełne wykresy 12 miesięcy plus porównanie okres do okresu (najwolniej);
- **tylko wybrany okres** — nic więcej nie pobiera; brakujące porównania są oznaczone „b.d.”, a nie liczone jako zero.

Dane starsze niż ok. 12 miesięcy: Meta usuwa reklamy komercyjne ok. roku po zakończeniu emisji, więc starszy okres jest zaniżony. W takiej sytuacji narzędzie nie pokazuje procentowej zmiany (w tabelach „—”), tendencję liczy jako ostatnie 90 dni vs poprzednie 90 dni i nie używa takiego porównania we wnioskach.

### Zapis i wczytanie analizy

„Zapisz analizę” zapisuje pobrane dane, ustawienia **oraz Twoje ręczne korekty rabatów i argumentów** do pliku `.json`. „Wczytaj analizę” otwiera go później — bez tokenu i bez pobierania (dobre do prezentacji i jako archiwum). Wczytana analiza ma baner „stan danych na …”.

### Założenia kosztu dla poszczególnych marek

„Ustawienia zaawansowane” → „Założenia dla poszczególnych marek”: CPM marki (min–max), częstotliwość marki (min–max) i CPM wg formatu kreacji (wideo, grafika, mem, inne).

Hierarchia: 1. CPM formatu tej marki → 2. CPM marki → 3. założenia globalne (benchmark albo kalibracja). Puste pole dziedziczy wartość z poziomu wyżej. Pole błędne (min > max, częstotliwość < 1) jest pomijane i oznaczone na czerwono — narzędzie niczego nie zgaduje. W wynikach widać efektywny CPM i tabelę „Skąd ten CPM”. CPM wg formatu działa tylko przy włączonym „Pobieraj typ mediów”.

### Kalibracja na realnym wydatku

„Ustawienia zaawansowane” → „Kalibracja na realnym wydatku”: wybierz markę, której prawdziwy wydatek znasz, wpisz kwotę i okno. Narzędzie wylicza efektywny CPM = wydatek ÷ (szacowane wyświetlenia ÷ 1000) i ustawia CPM ±15% dla wszystkich marek. Ręczna zmiana CPM albo wybór benchmarku wyłącza kalibrację. Osobna kalibracja Google jest w „Google: ustawienia”.

## 3. Ustawienia

| Ustawienie | Do czego służy |
|---|---|
| Benchmark branżowy | Podstawia CPM i częstotliwość dla branży. Mnożnik nakłada się na stawki wybranego kraju |
| Sezon | Korekta stawek: Q4 / Black Friday / Święta (+25%) lub lato (−10%) |
| CPM min/max, częstotliwość | Można nadpisać ręcznie — np. realnymi stawkami z kont klientów |
| Pobieraj demografię, targetowanie i płatników | Więcej danych, wolniej przy dużych markach. **Wymagane przez mapę wolnych pól** |
| Pobieraj typ mediów | Rozpoznaje wideo / grafikę (3 dodatkowe zapytania na markę) |
| Sprawdzaj reklamy społeczne i polityczne | Dla nich Meta podaje prawdziwe wydatki |
| Eksport / import migawek | Kopia zapasowa historii analiz |
| Wersja Graph API | Zmień, jeśli pojawi się błąd wersji |
| Opóźnienie danych Google | „Google: ustawienia” — korekta niepełnych ostatnich dni (zalecana) albo liczenie do ostatniej daty w danych. Patrz [punkt 6](#6-dane-google-opóźnienie-partii-i-granica-danych) |

Filtry wyników (pod formularzem, po analizie) przeliczają wszystko od razu, bez ponownego pobierania: okres emisji, platforma, format, tylko aktywne, próg evergreen. Próg evergreen jest jednocześnie progiem „żyje długo” w zakładce „Co przeżywa” i w briefie.

## 4. Wyniki — zakładki

Na górze wybierasz Porównanie albo konkretną markę (liczba obok nazwy to indeks aktywności 0–100). Niżej — zakładki tematyczne. Każda zaczyna się od ramki z najważniejszym wnioskiem.

### Zakładki marki

| Zakładka | Co zawiera |
|---|---|
| Przegląd | KPI, indeks aktywności, najważniejsze w skrócie, trend 12 miesięcy, szacowane wyświetlenia i koszt, największe aktywne reklamy |
| Oś czasu | Starty reklam, szacowany budżet tygodniowy i fale rabatów na jednym wykresie + lista „Co się działo” |
| Prawdopodobny budżet | Przedziały wydatków (99 / 95 / 90 / 80 / 50%), rozkład, kalkulator „jakie są szanse, że wydaje więcej niż X zł” |
| Kreacje i testy | % reklam wyłączanych w ≤7 dni, reklamy równoległe, DCO, formaty, platformy, długość życia, evergreeny |
| Kampanie | Koncepty kreatywne i fale startów |
| Przekaz | Ton, CTA, emoji, długość tekstów, najczęstsze słowa i hasła, mechaniki, strony docelowe, nagłówki |
| Co przeżywa | Argumenty reklam a przeżywalność, słowa reklam długich i krótkich, co zostawili i co wyłączyli, detektor testów A/B, **lista argumentów do korekty i słownik** |
| Brief kreatywny | Stawiaj na / Uważaj / Język / Oferta / Do kogo / trzy koncepty, „Kopiuj brief” |
| Oferty i ceny | Rabaty, ceny, mechaniki promocyjne, rabaty tydzień po tygodniu, zagrania promocyjne, **lista wykrytych rabatów do weryfikacji** |
| Odbiorcy | Piramida wieku i płci, kraje, targetowanie, lokalizacje, płatnik i beneficjent, **argumenty wg grup odbiorców** |
| Kalendarz | Mapa cieplna startów, dzień tygodnia startu, aktywność przed ważnymi datami |
| Zmiany | Co nowego od poprzedniej analizy |
| Społeczne i polityczne | Prawdziwe wydatki i wyświetlenia (tylko jeśli marka ma takie reklamy) |

### Zakładki porównania

Pod nagłówkiem „Porównanie z konkurencją” są przyciski „Porównuj:” — kliknięcie ukrywa markę we wszystkich zakładkach porównania, a udziały liczą się wtedy tylko dla zaznaczonych marek. Twoja marka zostaje zawsze, muszą zostać co najmniej dwie marki. PDF, prezentacja, Excel i pakiet do strategii nadal zawierają wszystkie marki.

| Zakładka | Co zawiera |
|---|---|
| Wnioski i rekomendacje | „W 5 sekund”, wnioski, rekomendacje z priorytetami, karty marek, mapa przewag |
| Udział w głosie | Budżety z przedziałami, udziały w wydatkach / reklamach / zasięgu, symulator budżetu |
| Prawdopodobny budżet | Budżety wszystkich marek obok siebie i „piramidka” 50–99% |
| Kreacje i testy | Formaty, testowanie, koncepty, DCO, evergreeny, platformy |
| Przekaz i oferty | „Konkurencja mówi, Ty nie”, Twoje wyróżniki, oferty, rabaty, ceny, CTA |
| Odbiorcy | Struktura wieku, luki demograficzne, lokalizacje |
| Kalendarz | Tygodniowa oś startów wszystkich marek z ważnymi datami |
| Co przeżywa | Argumenty × marki, słowa, testy A/B marka obok marki |
| Wojna rabatowa | Siatka tygodni, fale promocji, „kto zaczął, kto dołączył”, zagrania promocyjne |
| Mapa wolnych pól | Argument × grupa wieku i płci, wolne pola i miejsca gęste |
| Brief kreatywny | Brief z danych konkurencji |
| Rankingi i indeks | Wskaźniki indeksu i rankingi z różnicą „vs Ty” |

### Zakładki Google i Meta + Google

Gdy włączysz źródło Google, nad wynikami pojawiają się trzy poziomy: **Meta**, **Google** i **Meta + Google**. Zakładka Google ma własny zestaw widoków (porównanie marek i widok pojedynczej marki): udział w wyświetleniach, budżet i struktura, formaty, powierzchnie, odbiorcy, kraje, kreacje, kalendarz. Zakładka Meta + Google zestawia oba kanały: łączny udział w głosie, tabela marek w obu kanałach, wspólna oś czasu i podział budżetu w czasie.

## 5. Dwie liczby budżetu: prognoza i średnia z okresu

To najczęstsze źródło pytania „dlaczego ta sama marka ma tu inną kwotę”. Obie liczby są poprawne, mierzą co innego.

| Gdzie | Co to jest | Jak liczone |
|---|---|---|
| Zakładka **Meta** — „szac. koszt / mies. (prognoza)” | Ile marka wyda w ciągu najbliższego miesiąca, jeśli nic nie zmieni | Dzisiejszy zasięg dzienny aktywnych reklam × 30 dni × częstotliwość × CPM ÷ 1000 |
| Zakładka **Meta + Google** — kolumna „Meta / mies.” | Ile marka wydawała średnio w analizowanym okresie | Koszt całego okresu ÷ liczba dni × 30 |

Dlaczego nie jedna liczba w obu miejscach: **dla Google prognozy policzyć się nie da.** Centrum przejrzystości podaje wyświetlenia narastająco, bez dziennego tempa emisji, więc jedyna wspólna baza dla obu kanałów to średnia z okresu. Gdyby zakładka Meta + Google pokazywała prognozę Mety obok historii Google, suma i udziały byłyby bez sensu.

Skutek, który warto znać przed rozmową z klientem: **marka, która właśnie przyspieszyła, ma na zakładce Meta wyższą liczbę niż na Meta + Google, a marka wygaszająca emisję — niższą.** Przy marce rosnącej o 118% różnica potrafi być dwukrotna.

Gdzie to widać w narzędziu:

- zakładka Meta pisze „(prognoza)” przy etykiecie;
- zakładka Meta + Google ma w pasku stanu „budżet: średnia z okresu × 30 dni”, tooltipy przy nagłówkach kolumn Meta i Google oraz akapit pod tabelą;
- najechanie na wartość w kolumnie Meta pokazuje obie liczby obok siebie (prognoza pojawia się, gdy różni się o ponad 5%);
- okładka raportu i slajd „Najważniejsze liczby” używają średniej z okresu, gdy jest analiza Google, i mówią to w stopce;
- „Raport w skrócie” w PDF ma bazę podpisaną przy każdym nagłówku.

## 6. Dane Google: opóźnienie partii i granica danych

To **dwa osobne mechanizmy** na dwa osobne problemy. Łatwo je pomylić, bo oba kończą wykresy wcześniej niż dzisiejsza data.

### Horyzont kompletnych danych (opóźnienie partii)

Google dosyła statystyki partiami: część kreacji ma dane do dnia X, a pojedyncze już do X + kilka dni. Bez korekty analiza liczyłaby wszystko do najpóźniejszej daty, więc reszta kreacji wyglądałaby na wyłączone, a końcówka wykresów na spadek.

RivalCore wyznacza **horyzont kompletnych danych** — najpóźniejszy dzień, do którego sięga co najmniej połowa ostatnio aktywnych kreacji — i do niego liczy okres, aktywne kreacje, trendy, porównania i wykresy. Nad wynikami pojawia się baner „Dane Google kompletne do …” z liczbą pominiętych dni.

- Skala: dni, nie tygodnie.
- Wyłącznik: „Google: ustawienia” → „Opóźnienie danych Google”.
- Test z 9-dniowym opóźnieniem: bez korekty 11 aktywnych kreacji i ostatni tydzień 51 → 11; z korektą 52 i ostatni tydzień 59 → 52.

### Granica danych (zbiór przestaje raportować markę)

Zdarza się, że Centrum przejrzystości przestaje raportować wyświetlenia analizowanych marek na **tygodnie albo miesiące** przed ostatnią datą w zbiorze — bo inni reklamodawcy w tym kraju raportują dalej, horyzont jest aktualny, a akurat te marki znikają z danych. Wykresy spadały wtedy do zera i wyglądały jak wyłączone kampanie.

Detekcja patrzy na **sumę tygodniowych wyświetleń wszystkich analizowanych marek** i szuka urwiska: ostatni tydzień, w którym suma sięga co najmniej 15% typowego (mediannego) tygodnia. Flaga zapala się dopiero przy ogonie co najmniej dwóch tygodni. Celowo liczona jest suma, nie pojedyncza marka — jedna marka może naprawdę przestać emitować, ale żeby cały zestaw spadł do zera w tym samym tygodniu, musi to być koniec danych.

Co się wtedy dzieje:

| Element | Zachowanie |
|---|---|
| Wykresy liniowe | Linia Google urwana na ostatnim tygodniu z danymi; linia Meta biegnie dalej |
| Linia „Razem” | Też urwana — suma, w której brakuje jednego kanału, nie jest sumą |
| Obszar bez danych | Zakreskowany na szaro, podpis „brak danych Google”, w legendzie „brak danych — nie zero” |
| Pasek podziału kanałów | Tygodnie bez danych zakreskowane zamiast malowane na „100% Meta” |
| Porównanie pierwszych i ostatnich tygodni | Liczone do ostatniego tygodnia z danymi |
| Wykres miesięczny | Miesiące po granicy pominięte, z adnotacją |
| Komunikat | Ramka nad wykresami, wpis w „Najważniejsze w skrócie”, plakietka w pasku stanu, podpis pod wykresem |
| Eksporty | Wiersz w arkuszu „Zakres danych”, blok w pliku dla AI, ostrzeżenie na slajdzie „Meta + Google”, punkt w metodologii prezentacji, stopka okładki raportu |

Granica danych nie ma wyłącznika — to nie jest założenie modelu, tylko stwierdzenie faktu o zbiorze.

**Czego to nie rozwiązuje:** kreacja, której Google jeszcze nie pokazał w zbiorze, pojawi się dopiero przy kolejnej analizie. Jeśli granica cofa się o wiele tygodni przy każdej analizie, sprawdź liczbę reklam 1–2 marek na `adstransparency.google.com` — może chodzić o niekompletność zbioru względem strony, a nie o opóźnienie.

## 7. Co liczy Metę, co liczy oba kanały

Centrum przejrzystości Google **nie udostępnia tekstów reklam**. Dlatego wszystko, co powstaje z treści — argumenty, rabaty, ceny, CTA, ton, koncepty, brief, mapa wolnych pól — liczy wyłącznie Metę. W materiałach dla klienta każda taka sekcja jest teraz podpisana.

| Element | Źródło | Jak podpisany |
|---|---|---|
| Okładka raportu: koszt, aktywne reklamy, wyświetlenia | Meta + Google | Rozbicie pod każdą liczbą („Meta … + Google …”) |
| Indeks aktywności | Meta | „(Meta)” na okładce i „· META” w prezentacji |
| Udział w głosie, Aktywność, Marki w skrócie, Oś czasu | Meta | „· META” w kickerze slajdu, plakietka w nagłówku na ekranie, dopisek w kickerze strony PDF |
| Co przeżywa, Wojna rabatowa, Mapa wolnych pól, Brief kreatywny | Meta (teksty reklam) | „· META” w kickerze slajdu |
| Słupki podziału budżetu w „Raporcie w skrócie” | Meta + Google, jedna baza | Baza podpisana przy nagłówku |
| Zakładka Meta + Google | Oba kanały | Pasek stanu z bazą i datą końca danych Google |
| Sekcje Google (udział w wyświetleniach, formaty, powierzchnie) | Google | Kicker „Google Ads · Centrum przejrzystości reklam” |

Gdy analizy Google nie ma, dopiski znikają — raport wygląda jak przed wersją 25.2, bez niepotrzebnego szumu.

## 8. Ręczne korekty: rabaty, argumenty, słownik branżowy

Wykrywanie rabatów i argumentów to **reguły słownikowe, bez AI**. Dlatego każda z tych warstw ma listę do poprawienia — a wyniki korekt wchodzą wszędzie: na ekran, do PDF, do prezentacji i do Excela.

| Co poprawiasz | Gdzie | Jak |
|---|---|---|
| Rabaty | zakładka marki → Oferty i ceny → „Wykryte rabaty — lista do weryfikacji” | „Odrzuć” przy fałszywym trafieniu, „Uznaj za rabat” przy odrzuconym automatycznie, „Cofnij decyzję” wraca do automatu |
| Argumenty reklam | zakładka marki → Co przeżywa → „Argumenty reklam — lista do korekty” | Klik w argument zdejmuje go, „+ dodaj argument” przypisuje nowy |
| Słownik | pod listą argumentów → „Słownik argumentów” | Branża, własne frazy do każdego argumentu, własne argumenty (do 12) |

Zasady:

- Reklamy z identycznym tekstem (albo identycznym fragmentem rabatu) są zgrupowane w jednym wierszu — decyzja obejmuje wszystkie, także u innych marek w tej analizie.
- Korekty i słownik zapisują się w przeglądarce (localStorage) i w pliku „Zapisz analizę”. Przy zmianie komputera przenieś je przez zapisaną analizę.
- Każda zmiana natychmiast przelicza statystyki rabatów, „Wojnę rabatową”, „Co przeżywa”, mapę wolnych pól i brief.
- PDF i prezentacja nie pokazują przycisków — pokazują wynik po korektach plus linijkę „Słownik argumentów: …”, żeby było wiadomo, na czym liczono.
- Branże w słowniku to punkt startu ułożony ręcznie, nie wynik badania reklam w danej kategorii. Warto dopisać własne frazy.

## 9. Lupa detektywa — skąd pochodzi każda informacja

Pasek pod nagłówkiem strony. Zaznacz, co chcesz oznaczyć — bloki dostaną kolorową ramkę i etykietę. Oznaczenia trafiają też do PDF.

| Oznaczenie | Co to jest | Przykłady |
|---|---|---|
| 🟩 Czyste dane | Wartości wprost z Meta API | listy reklam, zasięg, demografia, targetowanie, płatnik, formaty |
| 🟦 Obliczenia | Matematyka na danych | średnie, udziały, trendy, rankingi, rozkłady, przeżywalność |
| 🟨 Poszlaki | Modele, przyjęte progi, wykrywanie w tekstach | szacowany koszt, indeks aktywności, rabaty, argumenty, ceny, ton, koncepty, testy A/B |
| 🟪 Dedukcja detektywa | Interpretacje narzędzia | ramki z żarówką, „Najważniejsze w skrócie”, rekomendacje, brief kreatywny |

Przed wysłaniem raportu klientowi warto włączyć „Poszlaki” i „Dedukcję”, żeby świadomie zdecydować, co zostawić.

### Dymki „Skąd to?”

Najedź kursorem na liczbę, rekomendację albo ikonę ⓘ przy tytule sekcji (na telefonie: stuknij). Dymek pokazuje rodzaj informacji w kolorze Lupy, rachunek na prawdziwych liczbach z tej analizy i źródło założeń. Przykład dla kosztu: `401 312 os./dzień × 30 dni × częst. 1,61 = 19 412 906 wyświetleń → ÷ 1000 × CPM 15,81 zł ≈ 306 945 zł`.

Dymki działają na ekranie w narzędziu **oraz w raporcie HTML w wersji „jak aplikacja”** — tam klient sam sprawdzi każdą liczbę, bez dzwonienia do Ciebie. W PDF, prezentacji i PNG ich nie ma (to formaty statyczne). Przy prezentacji dla zarządu można je wykorzystać do odpowiedzi na „skąd ta liczba?”.

## 10. Eksporty: PDF, prezentacja PPTX, Excel, plik dla AI, pakiet do strategii

Wszystkie eksporty są w jednym menu **„Eksport i zapis”** przy nagłówku „Wyniki” — widocznym niezależnie od tego, czy jesteś na zakładce Meta, Google czy Meta + Google. Pozycje są pogrupowane po źródle:

| Grupa | Pozycje |
|---|---|
| Raport i prezentacja (oba kanały) | Raport — PDF albo HTML, Prezentacja (PPTX) |
| Meta | Excel — Meta, Pakiet do strategii, Plik dla AI — Meta |
| Google | Excel — Google, Plik dla AI — Google |
| Meta + Google | Excel — oba kanały |
| Sesja | Zapisz analizę — Meta, Zapisz analizę — Google, Wyczyść wyniki |

Pozycja, dla której nie ma danych w sesji, jest wyszarzona i mówi w podpowiedzi, czego brakuje (np. „Excel — oba kanały” wymaga analizy z obu źródeł). Zakładki Google i Meta + Google mają dodatkowo własne przyciski eksportu przy wynikach — to skrót, menu robi to samo.

### Prezentacja PowerPoint (.pptx)

Przycisk **Prezentacja (PPTX)**. Plik otworzysz w PowerPoint, Google Slides i Keynote; z PowerPointa wyeksportujesz PDF.

- **Wszystko jest edytowalne**: teksty to pola tekstowe, tabele to tabele, wykresy to natywne wykresy PowerPointa z dołączonymi danymi („Edytuj dane”). Nic nie jest obrazkiem.
- **Do 15 slajdów do wyboru**: okładka, agenda, najważniejsze liczby, udział w głosie, aktywność i świeżość kreacji, marki w skrócie, oś czasu marki, Meta + Google, co przeżywa, wojna rabatowa, mapa wolnych pól, brief kreatywny, rekomendacje, metodologia, slajd końcowy.
- **Presety**: wszystkie / standard / krótka wersja.
- **Motyw**: ciemny BeDigital (na ekran) albo jasny (do druku i jasnego rzutnika). Pola na tytuł, podtytuł, klienta, autora i logo na okładce.
- **Notatki prelegenta** przy każdym slajdzie zawierają zastrzeżenia do liczb.
- **Slajd bez danych sam się pomija** (bez Google nie ma slajdu kanałów, przy jednej marce nie ma udziału w głosie) — i **agenda wymienia tylko te slajdy, które faktycznie powstały**.
- **Slajdy liczone tylko z Mety mają „· META” w kickerze**, gdy w analizie jest też Google.
- Jeśli któryś slajd zbuduje się niekompletnie, komunikat po pobraniu poda jego nazwę.
- Prezentacja uwzględnia aktualne filtry, założenia kosztu i ręczne korekty.
- Slajdy używają czcionki **Montserrat**; bez niej zainstalowanej PowerPoint podmieni ją na domyślną.
- Pierwsze kliknięcie pobiera bibliotekę generującą .pptx z jsDelivr (z adresami zapasowymi) — wymaga internetu.

### Raport HTML (jeden plik do wysłania klientowi)

W panelu raportu, obok „Pobierz PDF”, jest przycisk **Raport HTML** i lista wyboru wyglądu. Zapisuje raport jako **jeden samodzielny plik `.html`**: klient dostaje go mailem, klika i czyta w przeglądarce — bez instalowania czegokolwiek i bez okna drukowania.

**Wygląd „jak aplikacja” (domyślny)** — raport wygląda i działa jak samo narzędzie:

- **sekcja „Jak czytać ten raport”** na wejściu: co raport pokazuje, a czego nie, cztery rodzaje informacji z licznikiem każdego, i od czego zacząć;
- **każda liczba tłumaczy, skąd się wzięła** — najedź kursorem (na telefonie stuknij), a zobaczysz rachunek na danych z tej analizy, np. `401 312 os./dzień × 30 dni × częst. 1,61 = 19 412 906 wyświetleń → ÷ 1000 × CPM 15,81 zł ≈ 306 945 zł`. W pełnym raporcie takich objaśnień jest ok. 190;
- przycisk **Podświetl objaśnienia** zaznacza wszystkie miejsca, które coś tłumaczą — klient wie, gdzie klikać;
- menu sekcji po lewej, pogrupowane tak jak zakładki w RivalCore (Na start, Podsumowanie, Porównanie marek, każda marka osobno, Google Ads, Meta + Google, O raporcie), z **wyszukiwarką sekcji**;
- jedna sekcja naraz, przełączanie kliknięciem albo strzałkami ← →, adres w pasku przeglądarki zmienia się razem z sekcją (da się podesłać link do konkretnej strony raportu);
- nagłówek z nazwą klienta i kafelkami KPI, pod nim Twój komentarz analityka;
- przycisk **Jasny motyw / Ciemny motyw** — klient czyta na ekranie po ciemnemu, drukuje po jasnemu;
- przycisk **Zapisz jako PDF** (i zwykłe Ctrl+P) rozwija wszystkie sekcje i drukuje cały raport;
- na telefonie menu zamienia się w poziomy pasek, a szerokie tabele przewijają się w swojej sekcji.

**Wygląd „jak wydruk”** — kartki A4 na szarym tle, dokładnie to, co wychodzi z „Pobierz PDF”. Wybierz, gdy raport ma wyglądać jak dokument, a nie jak aplikacja.

Wspólne dla obu:

- plik jest w całości samowystarczalny: style, wykresy (inline SVG), logo i tabele siedzą w środku. Działa też bez internetu (wtedy przeglądarka podstawi zamienniki czcionek);
- treść decydują te same pola panelu (sekcje, marki, logo, komentarz);
- rozmiar: ok. 0,9 MB w wersji „jak aplikacja”, ok. 1,7 MB w wersji „jak wydruk” przy pełnym raporcie dla trzech marek.

Kiedy co wybrać: **HTML**, gdy raport ma być wygodny do czytania na ekranie i na telefonie, ma wyglądać nowocześnie albo gdy klient ma sobie zrobić PDF po swojemu. **PDF**, gdy ma trafić do archiwum, do druku albo do załącznika o stałej paginacji. **PPTX**, gdy raport ma być omawiany na spotkaniu.

### Raport PDF

Przycisk **Raport PDF** → panel z ustawieniami: tytuł, klient, autor, logo, komentarz analityka, wybór sekcji i marek, okładka ciemna albo jasna. Gotowe zestawy: **Pełny raport**, **Skrót dla klienta** (~10 stron) i **Dla zarządu** (~5 stron).

Otworzy się okno drukowania — jako drukarkę wybierz „Zapisz jako PDF”, zostaw skalę 100% i zaznacz „Grafika tła”. Do druku na papierze wybierz jasną okładkę.

PDF nie potrzebuje żadnej biblioteki zewnętrznej — działa też bez internetu.

### Excel

Przycisk **Pobierz Excel** — ponad 20 arkuszy, same wartości, bez formuł. Arkusz „Zakres danych” w eksporcie Google zawiera datę, do której dane są kompletne, i ostrzeżenie o końcówce wykresów. Osobne przyciski mają: Meta (pełny eksport), Google i Meta + Google.

### Eksport dla AI (.md)

Plik Markdown z gotowym promptem i danymi — do wklejenia w Claude, ChatGPT lub inne AI. Wybierasz zakres analizy, formę odpowiedzi (audyt, raport dla klienta, notatka dla zespołu, konspekt prezentacji), branżę i cel oraz liczbę tekstów reklam. Prompt każe AI opierać się wyłącznie na danych z pliku i odróżniać dane od szacunków.

### Pakiet do strategii (PNG + dane)

Jeden plik `.zip`: wykresy jako PNG (z logo i podpisem źródła), `dane/fakty-do-strategii.csv`, pełny Excel i `CZYTAJ-MNIE.md`. Pojedynczy wykres pobierzesz też z wyników — najedź i kliknij PNG przy tytule.

## 11. Zestawy konkurentów i migawki

**Zestawy** (przyciski u góry formularza): zapisz markę, konkurentów, obszar, język, limity i okres pod nazwą, np. „Natura — drogerie”, i wczytuj jednym kliknięciem. „Eksport / Import” przenosi zestawy między komputerami.

**Migawki** zapisują się automatycznie po każdej analizie (jedna dziennie na stronę i obszar). Przy kolejnej analizie — najwcześniej następnego dnia — zakładka „Zmiany” pokaże różnice. Migawki żyją w przeglądarce: przed zmianą komputera zrób „Eksport migawek”.

## 12. Słowniczek wskaźników

| Wskaźnik | Definicja |
|---|---|
| Aktywna reklama | Bez daty zakończenia emisji albo z datą od dziś wzwyż |
| Evergreen | Reklama emitowana co najmniej X dni (ustawiasz sam, domyślnie 30) |
| Zasięg | `eu_total_reach` — szacunek Meta: ile kont w UE zobaczyło reklamę |
| **Szacowany koszt (prognoza)** | Dzisiejszy zasięg dzienny aktywnych reklam × 30 dni × częstotliwość × CPM ÷ 1000. Liczba na zakładce Meta — „ile wyda, jeśli nic nie zmieni” |
| **Szacowany koszt (średnia z okresu)** | Koszt całego analizowanego okresu ÷ liczba dni × 30. Liczba na zakładce Meta + Google — „ile wydawała w okresie”. Jedyna baza wspólna z Google |
| Szacowane wyświetlenia | Zasięg × częstotliwość. Meta nie podaje wyświetleń reklam komercyjnych |
| Wyłączane ≤7 dni | % zakończonych reklam, które działały maks. 7 dni — miara intensywności testów |
| DCO | Reklamy z kilkoma wariantami tekstu (dynamiczne kreacje) |
| Koncept | Reklamy z tym samym tekstem głównym |
| Argument reklamy | Jeden z 12 motywów przekazu wykrywanych w tekście (cena i rabat, wielosztuki, darmowa dostawa, pilność, dowód społeczny, jakość i skład, nowość, problem i rozwiązanie, wygoda, ekspert i edukacja, emocje, konkurs) plus argumenty własne ze słownika. Jedna reklama może mieć kilka |
| Przeżywalność | Odsetek reklam z danym argumentem, które działały co najmniej X dni (próg evergreen). Liczona tylko z reklam uruchomionych dość dawno, żeby mogły tyle dożyć |
| Obecny w tygodniach | W ilu tygodniach okresu argument w ogóle był w emisji — odróżnia argument rotowany od porzuconego |
| Akcja czasowa (⏱) | Argument, przy którym krótka emisja jest normalna: rabaty, pilność, konkursy, nowości, gratisy |
| Test A/B (wykryty) | Test kreacji = ten sam tekst i domena, min. 2 reklamy wystartowane w odstępie do 7 dni. Test copy = ten sam nagłówek i domena, wspólny start, różne teksty główne. WINNER = najdłuższa emisja, gdy inny wariant wyłączono albo przewaga wynosi min. 7 dni |
| Fala rabatów | Kolejne tygodnie, w których rabat procentowy ma co najmniej 20% aktywnych reklam marki |
| Wolne pole | Grupa wieku i płci od 5% zasięgu, w której argument używany w kategorii (od 8%) pojawia się co najmniej o połowę rzadziej |
| **Horyzont kompletnych danych Google** | Najpóźniejszy dzień, do którego sięga co najmniej połowa ostatnio aktywnych kreacji — korekta opóźnienia partii, w skali dni |
| **Granica danych Google** | Ostatni tydzień, w którym suma wyświetleń wszystkich analizowanych marek sięga ≥15% mediannego tygodnia — moment, od którego zbiór przestaje raportować te marki, w skali tygodni |
| Fala startów | Dzień, w którym wystartowały co najmniej 3 nowe reklamy |
| Indeks aktywności 0–100 | Skala 25%, zasięg 25%, świeżość 15%, testowanie 15%, regularność 10%, różnorodność 10%. Liczony wyłącznie z Mety |
| Ton sprzedażowy | Reklama zawiera ofertę, cenę lub rabat |
| Luka demograficzna | Różnica udziału grupy (wiek + płeć) w zasięgu: średnia konkurencji minus Twoja marka, w pp |
| Udział w głosie | Udział marki w sumie szacowanych wydatków / aktywnych reklam / zasięgu wszystkich analizowanych marek |

## 13. Ograniczenia danych — przeczytaj przed wysłaniem raportu klientowi

### Meta

- **Brak realnych wydatków i wyników.** Meta nie publikuje wydatków reklam komercyjnych ani CTR / konwersji / ROAS. Koszt to zawsze szacunek — do porównań między markami, nie jako dokładny budżet.
- **Zasięg jest ogólnounijny.** `eu_total_reach` to zasięg w całej UE, a filtr obszaru dotyczy tego, gdzie reklama była emitowana. Marka paneuropejska wychodzi przez to wyżej niż marka emitująca tylko w Polsce — przy zestawianiu lokalnego gracza z siecią międzynarodową traktuj różnicę ostrożnie.
- **Tylko reklamy, które dotarły do UE.** Kampanie emitowane wyłącznie poza UE są niewidoczne.
- **Opóźnienie i retencja.** Reklamy pojawiają się z opóźnieniem do 1–2 dni; zakończone znikają ok. rok po końcu emisji.
- **Zasięg nie jest unikalny między reklamami.** Ta sama osoba może być policzona w kilku reklamach.
- **Pełne adresy stron docelowych nie są dostępne** — widać domenę z linku wyświetlanego w reklamie.
- **Nie ma identyfikatora grafiki.** Dlatego „test kreacji” to poszlaka: warianty mogą różnić się obrazem, wideo albo grupą odbiorców. Potwierdź w Bibliotece Reklam.

### Google

- **Brak wydatków i wyników.** Google publikuje zakresy wyświetleń, nie wydatki ani konwersje.
- **Zakresy wyświetleń są przedziałami** (np. 10–20 tys.). Część kreacji ma otwarty górny zakres.
- **Tylko EOG i Turcja.** Wyświetlenia raportowane od 1 marca 2023.
- **Zbiór bywa niepełny** względem strony Centrum przejrzystości. Przed raportem porównaj liczbę reklam 1–2 marek ze stroną `adstransparency.google.com`.
- **Dane przychodzą partiami, a raportowanie marki potrafi się urwać.** Stąd dwa mechanizmy z [punktu 6](#6-dane-google-opóźnienie-partii-i-granica-danych). Zerowa końcówka wykresu to brak danych, nie zerowe wydatki.
- **Brak tekstów kreacji.** Dlatego argumentów, rabatów, briefu i mapy wolnych pól nie da się policzyć dla Google — te zakładki liczą wyłącznie Metę i mówią to wprost.
- **Nazwy reklamodawców się powtarzają** („Bratex SARL” to inna firma niż polski Bratex). Sprawdź kraj i nazwę prawną, najpewniej wpisz ID `AR…`.

### Wnioski i interpretacje

- **Wykrywanie w tekstach to reguły.** Rabaty, argumenty, ceny, CTA i ton mogą się pomylić przy nietypowych sformułowaniach — dlatego są listy do korekty ([punkt 8](#8-ręczne-korekty-rabaty-argumenty-słownik-branżowy)).
- **Długa emisja to poszlaka, nie dowód**, że reklama się opłaca. Marka mogła ją zostawić z innych powodów.
- **Krótka emisja nie oznacza słabej reklamy.** Akcje czasowe, testy i kreacje sezonowe z założenia trwają krótko.
- **„Kto zaczął, kto dołączył”** w wojnie rabatowej to zbieżność w czasie, nie dowód reakcji.
- **Demografia Meta pokazuje, do kogo reklama dotarła**, a nie jak była targetowana. Wolne pole może być decyzją marek albo efektem algorytmu.
- **Rekomendacje i brief są regułowe** — nie znają marży, celów ani działań poza Meta. Traktuj je jako punkt wyjścia, a koncepty z briefu jako hipotezy do testu.

## 14. Rozwiązywanie problemów

### Meta

| Problem | Rozwiązanie |
|---|---|
| Błąd Meta 10 („Application does not have permission”) | Dokończ weryfikację na `facebook.com/ID` i akceptację na `facebook.com/ads/library/api`, potem wygeneruj nowy token tym samym kontem |
| Błąd Meta 190 | Token wygasł — wygeneruj nowy i przedłuż w Access Token Debugger |
| „Limit zapytań API, czekam…” | Normalne przy wielu markach — narzędzie samo odczeka |
| Błąd wersji API | W ustawieniach zmień wersję Graph API |
| Wybrana zła strona | Podaj ID strony / link albo kliknij właściwą stronę w „Przeglądzie” |
| Marka ma kilka fanpage'y i część reklam „ucieka” | Dodaj wszystkie konta przyciskiem „+ konto” |
| „Pominięto — ta sama strona już jest w analizie” | To samo konto jest w dwóch markach. Zostaw je w jednej |
| Brak demografii (i pusta mapa wolnych pól) | Włącz „Pobieraj demografię…”; dla reklam spoza UE Meta jej nie podaje |
| Zakładka „Zmiany” pusta | To pierwsza analiza tej strony na tym obszarze |
| Wolne pobieranie dużej marki | Ustaw limit reklam albo wyłącz „Pobieraj demografię…” i „Pobieraj typ mediów” |
| Marka międzynarodowa ma podejrzanie wysoki budżet | `eu_total_reach` liczy całą UE — patrz ograniczenia Meta wyżej |

### Google

| Problem | Rozwiązanie |
|---|---|
| „Logowanie Google nie działa w pliku otwartym z dysku” | Otwórz RivalCore z GitHub Pages albo lokalnie: `python -m http.server 8000` i `http://localhost:8000/index.html` |
| `redirect_uri_mismatch` / `origin_mismatch` | Adres narzędzia nie jest w „Autoryzowanych źródłach JavaScript” klienta OAuth. Dodaj bez ścieżki i bez ukośnika |
| „Przeglądarka zablokowała okno logowania” | Zezwól na wyskakujące okna dla tej strony |
| `access_denied` / „aplikacja nie przeszła weryfikacji” | Dodaj swoje konto jako użytkownika testowego (krok A4) |
| „API nie jest włączone w projekcie” | Włącz BigQuery API i Google Sheets API (krok A2) |
| „Brak uprawnienia do uruchamiania zapytań” | Sprawdź ID projektu (nie nazwę) albo nadaj rolę Użytkownik zadań BigQuery |
| „Przekroczony limit BigQuery” | Wyczerpany 1 TB w miesiącu. Podepnij płatności albo korzystaj z „Zapisz analizę” |
| Wykres Google spada do zera i tak zostaje | To granica danych, nie koniec emisji — narzędzie zakreskuje ten odcinek i poda datę. Patrz [punkt 6](#6-dane-google-opóźnienie-partii-i-granica-danych) |
| Ostatnie dni Google wyglądają na nagły spadek | Sprawdź baner „Dane Google kompletne do …”; jeśli korekta opóźnienia jest wyłączona, włącz ją w „Google: ustawienia” |
| Arkusz: „nie ma zakładek RivalCore” | Skrypt nie zapisał danych. Sprawdź `SHEET_URL` i uruchom skrypt ręcznie |
| Arkusz: 403 / 404 | Konto, którym się logujesz, nie ma dostępu do arkusza |

### Liczby i etykiety

| Problem | Rozwiązanie |
|---|---|
| Ta sama marka ma inny budżet na zakładce Meta i Meta + Google | To prognoza kontra średnia z okresu — obie poprawne. Patrz [punkt 5](#5-dwie-liczby-budżetu-prognoza-i-średnia-z-okresu); najedź na wartość w kolumnie Meta, żeby zobaczyć obie |
| Okładka raportu pokazuje inną kwotę niż zakładka Meta | Okładka sumuje oba kanały na bazie średniej z okresu, gdy jest analiza Google. Rozbicie jest pod liczbą |
| Nie wiem, czy slajd liczy Metę, czy oba kanały | Kicker slajdu kończy się „· META”, gdy liczy tylko Metę |

### Eksporty i korekty

| Problem | Rozwiązanie |
|---|---|
| „Nie udało się pobrać biblioteki (…)” | Sieć blokuje wszystkie trzy adresy zapasowe. Spróbuj z innej sieci albo wyłącz blokadę; raport PDF działa bez bibliotek zewnętrznych, a Excel Meta przełącza się wtedy na CSV |
| Excel pobrał się jako .csv zamiast .xlsx | Biblioteka Excela nie wczytała się z żadnego adresu — plik ma te same dane w jednym arkuszu |
| PowerPoint pyta o naprawę pliku | Zgłoś to z plikiem — generator można poprawić. W międzyczasie otwórz plik w Google Slides |
| Prezentacja ma inną czcionkę | Montserrat nie jest zainstalowany na tym komputerze. Zainstaluj go albo zmień czcionkę w PowerPoincie (Narzędzia główne → Zamień czcionki) |
| Po pobraniu prezentacji pojawia się „slajd zbudował się niekompletnie” | Otwórz wskazany slajd przed wysłaniem — reszta pliku jest w porządku. Zgłoś, który to slajd |
| Moje korekty rabatów zniknęły | Są zapisane w przeglądarce, na tym komputerze. Przy zmianie sprzętu przenieś je przez „Zapisz analizę” / „Wczytaj analizę” |
| „Mała próba” zamiast procentu w „Co przeżywa” | Mniej niż 5 reklam dość starych, żeby ocenić przeżywalność. Wydłuż okres albo obniż próg evergreen |
| Mapa wolnych pól pusta | Brak demografii w pobranych reklamach — włącz jej pobieranie i uruchom analizę ponownie |
| PDF bez kolorowych teł | W oknie drukowania zaznacz „Grafika tła” |

## 15. Prywatność i bezpieczeństwo

- Plik działa w całości w Twojej przeglądarce. Dane idą tylko między przeglądarką a Meta (`graph.facebook.com`) oraz Google (`accounts.google.com`, `bigquery.googleapis.com`, `sheets.googleapis.com`). Nic nie trafia na nasz serwer.
- Logowanie Google działa przez OAuth: RivalCore dostaje token na godzinę, trzyma go w pamięci karty i nie zapisuje. ID projektu i ID klienta OAuth nie są tajne; sekretu klienta narzędzie nie używa.
- Token Meta zapisuje się lokalnie tylko wtedy, gdy zaznaczysz „Zapamiętaj token”. Nie wysyłaj go nikomu — działa jak hasło.
- Z internetu dociągane są wyłącznie biblioteki open source (xlsx, pptxgenjs, jszip, html-to-image — z jsDelivr, cdnjs albo unpkg) i czcionki (Google Fonts). Żadna z nich nie dostaje Twoich danych — konwersja do Excela i .pptx dzieje się w przeglądarce.
- Zestawy, migawki, ustawienia, założenia marek, logo do PDF, wybór okładki, ważne daty **oraz ręczne korekty rabatów i argumentów i słownik branżowy** są w pamięci przeglądarki (localStorage) na tym komputerze.

## 16. Najczęstsze pytania (FAQ)

### O danych

**Skąd narzędzie bierze dane?** Z oficjalnego Meta Ad Library API i z publicznego zbioru Google w BigQuery — tych samych źródeł, które zasilają publiczne biblioteki reklam. Nie ma tu scrapowania; narzędzie pobiera to, co każdy może zobaczyć ręcznie, tylko automatycznie i dla wielu marek naraz.

**Jakie dane podaje Meta, a jakich nie?** Podaje: listę reklam, daty emisji, teksty, platformy, a dla emisji w UE także zasięg, rozkład wieku i płci oraz płatnika. Nie podaje dla reklam komercyjnych: wydatków, wyświetleń, kliknięć ani konwersji.

**Czy widać wyniki konkurencji — CTR, sprzedaż, ROAS?** Nie. Narzędzie pokazuje, co i jak intensywnie konkurencja reklamuje, a nie jak skuteczne są te reklamy. Pośrednią wskazówką jest czas emisji.

**Czy bot widzi reklamy, które już się skończyły?** Tak, ale tylko przez ok. rok od zakończenia emisji.

### O szacunkach kosztu

**Czy to są prawdziwe wydatki konkurencji?** Nie — to szacunek, wyraźnie oznaczony wszędzie. Koszt = zasięg × częstotliwość × CPM ÷ 1000.

**Dlaczego ta sama marka ma dwie różne kwoty w dwóch miejscach?** Bo to dwie różne miary: prognoza z dzisiejszego tempa emisji (zakładka Meta) i średnia z analizowanego okresu (zakładka Meta + Google, okładka raportu). Dla Google prognozy policzyć się nie da, więc zestawienie obu kanałów musi iść ze średniej. Szczegóły: [punkt 5](#5-dwie-liczby-budżetu-prognoza-i-średnia-z-okresu).

**Jak bardzo można ufać tym liczbom?** Jako rzędowi wielkości i do porównań między markami — bardzo dobrze, bo wszystkie marki liczone są tą samą metodą. Jako dokładnej kwoty — ostrożnie: bez kalibracji błąd może sięgać kilkudziesięciu procent. Najbardziej podnosi trafność kalibracja na realnym wydatku klienta agencji.

**Dlaczego marka międzynarodowa wychodzi tak wysoko?** Zasięg z Meta API (`eu_total_reach`) jest ogólnounijny, a nie z wybranego kraju. Sieć emitująca w kilkunastu krajach będzie przez to wyglądać na dużo większą od lokalnego gracza. Przy takim zestawieniu opisz to w raporcie albo skalibruj CPM na kliencie.

### O danych Google

**Wykres Google spada do zera w ostatnich tygodniach — konkurencja wyłączyła reklamy?** Najprawdopodobniej nie. To granica danych: Centrum przejrzystości przestało raportować te marki. Narzędzie wykrywa to samo, urywa linię, zakreskowuje odcinek i podaje datę. Patrz [punkt 6](#6-dane-google-opóźnienie-partii-i-granica-danych).

**Czym granica danych różni się od korekty opóźnienia?** Korekta opóźnienia obcina kilka ostatnich **dni**, w których Google jeszcze nie dosłał statystyk części kreacji — ma wyłącznik. Granica danych to **tygodnie albo miesiące**, w których zbiór w ogóle nie raportuje analizowanych marek — jest faktem o danych, więc wyłącznika nie ma.

**Dlaczego linia Meta biegnie dalej niż Google?** Bo dane Meta są świeższe. To różnica w dostępności danych, nie w wydatkach — i dokładnie dlatego linia „Razem” też jest urwana.

### O zakładkach i interpretacji

**Co to znaczy, że argument „przeżywa”?** Że reklamy z tym argumentem częściej niż średnia działają co najmniej X dni (domyślnie 30). To poszlaka, że się opłacają — marka wyłączyłaby je, gdyby nie działały. Nie jest to dowód skuteczności.

**Dlaczego sekcja nazywa się „Uważaj”, a nie „Nie rób tego”?** Bo krótka emisja często nie znaczy nic złego: rabaty, pilność, konkursy i nowości to akcje czasowe. Narzędzie oznacza je ⏱ i pokazuje kolumnę „Obecny w tygodniach” — jeśli argument wraca co tydzień, marka go rotuje, a nie porzuciła.

**Skąd wiadomo, że to był test A/B?** Nie wiadomo na pewno. Meta nie udostępnia identyfikatora grafiki ani struktury zestawu reklam, więc narzędzie wykrywa wzorzec: ten sam tekst albo nagłówek, ta sama domena, start w odstępie do 7 dni. Wariant „WINNER” to po prostu najdłużej emitowany. Przed pokazaniem klientowi warto kliknąć link i zobaczyć kreacje w Bibliotece Reklam.

**Czy „wolne pole” znaczy, że tam jest okazja?** Niekoniecznie. Demografia Meta mówi, do kogo reklama dotarła, a nie jak była targetowana. Wolne pole może być świadomą decyzją marek (ta grupa nie kupuje) albo efektem algorytmu. To miejsce do postawienia hipotezy, nie gotowa rekomendacja.

**Co zrobić, gdy detektor uzna „90% szynki” za rabat?** Kliknąć „Odrzuć” na liście wykrytych rabatów. Decyzja obejmie wszystkie reklamy z tym samym fragmentem i od razu przeliczy statystyki, wojnę rabatową i brief. Jeśli coś takiego powtarza się w Twojej branży, dopisz frazę do słownika.

**Czy brief kreatywny pisze AI?** Nie. Brief powstaje z reguł i liczb z tej analizy. Dla pogłębionej interpretacji jest osobny eksport z gotowym promptem do Claude albo ChatGPT.

### O eksportach

**PDF czy prezentacja?** PDF to pełna dokumentacja z metodologią — dobry jako załącznik i archiwum. Prezentacja PPTX jest do pokazania na spotkaniu: krótsza, edytowalna, z notatkami prelegenta. Z PowerPointa zrobisz z niej PDF, więc nie trzeba generować obu.

**Czy klient może edytować prezentację?** Tak — to zwykły plik .pptx: teksty, tabele i wykresy są natywnymi obiektami, a wykresy mają dołączone dane.

**Czy mogę wysłać raport, w którym jest i Meta, i Google?** Tak — od wersji 25.2 każda liczba w raporcie i prezentacji mówi, z którego kanału pochodzi, a okładka i „Najważniejsze liczby” sumują oba kanały z rozbiciem. Patrz [punkt 7](#7-co-liczy-metę-co-liczy-oba-kanały).

**Czy możemy użyć wyników w raporcie dla klienta?** Tak. Przy kwotach zawsze podawaj przedział i dopisek „szacunek na podstawie Biblioteki Reklam Meta”. Rekomendacje i brief traktuj jako punkt wyjścia.

### O pracy z narzędziem

**Co jeśli marka ma kilka kont reklamowych?** Dodaj je przy jednej marce przyciskiem „+ konto” (maks. 10) — policzą się razem. Żeby porównać konta tej samej firmy ze sobą, dodaj je jako osobnych konkurentów.

**Ile trwa analiza?** Od kilkunastu sekund do kilku minut — zależy od liczby marek i reklam. Marki pobierane są równolegle (domyślnie 3 naraz).

**Czym to się różni od zwykłego przeglądania Biblioteki Reklam?** Biblioteka pokazuje reklamy jedna po drugiej. Narzędzie liczy je za nas: ile reklam działa, jak długo żyją, jakie argumenty i rabaty komunikują, do kogo docierają, ile mniej więcej to kosztuje — i zestawia kilka marek obok siebie.

**Czy da się pokazać analizę bez internetu albo bez tokenu?** Tak — „Zapisz analizę” zapisuje dane i korekty do pliku, a „Wczytaj analizę” otwiera je później bez tokenu. Raport PDF działa wtedy w całości; prezentacja i Excel potrzebują internetu przy pierwszym użyciu.

**Jak sprawdzić, że narzędzie liczy poprawnie?** Porównaj liczbę aktywnych reklam 2–3 marek z Biblioteką Reklam na stronie Meta (ten sam kraj). Szacunek kosztu sprawdzisz kalibracją na kliencie, którego realny wydatek znamy. Wykrywanie rabatów i argumentów sprawdzisz na listach do korekty — one pokazują fragment tekstu i powód decyzji.
