# Tworzenie folderów i plików

Na początek należy przejść do folderu domowego użytkownika

```
cd
```

Utworzyć folder o nazwie "testfolder" i przejść do niego

```
mkdir testfolder
cd testfolder
```

Utworzyć plik tekstowy o nazwie "1.txt", edytować go edytorem vim w celu dodania dowolnego tekstu

```
touch 1.txt
vim 1.txt
```

Utworzyć folder o nazwie "testfolder2" i skopiować plik 1.txt do folderu pod nazwa 1-copy.txt

```
cp 1.txt testfolder2/1-copy.txt
```

Przejść do folderu "testfolder2" i wylistować pliki, oraz wypisać w terminalu zawartość pliku 1-copy.txt

```
cd testfolder2
ls
cat 1-copy.txt
```

Utworzyć plik 2.txt wykorzystując do tego celu funkcję "echo"

```
echo "123qwertyasdfg" > 2.txt
```

Utworzyć plik 3.txt zawierającego 5 ostatnich wpisów z historii terminala bash. Następnie dodać 3 pierwsze wiersze z historii terminala. Wyświetlić zawartość pliku

```

cat ~/.bash_history | tail -n 5 > 3.txt
cat ~/.bash_history | head -n 3 >> 3.txt
cat 3.txt

```

Nadpisać plik 3.txt ostatnimi 10 linijkami z historii terminala

```
cat ~/.bash_history | tail -n 10 > 3.txt
```

Przenieść plik 1.txt do folderu testfolder2, a następnie zmienić jego nazwę na 11.txt

```
mv ../1.txt ./1.txt
mv 1.txt 11.txt
```

Usunąć wszystkie pliki txt mające nazwy o długości 2 znaków

```
rm ??.txt
```

Utworzyć plik x.md. Wylistować wszystkie pliki .txt

```
touch x.md
ls *.txt
```

Wrócić do folderu domowego i wylistować wszystkie pliki i foldery, wliczając w to pliki ukryte. Listowanie powinno zawierać dodatkowe dane o plikach, takie jak uprawnienia i właściciel.

```
cd
ls -la
```

Usunąć folder testfolder.

```
rmdir testfolder
```