# Instalação do Ansible

##  Requisitos do servidor
1. Registro do servidor
```
subscription-manager register --auto-attach
```

1. Verificar o Status do servidor
```
subscription-manager status
```  

1. Listar as subscrições disponives
```  
subscription-manager list --all --available > /tmp/subs
```  

1. Attach da subscrição
```  
subscription-manager attach --pool=xxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

1. habilitar o repo ansible-automation-platform-2.2-for-rhel-9-x86_64-rpms
```
subscription-manager repos --enable=ansible-automation-platform-2.2-for-rhel-9-x86_64-rpms
```

1. Instalando os pacotes do Ansible
```
dnf install ansible-navigator ansible ansible-core
```

1. verificar a versao do ansible e/ou ansible-navigator
```
ansible --version
ansible-navigator --version
```

1. realizar login no registry da redhat
```
podman login registry.redhat.io
```

1. Baixar imagem do EE
```
podman pull registry.redhat.io/ansible-automation-platform-22/ee-supported-rhel8:latest
```

1. Listar imagens
```
ansible-navigator images
```
