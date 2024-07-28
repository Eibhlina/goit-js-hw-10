# Zadanie 1. Licznik czasu

Wykonaj to zadanie w plikach 01-timer.html і 01-timer.js. Napisz skrypt timera, który odlicza czas do określonej daty. Taki licznik może być używany na blogach, w sklepach internetowych, na stronach rejestracji na wydarzenia, podczas prac technicznych itp. Obejrzyj film demonstracyjny licznika.

## Elementy interfejsu

Dodaj do pliku HTML znaczniki licznika czasu, pola wyboru daty zakończenia i przycisk, który powinien uruchamiać licznik czasu po kliknięciu. Dodaj wygląd elementów interfejsu zgodnie z układem.


## Biblioteka flatpickr

Użyj biblioteki flatpickr, aby umożliwić użytkownikowi wybór daty i godziny zakończenia w różnych przeglądarkach w jednym elemencie interfejsu użytkownika. Aby dołączyć kod CSS biblioteki do swojego projektu, musisz dodać jeszcze jeden import, oprócz tego opisanego w dokumentacji.

Biblioteka oczekuje inicjalizacji na elemencie input[type="text"], więc dodaliśmy do dokumentu HTML pole input#datetime-picker.

Jako drugi argument funkcji flatpickr(selector, options) można przekazać opcjonalny obiekt opcji. Przygotowaliśmy już dla Ciebie obiekt potrzebny do wykonania tego zadania. Dowiedz się, za co odpowiadają poszczególne właściwości w dokumentacji «Options» і wykorzystaj je w swoim kodzie.


## Wybór daty

Metoda onClose() z obiektu parametru jest wywoływana za każdym razem, gdy zamykany jest element interfejsu, który tworzy flatpickr. Właśnie w tej metodzie należy przetwarzać datę wybraną przez użytkownika. Parametr selectedDates jest tablicą wybranych dat, więc bierzemy pierwszy element selectedDates[0].

Będziesz potrzebować tej wybranej daty w kodzie poza metodą onClose(). Dlatego zadeklaruj zmienną poza metodą let, na przykład userSelectedDate, a po sprawdzeniu poprawności w metodzie onClose() dla przeszłości/przyszłości, zapisz wybraną datę do tej zmiennej let.

* Jeśli użytkownik wybrał datę w przeszłości, wyświetl window.alert() z tekstem "Please choose a date in the future" і uczyń przycisk «Start» nieaktywnym.
* Jeśli użytkownik wybrał prawidłową datę (w przyszłości), przycisk «Start» staje się aktywny.
* Przycisk «Start» powinien być nieaktywny, dopóki użytkownik nie wybierze daty w przyszłości. Zwróć uwagę, że jeśli użytkownik wybierze prawidłową datę, nie uruchomi licznika czasu, a następnie wybierze nieprawidłową datę, to po odblokowaniu przycisk powinien ponownie stać się nieaktywny.
* Naciśnięcie przycisku «Start» rozpoczyna odliczanie do wybranej daty od momentu jego naciśnięcia.


## Odliczanie czasu

Po naciśnięciu przycisku «Start» skrypt powinien co sekundę obliczać ilość czasu pozostałego do określonej daty i aktualizować interfejs licznika czasu, wyświetlając cztery cyfry: dni, godziny, minuty i sekundy w formacie xx:xx:xx:xx.

* Liczba dni może składać się z więcej niż dwóch cyfr.
* Licznik powinien zatrzymać się, gdy osiągnie datę końcową, tj. pozostały czas wynosi zero 00:00:00:00.

NIE KOMPLIKUJMY SPRAWY Jeśli licznik czasu jest uruchomiony, aby wybrać nową datę i uruchomić go ponownie, należy odświeżyć stronę.

Aby obliczyć wartości, użyj gotowej funkcji convertMs, gdzie ms — to różnica między datą końcową a bieżącą datą w milisekundach.


## Formatowanie czasu

