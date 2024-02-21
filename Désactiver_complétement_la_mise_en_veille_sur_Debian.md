


Désactiver complétement la mise en veille sur Debian

Quand on a un serveur Debian qui tourne avec gnome, la gestion de l’énergie sous gnome peut mettre en veille le système. C’est pas adapté à un fonctionnement de type serveur.

Pour contourner le problème, il est possible de masquer complétement les demandes de mise en veille, d’hibernation etc… avec la commande suivante :

sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target

Au cas où vous souhaitez revenir en arrière, il suffit de faire :

