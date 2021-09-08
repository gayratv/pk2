# Проблема с описанием типов для существующего пакета
### Для примера взял пакет debug без типов
```
import  as createDebug from 'debug';
```
Такой код дает ошибку:
```angular2html
cli.ts:5:22 - error TS2349: This expression is not callable.
  Type 'typeof import("debug")' has no call signatures.
```

В документации сказано что надо добавить пути к описаниям типов в tsconfig.json что и было сделано:
```
"typeRoots": ["./node_modules/@types", "./types"],
одновременно с этим убрал секцию
"types" - которая ограничивает перечень импортируемых типов
```

проблема конечно решается импортом типов командой:
```angularjs
npm i -D @types/debug
```

Но Я хочу попробовать написать определения типов самостоятельно.  
Почему у меня это не получается ?


## Решение указал Alexey Ten :
вместо  
```export function```  
надо писать  
```export default function```  
рабочий код находится в соседней ветке

https://ru.stackoverflow.com/questions/1326450/%d0%9f%d1%80%d0%be%d0%b1%d0%bb%d0%b5%d0%bc%d0%b0-%d1%81-%d0%be%d0%bf%d0%b8%d1%81%d0%b0%d0%bd%d0%b8%d0%b5%d0%bc-%d1%82%d0%b8%d0%bf%d0%be%d0%b2-%d0%b4%d0%bb%d1%8f-%d1%81%d1%83%d1%89%d0%b5%d1%81%d1%82%d0%b2%d1%83%d1%8e%d1%89%d0%b5%d0%b3%d0%be-%d0%bf%d0%b0%d0%ba%d0%b5%d1%82%d0%b0/1326485#1326485