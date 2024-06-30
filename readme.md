## Author 
Errifai anass 
## Configuration PHP multienvironnement avec Ansible
Ce projet Ansible permet de configurer les paramètres PHP différemment entre les environnements de développement et de production.

## Prérequis
Ansible installé sur la machine de contrôle
Accès SSH aux serveurs cibles (webservers)
PHP installé sur les serveurs cibles
## Utilisation
Cloner le référentiel Git :
Copier
git clone https://github.com/mon-compte/config-php-ansible.git
cd config-php-ansible
Modifier le fichier d'inventaire hosts pour y ajouter vos serveurs cibles.
## Exécuter le playbook Ansible :
Copier
ansible-playbook site.yml
Par défaut, le playbook utilise l'environnement "dev". Pour déployer en production, définir la variable d'environnement ANSIBLE_ENVIRONMENT=prod :

Copier
ANSIBLE_ENVIRONMENT=prod ansible-playbook site.yml
## Fonctionnalités
Configuration différente des paramètres PHP (ex : memory_limit, error_reporting, display_errors) entre les environnements de développement et de production.
Utilisation de templates Jinja2 pour les fichiers de configuration PHP.
Ajout de tags pour lancer des parties spécifiques du playbook.
install, start, deploy, permissions, restart, apache, website
Redémarrage automatique du service Apache après la modification de la configuration PHP.
## Fichiers importants
site.yml : le playbook principal
php.ini.dev.j2 : modèle de configuration PHP pour l'environnement de développement
php.ini.prod.j2 : modèle de configuration PHP pour l'environnement de production