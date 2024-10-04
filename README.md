# Развёртывание Бота в коробке для МИЦ МГТУ им. Н.Э. Баумана

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

## Запуск бота

```bash
ansible-playbook playbook.yaml -i inventory.yaml -t deploy
```

## Добавление параметров Nginx

```bash
ansible-playbook playbook.yaml -i inventory.yaml -t nginx_config
```