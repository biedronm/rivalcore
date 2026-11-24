https://biedronm.github.io/rivalcore/#konkurencja
LUB Z TIKTOKIEM: 
https://biedronm.github.io/rivalcore/

# RivalCore — README

RivalCore to wewnętrzne narzędzie do analizy reklam marek i konkurencji z Biblioteki Reklam Meta (Facebook, Instagram, Messenger, Audience Network) i z Centrum przejrzystości reklam Google (Search, YouTube, sieć reklamowa), od wersji 30 z biblioteki reklam TikToka, od wersji 31 z biblioteki reklam LinkedIna, a od wersji 20 także wyników kont Google Ads naszych klientów. Jeden plik HTML — bez instalacji, bez serwera, bez opłat. Otwierasz w przeglądarce, wklejasz token, wpisujesz marki i dostajesz analizę z wykresami, raport PDF, prezentację PowerPoint, Excel oraz plik dla AI.

**Aktualna wersja: 31.1 (24 listopada 2026): przejrzysty ekran startowy (wspólne ustawienia, źródła, konta); od 31.0: LinkedIn jako czwarte źródło, udział w głosie ze wszystkich kanałów, galeria i oś czasu reklam, kreator i zestawy klientów.** Od 29.0 narzędzie powstaje z kodu źródłowego w modułach (rozdział 17), a do wdrożenia trafia nadal jeden plik — zbudowany `dist/index.html`. Plik narzędzia nazywa się `index.html` (repozytorium `biedronm/rivalcore`, adres `https://biedronm.github.io/rivalcore/`). Wygląd ekranu, raportów PDF, prezentacji i grafik PNG jest zgodny z identyfikacją wizualną BeDigital.

## Spis treści

