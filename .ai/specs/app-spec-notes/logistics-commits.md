# Logistyka — atomowy plan fundamentu

Źródło: [App Spec](../2026-09-19-app-spec-logistics-dashboard.md). Data: 2026-09-19.

Estymacja, nie zapis wykonanych commitów. Dwa commity w jednym wydaniu; testy muszą trafić do tej samej zmiany co funkcja. Nie wydawać samego C1.

| Commit | Zakres | Wynik weryfikowalny | Workflow / historie |
|---|---|---|---|
| C1 | Jeden moduł `logistics`: siedem stron z chronionymi metadanymi każdej strony, lokalne i18n, `acl.ts`, `setup.ts`, aktywacja w istniejącej konfiguracji; wymagane objęcie nowego modułu regułami DS | Wszystkie strony działają w istniejącej powłoce, jeden grant odczytu, zero nowych tabel/API, bez zmian logiki `auth`/UI platformy | WF1–3; US1–4 |
| C2 | Izolowane testy integracyjne siedmiu tras, grantów i braku grantów, wildcardów, organizacji, sesji, odebrania dostępu, klawiatury/mobile; krótka instrukcja włączenia i sync ACL | Reprodukowalne kryteria §7 i macierz pokrycia, generatory/i18n/typecheck/build według runnera repo | WF1–3; US1–4 |

Nie mnożyć C1 przez siedem stron: nie są to osobne portalowe aplikacje, tylko statyczne strony backendu współdzielące te same konwencje. Żadna historia nie wymaga ≥3 commitów. WF1 i WF3 ponownie wykorzystują istniejącą administrację ACL, bez lokalnych kopii helperów czy nowego silnika uprawnień.

Przed implementacją należy sprawdzić rzeczywisty zakres zmiany w rejestracji modułu i bloku lint DS. To nie daje zgody na przebudowę governance ani shell UI. Integracje GPS, dane operacyjne i Enterprise mają zero commitów w tym planie, bo są poza zakresem, a nie dlatego, że są gotowe.
