# Corrige - Exercice 2 - Monitoring - correction


## Que doit on monitorer sur un site web ?

| Quoi | Quand | Pourquoi |
| ---- | ----- | -------- |
| CPU : charge (%) | Temps réel | |
| espace disque (dur) | 1X/ 10 minutes | | 
| RAM | temps réel | | 
| I/O | temps reel | |

- Verifier syslog pour materiel 

## Exemple de script 

* Script pour vérifier la taille du disque : 
```bash
#!/bin/sh

SEUIL=80
message=/tmp/bidon

df -P | grep -v '^Filesystem' | sed 's/%//' | 
while read fs total used avail capacity mount
do
if [ $capacity -gt $SEUIL ];then
printf "%-20s %5d%%\n" $mount $capacity >> $message
fi
done
if [ -r $message ];then
mail -s "LES DISQUES SONT PLEINS" root < $message
rm -f $message
fi
```


