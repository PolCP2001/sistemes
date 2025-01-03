## Gestors d'arrancada 

Els gestors d'arrencada són programes que s'executen en l'arrencada del sistema i permeten seleccionar quin sistema operatiu o quin nucli del sistema vols iniciar.

### GRUB2

GRUB2 és el gestor d'arrencada més utilitzat en sistemes Linux. És molt flexible i suporta múltiples sistemes operatius, cosa que el fa ideal per a entorns de doble arrencada. GRUB2 permet personalitzar el procés d'arrencada i inclou eines per solucionar problemes de càrrega.

### MBR (Master Boot Record)

L’MBR és el tipus tradicional de particionament utilitzat pels discs durs més antics. Conté informació sobre com arrencar el sistema operatiu i com està estructurat el disc. És compatible amb sistemes antics, però té limitacions, com el màxim de 4 particions primàries i un límit de 2 TB per partició.

### GPT (GUID Partition Table)

El GPT és el sistema de particionament modern, utilitzat majoritàriament amb sistemes UEFI. Supera les limitacions de l’MBR, permetent un nombre gairebé il·limitat de particions i suportant discs durs de grans dimensions (més de 2 TB).