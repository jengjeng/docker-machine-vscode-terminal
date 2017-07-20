# docker-machine-vscode-terminal
Integration docker-machine in visual studio code integrated terminal

If you try to use docker but your windows doesn't support for HyperV and must to use docker-toolbox instead.
While you try to use it in visual studio code terminal but you encounter some errors like
```
error during connect: Get http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.30/containers/json?all=1:
open //./pipe/docker_engine: The system cannot find the file specified.
In the default daemon configuration on Windows,
the docker client must be run elevated to connect.
This error may also indicate that the docker daemon is not running.
```
Don't worry! Try this solution.

-----

## You have 2 solutions
### 1. Config "shellArgs" in vscode settings.
#### For bash user
```
{
  "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
  "terminal.integrated.shellArgs.windows": [
    "-c",
    "eval $(docker-machine env --shell=bash --no-proxy default);$SHELL"
  ]
}
```
#### For powershell user
```
{
  "terminal.integrated.shellArgs.windows": [
    "-NoExit"
    "iex",
    "\"& docker-machine env --shell=powershell --no-proxy default | iex\""
  ],
}
```
### or..
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
