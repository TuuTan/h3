x

tero karvisen artikkeli Apache installed with Ansible - quick notes kertoo miten apache asennetaan ansiblella. tärkeimpiä huomioita ja komentoja on,

sudo apt-get install apache2

sudoedit /etc/apache2/...

sudo systemctl restart apache2

muutokset konfiguraatioihin otetaan käyttöön vasta uudelleenkäynnistyksen jälkeen, minkä takia restart komento on tärkeä.


ansiblen dokumentaation osio Handlers: running operations on change kertoo miten käyttää handlereita. hendlereilla saa ansiblen tekemään toimenpiteitä vain tilanteissa, 
joissa ansible on tehnyt muita muutoksia. handlereja voi käskeä suorittamaan itsensä taskin suorittamisen jälkeen käyttämällä notify avainsanaa.

y

löysin uutisen ansible4.0 julkaisusta. https://news.ycombinator.com/item?id=27215477 

-vanha ansible piti poistaa ennen uuden asennusta

-kaikki muutokset eivät olleet takaperinyhteensopivia

-ansible 3 päivitykset loppuivat

lähteet:
https://terokarvinen.com/apache-ansible/

https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_handlers.html

https://news.ycombinator.com/item?id=27215477
