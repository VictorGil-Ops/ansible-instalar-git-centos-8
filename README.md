# ansible-instalar-git-centos-8
Este playbook despliega un servidor Gitlab en un Centos 8

# Requisitos

CPU:
`min. 2 vcpus `

RAM:
`min. 3GB ` 

Almacenamiento:
`min. 20GB`

# Preparar los nodos a gestionar

Como ROOT>>

Generar clave ssh en el nodo de control se creará en ~/.ssh/id_rsa.pub

`ssh-keygen -t rsa`

Copiar la clave pública en el script ubicado en preparara_nodos_administrados

`preparar_nodos_administrados\preparar_nodos.sh`

Ejecutar el script en los nodos administrados

# Ejecutar playbook de instalación para Jenkins

Modificar el fichero 'inventory.ini' con el nodo donde se va a realizar la instalación

ejemplo:

```
[git_master]
git-master ansible_host=192.168.205.220

```
Para ejecutar el playbook

`ansible-playbook git_role.yaml -vv`