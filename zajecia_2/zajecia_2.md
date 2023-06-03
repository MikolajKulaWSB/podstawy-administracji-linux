# Potrzebne komendy na zajeciach

### Tworzenie użytkownika (wymaga roota)
```
adduser <nazwa_uzytkownika>
```

### Tworzenie grupy (wymaga roota)
```
groupadd <nazwa_grupy>
```

### Zmiana uprawnień do pliku
Notacja numeryczna:
x (execute) - 1
w (write) - 2
r (read) - 4

Notacja tekstowa:

'+' lub '-' wskazuje czy dodajemy czy odejmujemy uprawnienia
dla kogo? a = wszyscy; u = uzytkownik; g = grupa
jakie uprawnienie? x = wykonywanie; r = odczyt; w = zapis

Przykład:

a+x = dodać prawo do wykonywania dla wszystkich


```
chmod <uprawnienia> <nazwa_pliku>
```

### Zmiana użytkownika właściciela pliku

```
chown <nazwa_uzytkownika> <nazwa_pliku>
```

Jeżeli chcemy zmienić i użytkownika i grupę

```
chown <nazwa_uzytkownika>:<nazwa_grupy> <nazwa_pliku>
```

### Zmiana grupy do której należy plik

```
chgrp <nazwa_grupy> <nazwa pliku>
```

### Dodanie uzytkownika do grupy
```
usermod -aG <nazwa_grupy> <nazwa_uzytkownika>
```

### Tworzenie dowiązania symbolicznego (symbolic link, symlink)
```
ln -s <nazwa_pliku> <nazwa_linku>
```

### Tworzenia dowiązania twardego (hard link)
```
ln <nazwa_pliku> <nazwa_linku>
```

### Zmiana użytkownika
```
su - <nazwa_uzytkownika>
```


# Zadania

1. Utworzyć 3 użytkowników (nie jest wymagana kreatywność, można ich nazwać user1, user2 itp.)
2. Utworzyć 2 grupy (IT, Sales) i przypisać do nich użytkowników
3. Stworzyć w root directory foldery /it i /sales
4. Nadać do folderów dostępy dla odpowiednich grup
5. Sprawdzić na użytkownikach czy mogą dostać się do odpowiednich folderów, jednocześnie nie mając dostępu do folderów do których dostępu mieć nie powinni
6. Utworzyć w folderze /tmp plik username.sh z tekstem

```
#!/bin/bash
whoami
```
7. Nadać pełne uprawnienia zapisu, odczytu, wykonywania do pliku dla wszystkich
8. Wykonać plik jako dowolny użytkownik
9. Stworzyć w folderze /tmp symlink do pliku username.sh
10. Przetestować symlink, a następnie usunąć plik username.sh, przetestować symlink jeszcze raz.
11. Usunąć symlink (polecenie rm), jeszcze raz stworzyć plik username.sh tak jak wcześniej (tekst + uprawnienia)
12. Stworzyć hard link do pliku username.sh w folderze /tmp
13. Przetestować link, usunąć plik username.sh, jeszcze raz przetestować link.