Role Name
=========

Rôle pour installer PostgreSQL, créer une base de données et un utilisateur avec tous les privilèges sur Ubuntu.

Requirements
------------

- Ubuntu 18.04 (Bionic), 20.04 (Focal), 22.04 (Jammy)
- Ansible >= 2.9
- Avoir les privilèges sudo sur le serveur cible
- Python3 sur le serveur cible pour les modules PostgreSQL

Role Variables
--------------

Les variables configurables pour ce rôle sont définies dans `defaults/main.yml` :

| Variable | Default | Description |
|----------|---------|-------------|
| db_name | app_db | Nom de la base de données à créer |
| db_user | user1 | Nom de l'utilisateur PostgreSQL |
| db_user_password | UserPass123! | Mot de passe de l'utilisateur PostgreSQL |

Ces variables peuvent être surchargées dans votre playbook comme suit :

```yaml
- hosts: dbservers
  roles:
    - role: database
      vars:
        db_name: "ma_base"
        db_user: "admin"
        db_user_password: "MotDePasse123"
