Здесь я сохраняю результаты вычисления числа pi.  

Все результаты сохраняются в файл `pi.txt`. По умолчанию он пуст, я архивирую результаты вычилений в `pi.tar.gz`.  

В файле `pi.tar.gz` лежит файл `pi.txt` с результатом вычисления 100.000.000 знаков после запятой.  

По дефолту в скрипте стоит 100.000.000, т.е. алгоритм будет вычислять 100.000.000 знаков после запятой в числе pi.  

Вот исходный код скрипта:  
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

from decimal import Decimal, getcontext
getcontext().prec=100000000
pi = str(sum(1/Decimal(16)**k * 
          (Decimal(4)/(8*k+1) - 
           Decimal(2)/(8*k+4) - 
           Decimal(1)/(8*k+5) -
           Decimal(1)/(8*k+6)) for k in range(100)))

f = open("pi.txt", "wb")
fd = f.write(pi.encode())

```

Открыть файл `pi.txt` реально только через UNIX утилиту less.
