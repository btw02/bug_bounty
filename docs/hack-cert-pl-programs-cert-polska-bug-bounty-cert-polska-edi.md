[Wróć do listy programów](https://hack.cert.pl/programs)

![Logo programu Bug Bounty CERT Polska](https://hack.cert.pl/api/v1/public/institutions/cert-polska/programs/bug-bounty-cert-polska/logo?v=df54133ac2fe98fb)

CERT Polska

# Bug Bounty CERT Polska

Aktywny

Edycja 11/2026Okres trwania: 03-11-2026 - 30-11-2026web

## Opis programu

* * *

Zespół **CERT Polska**, działający w strukturach NASK – Państwowego Instytutu Badawczego, to pierwszy powstały w Polsce zespół reagowania na incydenty. Dzięki prężnej działalności od 1996 roku stał się rozpoznawalnym i doświadczonym podmiotem w dziedzinie bezpieczeństwa komputerowego.

## Nagrody

| Poziom i nagroda | Niski | Średni | Wysoki | Krytyczny |
| --- | --- | --- | --- | --- |
| Tier 1 | 600 | 4000 | 9000 | 20000 |
| Tier 2 | 300 | 2000 | 4500 | 10000 |

## Zakres podatności

* * *

**Typy podatności objęte Konkursem**

01. Zdalne wykonanie kodu
    1. Zdalne wykonanie kodu (RCE / Remote Code Execution)

    2. Eskalacja do kontroli nad systemem lub usługą
02. Pełne przejęcie konta (podatności, które bezpośrednio pozwalają atakującemu przejąć konto użytkownika) m.in.:
    1. Reset hasła bez dostępu do skrzynki pocztowej lub numeru telefonu ofiary.

    2. Przejęcie sesji lub tokenów uwierzytelniających

    3. Logowanie bez znajomości hasła

    4. Fałszowanie tożsamości użytkownika
03. Dostęp do danych wrażliwych
    1. Wyciek danych osobowych umożliwiający identyfikację osób

    2. Dostęp do prywatnych treści lub wiadomości innych użytkowników

    3. Masowy odczyt wrażliwych danych użytkowników lub danych systemowych
04. SQL injection

05. Server-Side Request Forgery (SSRF)
    1. Odczyt zasobów dostępnych tylko z sieci wewnętrznej za pośrednictwem SSRF

    2. Dostęp do usług prywatnych (Dostęp do niepublicznych usług lub portów poprzez SSRF)

    3. Pełny SSRF umożliwiający RCE
06. Server-Side Template Injection (SSTI)
    1. Wykonanie kodu po stronie serwera poprzez podatność w silniku szablonowym
07. File Upload Vulnerabilities
    1. Przesyłanie pliku prowadzące do RCE

    2. Ominięcie filtrów typu MIME lub rozszerzeń prowadzący do podatności

    3. Ominięcie mechanizmów walidacji przesyłania plików prowadzące do istotnego wpływu na bezpieczeństwo takiego jak: możliwość wykonania kodu, uzyskanie nieautoryzowanego dostępu do zasobów.
08. Cross-Site Scripting (XSS) - poza określonymi wyłączeniami

09. Autoryzacja i dostęp
    1. IDOR / Broken Access Control

    2. Odczyt, modyfikacja lub usuwanie cudzych danych

    3. Omijanie autoryzacji w warstwie aplikacji (UI/Web) umożliwiające wykonywanie akcji lub dostęp do zasobów bez wymaganych uprawnień.
10. Eskalacja uprawnień
    1. Pionowa

    2. Pozioma
11. Problemy z sesją i uwierzytelnianiem (nieprowadzące bezpośrednio do pełnego przejęcia konta)
    1. Nadużycie sesji poprzez ponowne użycie tokena po wylogowaniu, brak rotacji ID sesji, brak wygasania sesji, które same w sobie nie umożliwiają przejęcia konta innych użytkowników.

    2. Brak wymaganego uwierzytelnienia do funkcji lub endpointów, które same w sobie nie pozwalają na zmianę stanu kont innych użytkowników ani odczytu prywatnych danych (dostęp do listy publicznych zasobów lub dokumentacji niepoprawnie chronionej).

    3. Pozostawione domyślne dane uwierzytelniające, które same w sobie nie umożliwiają przejęcia danych użytkowników (konto developerskie z ograniczonymi uprawnieniami np do panelu monitoringu).

> \*Problemy w tej kategorii nie prowadzą do przejęcia konta i będą traktowane jako informacyjne lub nagradzane niską kwotą według uznania zespołu weryfikującego zgłoszenia.

12. Podatności w API
    1. Omijanie autoryzacji na poziomie API (brak walidacji tokenów, brak sprawdzania uprawnień w endpointach).

    2. Dostęp do endpointów prywatnych (Dostęp do wewnętrznych, ukrytych lub nieudokumentowanych endpointów API prowadzący do wycieku danych lub akcji).
13. Mass Assignment
    1. Nadpisanie pól, których użytkownik nie powinien zmieniać (np. role=admin)
14. Błędna konfiguracja CORS
    1. Odczyt wrażliwych danych (Tylko jeśli błędna konfiguracja umożliwia odczyt danych przez nieautoryzowane domeny).

    2. Wykonanie akcji w kontekście zalogowanego użytkownika wyłącznie z powodu błędnej konfiguracji CORS.
15. Path Traversal / LFI / RFI
    1. Odczyt, zapis, modyfikacja lub usuwanie lokalnych plików na serwerze (np. LFI/L, path traversal), jeśli pozwalają uzyskać dostęp do danych wrażliwych lub wpływać na konfigurację systemu)
16. CSRF z realnym wpływem na bezpieczeństwo
    1. zmiana danych lub stanu konta użytkownika (usunięcie konta, zmiana maila, dodanie użytkownika).
17. Open Redirect wyłącznie, jeśli spełniony jest co najmniej jeden z poniższych warunków:


- Redirect URI w przepływie OAuth/OIDC umożliwia przekierowanie na zewnętrzną domenę z przechwyceniem kodu uwierzytelnienia lub tokenu dostępu

- Open Redirect na domenie organizacji jest wykorzystywany jako ogniwo w udokumentowanym łańcuchu ataku (np. phishing z zaufaną domeną, bypass CSP)

- Open Redirect osiągnięty przez HTML Injection z możliwością przekierowania ofiary Subdomain takeover z działającym PoC przejęcia kontroli.


18. Web Cache Poisoning i inne ataki prowadzące do nieautoryzowanej modyfikacji treści serwowanych innym użytkownikom (w tym treści pochodzących z cache), poza treściami wprowadzanymi przez użytkownika.

19. HTTP Request Smuggling (CL.TE, TE.CL, TE.TE) prowadzący do:


- przechwycenia żądań innych użytkowników (request hijacking),

- obejścia mechanizmów bezpieczeństwa (np. WAF, autoryzacji),

- uzyskania dostępu do wewnętrznych endpointów dostępnych tylko z zaufanych źródeł,

- ataków typu cross-site request smuggling (np. w połączeniu z XSS lub CSRF).


20. XML External Entity Injection (XXE) prowadzące do:

- odczytu lokalnych plików systemu operacyjnego (np. /etc/passwd, kluczy prywatnych),

- wykorzystania jako wektor SSRF do dostępu do sieci wewnętrznej,

- zdalnego wykonania kodu (RCE), np. przy użyciu mechanizmów takich jak expect lub innych technik eskalacji.


**Typy podatności wyłączone z Konkursu**

01. Podatności wymagające konta (np. w AD), lub specjalnych uprawnień posiadanych przez pracownika NASK PIB.

02. Wyciek informacji, który nie prowadzi do ujawnienia wrażliwych ani istotnych danych, ani nie umożliwia atakującemu przeprowadzenia dalszych nadużyć. Są one klasyfikowane jako niskie ryzyko, jeśli same w sobie nie umożliwiają przejęcia konta, zwiększenia uprawnień, wykonania akcji w imieniu użytkownika ani dostępu do danych wrażliwych. Dotyczy to w szczególności wycieków, takich jak:
    1. Stack trace, wersje oprogramowania, IP, ścieżki, listingi katalogów).

    2. User enumeration (np. sprawdzenie czy e-mail istnieje)

    3. Wycieki metadanych lub danych publicznych

    4. Autocomplete w formularzach

    5. Publiczne endpointy debugowe bez możliwości eskalacji

    6. Brak walidacji po stronie klienta.
