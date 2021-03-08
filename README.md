# RubyBomber
Простой смс бомбер на ruby.

## Установка

### Termux

```
pkg install ruby git
git https://github.com/AlianaBasil/RubyBomber
cd RubyBomber
ruby bomber.rb
```

### Ubuntu/Debian

``` 
sudo apt update && sudo apt upgrade
sudo apt install ruby git
git https://github.com/AlianaBasil/RubyBomber
cd RubyBomber
ruby bomber.rb
```

### Прочие системы

Установите интерплитатор ruby и запустить ``bomber.rb``

## Добавление своего сервиса

Создайте .json файл в папке services и добавьте в него следующее:

```
{
"name": "name", 
"url": "url", 
"body": {"phone": "$phone"}, 
"params": ""
}
```

``name`` - название сервиса

``url`` - ссылка для запроса

``body`` - тело запроса

Для вставки номера телефона в нужное место вам доступны переменные(я хз как это еще называеть) - ``$phone`` и ``$phone_np``, которые заменяются на номер телефона и номер телефона без + соответственно. Так же есть переменные ``$username`` и ``$password``, хотя они и генерируются одним методом и по сути одно и тоже. Важно: бомбер заменяет переменные на значение только если само значение ключа равно переменной.

``params`` - параметры запроса. Если нужно вставлять телефон или еще что-то в ссылке, то добавьте ``$url``. Если нужно отправлять ``body`` в качестве тела запроса, то добавьте ``$json``. Если в каком-то месте ``body`` использовали ``$password`` или ``$username``, то добавьте их и сюда.
