# Ansible

### Настройка
1. В файле `.vault_pass` лежит пароль от ansible vault.
1. Для корректной работы ansible лучше использовать virtualenv:
    ```shell script
    virtualenv -p /usr/local/bin/python3 ~/.local
    . ~/.local/bin/activate
    ```
1. Установить необходимые зависимости:
    ```shell script
    pip install -r requirements.txt
    ```
   
### Запуск playbook
```shell script
ansible-playbook -i inventories/local/static.yml --vault-password-file=.vault_pass consul.yml
```

curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
sudo apt-get update
sudo apt-get install consul