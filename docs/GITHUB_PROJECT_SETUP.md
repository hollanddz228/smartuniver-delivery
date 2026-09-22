# GitHub Projects жұмыс кеңістігін баптау жөніндегі нұсқаулық

Бұл құжатта 2-зертханалық жұмыстың 3-бөліміне сәйкес («SmartUniver» жобасы үшін) GitHub-та тірі жұмыс кеңістігін құру және баптаудың толық қадамдары көрсетілген.

---

## 1. Репозиторий және GitHub Projects ашу

1. GitHub профиліңізде жаңа репозиторий ашыңыз: `smartuniver-delivery`.
2. Репозиторийдің ішіндегі **Projects** қойындысына (tab) өтіп, **«New project»** батырмасын басыңыз.
3. Үлгіні **«Board»** немесе **«Team backlog»** түрінде таңдаңыз. Жоба атауы: `SmartUniver Delivery Board`.

---

## 2. Бағандар мен Статустарды (Statuses) баптау

Әдепкі (Default) бағандарды жобаның Гибридті (Scrum) процесіне сай келесідей етіп өзгертіңіз:
1. **📋 Backlog** — Барлық жиналған өнімдік идеялар, User Story және келешек функционалдар.
2. **🎯 Ready for Dev (Sprint Backlog)** — Ағымдағы спринтке таңдалған, нақтыланған және бағаланған тапсырмалар.
3. **⚡ In Progress** — Әзірлеушілер дәл қазір орындап жатқан тапсырмалар (WIP лимиті: әзірлеушіге 1 тапсырмадан).
4. **🔍 Code Review / QA** — Код тексеру сатысында немесе тестілеуші сынап жатқан тапсырмалар.
5. **✅ Done** — Definition of Done (DoD) критерийіне сай қабылданған және біріктірілген тапсырмалар.

---

## 3. Кастом өрістерді (Custom Fields) құру

Projects терезесінде **«+» (New Field)** батырмасын басып, жобаға қажетті қосымша өрістерді қосыңыз:

| Өріс атауы (Field Name) | Түрі (Field Type) | Опциялары / Мәндері | Мақсаты |
| :--- | :--- | :--- | :--- |
| **Priority** | Single select | `🔴 P0 - Critical`<br>`🟠 P1 - High`<br>`🟡 P2 - Medium`<br>`⚪ P3 - Low` | Тапсырмалардың маңыздылығын анықтау |
| **Story Points** | Number | `1, 2, 3, 5, 8, 13` | Еңбекті бағалау (Planning Poker) |
| **Delivery Stream** | Single select | `📱 Mobile App`<br>`🖥️ Admin Web`<br>`⚙️ Backend & DB API`<br>`📚 Docs & Architecture` | Жобаның қай компонентіне жататыны |
| **Sprint / Iteration** | Iteration | `Sprint 1 (Discovery)`, `Sprint 2 (Core MVP)`, `Sprint 3 (Integration)` | 2 апталық итерацияларға бекіту |

---

## 4. Тақта көріністерін (Views) құру

Тақтаның жоғарғы жағында 3 түрлі көрініс қосыңыз:
1. **View 1: «Kanban Board»** — Layout: *Board*, Group by: *Status* (Күнделікті командалық жұмыс үшін).
2. **View 2: «Sprint Planning»** — Layout: *Table*, Filter: `Iteration:"Sprint 1"`, Group by: *Delivery Stream*.
3. **View 3: «Priority Matrix»** — Layout: *Board*, Group by: *Priority* (Шұғыл мәселелерді бақылау үшін).

---

## 5. Тақтаға енгізілетін алғашқы тапсырмалар (Initial Tasks)

Атау келісімі (Naming Convention) толық сақталған мысал тапсырмалар:

| ID | Тапсырма атауы (Issue Title) | Тапсырма түрі | Статусы | Priority | Story Points | Delivery Stream |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **SU-1** | `[DOCS] docs/adr/ADR-001-delivery-model.md архитектуралық шешімін жазу` | Docs | Done | P0 - Critical | 2 | Docs & Architecture |
| **SU-2** | `[TASK] Репозиторий құрылымын және Naming Conventions құжатын бекіту` | Task | Done | P1 - High | 1 | Docs & Architecture |
| **SU-3** | `[SPIKE] Университеттің ескі деректер базасының API протоколдарын зерттеу` | Spike | In Progress | P0 - Critical | 5 | Backend & DB API |
| **SU-4** | `[FEAT] Студенттің жеке кабинетінде сабақ кестесін қарау интерфейсі` | Feature | Ready for Dev | P1 - High | 5 | Mobile App |
| **SU-5** | `[FEAT] Деканат веб-панелінде студенттік анықтамалар өтінімін мақұлдау модулі` | Feature | Backlog | P2 - Medium | 8 | Admin Web |
| **SU-6** | `[BUG] SSO авторизациясы кезіндегі токеннің жарамдылық мерзімін тексеру қатесі` | Bug | Ready for Dev | P1 - High | 3 | Backend & DB API |

---

## 6. Команданы және оқытушыны шақыру (Collaboration)

1. Репозиторийдің жоғарғы панелінен **Settings** бөліміне өтіңіз.
2. Сол жақ мәзірден **Collaborators** тармағын таңдаңыз.
3. **«Add people»** жасыл батырмасын басыңыз.
4. Оқытушының GitHub логинін (немесе команда мүшелерінің логинін) енгізіп, **«Add to this repository»** батырмасын басыңыз.
5. Projects тақтасына да осындай шақырту жіберіп, рұқсат деңгейін (Admin немесе Write) белгілеңіз.
