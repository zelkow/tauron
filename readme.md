## loading-csv : historia rocznych oplat

lista factur plik csv z https://ebok.tauron.pl/content/platnosci/archiwumFaktur


## parsing : wczytanie zlurzycia i innych oplat

sciagnij faktury rozliczeniowe w formie pdf do ./data


for i in *.pdf; do  pdftotext -layout $i; done
cat *.txt > faktury.txt
egrep "(I)" faktury.txt | grep Ener | grep 908 | tr -s " "| sort -k 7 -h | sed "s/(/ /g" | cut -d" " -f6-