03. Problemy konfiguracyjne, które nie tworzą wektorów ataku
    01. Brak lub niepełne nagłówki bezpieczeństwa (X-Frame-Options, CSP, X-XSS-Protection, Referrer-Policy itp.)

    02. HSTS

    03. brak captchy

    04. brak flag security w nagłówkach i ciasteczkach

    05. Mixed content warnings

    06. Brak weryfikacji SPF/DKIM/DMARC (jeśli nie umożliwia spoofingu)

    07. Wygasłe certyfikaty SSL, brak zgodności nazwy certyfikatu z domeną, algorytmy szyfrowania uznawane za słabe, problemy z TLS bez realnego scenariusza ataku z zewnątrz.

    08. Otwarty port bez znaczenia bezpieczeństwa

    09. Nieaktualne oprogramowanie/biblioteki bez wpływu

    10. Znane CVE bez działającego PoC.
04. Wymagające nieuzasadnionych lub nierealnych założeń
    1. Ataki wymagające MITM, proxy, przejęcia sieci użytkownika

    2. Ataki wymagające fizycznego dostępu do urządzenia ofiary

    3. Wykorzystanie funkcji deweloperskich przeglądarki (DevTools)

    4. Ataki działające jedynie na archaicznych/przestarzałych przeglądarkach.
