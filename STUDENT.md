# Moje wykonanie Lab00

- Login GitHub / pseudonim: czarogithub
- System i terminal (np. Windows + WSL Ubuntu): Linux
- Edytor / IDE: VSC
- Wersja Git: git version 2.51.0
- Wersja kompilatora C++: g++ 15.3.0
- Wersje java i javac: 25.0.4.1
- Link do pierwszego PR (uzupełnij w zadaniu 5): https://github.com/Czarogithub/oop-lab00-czarogithub/pull/1

## Uruchomienie lokalne
Wynik programu C++:
```text
Hello from C++! czarogithub pozdrawiam!
```
Wynik programu Java:
```text
Hello from Java! czarogithub pozdrawiam
```

## Błąd i poprawka (zadanie 5)
- Krótki fragment komunikatu błędu i numer linii: `cpp/main.cpp:5:67: error: expected ';' before 'return'` – linia 5 (kompilator wskazuje koniec instrukcji `std::cout`, tuż przed `return` z linii 6).
- Przyczyna oraz sposób naprawy: po usunięciu średnika instrukcja `std::cout << ... << '\n'` nie była zakończona, więc kompilator trafił na `return` w środku wyrażenia. Naprawa: przywróciłem średnik na końcu linii 5, ponownie skompilowałem i uruchomiłem program.
- Commit z błędem (SHA lub link): `046b1f4` – https://github.com/Czarogithub/oop-lab00-czarogithub/commit/046b1f45d8becf602db874db0fe1c3002960a1cd
- Czy Actions pokazały błąd, a po naprawie sukces? Tak – dla commita z błędem zadanie „C++ compilation and run” w workflow „Lab00 build” padło na kroku „Compile C++” (https://github.com/Czarogithub/oop-lab00-czarogithub/actions/runs/40240383028), zadanie Java przeszło. Po przywróceniu średnika oba zadania (C++ i Java) przeszły na zielono.

## Krótkie odpowiedzi
1. Co różni commit od push? Commit zapisuje wybrane (dodane przez `git add`) zmiany w lokalnej historii repozytorium na moim komputerze. Push wysyła te lokalne commity do repozytorium zdalnego (origin na GitHub). Dopóki nie zrobię push, nikt inny nie widzi moich commitów.
2. Dlaczego po scaleniu PR wykonuję lokalnie pull? Merge PR dzieje się na GitHub, czyli w repozytorium zdalnym – powstaje tam nowy commit na `main`. Moje lokalne `main` o nim nie wie, dopóki nie pobiorę zmian przez `git pull`. Bez tego dalsza praca (np. nowa gałąź) zaczynałaby się od nieaktualnego kodu.
3. Co potwierdza zielony wynik naszego CI, a czego nie potwierdza? Potwierdza, że kod z danego commita kompiluje się (g++ w C++17 z ostrzeżeniami, javac z JDK 17) i uruchamia bez błędu w czystym środowisku GitHub Actions. Nie potwierdza, że program wypisuje właściwy tekst (workflow nie porównuje wyniku), że wykonałem wszystkie zadania ani że moje lokalne środowisko jest dobrze skonfigurowane.

## Ewentualne problemy środowiska
Brak.
