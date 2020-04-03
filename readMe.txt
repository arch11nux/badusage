ansible-playbook -i hosts badusage.yml --syntax-check

=== pre-requis ===
# on remote server add authorized_keys
$ vi .ssh/authorized_keys
# on remote server add
$ sudo visudo
    ubuntu ALL=(ALL) NOPASSWD:ALL
===================

- hosts: esxcentos
  roles:
  - droits777
  - stickybit
  - gdbautologoutdisable
  - rselinux
  - bashrcsec   # inserer des parametres dans bash.rc

$ ansible-galaxy init roles/droits777
$ ansible-galaxy init roles/stickybit
$ ansible-galaxy init roles/gdbautologoutdisable
$ ansible-galaxy init roles/rselinux
$ ansible-galaxy init roles/bashrcsec
==============================================
Exemple de rapport:
-------------------
choix de demarrage:
    - droits777
    - stickybit
    - gdbautologoutdisable

output:
    - usager XX, chmod 777 fichier.ss
    - usager YY, unset TMOUT
    - usager ZZ, chmod -t repertoire00
==============================================