Funkcja convertMs() zwraca obiekt z obliczonym czasem pozostałym do daty końcowej. Zwróć uwagę, że nie formatuje ona wyniku. Oznacza to, że jeśli pozostały 4 minuty lub jakikolwiek inny składnik czasu, funkcja zwróci 4, а nie 04. W interfejsie licznika czasu należy dodawać 0, jeśli liczba jest mniejsza niż dwa znaki. Napisz funkcję, na przykład addLeadingZero(value), która używa metody łańcuchowej [padStart()](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padStart>) і formatuje wartość przed narysowaniem interfejsu.


## Biblioteka powiadomień

Aby wyświetlać powiadomienia użytkownikowi, zamiast window.alert() użyj biblioteki iziToast.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Zadanie 2. Generator obietnic

Wykonaj to zadanie w plikach 2-snackbar.html і 02-snackbar.js. Obejrzyj film demonstracyjny generatora obietnic.

Dodaj do pliku HTML znaczniki formularza. Formularz składa się z pola wejściowego do wprowadzenia wartości opóźnienia w milisekundach, dwóch przycisków radiowych określających sposób wykonania obietnicy oraz przycisku typu submit, którego kliknięcie spowoduje utworzenie obietnicy.

Napisz skrypt, który po przesłaniu formularza utworzy obietnicę. W połowie wywołania zwrotnego tej obietnicy po upływie określonej przez użytkownika liczby milisekund obietnica powinna zostać wykonana (jeśli "fulfilled") lub odrzucona (jeśli "rejected"), w zależności od opcji wybranej za pomocą przycisków radiowych. Wartością obietnicy przekazywanej jako argument do metod resolve/reject powinna być wartość opóźnienia w milisekundach.

Utworzoną obietnicę należy przetworzyć w odpowiednich metodach dla powodzenia/niepowodzenia.

Jeśli obietnica zostanie wykonana pomyślnie, wyświetl w konsoli następujący wiersz, gdzie delay jest wartością opóźnienia w milisekundach.

Jeśli obietnica zostanie odrzucona, wyświetl w konsoli następujący wiersz, gdzie delay jest wartością opóźnienia obietnicy w milisekundach.


## Biblioteka powiadomień

Do wyświetlania powiadomień zamiast console.log() użyj biblioteki iziToast. Aby dołączyć kod CSS biblioteki do swojego projektu, musisz dodać kolejny import, oprócz tego opisanego w dokumentacji.
















# Vanilla App Template

