# Instalação do Ansible

##  Pre-Req do S.O
1. Registro do servidor

```
subscription-manager register --auto-attach
```

1. Verificar o Status do servidor

```
subscription-manager status
```  

O Ansible esta disponivel em diferentes pacotes em diferentes repositórios:
* ansible-core                    rhel-9-for-x86_64-appstream-rpms
* ansible and ansible-navigator   ansible-automation-platform-2.3-for-rhel-9-x86_64-rpms

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

## Instalação do Ansible

1. Instalando os pacotes do Ansible
```
dnf install ansible-navigator ansible ansible-core
```

1. verificar a versao do ansible e/ou ansible-navigator
```
ansible --version
ansible-navigator --version
```

## Execution Environment

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
>[!NOTE]
>Por padrão o ansible navigator busca a ultima versão do EE valida, por exemplo: registry.redhat.io/ansible-automation-platform-23/ee-supported-rhel8:latest