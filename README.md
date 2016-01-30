1. Installer une debian de base avec partition chiffrée

2. Exécuter ces commandes avant de pouvoir lancer ansible

sed -i -e 's/^deb cdrom:/#deb cdrom:/' /etc/apt/sources.list
apt-get update
apt-get upgrade -y

apt-get install git
apt-get install python-pip
apt-get install python-dev
apt-get install python-ecdsa
pip install ansible
apt-get autoremove

3. Lancer ansible


git clone https://github.com/pgrange/pportable_ansible.git
cd pportable_ansible/
#touch LOCALHOST inventory to add you user name
ansible-playbook -i LOCALHOST all.yml --ask-sudo-pass
