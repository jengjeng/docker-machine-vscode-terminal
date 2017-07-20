# docker-machine-vscode-terminal
Integration docker-machine in visual studio code integrated terminal

-----

## You have 2 solutions
### 1. Using "shellArgs" in vscode settings.
```
{
  "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
  "terminal.integrated.shellArgs.windows": [
    "-c",
    "eval $(docker-machine env --shell=bash --no-proxy default);$SHELL"
  ]
}
```
### 2. Replace "start.sh" file in "Docker Toolbox" directory (see start.sh file) with following config in vscode settings.
```
{
  "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
  "terminal.integrated.shellArgs.windows": [
    "C:\\Program Files\\Docker Toolbox\\start.sh"
  ]
}
```

-----

#### Have fun with docker!
