# Práctica 8: Ansible + Docker

## Pasos
1. `docker build -t ubuntu-ssh:latest .`
2. `docker compose up -d`
3. Instalar Ansible (en WSL/Ubuntu): `sudo apt update && sudo apt install -y ansible sshpass`
4. Verificar conexión: `ansible all -m ping`
   (si las IPs no responden: `ansible all -i inventario-localhost.ini -m ping`)
5. Ejecutar: `ansible-playbook playbook.yml`
6. Verificar: `ansible all -a "cat /home/itla/app/hola.txt"`

## Archivos
- Dockerfile: Ubuntu 22.04 + SSH + usuario `ansible` (sudo sin password)
- docker-compose.yml: 5 servidores (172.20.0.11-15)
- inventario.ini / ansible.cfg: inventario y config (ignora advertencia SSH)
- playbook.yml: apt update, usuario itla, carpeta app, hola.txt, cowsay y htop
