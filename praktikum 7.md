# 7.praktikum - Haakimine
Selles praktikumis õppisin Windows 11 Kettahalduri kastuamist, kui ka Ubuntu kettahadustööriista "Disks kasutamist, võrguketaste kasutamist nii Windows 11-nes kui Ubuntus, USB kasutamist Ubuntus ning kuidas seda manuaalselt haakida mõne teise kaustaga. Viimasena õppisin, kuidas 4TB ketas automaatselt haakuks arvuti käivitamisel.

1. Andmekandjad vajavad lähtestamist, et neid saaks arvutis kasutadada. Põhjuseid, miks seda vaja on, on mitu, kuid mõned on näiteks, 1) sellega luukase andmekandja peale failisüsteem 2) kui lähtestamine on tehtud on võimalik ketas partisioneerida (ühest ketast mitu ketast teha) 3) Kui sama operatsioonisüsteem on andmekandja ise ülesseadnud, siis see vähendab riske, et andmekandja ei tööta õigesti.

2. 1. GPT toetab suuremaid andmekandjaid, kui MBR, mis toetab kuni 2TB kettaid.
   2. MBR toetab kuni 4 partitsiooni, GPT aga 128.
   3. GPT'ga on parem andmetetaastavus tõrgete korral, sest salvestab andmeid erinevatesse kohtadesse ketta peal.

3. Link tõestamaks ülesande läbitust: https://kodu.ut.ee/~hannesja/hdd.png

4. Lisasin küsimusele vastususe andva pildi manusesse.

5. Mount käsu parameeter -o ro tähistab mountimis optionseid nii et teeb võimaldab andmekandjalt ainult lugemist, kusjuures kasutades käsku mount --help on näha et parameeter -r teeb sama. Parameeter -t auto teeb nii et andmekandjaga ühilduv failisüsteem määratakse automaatselt.

6. Kasutades käsku mount -l leidsin, et auto asendati exfat'iga.

7. Lisasin küsimusele vastususe andva pildi manusesse.

![Ülesanne 4](https://github.com/HannesJaakson/opsys2023/assets/144902904/054bd6a9-cc1b-4c0c-ab3e-024f3f90a75c)
![Ülesanne 7](https://github.com/HannesJaakson/opsys2023/assets/144902904/8e38636c-f8e0-4c8b-8c31-1c402dfaaf93)
