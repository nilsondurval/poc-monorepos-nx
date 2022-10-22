# nx.dev

## Instalação
$ npm install -g nx

## Criar workspaces
$ npx create-nx-workspace@latest <my-workspace-name> --preset=npm
$ cd <my-workspace-name>
$ mkdir apps
$ mkdir libs

## Criar aplicação
$ cd apps
$ ng new <my-app-name>

-- Nota: Alterar package json
"name": "<@my-workspaces-name>/<my-app-name>",

## Criar biblioteca
$ cd libs
$ ng new <my-workspace-name> --no-create-application
$ cd <my-workspace-name>

-- Nota: Alterar package json
"name": "<@my-workspaces-name>/<my-lib-name>",

$ ng generate library <my-lib-name>

-- Nota: Alterar package json
"name": "<@my-workspaces-name>/<my-lib-name>",

## build de todas aplicações e libs
$ nx run-many --target=build

## Fazer build de uma aplicação/lib
$ nx build <@my-workspaces-name>/<my-app-or-lib-name>

## Fazer build de uma aplicação/lib com watch
$ nx watch <@my-workspaces-name>/<my-app-or-lib-name>

## Iniciar todas aplicações
$ nx run-many --target=start

## Iniciar aplicação
$ nx start <@my-workspaces-name>/<my-app-name>