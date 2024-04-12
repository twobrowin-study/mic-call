# Развёртывание Nginx и Kyecloak для ботов в коробках

## Предвариательные требования

Установить коллекцию vats:
```bash
ansible-galaxy install -r requirements.yml
```

## Доступ по ssh

После подготовки возможно получить доступ к машинам при помощи команды:
```bash
ansible -i inventory.yaml all --module-name include_role --args name=bmstu.vats.ssh_connection
```

## Иницилазция и получение сертификатов

```bash
ansible-playbook playbooks/01-init.yaml -i inventory.yaml
```

## Запуск Keycloak и nginx в Docker

```bash
ansible-playbook playbooks/02-docker.yaml -i inventory.yaml
```