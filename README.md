# Raport przeprowadzonych operacji
###### Filip Błażejewski, Damian Korcz

Temat projektu: _Aplikacja_ _przewidująca_ _ocenę_ _filmu_ _na_ _podstawie_ _informacji_ _o_ _nim._
---

Używane biblioteki:
- requests
- datetime
-	pandas
-	regex
-	sklearn
-	json
-	sys
-	random
-	nltk

Poleceniem frame = pd.DataFrame([[]]) tworzymy pusty obiekt DataFrame. 
Następnie w pętli, funkcją requests.get pobieramy tekst HTM ze strony www.rottentomatoes.com poszczególnych opisów filmów. Z każdej ze strony wyszukujemy danych takich jak: gatunek, studio filmowe, datę premiery, długość filmu, obsadę aktorską oraz oceny i ich liczbę. Dane typu string wektorujemy za pomocą sposobu "one hot encoding", zapisujemy wszystkie dane do odpowiednich zmiennych, a następnie dodajemy je do DataFrame frame.

Nasz obiekt DataFrame frame zapisujemy do pliku filmy.json, na jego podstawie uczymy nasz model przewidywania średniej oceny filmu. W klasie TestPageParser przeprowadzamy testy jednostkowe.

Wyniki:
-	średnia różnica ocen: 14.39%
-	różnica do 5%: 171
-	różnica do 15%: 310
-	różnica do 20%: 113
-	różnica powyżej 20%: 220

Średnia różnica przewidzianych ocen, od ocen ze strony wynosi  14.39, co według nas jest dobrym wynikem. Dokładniejsze przewidzenie jest ciężkie ze względu na to że ocena jest czymś subiektywnym i nie zawsze jest taka, jaką można by przewidywać według jakiegoś klucza.