- [Co nowego? Wersja 31.2 · ekran startowy krok po kroku](#co-nowego-wersja-312--ekran-startowy-krok-po-kroku)
- [Co nowego? Wersja 31.1 · przejrzysty ekran startowy: wspólne ustawienia, źródła, konta](#co-nowego-wersja-311--przejrzysty-ekran-startowy-wspólne-ustawienia-źródła-konta)
- [Co nowego? Wersja 31.0 · LinkedIn, udział w głosie ze wszystkich kanałów, galeria i oś czasu, kreator](#co-nowego-wersja-310--linkedin-udział-w-głosie-ze-wszystkich-kanałów-galeria-i-oś-czasu-kreator)
- [Co nowego? Wersja 30.0 · TikTok jako trzeci kanał](#co-nowego-wersja-300--tiktok-jako-trzeci-kanał)
- [Co nowego? Wersja 29.1 · formularz Meta | Google, raport „historia, potem aneks”](#co-nowego-wersja-291--formularz-meta--google-raport-historia-potem-aneks)
- [Co nowego? Wersja 29.0 · kod w modułach, jedna biblioteka wykresów, wspólny model reklamy](#co-nowego-wersja-290--kod-w-modułach-jedna-biblioteka-wykresów-wspólny-model-reklamy)
- [Co nowego? Wersja 28.2 · strategia, kampanie, rekomendacje z pomiarem, rejestr trafności](#co-nowego-wersja-282--strategia-kampanie-rekomendacje-z-pomiarem-rejestr-trafności)
- [Co nowego? Wersja 28.1 · zasięg z wybranego obszaru zamiast z całej UE](#co-nowego-wersja-281--zasięg-z-wybranego-obszaru-zamiast-z-całej-ue)
- [Co nowego? Wersja 28.0 · sandbox korekt, spis treści, hasło do raportu](#co-nowego-wersja-280--sandbox-korekt-spis-treści-hasło-do-raportu)
- [Co nowego? Wersja 27.0 · warstwa analityczna i interaktywny raport](#co-nowego-wersja-270--warstwa-analityczna-i-interaktywny-raport)
- [Co nowego? Wersja 26.0 · podsumowania obu kanałów](#co-nowego-wersja-260--podsumowania-obu-kanałów)
- [Co nowego? Wersje 25.1–25.9](#co-nowego-wersje-251259)
- [Co nowego? Wersja 25.0 · warstwa „co z tego wynika”](#co-nowego-wersja-250--warstwa-co-z-tego-wynika)
- [Starsze wersje: 20–24](#starsze-wersje-2024)
- [1. Pierwsze uruchomienie (token Meta)](#1-pierwsze-uruchomienie-token-meta)
- [1b. Pierwsze uruchomienie: Google](#1b-pierwsze-uruchomienie-google)
- [1c. Pierwsze uruchomienie: TikTok](#1c-pierwsze-uruchomienie-tiktok)
- [1d. Pierwsze uruchomienie: LinkedIn](#1d-pierwsze-uruchomienie-linkedin)
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
- [17. Kod źródłowy, budowanie i testy](#17-kod-źródłowy-budowanie-i-testy)

## Co nowego? Wersja 31.2 · ekran startowy krok po kroku

Formularz prowadzi teraz w pięciu krokach (pasek kroków u góry; do każdego kroku można wrócić jednym kliknięciem):

1. **Co analizujemy** - zaznaczasz platformy: Meta, Google, TikTok, LinkedIn. Każda działa samodzielnie.
2. **Połączenia** - tokeny, klucze i pośrednik tylko dla wybranych platform, z przyciskiem „Sprawdź połączenie”. Klucze zostają w karcie przeglądarki, nie trafiają do plików ani zestawów.
3. **Marki** - Twoja marka i konkurenci, każda w osobnym polu (same nazwy). Kraje i okres są wspólne dla wszystkich platform.
4. **Ustawienia platform** - platforma po platformie („Dalej: Google”, „Dalej: LinkedIn”…):
   - A. ustawienia ogólne platformy: okres platformy, stawki (CPM, częstotliwość), limity pobierania,
   - B. marka po marce: konta na tej platformie i zwinięte „Własne ustawienia tej marki”. Puste pole = ustawienie ogólne (pokazane na szaro), zmienione pola są oznaczone „zmienione”, „Przywróć ogólne” czyści markę.
5. **Podsumowanie** - co zostanie pobrane, z jakim okresem, które połączenia są gotowe; tu jest „Analizuj”.

Co marka może zmienić (reszta jest wspólna dla platformy):
- Meta - okres, limit reklam, CPM min/max, częstotliwość min/max (CPM według formatu nadal w „Zaawansowane”),
- Google - CPM min/max osobno dla tekstu, grafiki i wideo (okres jeden dla całego Google, bo to jedno zapytanie do BigQuery),
- TikTok - strony wyników, CPM, częstotliwość,
- LinkedIn - strony wyników, CPM.

Jak to liczymy: koszt marki liczymy z jej stawek, a gdy ich nie ma - ze stawek ogólnych platformy. Zmiana stawki jednej marki przelicza tylko tę markę (dane nie są pobierane ponownie). Konto Meta wpisane w kroku 4 trafia do tych samych pól co wcześniej, a ustawienia marki przechodzą pod jej nowy klucz (ID strony). Zestawy klientów zapamiętują też nadpisania. Kreator 3 kroków jest schowany - zastępują go kroki.

## Co nowego? Wersja 31.1 · przejrzysty ekran startowy: wspólne ustawienia, źródła, konta

Ekran „Dane wejściowe” ma teraz trzy jasne części:

1. **Wspólne ustawienia** - marki, kraje i okres analizy. Dotyczą wszystkich włączonych źródeł.
2. **Źródła danych** - zakładka na każde źródło (Meta, Google, TikTok, LinkedIn) ze stanem: wyłączone / włączone, gotowe / włączone, czego brakuje. W zakładce: dostęp (klucze), konta, „Dostosuj …”, ustawienia i założenia kosztu tylko tego źródła. **Każde źródło działa samodzielnie** - wystarczy włączyć jedno (np. sam LinkedIn), a ustawienia jednego źródła nie zmieniają pozostałych (np. limit reklam Mety nie rusza okresu Google).
3. **„Analiza obejmie”** nad przyciskiem „Analizuj” - co dokładnie zostanie pobrane i z jakim okresem w każdym źródle.

**Dostosuj (zwinięte, domyślnie nic nie trzeba zmieniać):** kolejność to konto → źródło → wspólne. Puste pole = wartość z poziomu wyżej. Każda zmiana jest oznaczona „zmienione”, zakładka pokazuje liczbę zmian, a „Przywróć domyślne” czyści je dla źródła.

- Meta: własny okres źródła, a dla każdego konta własny okres i limit reklam.
- Google: własny okres źródła (wszystkie marki idą jednym zapytaniem do BigQuery, więc okres konta nie ma sensu).
- TikTok i LinkedIn: własny okres źródła i liczba stron wyników na konto (okres wspólny dla marek, bo udziały porównujemy w tym samym okresie).

Nadpisania zapisują się w tej przeglądarce i w zestawach klientów (bez kluczy). Kolorowe ramki kart i pomarańczowy pasek kroków zastąpił stonowany układ z jednym akcentem.

## Co nowego? Wersja 31.0 · LinkedIn, udział w głosie ze wszystkich kanałów, galeria i oś czasu, kreator

### Nowe funkcje

- **LinkedIn Ad Library** jako czwarte źródło: reklamy B2B (oficjalne API LinkedIna), liczba reklam, aktywne, nowe w 30 dniach, typy i formaty, szacowany koszt, udział w głosie. Statystyki wyświetleń LinkedIn podaje tylko dla reklam emitowanych w UE. Instrukcja dostępu: [rozdział 1d](#1d-pierwsze-uruchomienie-linkedin).
- **Udział w głosie: wszystkie kanały w jednym wskaźniku** (zakładka „Kanały razem”, raport, PDF): Meta + Google + TikTok + LinkedIn. Jak to liczymy: dla każdej marki sumujemy szacowany miesięczny koszt reklam ze wszystkich kanałów, a udział = suma marki ÷ suma wszystkich marek. Kanał, w którym rynek wydaje więcej, waży więcej (wagi kanałów są pokazane). Dodatkowo pokazujemy udział „w kanale” i wariant z równymi wagami kanałów.
- **Reklamy: galeria, porównanie i oś czasu** (zakładka „Reklamy” i sekcje raportu HTML): filtry - platforma, format, kraj, aktywne / zakończone, marka - i wyszukiwarka; podgląd reklamy; porównanie do 4 reklam obok siebie; **oś czasu emisji (Gantt)** kampanii każdego konkurenta.
- **Zestawy konkurentów per klient:** zestaw ma pole „Klient” i zapamiętuje marki, okres, kraje, ustawienia i włączone źródła. Pod nagłówkiem „01 Dane wejściowe” są przyciski zestawów pogrupowane po klientach - jedno kliknięcie wczytuje zestaw. Klucze i tokeny nigdy nie trafiają do zestawu.
- **Kreator 3 kroków** (przycisk „Kreator 3 kroków”): klient → konkurenci → okres i kraje (oraz źródła) → gotowe. Wypełnia formularz i zapisuje zestaw klienta.
- **Pasek postępu per źródło** (Meta, Google, TikTok, LinkedIn) pod przyciskiem „Analizuj” i w okienku pobierania oraz **zużycie dziennego limitu TikToka**.
- **Tryb „dla klienta”** (przełącznik w pasku aplikacji i w raporcie HTML): ukrywa szczegóły techniczne (klucze, pośredników, lupę źródeł, metodologię), zostawia wyniki i wnioski. Raport zapisany w tym trybie otwiera się od razu w trybie dla klienta.
- **Styl BeDigital w Excelu:** nagłówki arkuszy na czarnym tle (#0B0B0B) z jasnym pogrubionym tekstem (#EEEEEE), przypięty pierwszy wiersz. Wartości bez zmian, bez formuł.

### Wyraźne komunikaty

Każde źródło pokazuje jeden z czterech stanów:

- **BŁĄD** - awaria (złe klucze, limit API, brak połączenia). Wynik nic nie mówi o konkurencji - trzeba naprawić przyczynę.
- **BRAK DANYCH** - źródło odpowiedziało poprawnie, ale marka nie ma reklam w tym okresie i obszarze. To wynik, nie usterka.
- **NIEPEŁNE DANE** - pobieranie zatrzymane przed końcem (limit stron, limit bezpieczeństwa).
- **BRAK DOSTĘPU** - źródło działa, ale aplikacja nie ma jeszcze zgody na dane (LinkedIn przed akceptacją Ad Library API).

**Poprawiony błąd: ciche urywanie pobierania z Mety.** Przy bardzo dużych markach pobieranie zatrzymywało się na limicie bezpieczeństwa (ok. 100 tys. reklam) bez słowa. Teraz wynik jest oznaczony jako NIEPEŁNE DANE z liczbą pobranych reklam, a ostrzeżenie widać przy wynikach marki.

### Porządki w kodzie (plan 29.2)

`src/meta/app.js` podzielony na moduły (z ok. 7200 do ok. 3800 linii): pobieranie z API, okienko ładowania, promocje i ceny, Excel, plik dla AI, pakiet do strategii, ochrona raportu, PDF, prezentacja, analizy, budżet, rekomendacje, podsumowanie, obszar, odkrywanie konkurentów, zestawy, kreator. Liczby, rekomendacje, plik dla AI i Excel identyczne jak w złotym wzorcu (test).

### LinkedIn: co jest do potwierdzenia na prawdziwym tokenie

Nazwy parametrów filtrów (kraje, zakres dat) i stronicowania wzięliśmy z publicznych opisów API - LinkedIn nie publikuje pełnej specyfikacji bez dostępu. Przy pierwszym tokenie uruchom `node tests/test-linkedin.mjs "Nazwa reklamodawcy"` (instrukcja w pliku; token tylko w zmiennej środowiskowej, nigdzie nie jest wypisywany) i prześlij wynik - poprawki będą w `src/linkedin/client.js`.

## Co nowego? Wersja 30.0 · TikTok jako trzeci kanał

RivalCore pobiera reklamy marek z biblioteki reklam TikToka (Commercial Content API) i liczy je obok Meta i Google: udział w głosie, aktywność, szacowany koszt, odbiorców, długość życia reklam. Wyniki są w aplikacji, w raporcie PDF/HTML, w prezentacji, w Excelu i w pliku dla AI.

### Jak działa połączenie z TikTokiem

- **Klucze wpisujesz za każdym razem.** Client key i Client secret aplikacji TikTok for Developers wklejasz w karcie TikTok (krok 1). Siedzą tylko w pamięci otwartej karty: nie trafiają do localStorage, do zapisanej analizy, do raportu, Excela ani pliku dla AI (sprawdza to test).
- **Pośrednik (Cloudflare Worker).** TikTok nie pozwala pytać swojego API bezpośrednio ze strony na innej domenie (brak CORS), więc zapytania idą przez mały pośrednik. Pośrednik nie przechowuje kluczy ani danych, przepuszcza tylko 4 ścieżki TikToka i tylko ze stron wpisanych w ALLOWED_ORIGINS. Instrukcja wdrożenia: [rozdział 1c](#1c-pierwsze-uruchomienie-tiktok). Kod: `worker/tiktok-proxy.js`.
- **Wyszukiwanie po nazwie, filtr po koncie.** API TikToka nie filtruje reklam po ID reklamodawcy, więc narzędzie szuka po nazwie marki, a potem zostawia tylko reklamy z wybranych kont (business_id). Konto dobiera się samo (najlepsze dopasowanie nazwy) albo wybierasz je z listy.
- **Limit ok. 1000 zapytań dziennie.** Każda strona wyników (10 reklam) i każde zapytanie o szczegóły reklamy to jedno zapytanie. Licznik dzisiejszych zapytań widać pod ustawieniami TikToka. Domyślnie: 20 stron i 10 szczegółów na markę.
- **Zakres dat:** do 2 dni wstecz (wcześniejszych dni TikTok jeszcze nie udostępnia) i najwyżej rok wstecz.

### Co liczymy na TikToku (jak to liczymy)

- **Zasięg** TikTok podaje jako przedział (np. „1M-5M”). Środek przedziału to średnia geometryczna końców; przy „0-1K” połowa górnej granicy; przy „100K+” dolna granica. Zasięg reklamy rozkładamy równo na jej dni emisji i bierzemy część przypadającą na okres analizy.
- **Koszt = zasięg × częstotliwość × CPM ÷ 1000**, z osobnymi założeniami TikToka (domyślnie CPM 8–22 zł, częstotliwość 1,5–3; trzecia kolumna w „Założeniach kosztu”). Widełki: dolne końce przedziałów razy dolne założenia i górne razy górne.
- **Odbiorcy:** z targetowania i rozkładu zasięgu (wiek, płeć, kraje) w szczegółach reklam o największym zasięgu.
- **Kanały razem:** gdy w analizie jest TikTok, zakładka „Meta + Google” nazywa się „Kanały razem” i pokazuje też TikToka (udział w głosie i budżet we wszystkich kanałach). Wymaga co najmniej dwóch kanałów.

### Zmiana liczb Google (celowa)

- **Środek widełek CPM w Google liczymy teraz średnią geometryczną**, tak jak w Meta i TikToku (wcześniej Google brał średnią arytmetyczną). Przy CPM 10–25 zł środek spada z 17,50 zł do 15,81 zł, więc szacowany koszt środkowy Google jest niższy o kilka do kilkunastu procent. Dolne i górne widełki się nie zmieniają. Powód: wszystkie kanały liczą tak samo, a średnia geometryczna lepiej pasuje do szerokich widełek. Kalibracja Google wylicza stawki tym samym wzorem.
- Liczby Meta, rekomendacje i Excel na danych testowych są identyczne jak w 29.1 (złoty wzorzec dostał tylko nową część „tiktok”).

## Co nowego? Wersja 29.1 · formularz Meta | Google, raport „historia, potem aneks”

Liczby się nie zmieniają (test ze złotym wzorcem przechodzi), zmienia się sposób wprowadzania danych i wygląd raportu.

### Poprawione błędy

- **Meta i Google po cichu analizowały różne obszary.** Przy kilku krajach Meta liczy wszystkie, a Google bierze Polskę (jeśli jest wśród wybranych) albo cały EOG — Centrum przejrzystości nie ma dowolnych zestawów krajów. Teraz pod wyborem krajów widać, jaki obszar weźmie Google, z ostrzeżeniem, gdy różni się od Meta. To samo jest w metodologii raportu.
- **Link do konkretnej sekcji raportu otwierał zawsze „Raport w skrócie”.** Przełącznik widoku podmieniał kotwicę adresu przed odczytaniem jej. Teraz link `raport.html#cmp-sov` otwiera „Udział w głosie”, a pierwsze otwarcie zaczyna od spisu treści.
- **Logo BeDigital nie pojawiało się na okładce raportu**, a w raporcie było podwójne „Za 30 dni”.
- **Okładka w trybie „jak wydruk” nie miała marginesów** na ekranie.

### Formularz

- **Kroki ponumerowane po kolei:** 1 źródła, 2 marki, 3 obszar i okres, 4 założenia kosztu, 5 analiza (wcześniej były dwa kroki „2” i brakowało „3”).
- **Okienko marki ma teraz obie kolumny: Meta i Google.** Przy włączonym Google pod polami Meta każdej marki jest komórka Google: konto dobrane automatycznie albo wybrane, przyciski „Znajdź”, „Wklej ID”. Nie ma już osobnej listy kont Google pół ekranu niżej. Pod spodem zostaje sekcja „Google: wyszukiwanie kont i ustawienia” (źródło danych, opóźnienie, tryb pliku).
- **Założenia kosztu w jednej sekcji, dwie kolumny:** Meta (benchmark, CPM, częstotliwość, założenia marek, kalibracja, rejestr trafności) i Google (CPM wg formatu, kalibracja Google). Podsumowanie stawek obu kanałów widać na zwiniętym pasku.
- Nagłówek z opisem narzędzia pokazuje się w całości tylko przy pierwszej wizycie; potem jest zwinięty (klik w nazwę rozwija). Z pustego stanu zniknęła lista kroków, która powtarzała pasek kroków.

### Raport HTML

- **Historia, potem aneks.** Menu i kolejność: Na start → Najważniejsze (skrót, wnioski, rekomendacje, udział w głosie, budżet, strategia i testy, przekaz i oferty, Meta + Google) → Więcej porównań → Aneks: strony marek → O raporcie.
- **Pełny nagłówek z liczbami tylko na pierwszej stronie.** W dalszych sekcjach treść zaczyna się od góry ekranu (oznaczenie korekt z sandboxu zostaje widoczne wszędzie).
- **Karty marek** (udział w głosie, koszt, aktywne reklamy, zmiana okres do okresu) nad kluczowymi porównaniami.
- **„Jak to liczymy” zwinięte w stopce bloku** („+ Jak to liczymy i ograniczenia metody”) — wykres i wniosek są pierwsze, metoda o jedno kliknięcie. Przy zapisie do PDF rozwija się sama.
- Usunięte powtórzone nagłówki i notka „analiza wczytana z pliku” (zostaje w aplikacji, nie trafia do klienta).
- **Telefon:** pasek ma „Skrót / Pełna” i przycisk „⋯” z resztą opcji.
- **Nowa okładka „z logo klienta na pierwszym planie”** (PDF, tryb wydruku i raport „jak aplikacja”). Panel nazywa się teraz „Raport (PDF / HTML)”.

## Co nowego? Wersja 29.0 · kod w modułach, jedna biblioteka wykresów, wspólny model reklamy

To przebudowa „pod maską”. Na tych samych danych testowych liczby, rekomendacje, Excel (27 arkuszy) i plik dla AI są **identyczne jak w 28.2** — sprawdza to automatyczny test ze złotym wzorcem (rozdział 17). Wdrożenie wygląda tak samo: jeden plik `index.html` na GitHub Pages.

**Co zniknęło i dlaczego to ważne**

- **Dwa bloki `<script>` i most `window.RivalCoreG`.** Moduł Meta i moduł Google importują od siebie nawzajem tylko to, czego potrzebują — 14 nazw zamiast globalnej przestrzeni z 539 deklaracjami. Nazwa użyta w module, w którym nie istnieje, zatrzymuje budowanie (ESLint `no-undef`), zamiast wysadzać aplikację u klienta. Cała klasa błędów typu „`kk`/`dPL`/`RCV` niewidoczne w drugim skrypcie” przestaje istnieć.
- **`toString()` dla raportu.** Skrypt raportu HTML (symulator, wykresy, nawigacja, wyszukiwarka) to zwykły moduł `src/report/runtime.js`, kompilowany przy budowaniu do jednego skryptu i wklejany do raportu. Funkcje wykresów nie muszą już być „samowystarczalne”.
- **Style raportu w szablonach JS.** Style raportu, wersji samodzielnej i ekranu hasła to prawdziwe pliki CSS w `src/styles/`.
- **Nadpisywanie `renderAll` z dwóch miejsc.** Zamiast podmieniać funkcję, moduły rejestrują zaczepy (`addRenderHook`) wołane po każdym renderze, w tej samej kolejności co wcześniej.

**Jedna biblioteka wykresów** (`src/charts/gch.js`). Miesięczny wykres emisji w module Meta rysuje teraz ta sama funkcja co wykresy Google i raportu, więc dostał to, co tamte już miały: odczyt wartości po najechaniu, zakres czasu (3/6 mies./wszystko) i przełącznik wartości / % udziału / indeksu.

**Wspólny model reklamy** (`src/model/ad.js`). Każde źródło ma przejściówkę w `src/adapters/` (`meta.js`, `google.js`), która zwraca obiekt z polami wspólnymi: źródło, identyfikator, marka, start i koniec emisji, dni, format, zasięg albo przedział wyświetleń, tekst, platformy, kraje. Pola źródłowe (np. demografia Meta, powierzchnie Google) zostają obok. Kolejne źródło (np. TikTok) to nowa przejściówka, a nie nowy moduł. Analizy Google nadal czytają swoje pola źródłowe — przeniesienie ich na pola wspólne to kolejny krok, robiony przy okazji zmian w tych analizach. Analizy zapisane przed 29.0 uzupełniają się przy wczytaniu.

**Uczciwie o tym, czego ta wersja jeszcze nie robi:** moduł Meta to nadal jeden plik `src/meta/app.js` (ok. 7,1 tys. linii). Dzielenie go na mniejsze moduły (pobieranie, analiza, panele, eksporty) jest teraz bezpieczne, bo każdy błąd w nazwach wyłapie budowanie, ale robimy je krokami przy kolejnych zmianach, z testem ze złotym wzorcem po każdym kroku.

## Co nowego? Wersja 28.2 · strategia, kampanie, rekomendacje z pomiarem, rejestr trafności

### Poprawione błędy

- **Zakładka „Zmiany” porównywała kwoty liczone na różnych założeniach.** Migawka zapisywała budżet już po korektach z sandboxu i po bieżących założeniach CPM i częstotliwości. Analiza z korektą ×2, a potem bez niej, pokazywała „budżet spadł o 50%”. Teraz migawka zapisuje swoją podstawę kosztu: zasięg obszaru, korektę zasięgu i ręczny budżet z sandboxu, CPM, częstotliwość, CPM i częstotliwość wg formatu. Gdy podstawa się różni, kwoty dostają „b.d.” z listą tego, co się zmieniło. Liczby reklam porównują się normalnie. Migawki sprzed 28.2 znają tylko podstawę zasięgu.
- **Pamięć podręczna widoków mogła pokazać stary wynik.** Część analiz (m.in. tygodniowy koszt na osi czasu marki i we wspólnej osi Meta + Google) nie przeliczała się po zmianie w sandboxie, bo cache trzeba było unieważniać ręcznie. Teraz każdy odczyt porównuje sygnaturę stanu: ręczne korekty tekstów, podstawę zasięgu, sandbox, CPM, częstotliwość i liczbę reklam.
- **Data ważności raportu udawała zabezpieczenie.** Teraz jest „przypomnieniem o aktualności danych”. Po terminie raport bez hasła pokazuje nakładkę z przyciskiem „Otwórz mimo to”, a raport z hasłem — ostrzeżenie na ekranie logowania. Hasło (AES-256-GCM) działa bez zmian i jest jedynym prawdziwym zabezpieczeniem.

### Nowa zakładka „Strategia i testy” (porównanie i każda marka)

- **Zmiany strategii.** Dla ostatnich 52 tygodni szukamy tygodnia, od którego marka wyraźnie zmieniła budżet, udział argumentu, reklam z rabatem albo formatów. Przykład: „od 14.10 argument »Cena i rabat«: 12% → 41% zasięgu”. Pokazujemy tylko duże i wyraźne zmiany: budżet ×1,5 albo ÷1,5, udział o ≥ 15 pp, statystyka różnicy ≥ 4. Ograniczenie: zasięg rozłożony równo na dni emisji wygładza serie, więc data zmiany jest przybliżona (±1–2 tygodnie).
- **Indeks testowania** = odsetek reklam wyłączonych w ≤ 7 dni × nowe reklamy na tydzień (ostatnie 90 dni), czyli w przybliżeniu „testów tygodniowo”. Odsetek liczymy tylko z reklam, które miały 7 dni na wyłączenie. Styl marki: testuje intensywnie / dużo nowości, mało cięcia / tnie, ale mało nowego / emituje sprawdzone. Liczony względem mediany marek, z dolnym progiem 15% i 2 reklam tygodniowo. Ograniczenie: szybkie wyłączenie to poszlaka testu — tak samo wygląda krótka akcja czasowa.
- **Dokłada czy wymienia (kanibalizacja).** Po każdej fali nowych reklam (≥ 3 reklamy, ≥ 15% dotychczasowej emisji) porównujemy łączny dzienny zasięg marki tydzień przed i tydzień po i dzielimy różnicę przez zasięg nowych reklam. Mediana ≥ 0,7 oznacza „dokłada”, ≤ 0,3 — „wymienia”. Ograniczenie: Meta podaje łączny zasięg reklamy, więc widzimy wyłączenia starych reklam, ale nie spadek ich emisji, gdy dalej działają. Prawdziwa kanibalizacja w aukcji jest niewidoczna.

### Kampanie (zakładka „Kampanie” marki)

Reklamy wystartowane w odstępie do 7 dni z tym samym albo podobnym tekstem (podobieństwo słów ≥ 0,35) łączą się w kampanię. Dla każdej kampanii widać:
- liczbę reklam i długość,
- szacowany budżet łącznie i na miesiąc,
- argumenty i udział reklam z rabatem.

Kampanie dłuższe niż 120 dni mają znacznik „always-on”. Pełna lista jest w Excelu, w arkuszu „Kampanie”. Ograniczenie: grupujemy po tekście i dacie, nie po identyfikatorze kampanii z konta (Meta go nie publikuje).

### Rozjazd Meta–Google (zakładka „Meta + Google”)

Dla każdej marki zestawiamy tempo zmiany szacowanego kosztu osobno w Meta i w Google: ostatnie 4 tygodnie vs pierwsze 4 z danymi w obu kanałach. Werdykty:
- rośnie w Google, w Meta stoi (i odwrotnie),
- przesuwa budżet,
- wchodzi do kanału,
- rośnie lub spada w obu.

„Rośnie” oznacza zmianę o ≥ 30%, „stoi” — o < 15%. Ograniczenie: oba koszty to szacunki z różnych źródeł, więc porównujemy kierunek zmian w każdym kanale, nie kwoty między kanałami.

### Rekomendacje w stałym formacie

Każda rekomendacja ma cztery części: **obserwacja → działanie → oczekiwany efekt → jak zmierzyć za 30 dni**.
- Efekt z przedziałem liczymy tam, gdzie pozwala na to ten sam model co symulator. Przykład dla niskiego udziału w głosie: ile szacowanego budżetu brakuje do równego udziału, z przedziałem 80% z niepewności szacunków konkurencji.
- Tam, gdzie efektu nie da się policzyć z danych publicznych, narzędzie mówi to wprost i podaje mierzalny cel z benchmarku konkurencji (np. udział wideo, odsetek reklam wyłączanych w ≤ 7 dni).

Nowy format jest w aplikacji, w raportach, w Excelu (nowe kolumny), w notatkach slajdu i w pliku dla AI.

### Rejestr trafności (Ustawienia zaawansowane → Kalibracja)

- Nowe pole „Branża”. Punkt dodany przyciskiem „Dodaj punkt” z wpisaną branżą trafia też do rejestru, który zostaje między analizami. Zapisujemy zasięg w oknie wydatku, nie wyświetlenia, więc późniejsza zmiana częstotliwości nie psuje punktów.
- Od 3 kont w branży narzędzie liczy błąd szacunku testem „każde konto przewidziane ze stawki CPM pozostałych”. Przycisk „Skalibruj z tej branży” ustawia CPM z rejestru.
- Raport (metodologia, skrót dla zarządu, slajd, plik dla AI) dostaje wtedy zdanie typu: „Szacunki skalibrowane na N kontach z branży X: szacunek mieścił się w ±Y% realnego wydatku dla K z N kont”.
- Bez kalibracji z rejestru metodologia mówi wprost, że błąd szacunku nie jest zmierzony.
- Ograniczenie: wydatki wpisujesz ręcznie. Wydatek z konta obejmuje też emisję poza wybranym obszarem, a rozjazd okien czasu zawyża błąd.

## Co nowego? Wersja 28.1 · zasięg z wybranego obszaru zamiast z całej UE

To poprawka błędu, nie nowa funkcja. Meta podaje przy każdej reklamie `eu_total_reach` — zasięg z **całej Unii**, niezależnie od tego, jaki obszar wybierzesz w formularzu. Marka paneuropejska (H&M, LPP, Zalando) wychodziła przez to wielokrotnie większa od marki działającej tylko w Polsce: budżet, wyświetlenia i udział w głosie były zawyżone nawet o rząd wielkości.

**Jak to liczymy teraz.** Każda reklama ma rozbicie zasięgu na kraje (to samo, z którego powstaje wykres „Kraje”). Zasięg reklamy mnożymy przez udział wybranych krajów w jej rozbiciu:

`zasięg obszaru = eu_total_reach × (zasięg w wybranych krajach ÷ zasięg we wszystkich krajach rozbicia)`

- Reklama bez własnego rozbicia dostaje **udział całej marki** — średnią ważoną zasięgiem z reklam, które rozbicie mają.
- Przeskalowany zasięg wchodzi do wszystkiego naraz: budżet (prognoza i średnia z okresu), wyświetlenia, udział w głosie, indeks aktywności, wykresy, Meta + Google, symulator, wszystkie eksporty.
- **Struktura wieku i płci** (piramida, mapa wolnych pól, luki demograficzne) liczy się tylko z wybranych krajów. Wykres **„Kraje (zasięg w całej UE)”** pokazuje dalej całą UE — to dowód, ile zasięgu marki jest poza obszarem.
- Przy „Cały świat” nic nie jest skalowane (zasięg i tak dotyczy UE).

**Gdzie to widać.**

- pasek nad wynikami i w nagłówku raportu HTML: „Zasięg przeskalowany do obszaru PL” z udziałem obszaru dla każdej marki, np. „Twoja marka 97% · H&M 6% · LPP 41%”;
- dymki „Skąd to?” przy zasięgu, koszcie i wyświetleniach — rachunek z liczbami tej marki;
- metodologia raportu HTML/PDF: pełny opis „jak to liczymy” z ograniczeniem metody;
- slajd „Metodologia” w prezentacji, plik dla AI;
- Excel: w arkuszu „Reklamy” trzy kolumny — „Zasięg UE (z Meta)”, „Zasięg obszaru (do wyliczeń)”, „Udział obszaru (%)”; w arkuszu „Zakres danych” kolumna „Podstawa zasięgu” dla każdej marki.

**Marka bez rozbicia krajów** (np. analiza bez „Pobieraj demografię…”) zostaje **nieprzeskalowana** i narzędzie mówi to wprost: w pasku nad wynikami, w „Wiarygodności danych” i w metodologii — jej liczby dotyczą całej UE i są zawyżone względem pozostałych. Napraw to, włączając demografię, albo ręcznie w sandboxie.

**Wyłącznik**: Ustawienia zaawansowane → „Zasięg tylko z wybranego obszaru” (domyślnie włączone, pamiętane w przeglądarce). Przełączenie przelicza wyniki bez ponownego pobierania. Korekta zasięgu w sandboxie działa teraz **na wierzchu** przeskalowania.

**Zapisane analizy** z wersji 28.0 i starszych przeliczają się po wczytaniu automatycznie — rozbicie krajów jest w pliku.

**Migawki („Zmiany”).** Pierwsza analiza po aktualizacji porównuje się z migawką liczoną z całej UE. Liczby reklam porównujemy normalnie, ale zmiany kosztu nie — zakładka pokazuje „b.d.” i wyjaśnienie, bo różnica byłaby zmianą metody, nie budżetu. Przy kolejnej analizie porównanie kwot wraca.

**Ograniczenie metody.** Rozbicie krajów to też szacunek Meta, a zasięg nie sumuje się idealnie między krajami (osoba widziana w dwóch krajach liczy się w rozbiciu dwa razy) — udział obszaru jest przybliżeniem. Częstotliwość i CPM dalej pochodzą z założeń dla wybranego kraju, nie ze średniej UE.

Przy okazji: w „Markach w skrócie” (Porównanie → Wnioski) przy szerokości ok. 1024 px kafelki wchodziły w trzy kolumny za wąskie na etykiety i strona dostawała poziomy pasek przewijania. Teraz przy tej szerokości są dwie kolumny.

## Co nowego? Wersja 28.0 · sandbox korekt, spis treści, hasło do raportu

### Sandbox korekt (przycisk „Sandbox korekt” obok eksportów)

Jedno miejsce, w którym podmieniasz dowolne założenie i klikasz **Przelicz** — cała analiza, wszystkie wykresy i wszystkie eksporty liczą się od nowa.

- **Założenia globalne**: CPM min/max, częstotliwość min/max.
- **Korekta zasięgu (%)** — globalna i osobna dla każdej marki. Mnoży zasięg każdej reklamy *przed* wszystkimi wyliczeniami, więc spójnie wpływa na budżet, udział w głosie, koszt kreacji i wykresy. Od 28.1 zasięg z całej UE jest skalowany do obszaru automatycznie — korekta działa na wierzchu tego przeskalowania (przydaje się np. przy marce bez rozbicia krajów).
- **CPM i częstotliwość osobno dla każdej marki** — te same wartości, co w ustawieniach marki, ale w jednej siatce obok siebie.
- **Realny budżet / mies.** — wpisujesz kwotę znaną z konta albo od klienta, a narzędzie dobiera CPM tej marki tak, żeby szacunek trafił w nią co do złotówki. Gdy z kwoty wychodzi nierealna stawka (poniżej 1 zł albo powyżej 120 zł), wiersz mówi o tym wprost.
- **Przywróć oryginał** kasuje wszystkie korekty naraz.

Dopóki korekty są włączone, **narzędzie i każdy eksport mówią o tym wprost**: nad wynikami, w nagłówku raportu HTML, w sekcji metodologii i na stronie metodologii w PDF pojawia się ramka z listą zastosowanych korekt. Raport z ręcznie poprawionymi liczbami nigdy nie wygląda jak surowy szacunek.

### Spis treści z czasem czytania

Pierwsza sekcja raportu HTML: wszystkie sekcje pogrupowane jak w menu, z czasem czytania każdej z nich, sumą dla całego raportu i osobną sumą dla skrótu dla zarządu. Sekcje wchodzące do skrótu są oznaczone. Czas liczymy z objętości tekstu oraz liczby wykresów i tabel. Opcja przy eksporcie — można wyłączyć.

### Hasło i data ważności raportu

Dwa nowe pola w panelu eksportu, oba dotyczą raportu HTML:

- **Hasło** szyfruje cały dokument (AES-256-GCM, klucz z PBKDF2, 250 tys. iteracji). Plik otwiera się ekranem logowania, a treści nie da się odczytać nawet w podglądzie źródła. Hasła nie da się odzyskać — zgubione oznacza nowy eksport.
- **Data aktualności** (od 28.2 nazwana uczciwie: przypomnienie, nie zabezpieczenie) — po terminie raport pokazuje komunikat „Dane mogą być nieaktualne” z przyciskiem „Otwórz mimo to”. Nie blokuje dostępu, bo plik leży u odbiorcy i datę sprawdza jego przeglądarka.

## Co nowego? Wersja 27.0 · warstwa analityczna i interaktywny raport

Największe wydanie od czasu dołączenia Google. Dwa kierunki: **raport HTML zachowuje się jak aplikacja**, a **analiza odpowiada na pytania, których wcześniej nie dało się zadać**.

### Raport HTML: czyta się go, a nie przewija

- **Wyszukiwarka po treści** — jedno pole przeszukuje wszystkie sekcje naraz, także te zwinięte.
- **Ścieżka „obejrzyj w 5 minut”** — prowadzi przez najważniejsze sekcje z licznikiem postępu.
- **Skróty klawiszowe** z panelem pod `?`.
- **Wznów, gdzie skończyłeś** — raport pamięta ostatnią sekcję (osobno dla każdego klienta i daty).
- **Słowniczek w dymkach** — 15 pojęć podkreślonych w tekście, z definicją po najechaniu.
- **Trzy motywy**: jasny, ciemny i wysoki kontrast.
- **Dwie wersje w jednym pliku**: skrót dla zarządu i pełna treść, przełączane jednym kliknięciem.
- **Odczyt wartości z wykresu** — po najechaniu na punkt pojawia się linia prowadząca i wszystkie serie z wartościami.
- **Zakres czasu na wykresach** — ostatnie 4 / 12 / 52 tygodnie (albo 3 / 6 / 12 miesięcy) bez przeładowania.
- **Przełącznik jednostek** — wartości bezwzględne, udział procentowy albo indeks 0–100 (100 = maksimum danej serii).

Wykresy w raporcie rysuje **ta sama funkcja, co w narzędziu** — trafia do pliku razem z danymi, więc raport i aplikacja nie mogą się rozjechać.

### Nowe analizy

| Analiza | Gdzie | Co odpowiada |
|---|---|---|
| Przedziały ufności przy szacunkach | kafelki kosztu, przegląd | „80% szans: A–B zł” przy każdej kwocie, z tego samego modelu co „Prawdopodobny budżet” |
| Częstotliwość wg formatu | Ustawienia → założenia marki | osobna częstotliwość dla wideo, grafiki i karuzeli; efektywna wartość ważona udziałem formatów w zasięgu |
| Sezonowość: presja aukcyjna | Prawdopodobny budżet | w których miesiącach kategoria emituje najwięcej i co to znaczy dla stawki (pełne i połowiczne przełożenie) |
| Kalibracja wielopunktowa | Ustawienia → kalibracja | kilka znanych wydatków naraz, wspólny CPM, odchyłka każdego punktu, automatyczne pomijanie odstających |
| Krzywa życia kreacji | Co przeżywa | jaki odsetek reklam przeżywa 7 / 28 / 84 dni i po ilu dniach kończy się połowa |
| Nasycenie zasięgu | Kreacje i testy | po ilu tygodniach kreacja zbiera dziennie mniej niż połowę zasięgu z pierwszego tygodnia |
| Miks platform w czasie | Kreacje i testy | jak przez miesiące przesuwa się obecność na Facebooku, Instagramie i pozostałych |
| Prognoza udziału w głosie | Udział w głosie | tempo zmian w pp/tydzień i prognoza na 8 tygodni z pasmem 80% |
| Architektura oferty | Oferty i ceny, Przekaz | trzy półki cenowe wyznaczone z rozkładu cen kategorii i obecność marek na każdej |
| Nakładanie się grup odbiorców | Odbiorcy | macierz pokrycia: jak podobnie zbudowane grupy osiągają poszczególne marki |
| Udział w głosie per argument | Co przeżywa | na którym argumencie marka jest głośniejsza, a na którym cichsza niż średnio |
| Wolne pola ważone wielkością grupy | Mapa wolnych pól | potencjał luki wyrażony w wyświetleniach na miesiąc, nie tylko w procentach |
| Mapa postaw kanałowych | Wnioski, raport | Meta vs Google × emisja stała vs zrywami, wielkość koła = budżet |
| Miks powierzchni Google w czasie | Google → Platformy | jak zmienia się podział wyświetleń między wyszukiwarkę, YouTube i Display |

Każda z nich ma pod spodem opis „jak to liczymy” wraz z ograniczeniem metody — te opisy trafiają też do raportu HTML i PDF.

### Google w eksportach: wszystko, nie wycinek

Raport HTML i PDF eksportowały wcześniej trzy sekcje Google (wnioski, udział w głosie, oba kanały razem) — reszta modułu zostawała w narzędziu. Teraz do wyboru są **wszystkie zakładki Google**: porównanie marek (wnioski, udział w głosie, okres do okresu, kreacje i testy, platformy i odbiorcy, kalendarz, rankingi) oraz **osobne strony każdej marki w Google** (przegląd, budżet, kreacje, platformy, kalendarz, konta i płatnicy). Każda sekcja Google niesie własną notę o granicy danych Transparency Center — w raporcie czyta się jedną sekcję naraz, więc ostrzeżenie musi być przy każdej.

## Co nowego? Wersja 26.0 · podsumowania obu kanałów

### Podsumowania liczą Metę i Google razem

„Raport w skrócie” i blok „W 5 sekund” w narzędziu pokazywały sam obraz Meta — werdykt mówił o udziale w Meta, mapa przewag nosiła podpis „(Meta)”, a Google było tylko osobnym kafelkiem obok. Doszła warstwa liczona z obu kanałów naraz:

- **werdykt** dopisuje zdanie o obrazie łącznym: udział w głosie po zsumowaniu kanałów, pozycja w zestawieniu i to, jaką część budżetu marki stanowi Google;
- **nowy rząd kafelków „Meta i Google razem”**: udział w głosie obu kanałów, łączny budżet z rozbiciem, pozycja po zsumowaniu i udział Google u Ciebie z medianą zestawu;
- **mapa przewag** dostaje cztery kolumny Google: budżet, kreacje, „Razem / mies.” i udział Google w budżecie marki — więc widać nie tylko kto prowadzi w Meta, ale kto prowadzi w ogóle;
- każdy nowy kafelek ma własne objaśnienie „skąd ta liczba”, z bazą wyliczenia i datą końca danych Google.

Baza dla kolumn łącznych to średnia z analizowanego okresu × 30 dni — jedyna wspólna dla obu kanałów ([punkt 5](#5-dwie-liczby-budżetu-prognoza-i-średnia-z-okresu)). Kolumny Meta zostają na prognozie i są tak podpisane.

### Zakładka „Jak czytać ten raport” jako strona tytułowa

Zamiast jednego akapitu i czterech kafelków — pełne wprowadzenie:

- **Skąd pochodzą dane** — karta na każde źródło z liczbą pobranych reklam i kreacji oraz opisem, co dane źródło obejmuje;
- **Czego ten raport nie pokazuje** — wydatki z kont, wyniki, kampanie spoza UE/EOG, a przy Google także brak tekstów reklam;
- **Każda liczba mówi, skąd się wzięła** — licznik objaśnień i cztery rodzaje informacji;
- **Jak się po nim poruszać** — menu, strzałki, motyw, wydruk, symulator, od czego zacząć;
- **stopka** z autorem, klientem, stanem danych, datą końca danych Google i podpisem „Raport przygotowany przez beDigital w narzędziu RivalCore”.

## Co nowego? Wersje 25.1–25.9

Seria wydań wokół jednego: **materiał, który idzie do klienta, ma być prawdziwy, czytelny i ma tłumaczyć sam siebie.**

### Raport HTML jako produkt (25.9)

Cztery rzeczy, przez które raport przestaje być „wysłanym plikiem HTML”, a staje się narzędziem w rękach klienta.

**Symulator budżetu działa w eksporcie.** Suwak „co, jeśli zmienisz budżet” był w pliku, ale martwy — logika została w narzędziu. Teraz jedzie razem z raportem: przesuwasz suwak, a udział w głosie, pozycja w rankingu, zmiana budżetu i słupki wszystkich marek przeliczają się na żywo. Działają też gotowe scenariusze („Stan dziś”, „Udział 25%”, „Udział 40%”, „Wyprzedź markę wyżej”). Kod symulatora trafia do raportu wprost z narzędzia, więc obie wersje nie mogą się rozjechać.

**Martwe sterowanie wycięte.** Przełączniki widoku, listy ręcznej korekty rabatów i argumentów, słowniki branżowe — wszystko, co wymaga przeliczenia wyników, w samodzielnym pliku nie miało czego przeliczać. Klient klikał i nic się nie działo. Teraz tych elementów w raporcie po prostu nie ma; zostaje wynik ich działania.

**Menu dwupoziomowe i zwijane.** Zamiast jednej długiej listy: kategorie (Na start, Podsumowanie, Meta, Google Ads, Meta + Google, O raporcie) z licznikiem sekcji, a w środku podgrupy — porównanie marek i każda marka osobno. Gałąź prowadząca do otwartej sekcji rozwija się sama, wyszukiwarka otwiera gałęzie z trafieniami. Pod każdą sekcją są odsyłacze „Poprzednia / Następna” z nazwami, a w nagłówku licznik „5 / 52”.

**Ikona pliku i metadane.** Raport dostaje ikonę karty przeglądarki: logo wgrane w panelu raportu, a gdy go nie ma — monogram z nazwy klienta na ciemnym kwadracie. Logo trafia też do paska u góry raportu. W pliku są opis, nazwa generatora i deklaracja obsługi obu motywów. (Ikony pliku w Eksploratorze czy Finderze nie da się ustawić z wnętrza `.html` — to zawsze ikona przeglądarki.)

**Kontrast sprawdzony maszynowo.** Napisałem miernik, który dla każdego elementu tekstowego w raporcie składa warstwy tła z uwzględnieniem przezroczystości i liczy kontrast. Znalazł resztki twardo wpisanych kolorów z wydruku (podtytuły „Raportu w skrócie” były czarne na czarnym) oraz ciemny tekst na nasyconych kafelkach w motywie jasnym. Po poprawkach: zero elementów poniżej progu w obu motywach.

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

## 1c. Pierwsze uruchomienie: TikTok

**Potrzebujesz:** aplikacji w TikTok for Developers z dostępem do Commercial Content API (Client key i Client secret) oraz pośrednika na Cloudflare.

**Pośrednik (raz, ok. 10 minut, darmowy plan Cloudflare):**

1. dash.cloudflare.com → Workers & Pages → Create → Worker → nazwa np. `rivalcore-tiktok` → Deploy.
2. Edit code → wklej cały plik `worker/tiktok-proxy.js` → Deploy.
3. Settings → Variables and Secrets → Add: `ALLOWED_ORIGINS` = `https://biedronm.github.io` (kilka adresów po przecinku, np. dodatkowo `http://localhost:5173` do pracy lokalnej) → Deploy.
4. Adres Workera (`https://rivalcore-tiktok.<konto>.workers.dev`) wklej w RivalCore: karta TikTok → „Adres pośrednika”. Adres się zapamiętuje, klucze nie.

Sekret przechodzi przez pośrednika (w drodze do TikToka), więc Worker powinien stać na Twoim koncie Cloudflare albo koncie agencji, nie na cudzym.

**W narzędziu:** krok 1 → włącz TikTok → wklej Client key i Client secret → „Sprawdź połączenie”. Potem w kroku 2 przy marce wybierz konto TikTok (albo zostaw automatyczny wybór) i uruchom analizę.

**Błędy, które zobaczysz po polsku:** złe klucze aplikacji, wyczerpany dzienny limit zapytań, brak połączenia z pośrednikiem (zły adres albo strona spoza ALLOWED_ORIGINS — pośrednik odpowiada wtedy 403).

## 1d. Pierwsze uruchomienie: LinkedIn

**Potrzebujesz:** aplikacji w LinkedIn Developers z zatwierdzonym produktem Ad Library API, tokenu OAuth tej aplikacji i pośrednika na Cloudflare (tego samego co dla TikToka).

**Co wpisujesz w karcie LinkedIn (krok 1 → włącz LinkedIn):**

- **Token dostępu** - nie Client ID ani Client Secret. Token wpisujesz przy każdej sesji (pole hasła, tylko pamięć karty). Ważny ok. 60 dni.
- **Adres pośrednika** - adres Workera `worker/rivalcore-proxy.js` (zapamiętuje się).
- **Wersja API** (opcjonalnie, domyślnie 202510) - nagłówek LinkedIn-Version w formacie RRRRMM.

Potem „Sprawdź połączenie”. W kroku 2 przy marce możesz wpisać nazwę strony firmy na LinkedInie, jeśli różni się od nazwy marki.

**Pośrednik TikTok i LinkedIn (jeden Worker):** wdrożenie jak w [rozdziale 1c](#1c-pierwsze-uruchomienie-tiktok), tylko wklejasz plik `worker/rivalcore-proxy.js`. Jeśli masz już pośrednika z 30.0, podmień jego kod na ten plik - adres zostaje ten sam. Pośrednik przepuszcza tylko ścieżki biblioteki reklam TikToka (POST) i LinkedIna (GET /rest/adLibrary), tylko ze stron z ALLOWED_ORIGINS, i niczego nie przechowuje.

### LinkedIn: jak złożyć wniosek o dostęp (krok po kroku)

LinkedIn ma oficjalne API biblioteki reklam (Ad Library API), ale daje je tylko aplikacjom, które zatwierdzi. **Do czasu akceptacji źródło LinkedIn pokazuje stan BRAK DOSTĘPU** (nie BŁĄD i nie BRAK DANYCH), a Meta, Google i TikTok liczą się normalnie.

1. Zaloguj się na LinkedInie kontem, które jest **administratorem strony firmy BeDigital** (strona firmowa jest wymagana do utworzenia aplikacji).
2. Wejdź na https://www.linkedin.com/developers/apps i kliknij **Create app**.
3. Wypełnij formularz: nazwa aplikacji (np. „RivalCore BeDigital”), **LinkedIn Page** = strona BeDigital, adres polityki prywatności (strona bedigital), logo. Zaakceptuj warunki i kliknij **Create app**.
4. W zakładce **Settings** aplikacji kliknij **Verify** przy stronie firmy i wyślij link weryfikacyjny administratorowi strony (jeśli to Ty - otwórz go sam i zatwierdź).
5. Przejdź do zakładki **Products**, znajdź **Ad Library API** (nazwa w portalu może się nieznacznie różnić, szukaj „Ad Library”) i kliknij **Request access**.
6. Wypełnij formularz wniosku. Opis zastosowania: *„Analiza publicznie dostępnych reklam B2B konkurencji dla klientów agencji (narzędzie wewnętrzne, odczyt danych z biblioteki reklam, bez publikowania i bez danych osobowych)”*. Zaznacz, że dane służą do badań rynku i przejrzystości reklam.
7. Czekaj na decyzję LinkedIna (zwykle od kilku dni do kilku tygodni; status widać w zakładce **Products**: „Review in progress” → „Added”).
8. Po akceptacji: zakładka **Auth** → **OAuth 2.0 tools / Token generator** → wygeneruj token z uprawnieniem zaproponowanym dla Ad Library API. Token jest ważny ok. 60 dni.
9. W RivalCore włącz źródło **LinkedIn**, wklej token (pole hasła, trzymane tylko w pamięci karty) i adres pośrednika `worker/rivalcore-proxy.js`, kliknij **Sprawdź połączenie**. Wynik „działa” = gotowe; „BRAK DOSTĘPU” = wniosek jeszcze niezatwierdzony albo token z innej aplikacji.
10. Przy pierwszym prawdziwym tokenie uruchom `node tests/test-linkedin.mjs` (instrukcja w pliku), żeby potwierdzić nazwy parametrów i pól odpowiedzi. Token nie trafia do logów ani plików.

Nigdy nie wklejaj tokenu do czatu, e-maila ani plików projektu.


**Jak to liczymy (LinkedIn):** LinkedIn podaje wyświetlenia reklamy jako przedział za cały czas emisji. Rozkładamy je równo na dni emisji i bierzemy dni z okresu analizy; przy wybranych krajach mnożymy przez udział tych krajów w wyświetleniach reklamy. Koszt = wyświetlenia × CPM ÷ 1000, przeliczony na miesiąc (domyślnie CPM 40-120 zł, środek to średnia geometryczna). Reklama jest „aktywna”, gdy ostatnie wyświetlenie było najwyżej 3 dni przed datą danych (LinkedIn nie podaje statusu).

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
| Pobieraj demografię, targetowanie i płatników | Więcej danych, wolniej przy dużych markach. **Wymagane przez mapę wolnych pól i przez przeskalowanie zasięgu do obszaru** |
| Zasięg tylko z wybranego obszaru | Skaluje zasięg Meta (cała UE) udziałem wybranych krajów z rozbicia demograficznego każdej reklamy. Domyślnie włączone. Patrz [wersja 28.1](#co-nowego-wersja-281--zasięg-z-wybranego-obszaru-zamiast-z-całej-ue) |
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

- **działający symulator budżetu** — suwak przelicza udział w głosie, pozycję i słupki wszystkich marek na żywo, razem z gotowymi scenariuszami;
- **menu dwupoziomowe, zwijane**: kategorie z licznikiem sekcji, w środku podgrupy (porównanie marek, każda marka osobno); gałąź do otwartej sekcji rozwija się sama;
- **odsyłacze „Poprzednia / Następna”** pod każdą sekcją i licznik „5 / 52” w nagłówku;
- **ikona karty przeglądarki** z Twojego logo (albo monogram klienta), logo także w pasku u góry;
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
| Zasięg | `eu_total_reach` — szacunek Meta: ile kont w UE zobaczyło reklamę. Od 28.1 przeskalowany do wybranego obszaru udziałem tych krajów w rozbiciu demograficznym reklamy |
| Udział obszaru | Jaka część zasięgu marki w UE przypada na wybrane kraje (z rozbicia krajów). Mnożnik zasięgu każdej reklamy |
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
- **Zasięg z API jest ogólnounijny — narzędzie go przeskalowuje.** `eu_total_reach` to zasięg w całej UE. Od 28.1 mnożymy go przez udział wybranych krajów w rozbiciu demograficznym reklamy. Udział obszaru to przybliżenie (rozbicie też jest szacunkiem Meta). Marka bez rozbicia krajów zostaje nieprzeskalowana i jest wtedy oznaczona — jej liczby są zawyżone.
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
| Brak demografii (i pusta mapa wolnych pól, marka „bez przeskalowania” zasięgu) | Włącz „Pobieraj demografię…”; dla reklam spoza UE Meta jej nie podaje |
| Zakładka „Zmiany” pusta | To pierwsza analiza tej strony na tym obszarze |
| Wolne pobieranie dużej marki | Ustaw limit reklam albo wyłącz „Pobieraj demografię…” i „Pobieraj typ mediów” |
| Marka międzynarodowa ma podejrzanie wysoki budżet | Sprawdź pasek „Zasięg przeskalowany do obszaru” nad wynikami. Jeśli marka jest w nim „bez przeskalowania”, brakuje rozbicia krajów — włącz „Pobieraj demografię…” i uruchom analizę albo skoryguj zasięg w sandboxie. Sprawdź też, czy w ustawieniach nie jest wyłączone „Zasięg tylko z wybranego obszaru” |

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

- Plik działa w całości w Twojej przeglądarce. Dane idą tylko między przeglądarką a Meta (`graph.facebook.com`), Google (`accounts.google.com`, `bigquery.googleapis.com`, `sheets.googleapis.com`) oraz TikTokiem przez Twojego pośrednika (Cloudflare Worker → `open.tiktokapis.com`). Pośrednik niczego nie zapisuje.
- Klucze TikToka (Client key, Client secret) są tylko w pamięci karty, nigdy w localStorage ani w plikach eksportu. Token TikToka żyje 2 godziny i też nie jest zapisywany.
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

**Dlaczego marka międzynarodowa wychodziła tak wysoko?** Zasięg z Meta API (`eu_total_reach`) jest ogólnounijny. Do wersji 28.0 sieć emitująca w kilkunastu krajach wyglądała przez to na wielokrotnie większą od lokalnego gracza. Od 28.1 zasięg każdej reklamy jest skalowany udziałem wybranych krajów, a udział obszaru każdej marki widać nad wynikami. Jeśli marka nadal wychodzi wysoko, sprawdź, czy nie jest oznaczona jako „bez przeskalowania”.

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

## 17. Kod źródłowy, budowanie i testy

**Struktura**

- `index.html` — szkielet strony (bez stylów i skryptów)
- `src/main.js` — punkt wejścia: kolejność uruchamiania modułów
- `src/meta/app.js` — moduł Meta (pobieranie, analizy, panele, eksporty)
- `src/google/app.js` — moduł Google (BigQuery, logowanie, zakładki Google, Meta + Google)
- `src/charts/gch.js` — wspólna biblioteka wykresów liniowych (aplikacja i raport)
- `src/tiktok/` — moduł TikTok: `client.js` (zapytania, token, ponowienia), `json.js` (duże ID bez zaokrągleń), `analyze.js` (analizy), `app.js` (panele, raport, eksporty)
- `worker/rivalcore-proxy.js` — pośrednik TikTok + LinkedIn (Cloudflare Worker, od 31.0), wdrażany osobno; `worker/tiktok-proxy.js` — dawny pośrednik tylko dla TikToka (działa dalej)
- `src/linkedin/` — moduł LinkedIn: `client.js` (zapytania Rest.li, ponowienia, BRAK DOSTĘPU), `analyze.js` (wskaźniki), `app.js` (karta, wyniki, eksporty); `src/adapters/linkedin.js` — przejściówka
- `src/sov/` — udział w głosie ze wszystkich kanałów; `src/explorer/` — galeria, filtry, porównanie, oś czasu; `src/v31/` — spięcie z modułami źródeł
- `src/meta/*.js` — moduły wydzielone z `app.js` (api, loader, promo, xlsx, ai-export, strategy-pack, report-protect, report-pdf, pptx, analyze, budget, recs, exec, geo, discover, sets, wizard)
- `src/ui/progress.js` — pasek postępu per źródło; `src/ui/client-mode.js` — tryb dla klienta; `src/core/state.js` — stany BŁĄD / BRAK DANYCH / NIEPEŁNE DANE / BRAK DOSTĘPU; `src/core/xlsx-brand.js` — styl Excela
- `src/model/ad.js` — wspólny model reklamy; `src/adapters/meta.js`, `src/adapters/google.js`, `src/adapters/tiktok.js` — przejściówki
- `src/report/runtime.js` — skrypt raportu HTML; `src/report/styles.js` — style raportu jako tekst
- `src/sim/simulator.js` — symulator budżetu (aplikacja i raport)
- `src/core/` — formatowanie, daty, teksty, wersja
- `src/styles/` — `app.css`, `v31.css` (nowe elementy 31.0), `report.css`, `report-standalone.css`, `gate.css`
- `tests/` — testy jednostkowe (`unit.mjs`), testy w przeglądarce (`run_all.py`), dane testowe i złoty wzorzec

**Budowanie i wdrożenie**

- Raz: `npm install` (Node 18+).
- Praca na żywo: `npm run dev` → `http://localhost:5173`.
- Budowanie: `npm run build` → najpierw ESLint (nieznana nazwa = błąd), potem `dist/index.html` — jeden plik ze wszystkim w środku, jak dotąd.
- Wdrożenie: `dist/index.html` podmieniasz jako `index.html` w repo `biedronm/rivalcore`. Źródła trzymaj obok, np. w folderze `app/` tego samego repo (wtedy Pages dalej serwuje plik z katalogu głównego).

**Testy**

- `npm test` = budowanie + testy jednostkowe modelu i przejściówek, klienta TikToka (atrapa serwera: limit, wygasły token, stronicowanie, duże ID) i pośrednika, testy 31.0 (`unit_v31.mjs`: limit Mety, udział w głosie, filtry i oś czasu, LinkedIn, styl Excela; `unit_proxy.mjs`: pośrednik TikTok + LinkedIn) + testy w przeglądarce, w tym LinkedIn na atrapie API (wyniki, BRAK DOSTĘPU przy 403, udział w głosie, galeria i raport z filtrami, tryb dla klienta, kreator i zestawy, brak tokenu w plikach), w tym TikTok na atrapie API (wyniki, raport, Excel, PPTX, brak kluczy w plikach) (Playwright: `pip install playwright openpyxl` i `playwright install chromium`).
- Testy w przeglądarce sprawdzają: wszystkie zakładki bez błędów, przełącznik zasięgu obszaru, przeliczanie pamięci podręcznej po sandboxie, podstawę migawek, Excel, plik dla AI, raport HTML (metodologia, przypomnienie o aktualności, zakres czasu na wykresie, symulator), PPTX, 5 szerokości ekranu bez przewijania w poziomie, rozjazd Meta–Google.
- **Złoty wzorzec** (`tests/golden.json`, zrzut z 28.2): liczby marek, rekomendacje, plik dla AI i wszystkie arkusze Excela muszą wyjść identycznie. Zmiana, która celowo zmienia liczby, wymaga świadomego odświeżenia wzorca: `python3 -I tests/run_all.py --write-golden` — i opisania zmiany w „Co nowego”.
- Dostęp testów do wnętrza aplikacji (`window.RC`) jest włączany tylko adresem z `?test`; zwykłe otwarcie pliku go nie ma.

