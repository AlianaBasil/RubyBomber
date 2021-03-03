# RubyBomber
Простой смс бомбер на ruby.

# Установка

### Termux

```pkg install ruby git
git https://github.com/AlianaBasil/RubyBomber
cd RubyBomber
ruby bomber.rb
```

### Ubuntu/Debian

``` sudo apt update && sudo apt upgrade
sudo apt install ruby git
git https://github.com/AlianaBasil/RubyBomber
cd RubyBomber
ruby bomber.rb
```

# Добавление своего сервиса

Создайте .json файл в папке services и добавьте в него следующее:

```
{
"method":"post_json", 
"name": "name", 
"url": "url", 
"body": {"phone": "$phone"}, 
"key_with_phone": "phone"
}
```

``method`` - метод запроса, может быть ``post`` и ``post_json``. Подробнее о методах ниже.

``name`` - название сервиса

``url`` - ссылка для запроса

``body`` - тело запроса - нужно только для метода ``post_json``, если методом установлено ``post``, то не важно какие в ней данные, но удаление может вызвать ошибки.

``key_with_phone`` - какому ключу в ``body`` присвоить значение номера телефона. Так же не нужен для метода ``post``

Так же вам доступны две переменные ``$phone`` и ``$phone_np``, которые заменяются на номер телефона и номер телефона без + соответственно.

Теперь перейдем к методам. 

``post`` - этот метод подразумевает, что все данные для запроса находятся в ``url``, поэтому и потому, что запрос в этом случае идёт без тела, ключи ``body`` и ``key_with_phone`` не нужны, однако луяши их оставить во избежания проблем. Пример: ``citilink``

``post_json`` - при использовании этого метода номер телефона и прочие данные посылаются в теле запроса, котором является ``body``. Ключ, в котором находится ``$phone`` или ``$phone_np``, устанавливается значением ``key_with_phone``. Примеры: ``lenta`` и``youla``
