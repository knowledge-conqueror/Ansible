# Czym jest Ansible?

Ansible to open-source narzedzie do automatyzacji, zarzadzania konfiguracja i instalacja pakietow. Jego glownym celem jest ulatwienie i przyspieszenie procesow zarzadzania infrastruktura IT. Ansible zostal stworzony przez firme Ansible, Inc., a obecnie jest utrzymywany przez Red Hat.

# Zastosowania Ansible

1. Zarzadzanie konfiguracja: Ansible pozwala na jednolite zarzadzanie konfiguracja serwerow, urzadzen sieciowych i innych systemow.

2. Automatyzacja wdrozen: Mozna go wykorzystac do automatyzacji procesow wdrozeniowych aplikacji, co przyspiesza cykl zycia oprogramowania.

3. Monitorowanie i zarzadzanie infrastruktura: Ansible pomaga w monitorowaniu i utrzymaniu systemow, jak rowniez w szybkiej reakcji na zmiany w infrastrukturze.

4. Cloud Computing: Ansible integruje siz z roznymi platformami chmurowymi, umozliwiajac zarzadzanie zasobami w chmurze.

5. Bezpieczenstwo: Ansible moze byc uzywany do wdrazania zabezpieczen oraz do przeprowadzania audytow bezpieczenstwa.

# Korzysci z uzycia Ansible

1. Prostota: Ansible jest latwy do nauczenia i stosunkowo prosty w uzyciu, zwlaszcza dla osob majacych doswiadczenie w YAML.

2. Bezagentowosc (Agentless): Ansible dziala bez koniecznosci instalowania agentow na zarzadzanych maszynach. Komunikuje sie zdalnie poprzez protokol SSH (Secure Shell) dla systemow Unix-like i WinRM (Windows Remote Management) dla systemow Windows.

3. Bezpieczenstwo: Bezagentowosc eliminuje potrzebe instalowania dodatkowych agentow na zarzadzanych maszynach, co przyczynia sie do zwiekszenia bezpieczenstwa.

4. Spojnosc: Ansible pozwala na jednolite zarzadzanie roznymi rodzajami infrastruktury, niezaleznie od platformy czy systemu operacyjnego.

5. Skalowalnosc: Ansible mozna latwo rozbudowac o wlasne moduly i playbooki, dostosowujac je do specyficznych potrzeb organizacji.

6. Moduly Ansible: Ansible uzywa modulow do wykonywania konkretnych zadan na maszynach zarzadzanych. Moduly to jednostki kodu, ktore mozna uzywac w Playbookach, aby zdeklarowac stan systemu.

# Czym sa Playbook-i

 Playbook to plik YAML, ktory zawiera zestaw instrukcji i deklaratywnych opisow, sluzacych do automatyzacji i zarzadzania konfiguracja systemow. Playbooki definiuja zadania, ktore maja byc wykonane na konkretnej grupie maszyn (hostow) oraz okreslaja, w jaki sposob maja zostac te zadania zrealizowane.

Struktura playbooka jest intuicyjna i czytelna, co ulatwia zrozumienie i utrzymanie kodu. Playbook sklada sie z listy blokow, a kazdy blok zawiera definicje zadania do wykonania na okreslonych hostach. Kluczowym elementem playbooka jest takze sekcja "hosts", w ktorej okresla sie grupe maszyn, na ktorych maja byc realizowane zadania.

Przykladowy playbook Ansible moze wygladac tak:

```yml
---
- name: Przykladowy Playbook
  hosts: webservers
  become: yes  # Uruchamianie zadan z uprawnieniami administratora

  tasks:
    - name: Zainstaluj Apache
      apt:
        name: apache2
        state: present  # Upewnij sis, ze Apache jest zainstalowany

    - name: Uruchom usluge Apache
      service:
        name: apache2
        state: started  # Uruchom Apache
```

W tym przykladzie:

 - name: Opisuje nazwe playbooka.
 - hosts: Okresla grupe maszyn, na ktorych maja byc wykonywane zadania. W tym przypadku, grupa to "webservers".
 - become: Wskazuje, ze zadania beda uruchamiane z uprawnieniami administratora.
 - tasks: Zawiera liste zadan do wykonania. Kazde zadanie ma swojc nazwe i okreslone kroki, ktore maja zostac podjete (np. instalacja pakietu, uruchomienie uslugi).