# Lets setup vscode tasks
Everytime we cant be typing these cmds in the terminal, so lets automate this

create a **.vscode** folder in the root directory.
Inside .vscode folder create **tasks.json** file

type **(⌃Space</mark>)** you'll get a basic template

```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "My Task",
            "command": "echo hello",
            "type": "shell",
            "args": [],
            "problemMatcher": [
                "$tsc"
            ],
            "presentation": {
                "reveal": "always"
            },
            "group": "build"
        }
    ]
}
```
you can hover the field names for more details about the fields or you can check this schema ( https://code.visualstudio.com/docs/editor/tasks-appendix ).

## Lets create a task that compiles c++ program
before going that take a look at usefull variables ( https://code.visualstudio.com/docs/editor/variables-reference )

```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Compile current c++ program",
            "command": "clang++",
            "type": "shell",
            "args": [
                "${fileBasename}",
                "-o",
                "${fileBasenameNoExtension}.out"
            ],
            "group": "build"
        },
    ]
}
```
* **verison** - its the tasks version based on vscode settings
* **group** - group has ( "build" | "test" ) , press **( cmd + shift + b )** to view your task lists , b - stands for build. you can also see the all kinds of tasks by **( cmd + shift + p )** and search **run task**


