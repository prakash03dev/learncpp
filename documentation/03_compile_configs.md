# Lets config the compilation

Add the below cmds in the args array, please skip the brackets
*  (-ggdb) - for development builds
* (-O2 -DNDEBUG) - for production builds

>For GCC and Clang, the -O# option is used to control optimization settings. The most common options are as follows:

* -O0 is the recommended optimization level for debug builds, as it disables * optimization. This is the default setting.
* -O2 is the recommended optimization level for release builds, as it applies optimizations that should be beneficial for all programs.
* -O3 adds additional optimizations that may or may not perform better than -O2 depending on the specific program. Once your program is written, you can try compiling your release build with -O3 instead of -O2 and measure to see which is faster.

For development
```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Compile current c++ program",
            "command": "clang++",
            "type": "shell",
            "args": [
                "-ggdb",
                "${fileBasename}",
                "-o",
                "${fileBasenameNoExtension}.out"
            ],
            "group": "build"
        },
    ]
}
```
For production
```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Compile current c++ program",
            "command": "clang++",
            "type": "shell",
            "args": [
                "-O2",
                "-DNDEBUG",
                "${fileBasename}",
                "-o",
                "${fileBasenameNoExtension}.out"
            ],
            "group": "build"
        },
    ]
}
```


## Other cmds

### -pedantic-errors
enables c++ standards ( Most machines will support )

### -Wall, -Weffc++, -Wextra, -Wconversion, -Wsign-conversion
It enables the compiler to provide more detailed warnings about various coding practices that might lead to errors or unexpected behavior.

Key Warnings:

Unused variables, Unused functions, Implicit conversions, Unreachable code, Suspicious constructs


### -Werror
Treat warnings as errors


 ### -std=c++20
 Specific version of c++, check (https://www.learncpp.com/cpp-tutorial/configuring-your-compiler-choosing-a-language-standard/)

 >Dont forget to change your vscode c++ extension version also \
 >Extenstion >> c/c++ >> settings >> CPP Standard > your c++ version
