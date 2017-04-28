# soc-ldap

cloner le dépôt
lancer cert.bash pour créer les certificats 
faire un docker-compose up -d pour lancer les conteneurs


changement (moche) des droits dans l'annuaire:

# docker exec -ti openldap /bin/bash
# apt update
# apt install -y ldapvi nano ldap-utils
# ldapvi -h ldapi:/// -Y EXTERNAL -b cn=config

dans la partie
20 olcDatabase={1}hdb,cn=config

modifier la ligne
olcAccess: {1}to * by self write by dn="cn=admin,dc=soc,dc=imerir" write by * none

en
olcAccess: {1}to * by self write by dn="cn=admin,dc=soc,dc=imerir" write by * read

sauver et sortir
