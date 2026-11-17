x

tero karvisen artikkeli Apache installed with Ansible - quick notes kertoo miten apache asennetaan ansiblella. tärkeimpiä huomioita ja komentoja on,

sudo apt-get install apache2

sudoedit /etc/apache2/...

sudo systemctl restart apache2

muutokset konfiguraatioihin otetaan käyttöön vasta uudelleenkäynnistyksen jälkeen, minkä takia restart komento on tärkeä.


ansiblen dokumentaation osio Handlers: running operations on change kertoo miten käyttää handlereita. hendlereilla saa ansiblen tekemään toimenpiteitä vain tilanteissa, 
joissa ansible on tehnyt muita muutoksia. handlereja voi käskeä suorittamaan itsensä taskin suorittamisen jälkeen käyttämällä notify avainsanaa.

y

löysin uutisen Fossilista joka on scw ohjelma https://news.ycombinator.com/item?id=49335217

-versionhallintaominaisuudet

-avoin lähdekoodi

a

asensin apache2 käsin käyttämällä tero karvisen ohjetta Install Apache Web Server on Ubuntu https://terokarvinen.com/install_apache_on_ubuntu.html annoin ensin komennon "sudo apt-get install apache2" jonka jälkeen tarkistin että apache sivu on localhostissa

<img width="1272" height="796" alt="kuva" src="https://github.com/user-attachments/assets/edca0742-95ec-4e0d-93b9-f1471540cc93" />

tarkistan index.html tiedoston oikeudet

<img width="595" height="177" alt="kuva" src="https://github.com/user-attachments/assets/b1287515-1560-4fcb-8e1e-f210c7ddfe4a" />

vain root käyttäjät voivat muokata tiedostoa

muokkaan oikeuksia niin että kaikki käyttäjät voivat muokata tiedostoa
<img width="796" height="190" alt="kuva" src="https://github.com/user-attachments/assets/0eb8b317-8fee-4a00-befa-197fad3bb044" />

b

pysäytin ensiksi apache2 komennolla "sudo systemctl stop apache2" jotta se ei häiritse nginx:iä 

seuraavaksi asensin nginx:in komennolla "sudo apt-get install nginx"

poistin apache2:n luoman index.html tiedoston, jonka jälkeen nginx etusivu tuli näkyviin

<img width="1263" height="355" alt="kuva" src="https://github.com/user-attachments/assets/2781719b-3784-4635-b75f-3a6ac0ec8c45" />

tarkistan nginx etusivun oikeudet

vain root käyttäjillä on oikeudet muokata tiedostoa, annan muille oikeudet tiedoston muokkaamiseen 

<img width="993" height="257" alt="kuva" src="https://github.com/user-attachments/assets/56431aa5-05a2-40ce-9fab-03114bb3ab7c" />


lähteet:
https://terokarvinen.com/apache-ansible/

https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_handlers.html

https://news.ycombinator.com/item?id=49335217
