# Important Information

Este apartado es para aclararles que solo debe haber un func main, sino dará error cuando ejecute el debugger, más adelante veremos como resolver estos problemas, también para correr el debug tenemos dos modos que son:\
\
1\. crear el mod.go\
2\. configurar el launch.json&#x20;

```
 {
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Launch Package",
            "type": "go",
            "request": "launch",
            "mode": "auto",
            "program": "${fileDirname}"
        }
    ]
}
```

Deja el código como esta arriba.

