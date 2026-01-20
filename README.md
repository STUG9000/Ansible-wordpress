# Ansible WordPress (VMs locais)

Automação com **Ansible** para provisionar um servidor WordPress em **VMs locais** (Linux/Debian/Ubuntu).

Este projeto foi desenvolvido **como forma de estudo**, com o objetivo de aprofundar o entendimento sobre:

- Provisionamento automatizado
- Gerenciamento de configuração
- Idempotência no Ansible
- Uso de handlers, notify e módulos nativos

O playbook instala dependências, prepara diretórios, baixa e extrai o WordPress e aplica a configuração do Apache automaticamente.

---

## O que este projeto faz

- Instala dependências do WordPress (Apache, PHP e módulos, MySQL)
- Cria o diretório `/srv/www`
- Baixa o WordPress (`latest.tar.gz`)
- Extrai o WordPress em `/srv/www` (resultando em `/srv/www/wordpress`)
- Copia o VirtualHost do Apache (`files/wordpress.conf`)
- Recarrega o Apache quando o arquivo de configuração muda (handlers + notify)

---

## Requisitos

- Control node com Ansible instalado
- VM(s) destino com acesso SSH
- Sistema alvo: Debian/Ubuntu (usa `apt`)
- Permissão de `sudo` no usuário remoto

---

## Estrutura do projeto
├── provisioning.yml
├── files/
│ └── wordpress.conf
├── hosts.example
└── .gitignore
