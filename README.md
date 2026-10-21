# Aplikacja: HomeVault


Zespół:
- Weronika Zielińska dsw58966
- Danyl Takiullin Pro100D

Opis projektu:
HomeVault to aplikacja internetowa, w której użytkownik zapisuje rzeczy, które kupił — na przykład laptop, telefon, pralkę czy słuchawki. 
Przy każdej rzeczy można wpisać datę zakupu, cenę, sklep oraz datę końca gwarancji, a także dodać dokumenty: zdjęcie paragonu, fakturę PDF lub kartę gwarancyjną. Użytkownik może mieć kilka adresów (np. mieszkanie w mieście i dom rodzinny). Przy dodawaniu zakupu wybiera, do którego adresu należy dana rzecz, a potem może przeglądać zakupy osobno dla każdego adresu i dla wybranego okresu.

Dlaczego taka aplikacja:
Paragony często giną albo blakną, faktury są rozrzucone po skrzynce e-mail, a daty końca gwarancji trudno zapamiętać. HomeVault zbiera wszystkie te informacje w jednym miejscu, a pliki trzyma w chmurze, więc są dostępne z każdego urządzenia.

Technologia:
JavaScript, React, Node.js + Express, MongoDB Atlas, AWS S3, JWT, Git + GitHub.


Funkcjonalności: 
-  Konto użytkownika — rejestracja i logowanie (JWT).
-  Adresy — użytkownik może mieć dowolną liczbę adresów i wybrać adres domyślny.
-  Zakupy (CRUD) — dodawanie, edycja, usuwanie i przeglądanie zakupów; filtrowanie po adresie, okresie (od–do), kategorii i nazwie.
-  Dokumenty w chmurze — upload plików PDF/JPG/PNG do AWS S3, podgląd, pobieranie i usuwanie.
-  Gwarancje — data końca gwarancji, liczba dni do końca, status: aktywna / kończy się / wygasła.
-  Powiadomienia — automatyczne alerty 30, 7 i 1 dzień przed końcem gwarancji (w aplikacji, opcjonalnie e-mail).
-  Przypomnienia — własne terminy związane z rzeczą (serwis, filtr, ubezpieczenie).
-  Statystyki — suma wydatków i liczba rzeczy dla adresu i okresu, podział na kategorie.

Architektura:
1. Ekrany aplikacji
-  Logowanie / rejestracja — formularz z e-mailem i hasłem.
-  Strona główna — wybór adresu, ostatnio dodane rzeczy, gwarancje, które niedługo się kończą.
-  Lista zakupów — rzeczy z wybranego adresu, filtr dat (od–do), wyszukiwarka.
-  Dodawanie / edycja zakupu — formularz z danymi rzeczy, datą gwarancji i dodawaniem plików.
-  Adresy — lista adresów użytkownika, dodawanie, edycja i usuwanie.
-  Powiadomienia — lista powiadomień o kończących się gwarancjach.

2. Baza danych
-  users — użytkownicy (e-mail, hasło, imię).
-  addresses — adresy użytkowników (nazwa, ulica, miasto).
-  purchases — zakupy (nazwa, cena, data zakupu, koniec gwarancji, adres i lista dokumentów),
-  notifications — powiadomienia o kończących się gwarancjach.
-  Powiązania: jeden użytkownik może mieć wiele adresów i wiele zakupów, a do jednego adresu może należeć wiele zakupów. Same pliki (paragony, faktury) nie są w bazie, w bazie zapisany jest tylko link do pliku w AWS S3.

Uruchomienie:

Wdrożenie:
