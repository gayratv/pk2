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