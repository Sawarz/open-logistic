# Logistics — architect checkpoints

Źródło: [App Spec](../2026-09-19-app-spec-logistics-dashboard.md). Data: 2026-09-19.

## Checkpoint #1 — workflow gap matrix

Fresh-context reviewer: `architect1`. Werdykt: PASS z drobnymi korektami specyfikacji; brak blokady architektonicznej.

- Standardowe strony, metadata, i18n i ACL pokrywają zakres; brak pominiętej funkcji i brak potrzeby menu injection, serwisów, encji czy API.
- Uściślono aktywację przez `enabledModules` / `{ id: 'logistics', from: '@app' }` w `apps/mercato/src/modules.ts`.
- Zapisano właściwe wspólne komponenty `Page`/`PageHeader`/`PageBody` i `EmptyState`, zamiast pustego stanu zakładki szczegółów.
- Zapisano przyszłe `generate`, `auth sync-role-acls` i odświeżenie cache strukturalnego.
- Dwa atomowe commity są rozsądną małą estymacją, dostarczaną w jednym wydaniu.

Dowody sprawdzone przez reviewera: `.ai/docs/module-development.md`, `packages/core/AGENTS.md`, metadata Work Inbox, `apps/mercato/src/modules.ts`, `.ai/ui-backend-components.md`, backend catch-all i `auth/services/rbacService.ts`. Autor zastosował korekty.

## Checkpoint #2 — story gap matrix

Fresh-context reviewer: `architect2`. Werdykt: PASS po drobnej korekcie; brak blokady architektonicznej.

- US1/WF1 wymaga pełnego zestawu uprawnień istniejącej ścieżki UI, nie samego `auth.acl.manage`. Dodano `auth.roles.list` i `auth.roles.manage`, istniejące adresy ról/edycji oraz opcjonalne strony użytkownika z ich uprawnieniami do §3.5.
- Mapowanie czterech historii kompletne; zero nowej logiki sesji, ACL, workflow, powiadomień, usług i encji.
- Estymacja dwóch commitów poprawnie deduplikuje wspólną pracę; testy w tym samym wydaniu, bez publikacji C1 osobno.
- Metadata w C1 obejmuje siedem chronionych stron; aktywacja, setup, sync ACL, cache, i18n i DS pozostają standardowe.

Dowody: `auth/backend/{roles,users}/page.meta.ts`, odpowiadające strony `[id]/edit/page.meta.ts`, `auth/api/{roles,users}/acl/route.ts`, `.ai/docs/module-development.md` i `auth/cli.ts`. Autor zastosował korekty. Końcowy status dokumentu uzgadniany po przeglądzie §7.
