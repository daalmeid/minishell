#
# MINISHELL

@42 lisbon
Coauthored by: https://github.com/Rafael2sf

#
## 📝   - Description 
This project brings together all the knowledge acquired in previous projects and more, by rebuilding one of the core features of any modern pc, a shell, based on i/o methodology, you will be able to run builtins and programs in the terminal using environment variables as well.

#
## 📓   - Implementation

#### 1)  User input <br />
&emsp;  The shell stays in a waiting mode, using the readline library, managing the terminal buffer and history.
   
#### 2)  Lexer / Tokenizing <br />
&emsp;  After receiving the input and making some basic checks, the input line is splitted into tokens, in the format of a binary tree, also known as Abstract syntax tree, in this way we can manage the diferent tokens based on their type in a generalized way.

#### 3)  Parser <br />
&emsp;  Once the tree is built with all the tokens, we iterate it to make all the necessary changes, such as removing unwanted and special characters, ex: spaces, tabs, quotes... And expanding the variables to their value.
  
#### 4)  Executor <br />
&emsp;  Now that the input is ready to be used, we can pump it into the executor, all the command line will be exeuted at the same time, builtins functions will be run in the main process, and binaries will be executed in child processes using execve and pipes. Once it's complete, all the unecessary memory is freed and user input is requested again.

Note: This project makes use of termios structure and signal handling to manage some of the behavior.


#
## ℹ️   - Usage

Compiles under macOS and linux, requires readline library

~~~git
git clone https://github.com/Rafael2sf/minishell.git minishell
~~~

#
## 🔨   - Build

~~~c
cd minishell; make
~~~
