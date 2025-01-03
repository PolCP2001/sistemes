# Permisos especials i ACL

## Permisos d'usuari, propietari i grups

Els permisos *normals* de Linux es gestionen amb les comandes <code>chown</code>, <code>chgrp</code> i <code>chmod</code>. Aquestes comandes desenvolupen les següents funcions:

> **chown (-R)**    Canvia el propietari d'un fitxer o directori

> **chgrp (-R)**    Canvia el grup propietari d'un fitxer o directori

> **chmod (-R)**    Modifica els permisos d'un fitxer o directori


## Modes de permisos

Els fitxers o directoris poden tenir permisos assignats per l'usuari (**U**), el grup (**G**) i/o altres (**O**). La taula que es presenta a continuació defineix els valors dels permisos:

| MODE   | PERMISOS   |
|--------|------------|
| 0      | ---        |
| 1      | --x        |
| 2      | -w-        |
| 3      | -wx        |
| 4      | r--        |
| 5      | r-x        |
| 6      | rw-        |
| 7      | rwx        |


## UMASK

La <code>umask</code> és un valor que defineix els permisos predeterminats dels fitxers i directoris nous. Aquesta taula mostra com s'apliquen aquests valors:

| Configuració | Directori | Fitxers |
|--------------|-----------|---------|
| Original     | 777       | 666     |
| Umask        | 022       | 022     |
| Resultat     | 755       | 644     |

> **Explicació:** Sense cap canvi en la configuració predeterminada de la <code>umask</code>, tots els fitxers creats per l'usuari root obtindran permisos **644** (666 - 022), i tots els directoris obtindran permisos **755** (777 - 022).


### Com funciona la <code>umask</code>?

La <code>umask</code> no funciona per resta aritmètica, sinó *bit a bit*, apagant (desactivant) els permisos corresponents. Cada bit del valor predeterminat interacciona amb el bit equivalent de la <code>umask</code>.


##### Exemple de càćul per fitxers

Per calcular els permisos per a fitxers, seguim aquests passos:

| Pas           | Permisos    | Binari          |
|---------------|-------------|-----------------|
| Predeteminats | 666         | 110 110 110     |
| Umask         | 022         | 000 010 010     |
| NOR de l'Umask| Negació     | 111 101 101     |
| Resultat (AND)| Càlcul final| 110 100 100     |

Els permisos resultants són **110 100 100 = 644**

> - **Propietari**:     Pot llegir i escriure.

> - **Grup i altres**:  Només lectura.


##### Exemple de càlculs per directories

Per calcular els permisos per a directoris, seguim aquests passos:

| Pas           | Permisos    | Binari          |
|---------------|-------------|-----------------|
| Predeteminats | 777         | 111 111 111     |
| Umask         | 022         | 000 010 010     |
| NOR de l'Umask| Negació     | 111 101 101     |
| Resultat (AND)| Càlcul final| 110 101 101     |

Els permisos resultants són **110 101 101 = 755**

> - **Propietari**:     Pot llegir, escriure i executar.

> - **Grup i altres**:  Només poden llegir i executar.


##### Explicació Visual del Procés

1. **NOR (Negació)**: S'inverteixen els bits de l'Umask.

Exemple: <code>000 010 010</code> → <code>111 101 101</code>.

2. **AND (Intersecció)**: Es combinen els permisos predeterminats amb el resultat de la NOR.

Exemple: <code>110 110 110</code> AND <code>111 101 101</code> → <code>110 100 100</code>.


## Permisos especials

Els permisos especials com <code>sticky</code>, <code>suid</code> i <code>sgid</code> permeten funcionalitats addicionals en fitxers o carpetes. La taula següent explica cadascun d'ells:

| **Permís**           | **Comanda**    | **Descripció**          |
|---------------|-------------|-----------------|
| sticky    | chmod 1 +t        | Bloqueja la modificació d’arxius per altres usuaris.     |
| suid      | chmod 4 u+s        | Executa amb privilegis del propietari.     |
| sgid      | chmod 2 g+s     | Executa amb privilegis del grup.     |


## ACLs (Access Control Lists)

Les ACLs permeten definir permisos més granulars que els permisos "normals". Aquestes comandes permeten gestionar-les:

| Comanda      | Descripció               |
|--------------|--------------------------|
| getfacl      | Mostra les ACLs del fitxer/directori.        |
| setfacl -m   | Defineix permisos ACL.        |
| setfacl -b   | Esborra les ACLs del fitxer/directori.        |