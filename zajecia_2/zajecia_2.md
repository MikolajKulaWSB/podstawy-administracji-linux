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
```
sudo adduser user1
sudo adduser user2
sudo adduser user3
```
2. Utworzyć 2 grupy (IT, Sales) i przypisać do nich użytkowników
```
sudo groupadd it
sudo groupadd sales
sudo usermod -aG it user1
sudo usermod -aG sales user2
sudo usermod -aG sales user3
```
3. Stworzyć w root directory foldery /it i /sales
```
sudo mkdir /it
sudo mkdir /sales
```
4. Nadać do folderów dostępy dla odpowiednich grup
```
sudo chgrp /sales sales
sudo chgrp /it it
```
5. Sprawdzić na użytkownikach czy mogą dostać się do odpowiednich folderów, jednocześnie nie mając dostępu do folderów do których dostępu mieć nie powinni
```
su user1
cd /it

Powtórzyć dla pozostałych użytkowników
```
6. Utworzyć w folderze /tmp plik username.sh z tekstem

```
#!/bin/bash
whoami
```

```
vim /tmp/username.sh
```
7. Nadać pełne uprawnienia zapisu, odczytu, wykonywania do pliku dla wszystkich
```
sudo chmod 777 /tmp/username.sh
```
8. Wykonać plik jako dowolny użytkownik
```
su user1
/tmp/username.sh
```
1.  Stworzyć w folderze /tmp symlink do pliku username.sh
```
sudo ln -s /tmp/username.sh /tmp/username_symlink
```
2.  Przetestować symlink, a następnie usunąć plik username.sh, przetestować symlink jeszcze raz.
```
/tmp/username_symlink
sudo rm /tmp/username.sh
/tmp/username_symlink
```
3.  Usunąć symlink (polecenie rm), jeszcze raz stworzyć plik username.sh tak jak wcześniej (tekst + uprawnienia)
```
sudo rm /tmp/username_symlink
sudo vim /tmp/username.sh
```
4.  Stworzyć hard link do pliku username.sh w folderze /tmp
```
sudo ln /tmp/username.sh /tmp/username_hardlink
```
5.  Przetestować link, usunąć plik username.sh, jeszcze raz przetestować link.
```
/tmp/username_hardlink
sudo rm /tmp/username.sh
/tmp/username_hardlink

```