05. Ataki frontendowe, które da się wywołać tylko po stronie użytkownika, nie pozwalają uruchomić złośliwego kodu u innych osób oraz nie wpływają na bezpieczeństwo danych - na integralność, poufność ani dostępność.
    1. Self-XSS

    2. Tabnabbing. (wymaga pełnej interakcji użytkownika, nie powoduje realnego wpływu bezpieczeństwa i jest uznawane za problem przeglądarki/UX, a nie podatność aplikacji)

    3. Content injection bez wykonania kodu

    4. Clickjacking bez krytycznej akcji

    5. XSS lub Open Redirect w nagłówku Host bez możliwości wykorzystania

    6. Błędnie zaimplementowana polityka CORS nie prowadząca do kradzieży danych (np. brak Access-Control-Allow-Origin: \* bez możliwości kradzieży danych).

    7. czysty HTML injection bez możliwości JS
06. CSRF (wykluczone są zgłoszenia dotyczące problemów które nie mają realnego wpływu na integralność, poufność ani dostępność danych).
    1. CSRF w akcjach niezmieniających stanu użytkownika (logout, profil bez zmian, ekrany read-only)

    2. CSRF niewymagające faktycznego uwierzytelnienia lub niewpływające na dane.
07. Blind SSRF, gdzie jedynym dowodem jest odpowiedź DNS (brak możliwości odczytu danych lub eskalacji).

08. Open Redirect wymagający pełnej interakcji użytkownika bez realnego scenariusza phishingowego lub przechwycenia tokenu.

09. Problemy z kontami i sesjami niskiego wpływu
    1. Informacje o wymaganiach haseł (złożoność, długość)

    2. Polityki bezpieczeństwa haseł, które są zbyt liberalne, ale nie stanowią podatności
10. Ataki związane z zasobami
    1. Denial of Service (DoS / DDoS) – wszystkie formy ataków skutkujących zakłóceniem lub przerwaniem działania usług są zabronione.

    2. Testy obciążeniowe

    3. Brak rate limiting bez realnego scenariusza ataku (np. brak możliwości przejęcia konta)

    4. Możliwość wykonania ataku typu spam (wysyłanie wielu powiadomień/e-maili/SMS)
11. Podatności wymagające zewnętrznych narzędzi lub ingerencji
    1. CSV injection bez działającej formuły lub bez możliwości wykonania kodu

    2. Subdomain takeover bez działającego PoC przejęcia kontroli.
12. Klucze API i integracje zewnętrzne
    1. Ujawnione klucze API bez możliwości nadużyć.

    2. Ujawnione klucze API z restrykcjami domenowymi lub tylko do odczytu.

    3. Ujawnienie referera do zaufanych usług typu analytics/ads bez ataku.
13. Social engineering & wektory nietechniczne
    1. Phishing wobec pracowników.

    2. Social engineering wobec kontraktorów, partnerów i moderatorów.
14. Scenariusze teoretyczne lub nieudowodnione
    1. Podatności zgłaszane bez PoC.

    2. “Potencjalne” ataki bez realnej ścieżki wykonania

    3. Wymagające niestandardowej konfiguracji, rozszerzeń, proxy lub manipulacji przeglądarką

    4. Raporty na podstawie automatycznych skanerów bez ręcznego potwierdzenia.
15. Wewnętrzne błędy UX/UI
    1. Błędy tekstowe, literówki, grafika, layout.

    2. Niepoprawne komunikaty błędów

    3. Problemy użyteczności bez wpływu na bezpieczeństwo

## Zakres systemów

* * *

**Tier 1**: cert.pl, m.cert.pl, incydent.cert.pl, moje.cert.pl, n6portal.cert.pl, mwdb.cert.pl, hack.cert.pl

**Tier 2**: \*.cert.pl, ctf.hack.cert.pl

**Wykluczenia**: \*..hack.cert.pl, \*.lab.cert.pl

(\\* oznacza wszystkie subdomeny danej domeny)

Oznacza to, że domena hack.cert.pl (portal, z którego teraz korzystasz) jest objęta Programem, zaś jej subdomeny - nie, za wyjątkiem portalu ctf.hack.cert.pl.

## Zasady testowania

* * *

1. Testy mogą być prowadzone bez uwierzytelnienia, a w przypadku uwierzytelnienia - wyłącznie z użyciem kont własnych (poza domenowymi) lub kont testowych. Nie wolno korzystać z kont innych użytkowników.
2. Dopuszczalne jest użycie automatycznych narzędzi z maksymalną szybkością skanowania na poziomie 5 req/s.
3. Nie udostępniamy dedykowanych kont w serwisach na potrzeby testowania.

## Regulamin

[Pobierz regulamin edycji](https://hack.cert.pl/api/v1/public/institutions/cert-polska/programs/bug-bounty-cert-polska/editions/1/terms/download "Pobierz regulamin edycji")

## Aby zgłosić podatność, musisz być zalogowany.

[Zaloguj się](https://hack.cert.pl/login?returnTo=%2Fprograms%2Fcert-polska%2Fbug-bounty-cert-polska%2Feditions%2F1)