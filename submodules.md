# Submodules

Imagine a situation where you want to include a project/code(lets call it Project-Common-Code) into two separate git projects(Project-A and Project-B).  You can easily copy the Project-Common-Code into Project-A and Project-B, but everytime the Project-Common-Code is updated you have to copy that again to Project-A and Project-B. You may also face merge issues if you modify them. To avoid such situations you can make the Project-Common-Code as a submodule inside the Project-A and Project-B. And you can independently modify that project and pull them into Project-A and Project-B.
