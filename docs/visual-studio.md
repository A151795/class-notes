---
sidebar_position: 3
---

# Visual Studio

## General Notes
- We can check out the compiled machine code of a C\# build by opening up the cmd and running `ildasm`. 
- VS has snippets built into it.  Just type the shortcut and then hit tab twice.
    - cw: Console.WriteLine
    - if: IF Statement

## Shortcuts
- General Shortcuts
    - ctrl + .
        - Brings up Intellisense
        - This is a magical shortcut, and can help create methods, classes, etc.
    - shift + alt + enter
        - Opens code window in full screen
    - F5
        - Run project with debugger
    - ctrl + F5
        - Runs project without debugger
    - F6 or shift + F6 or ctrl + shift + B
        - Build project
    - F12
        - Go to defination    
        - ctrl + -
            - Go back to where you were before you went to the definition
    - alt + F12
        - Go to definition in a new window
    - ctrl + ]
        - Finds associated closing bracket when the opening bracket is highlighed
    - ctrl + K ... ctrl + K
        - Bookmarks a line of code.  This puts a little bookmark at the left of the line where breakpoints go.
        - Bookmarks can be viewed in the bookmarks window.
        - The bookmarks window can be viewed with View > Bookmarks Window or with ctrl + K ... ctrl + W
- Opening Windows
    - ctrl + alt + L
        - Opens solution explorer
    - ctrl + K ... ctrl + W
        - Open the bookmarks window
    - ctrl + E ... T
        - Open the test explorer
- Refactoring
    - ctrl + R, ctrl + R
        - Renames method, variable, etc.
    - ctrl + K, ctrl + S
        - Surround with an if, try, for, etc.
    - alt + UP/DOWN
        - Move selection up or down a line
    - ctrl + K ... ctrl + C
        - Comments a block of code
    - ctrl + K ... ctrl + U
        - Uncomments a block of code
    - ctrl + K ... ctrl + D
        - Formats code per editor config
    - ctrl + K ... ctrl + F
        - Formats selection per editor config
    - ctrl + R ... ctrl + M
        - Extracts a selection of code into a new method.
        - Visual Studio will guess what parameters you will want in the method.
- Debugging
    - ctrl + shift + F5
        - Stops the current debugging session, rebuilds the solution, and starts another debugging session.
    - F9
        - Toggle breakpoint
    - F10
        - Step Over
    - F11
        - Step Into
    - UP + F11
        - Step Out
- Testing
    - ctrl + R ... A
        - Runs all tests
    - ctrl + R ... ctrl + A
        - Debug all tests  

  
