# Praktikum 5 Failiõigused Linuxis

Selles praktikumis õppisin Linuxi failiõigusi. Õppisin lihtsamaid käske, nagu chmod ja chown. Õppisin ka setuid- ja setgid ning kuidas nende kasutamine võib olla turvarisk. Õppisin sticky biti kohta ning ACL'i kohta, mis võimaldab veelgi paindlikumat konfigureerida õigustejagamist. Uurisin ka wikipeedidast ja mujalt veebist chattr kohta, millega saab ülipõhjalikult konfigureerida faile.

Järgnevad üleannete lahendused ja pilt, mis tõestavad minu osalemist praktikumis.

Ülessane 5-1: a) Kataloogis oleva faili lugemiseks on kataloogile vaja minimaalselt execute õiguseid. Failile on vaja minimaalselt read õiguseid.
b) Kataloogis oleva faili kustutamiseks on kataloogile vaja minimaalselt execute õiguseid ja failile polegi ühtegi õigust vaja

Ülessanne 5-2: chmod a=x skriptifail ei ole piisav õigus shelli skriptifaili käivitamsiseks, sest tal puuduvad read õigused (puuduvad õigused, mis laseks vaadata faili sisse), vaja läheb veel read õigused juurde lisada. 

Ülesanne 5-3: Igal kasutajal on omanimeline grupp, et oleks lihtsam hallata õigusi samanimelise kasutaja failidele. Nt kasutajale ylemus võidakse anda grupi töötaja1 failidele ligipääs, et ülemus saaks täielikult hallata konkreetse töötaja kaustasid ja faile.

Ülesanne 5-5. Setuid on on vajalik, kui programm peab käivitama ennast teise kasutaja õigustes, et programm töötaks õigesti, sest programmi orginaalsel käivitajal ei pruugi olla õigusi käivitada vastavat programmi.

Ülesanne 5-6. Jah, setuid biti kasutamine võib süsteemi turvalisust vähendada, sest kasutaja kellel ei pruugi olla õigusi käivtada programmi, saab nüüd programmi käivitada teise kasutaja (jukuisa juhul õpetaja ehk omaniku) õigustes. Teisisõnu saab käivitada programmi suuremate õigustega, kui tal endal on.

Ülesanne 5-7. Sticky bit õigustega yhiskaust-kataloogist saavad Peetri faile kustutada kasutajad root (ta saab kõike teha), opetaja (tema on kausta omanik) ja peeter (tema on faili omanik).

Ülesanne 5-8. Uurides käsuga ls -la faili hinded.txt õigusi näen, et ainult kasutajal opetaja on kirjutamis ja lugemis õigused. Kopeerisin käsuga getfacl hinded.txt saadud vastuse siia:

peeter@jaakson-U23:/home/opetaja/klass$ getfacl hinded.txt

#file: hinded.txt

#owner: opetaja

#group: opetaja

user::rw-

group::---

other::---

Ülesanne 5-9. Keegi ei saa faili sisu modifitseerida, kui failile on seatud +i atribuut. Faili testfail-2 saab kustuda, kui esmalt eemaldada +i atribuut ja seejärel kustutades käsuga rm. Käsud millega seda saab teha on:
$ sudo chattr -i testfail-2
$ sudo rm testfail-2

![Ülesanne 5-4](https://github.com/HannesJaakson/opsys2023/assets/144902904/89a9aaf2-45be-4529-80ad-4f172295387f)