Цей проект було створено за допомогою Vite. Для знайомства та налаштування
додаткових можливостей [звернись до документації](https://vitejs.dev/).

## Створення репозиторію за шаблоном

Використовуй цей репозиторій організації GoIT як шаблон для створення
репозиторію свого проекту. Для цього натисни на кнопку `«Use this template»` і
обери опцію `«Create a new repository»`, як показано на зображенні.

![Creating repo from a template step 1](./assets/template-step-1.png)

На наступному етапі відкриється сторінка створення нового репозиторію. Заповни
поле його імені, переконайся, що репозиторій публічний, після чого натисни
кнопку `«Create repository from template»`.

![Creating repo from a template step 2](./assets/template-step-2.png)

Після того, як репозиторій буде створено, необхідно перейти в налаштування
створеного репозиторію на вкладку `Settings` > `Actions` > `General` як показано
на зображенні.

![Settings GitHub Actions permissions step 1](./assets/gh-actions-perm-1.png)

Проскроливши сторінку до самого кінця, в секції `«Workflow permissions»` обери
опцію `«Read and write permissions»` і постав галочку в чекбоксі. Це необхідно
для автоматизації процесу деплою проекту.

![Settings GitHub Actions permissions step 2](./assets/gh-actions-perm-2.png)

Тепер у тебе є особистий репозиторій проекту, зі структурою файлів та папок
репозиторію-шаблону. Далі працюй з ним, як з будь-яким іншим особистим
репозиторієм, клонуй його собі на комп'ютер, пиши код, роби коміти та відправляй
їх на GitHub.

## Підготовка до роботи

1. Переконайся, що на комп'ютері встановлено LTS-версію Node.js.
   [Скачай та встанови](https://nodejs.org/en/) її якщо необхідно.
2. Встанови базові залежності проекту в терміналі командою `npm install`.
3. Запусти режим розробки, виконавши в терміналі команду `npm run dev`.
4. Перейдіть у браузері за адресою
   [http://localhost:5173](http://localhost:5173). Ця сторінка буде автоматично
   перезавантажуватись після збереження змін у файли проекту.

## Файли і папки

- Файли розмітки компонентів сторінки повинні лежати в папці `src/partials` та
  імпортуватись до файлу `index.html`. Наприклад, файл з розміткою хедера
  `header.html` створюємо у папці `partials` та імпортуємо в `index.html`.
- Файли стилів повинні лежати в папці `src/css` та імпортуватись до HTML-файлів
  сторінок. Наприклад, для `index.html` файл стилів називається `index.css`.
- Зображення додавай до папки `src/img`. Збирач оптимізує їх, але тільки при
  деплої продакшн версії проекту. Все це відбувається у хмарі, щоб не
  навантажувати твій комп'ютер, тому що на слабких компʼютерах це може зайняти
  багато часу.

## Деплой

Продакшн версія проекту буде автоматично збиратися та деплоїтись на GitHub
Pages, у гілку `gh-pages`, щоразу, коли оновлюється гілка `main`. Наприклад,
після прямого пуша або прийнятого пул-реквесту. Для цього необхідно у файлі
`package.json` змінити значення прапора `--base=/<REPO>/`, для команди `build`,
замінивши `<REPO>` на назву свого репозиторію, та відправити зміни на GitHub.

```json
"build": "vite build --base=/<REPO>/",
```

Далі необхідно зайти в налаштування GitHub-репозиторію (`Settings` > `Pages`) та
виставити роздачу продакшн версії файлів з папки `/root` гілки `gh-pages`, якщо
це не було зроблено автоматично.

![GitHub Pages settings](./assets/repo-settings.png)

### Статус деплою

Статус деплою крайнього коміту відображається іконкою біля його ідентифікатора.

- **Жовтий колір** - виконується збірка та деплой проекту.
- **Зелений колір** - деплой завершився успішно.
- **Червоний колір** - під час лінтингу, збірки чи деплою сталася помилка.

Більш детальну інформацію про статус можна переглянути натиснувши на іконку, і в
вікні, що випадає, перейти за посиланням `Details`.

![Deployment status](./assets/deploy-status.png)

### Жива сторінка

Через якийсь час, зазвичай кілька хвилин, живу сторінку можна буде подивитися за
адресою, вказаною на вкладці `Settings` > `Pages` в налаштуваннях репозиторію.
Наприклад, ось посилання на живу версію для цього репозиторію

[https://goitacademy.github.io/vanilla-app-template/](https://goitacademy.github.io/vanilla-app-template/).

Якщо відкриється порожня сторінка, переконайся, що у вкладці `Console` немає
помилок пов'язаних з неправильними шляхами до CSS та JS файлів проекту
(**404**). Швидше за все у тебе неправильне значення прапора `--base` для
команди `build` у файлі `package.json`.

## Як це працює

![How it works](./assets/how-it-works.png)

1. Після кожного пуша у гілку `main` GitHub-репозиторію, запускається
   спеціальний скрипт (GitHub Action) із файлу `.github/workflows/deploy.yml`.
2. Усі файли репозиторію копіюються на сервер, де проект ініціалізується та
   проходить лінтинг та збірку перед деплоєм.
3. Якщо всі кроки пройшли успішно, зібрана продакшн версія файлів проекту
   відправляється у гілку `gh-pages`. В іншому випадку, у лозі виконання скрипта
   буде вказано в чому проблема.
