# Potrzebne komendy na zajeciach

### Listowanie miejsca zajmowanego przez foldery i pliki w lokalizacji

```
du
```
Dodatkowe parametry

```
-d <liczba> - listuje drzewo plików tylko do określonej głębokości
```

### Sortowanie

```
sort
```
Dodatkowe parametry

```
-n sortowanie numeryczne (liczby traktowane są jako liczby a nie jako tekst)
-r sortowanie odwrotne
```

### Wyszukiwanie pliku

```
find <lokalizacja> -name <nazwa pliku> (może też być -type <typ pliku>)
```

Dodatkowe parametry
```
-maxdepth <liczba> - maksymalny poziom załębienia drzewa w którym będą przeszukiwane pliki
-mindepth <liczba> - minimalny poziom załębienia drzewa w którym będą przeszukiwane pliki
-regex <wyrażenie regularne> - wyszukiwanie przy użyciu wyrażeń regularnych
```

### Zliczanie linii/słów/liter

```
wc
```

Dodatkowe parametry

```
-l zliczanie linii
-w zliczanie słów
-m zliczanie znaków
```


### Filtrowanie tekstu

```
grep <wymagana fraza>
```

### Deduplikacja

```
uniq
```
### Pakowanie plików algorytmem tar

```
tar -zcvf <plik.tar.gz> <folder/plik do spakowania>
```

### Rozpakowanie plików algorytmem tar

```
tar -zxvf <plik.tar.gz> <folder/plik do spakowania>
```

# Zadania

1. Wylistować miejsce zajmowane przez pliki i foldery w folderze /etc
```
cd /etc
sudo du
```
2. Wylistować miejsce zajmowane przez pliki i foldery w folderze /etc wybierając tylko 5 największych
```
sudo du | sort -n -r | head -n 5 
```
3. Wylistować miejsce zajmowane przez pliki i foldery w folderze /etc wybierając tylko 2-6 najmniejszych na głębokości 1
```
sudo du -d 1 | sort -n | head -n 6 | tail -n 5
```
4. Znaleźć lokalizację pliku "shadow"
```
sudo find / -name shadow
```
5. Znaleźć wszystkie pliki w folderze etc, które w swojej nazwie zawierają cyfrę, nie będącą ani na początku, ani na końcu nazwy pliku (użyć regex w poleceniu find), zliczyć ich ilość.
```
sudo find /etc/ -regex ".*[0-9].*" | wc -l
```
6. Wyświetlić plik /proc/cpuinfo
```
sudo cat /proc/cpuinfo
```
7. Wyszukać linijkę odpowiadającą za liczbę rdzeni procesora, jeżeli pojawia się ona wielokrotnie, należy wynik zdeduplikować
```
sudo cat /proc/cpuinfo | grep "cores" | uniq
```
8. Wyszukać linijkę odpowiadającą za częstotliwość taktowania zegara procesora, jeżeli pojawia się ona wielokrotnie, należy wynik zdeduplikować
```
sudo cat /proc/cpuinfo | grep "MHz" | uniq
```
9.  Utworzyć w folderze domowym folder o nazwie "1", stworzyć w nim 5 plików a następnie spakować go do archiwum "1.tar.gz".
```
cd
mkdir 1
cd mkdir 1
touch a.txt
touch b.txt
touch c.txt
touch d.txt
touch e.txt
cd
tar -cvzf 1.tar.gz 1
```
10. Usunąć folder "1", a następnie wypakować go z archiwum
```
rm -r 1
tar -xvzf 1.tar.gz
```