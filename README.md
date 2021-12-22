# Алгоритмы асимметричного шифрования
### Лабораторная работа 5 “Протоколы шифрования”

### Работа программы:

client.py:

![client](https://user-images.githubusercontent.com/90343173/147148264-996552dc-3c57-4d7e-85e5-bbc42c5b7e3f.jpg)

server.py:

![server](https://user-images.githubusercontent.com/90343173/147148269-84aeccb4-df2f-4354-a392-59770452efae.jpg)

### Задания:

1.	Модифицируйте код клиента и сервера так, чтобы приватный и публичный ключ хранились в текстовых файлах на диске и, таким образом, переиспользовались между запусками.

      keys_c и keys_s:

<img width="87" alt="keys_c" src="https://user-images.githubusercontent.com/90343173/147163743-ed132b64-08f0-44be-8a93-a9827c267ff4.png">     <img width="87" alt="keys_s" src="https://user-images.githubusercontent.com/90343173/147163756-c955b9b1-42ca-4f87-b51f-ba94f304e84a.png">

2.	Проведите рефакторинг кода клиента и сервера так, чтобы все, относящееся к генерации ключей, установлению режима шифрования, шифрованию исходящих и дешифрованию входящих сообщений было отделено от основного алгоритма обмена сообщениями.

Функция обмена сообщениями:

<img width="309" alt="send_msg2" src="https://user-images.githubusercontent.com/90343173/147164813-4677c4fc-ecf4-46de-92c7-7cd3ddee3aae.png">

Функции calculation_part_key и calculation_full_key:

<img width="342" alt="calc" src="https://user-images.githubusercontent.com/90343173/147165053-f2ff2c1d-16ce-4938-8d57-7596f95ff2de.png">

Функции encoding и decoding:

<img width="359" alt="coding" src="https://user-images.githubusercontent.com/90343173/147165109-9672ce3c-2ff8-4ef7-bd73-704dcd494792.png">

Выше приведенные функции реализованны и в server.py, и в client.py. 

3.	Реализуйте на сервере проверку входящих сертификатов. На сервере должен храниться список разрешенных ключей. Когда клиент посылает на сервер свой публичный ключ, сервер ищет его среди разрешенных и, если такого не находит, разрывает соединение. Проверьте правильность работы не нескольких разных клиентах.

Список разрешенных ключей – keys_list.csv:

<img width="96" alt="keys_list" src="https://user-images.githubusercontent.com/90343173/147165487-86ed23b0-7165-46e5-8f9f-32315f468102.png">

4.	Модифицируйте код клиента и сервера таким образом, чтобы установление режима шифрования происходило при подключении на один порт, а основное общение - на другом порту. Номер порта можно передавать как первое зашифрованное сообщение.

![client — server](https://user-images.githubusercontent.com/90343173/147165565-ca718850-5f71-4563-9097-8a1eab9a282a.jpg)

server.py – функция port2:

<img width="266" alt="port2" src="https://user-images.githubusercontent.com/90343173/147165631-f795388b-cfcc-4c6f-9834-2dfbc84efa63.png">       <img width="126" alt="port2 2" src="https://user-images.githubusercontent.com/90343173/147165642-90b43bf7-0e9d-4370-9842-5a2c602ff638.png">

















