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




