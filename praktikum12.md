# Praktikum 12 - Skriptimine Linuxis

Selles praktikumis õppisin Linuxi skripte kirjutama. Mulle jäi sellest mulje justkui uue programmeerimiskeele õppimine. Keel ei tundnud keeruline, kuid kindlasti tundus aegunud olevat.

Järgnev tekst on praktikumi ülesannete 3-6 plain tekst lahendused:

Ülesanne 3.
#!/bin/sh

echo 'Sisestage oma nimi: '
read nimi
echo 'Sisestage oma eriala: '
read eriala
echo 'Sisestage oma matriklinumber: '
read matriklinumber
echo "Teie nimi on $nimi, teie eriala on $eriala, teie matriklinumber on $matriklinumber"

Ülesanne 4.
#!/bin/bash

echo 'Sisestage faililaiend mida soovite muuta ilma punktita: '
read A

echo 'Sisestage faililaiend millega soovite asendada ilma puntktita: '
read B

failid=$(ls)

for i in $failid
do
    if [ "${i##*.}" = "$A" ]
    then
    mv "$i" "${i/$A/$B}"
    fi
done

ülesanne 5.
#!/bin/bash

protsessi_nimi=$1
IFS=$'\n' # see teeb nii, et tühikud ei eraldaks for tsüklis elemente vaid ainult reavahetused eraldavad elemente.

echo "Otsitava protsessi nimi: $protsessi_nimi"
echo "Leitud protsessid:"
echo ""

for line in $(ps -A | grep "$protsessi_nimi")
do
    pid=$(echo "$line" | tr -s ' ' | cut -d ' ' -f2)
    nimi=$(echo "$line" | tr -s ' ' | cut -d ' ' -f5)
    echo "PID: $pid, Nimi: $nimi"
done

Ülesanne 6.
#!/bin/bash
astenda () {
arv="$1"
asetendaja="$2"
i=1
while [ $i -lt $2 ]
do
    arv=$(($arv*$1))
    i=$(($i+1))
done
echo  "$arv"
}

a=$(astenda 9 5)
echo "$a"

Jägnevad pildid mis näitavad nende skriptide töötamist minu virutaalmasinas ning pildid GPT-4 lahenduses ülesanne 6-ele. Kahjuks ei mahtunud mul AI tehtud lahendus ühele pildile ära nii et tegin kolm kuvatõmmist. Saatsin ka txt faili koos kirjalike ülesannete vastustega, sest github ei näita neid korrektselt.

[ülesanded 12. praks.txt](https://github.com/HannesJaakson/opsys2023/files/13634317/ulesanded.12.praks.txt)
![ülesanne 3](https://github.com/HannesJaakson/opsys2023/assets/144902904/03e61373-f1a8-49a1-9d55-2e0a07b32723)
![ülesanne 4](https://github.com/HannesJaakson/opsys2023/assets/144902904/5a205ae3-1aba-43e6-9151-2f14bc4b046c)
![ülesanne 5](https://github.com/HannesJaakson/opsys2023/assets/144902904/0c9d69cf-3272-402d-80a9-ecdee77d6bf0)
![Ülesanne 6](https://github.com/HannesJaakson/opsys2023/assets/144902904/ef02b502-1b13-4422-8597-f0d72d824c6f)
![Ülesanne 7-1](https://github.com/HannesJaakson/opsys2023/assets/144902904/7e20f96f-7779-4110-9a10-30232003045d)
![Ülesanne 7-2](https://github.com/HannesJaakson/opsys2023/assets/144902904/e0b6433d-c4e4-4357-aec0-77bfd27a1056)
![Ülesanne 7-3](https://github.com/HannesJaakson/opsys2023/assets/144902904/6976d572-0c8d-45d5-88e9-907afc885e4b)



