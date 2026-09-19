# Logistics — stories / cross-story impact / role reversal

Data: 2026-09-19. Fresh-context reviewer `stories_review`; prompt DDD skilla, zakres §5–6, słownik, tożsamość i UI jako kontekst.

- CRITICAL: brak.
- WARNING: US4 musi określić nieznany stan po timeout zmiany organizacji. Dodano standardowy odczyt sesji bez deklarowania sukcesu przed jego ustaleniem.
- WARNING: macierz musi rozstrzygać równoczesność US1/US3 × US4. Dopisano rzeczywiście aktywny zakres + efektywny ACL na następnym autoryzowanym żądaniu; stara odpowiedź nie potwierdza nowego dostępu.
- OK: cztery historie mają alternatywy i błędy, ACL timeout ma uczciwy nieznany wynik, brak wymyślonych kompensacji transportowych i zdarzeń za wejście na stronę.
- Ocena po zastosowaniu drobnych korekt: brak nierozwiązanych CRITICAL/WARNING w zakresie review.

## Kryteria DDD napisane przez reviewera

1. Jedna grupa i siedem sekcji, wspólne Pojazdy / kierowcy.
2. Nazwy i opisy zgodne ze słownikiem; jawny stan funkcji planowanej.
3. Brak danych lub operacji udających wdrożoną logistykę.
4. Wspólne efektywne `logistics.view` dla menu i URL; poprawne wildcardy i odebranie ostatniego źródła.
5. Aktualny kontekst organizacji i efektywne ACL na następnym autoryzowanym wejściu, także po równoczesnych zmianach.
6. Brak mutacji danych transportowych przy nawigacji, odświeżeniu, retry i zamknięciu; niezależność od integracji.

PM przyjął wszystkie sześć. Każde chroni rzeczywisty zakres, integralność lub dostęp. Zawężenie interpretacji: brak nowych modeli/KPI/sesji i brak natychmiastowego zdalnego wymazywania otwartych statycznych stron. Operacyjne blokady rezerwacji, GPS i zdarzenia transportowe pozostają poza wydaniem.

Źródło: [App Spec](../2026-09-19-app-spec-logistics-dashboard.md).
