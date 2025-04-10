# Role Ansible: zabbix_agent2_v7_snmp

Esta role instala e configura o **Zabbix Agent2 versão 7**, além de fornecer suporte ao **SNMP** com os **MIBs padrões** no **Ubuntu 24.04 (Noble Numbat)**.

## Funcionalidades

- Instala o `zabbix-agent2`, `snmp` e `snmp-mibs-downloader`
- Configura o arquivo `/etc/snmp/snmp.conf` com boas práticas
- Garante que o serviço do agente Zabbix esteja ativo e habilitado
- Compatível com Ansible 2.10+

## Variáveis Padrão

```yaml
# defaults/main.yml
zabbix_agent_snmp_packages:
  - zabbix-agent2
  - snmp
  - snmp-mibs-downloader
```

## Estrutura

```
zabbix_agent2_v7_snmp/
├── defaults/
│   └── main.yml
├── handlers/
│   └── main.yml
├── meta/
│   └── main.yml
├── tasks/
│   └── main.yml
├── templates/
│   └── snmp.conf.j2
├── tests/
│   └── test.yml
├── vars/
│   └── main.yml
└── README.md
```

## Uso

Adicione esta role ao seu playbook:

```yaml
- name: Instalar Zabbix Agent 2 e suporte SNMP
  hosts: all
  become: true
  roles:
    - zabbix_agent2_v7_snmp
```

Ou utilize o playbook de teste incluído em `tests/test.yml`.

## Requisitos

- Ubuntu 24.04
- Ansible 2.10 ou superior

## Handlers

- `Restart Zabbix Agent`: reinicia o serviço `zabbix-agent2` quando há alterações na configuração

## Tags Galaxy

`zabbix`, `agent`, `snmp`, `ubuntu`, `monitoring`

## Autor

José Zipf – [Nototi](https://nototi.com.br)

## Licença

MIT
