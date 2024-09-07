# My Ansible Playbook

## Описание

Этот проект представляет собой Ansible playbook, созданный для автоматизации задач с использованием групп хостов и переменных. Он включает в себя несколько окружений (например, `prod` и `test`) и использует плагины подключения Docker и Local для работы с различными хостами.

## Структура проекта

- `group_vars/`: Переменные для групп хостов.
  - `deb/`: Переменные для группы `deb`.
  - `el/`: Переменные для группы `el`.
  - `all/`: Общие переменные для всех хостов.
- `inventory/`: Инвентарные файлы для различных окружений.
  - `prod.yml`: Окружение для производственных хостов.
  - `test.yml`: Окружение для тестовых хостов.
- `site.yml`: Основной playbook для выполнения задач на всех хостах.

## Установка

1. Установите Ansible (версия 2.10 или выше):

   ```bash
   sudo apt update
   sudo apt install ansible
Использование
Клонируйте репозиторий:

bash
Копировать код
git clone https://github.com/cherkasovNV/my-ansible-playbook.git
cd my-ansible-playbook
Для запуска playbook на тестовом окружении:

bash
Копировать код
ansible-playbook -i inventory/test.yml site.yml
Для запуска на продакшн окружении:

bash
Копировать код
ansible-playbook -i inventory/prod.yml site.yml
Факты
В каждом окружении используются уникальные значения для факта some_fact, которые задаются в файлах group_vars.
В группе хостов deb используется значение: "deb default fact".
В группе хостов el используется значение: "el default fact".
Шифрование переменных
Переменные в group_vars/deb и group_vars/el зашифрованы с использованием Ansible Vault. Чтобы запустить playbook, введите пароль:
ansible-playbook -i inventory/prod.yml site.yml --ask-vault-pass
Автор
cherkasovNV (veseliifarsh@gmail.com)

Этот `README.md` описывает структуру проекта, инструкции по установке и запуску playbook, а также объясняет использование фактов и шифрования с помощью Ansible Vault. Ты можешь адаптировать этот шаблон под свои нужды, добавив дополнительную информацию, если потребуется.

