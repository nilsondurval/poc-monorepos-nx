# poc-monorepos-nx
This is a POC of monorepos using nx from nx.dev. The concepts that i want to prove are:
- I can have multiple apps and libs in the same workspace/repository
- The applications and libs are auto linked
- Changes in a lib are immediately reflected in the apps at runtime
- I can have multiple package.json (one per app/lib)
- I can have dependencies installed in one app/lib and others no
- I can run a single build/start/pack
- I can have ci/cd separate per app

# Stack
- nx - 15.0.1
- Angular - 14.2.0

# Installing nx
```sh
$ npm install -g nx
```

# How this nx workspace was created
```sh
$ npx create-nx-workspace@latest <my-workspace-name> --preset=npm
$ cd <my-workspace-name>
$ mkdir apps
$ mkdir libs
```

# Setup development enviroment

## Building

###  Building of one app/lib
```sh
$ nx build <@my-workspaces-name>/<my-app-or-lib-name>
```

### Building all apps/libs
```sh
$ nx run-many --target=build
```

###  Building app/lib with watch option
```sh
$ nx watch <@my-workspaces-name>/<my-app-or-lib-name>
```

## Starting the apps

### Starting one app
```sh
$ nx start <@my-workspaces-name>/<my-app-name>
```

### Starting all apps
```sh
$ nx run-many --target=start
```

### Creating a new app
```sh
$ cd apps
$ ng new <my-app-name>
```
-- Note: Alter package json as below
> "name": "<@my-workspaces-name>/<my-app-name>"

### Creating a new lib

#### Creating cli workspace
```sh
$ cd libs
$ ng new <my-workspace-name> --no-create-application
$ cd <my-workspace-name>
```
-- Note: Alter package json as below
> "name": "<@my-workspaces-name>/<my-lib-workspace-name>"

#### Generate lib on workspace
```sh
$ ng generate library <my-lib-name>
```

-- Note: Alter package json as below
> "name": "<@my-workspaces-name>/<my-lib-name>"
