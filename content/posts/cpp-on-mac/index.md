---
title: "Setup C++ dev on Mac"
date: 2024-09-17T11:18:17+02:00
draft: false
description: "A guide to setting up a C++ development environment on macOS, including installing the necessary tools and configuring your system to compile and run C++ code."
summary: ""
categories: ["coding", "development", "tutorial"]
tags: ["cpp", "macos", "development", "setup", "c++"]
showAuthor: true
---

I wrote this guide to explain to my fellow TPS students how to set up a C++ development environment on macOS because teachers won't teach us how to do it.

{{< alert icon="heart" cardColor="#eb9486" iconColor="#f1faee" textColor="#f1faee" >}}
Hope this helps my friends from TPS. If you have any questions, feel free to ask me IRL.
{{< /alert >}}

## Too long didn't read

If you don't want to take the time to understand the whole process, just copy paste the following commands in your terminal:

```bash
xcode-select --install # Install Xcode Command Line Tools
clang --version # Verify installation
cat <<\EOF > hello.cpp # Create a new C++ file
#include <iostream>
int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
EOF
g++ hello.cpp -o hello # Compile the C++ file
./hello # Run the compiled file
```

---

## What you'll need

### Terminal

On Mac, you can use your default terminal to compile and run C++ code. However, it is common to switch to a more advanced terminal like iTerm2, which offers more features and customization options.

So this is optional but recommended to switch to [iTerm2](https://iterm2.com/) if you want to have a better experience.

### Compiler

To run C++ code, you need to **"translate"** it into a format that your computer can _understand_. This is done by a **compiler**. On macOS, the default compiler is Clang, which is part of the Xcode Command Line Tools.

> "What is Clang?"

you may ask.

Clang is a compiler front end for the **C, C++, and Objective-C programming languages**. You can install it by running the following command in your terminal:

```bash
xcode-select --install
```

After the installation is complete, you can verify that Clang is installed by running:

```bash
clang --version
```

{{< alert icon="lightbulb" cardColor="#edae49" iconColor="#f1faee" textColor="#f1faee" >}}
It is a common practice to type `<command> --version` to verify that a tool is installed and working correctly.
{{< /alert >}}

From now on, you can use Clang / G++ to compile and run C++ code on your Mac.

> Not sure if G++ is installed? You know what to run to check it out!

### Code editor

If you don't feel confident about coding in general and you're not sure which code editor to use, I recommend starting with **[Visual Studio Code](https://code.visualstudio.com/download)**. It is a free and open-source code editor that a **lot** of developers use.

But if you're cool, try this (not recommended for beginners) :

{{< article link="blog/posts/nvchad/" >}}

When you use VSC for the first time with a new language, you often look for extensions to help you write code more efficiently. Extensions will get your code highlighted, auto-completed, and more. Unfortunately, as I'm not a pro C++ dev with 10 years of experience, I won't be able to recommend you some extensions to use because I just don't em. But check out by yourself on the _net_ or in the _VSC marketplace_ (you can access it with `Ctrl+Shift+X` when inside VSC).

## Writing your first C++ program

Now that you have all the tools you need, I'll guide you through ALL the steps to a better understanding of how to write, compile, and run a C++ program.
So STEP-0: open your terminal and let's get started.

### Create a new C++ file

Naviguate to the directory where you want to create your C++ file using `cd` and `ls` commands. What I recommend you is to create a new directory for your C++ projects. You can do this with the following command:

```bash
cd ~/Documents/ # Go to your Documents directory
mkdir cpp-projects # Create a new directory named cpp-projects
cd cpp-projects # Go to the cpp-projects directory
```

Then, create a new file named `hello.cpp` with the following command:

```bash
touch hello.cpp
```

`touch` is a command that creates a new **empty** file. So if you type `ls` in your terminal, you should see the `hello.cpp` file.

### Edit the file

On a computer, you can edit a file by using a text editor. You can use the default text editor on your Mac, but in our case we installed a very specific code-oriented text editor earlier : **Visual Studio Code**.

You can open VSC by starting the application from the Applications folder of your Mac and try to figure out what the hell is going on and why you can't find your file or you can just type the following command in your terminal:

```bash
code . # Will open VSC in the current directory
# or
code hello.cpp # Will open the file hello.cpp in VSC
```

{{< alert icon="lightbulb" cardColor="#edae49" iconColor="#f1faee" textColor="#f1faee" >}}
If your terminal is complaining about the `code` command not being found, try following this [guide](https://code.visualstudio.com/docs/setup/mac) to add the `code` command to your $PATH. (don't worry, it's not that hard)
{{< /alert >}}

Now, you should see the VSC window with the `hello.cpp` file opened. You can start writing your C++ code in this file.

### Write the code

Copy and paste the following code into the `hello.cpp` file:

```cpp
#include <iostream>
int main() {
    std::cout << "Hello TPS!" << std::endl;
    return 0;
}
```

This code is a simple C++ program that prints "Hello TPS!" to the console. You can customize it by changing the text inside the `std::cout` statement.

### Compile the file

You have many ways of compiling your C++ code. The most common way is to use the `g++` command, which is a **GNU Compiler Collection** that includes compilers for C, C++, and other languages.

> At TPS, professors often use `CMakeLists.txt` files to compile C++ projects. But for this guide, we'll stick to the basics. If you want to learn more about CMake, MakeFiles and other compilation tools, give me feedback and I'll write a new guide on this topic.

To compile the `hello.cpp` file, run the following command in your terminal:

```bash
g++ hello.cpp -o hello
```

This command tells the `g++` compiler to compile the `hello.cpp` file and output the compiled program to a file named `hello`. The `-o` flag specifies the output file name.

If there are no errors in your code, the compilation process should complete successfully, and you should see a new file named `hello` in your directory when you using the `ls` command.

### Run the compiled file

To run the compiled `hello` program, use the following command in your terminal:

```bash
./hello
```

This command executes the compiled program, and you should see the output "Hello TPS!" printed to the console.

### Conclusion

Congrats. You are ready to start coding non-sens stuff in C++ on your Mac. If you have any questions or need help with anything, feel free to ask, I'll be happy to help you.

![honest-work](img/honest-work.jpg)

PS: shout out to my Windows friends, just use WSL and you'll be fine.
