# docker-machine-vscode-terminal
Integration docker-machine in visual studio code integrated terminal

If you try to use docker but your windows doesn't supported for HyperV and must to use docker-toolbox instead.
While you try to use it in visual studio code terminal but you encouter some errors like
```
error during connect: Get http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.30/containers/json?all=1:
open //./pipe/docker_engine: The system cannot find the file specified.
In the default daemon configuration on Windows,
the docker client must be run elevated to connect.
This error may also indicate that the docker daemon is not running.
```
Don't worry! Try this solutions.

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
