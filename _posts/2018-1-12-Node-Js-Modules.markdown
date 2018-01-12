---
layout: post
title: Node.js Modules
date: 2018-1-12 07:38:40 +0530
description: This post discusses the basics of node js modules and several other node.js fundamental concepts.
img: post-2.png # Add image post (optional)
tags: [Javascript, Node.js, Modules, Basics, Fundamentals]
author: Himanshu Kumar # Add name author (optional)
---

# Modules
In Layman terms we can state that any Javascript may be considered as a Module. There are three types of modules present in Node.js.These are namely,
1. File Modules
2. Core-Modules
3. Node-Modules
Now let us discus one by one all of this
Following are the salient featuers of module based systems:
1. Each file is its own module
2. Each file has access to current module defineition using module varaible.
3. To export a module, use module.export keyword.
4. To import a module, use module.import Keyword.

## File Modules
This are simple javascript files that a user can write and include in other files. The most common way to include these files is through
'require('./path/you/want/to/include')'.
Some main features of Node.js Modules is that,
1. Its is *safe*, as whenever we import it, we basically store it in a variable, thus it saves us from the collisions that may arise due to import of modules that have same name functions, as can be seen from popular languages, C++, PHP. Though they have come over this issue by using keywords `namespaces`.
2. We can *conditionally* load a module.
3. *Blocking* : It simply means that whenever we are importing some modules, then the remaining functions defined below must wait. They are, in a sense, blocked from being executed until the requre functions terminates.
4. *Cached* : It simply means that the subsequent `require('/path')` does not take much time as whenver a new modules is imported, it is simultaneously cached. Thus making it fast.
5. *Shared State* : Simply means that the modules can access variable. As we know that module implicitly works by returning objects. So, whenver you import it to another functions and change its value from other functions, it would definitley get changed. Some, may see this as a problem, some as a feature. But I consider this as a feature. We can get aroound its problem by incubating the variables inside functions while exporting them.
6. There are several ways to export modules,
    a. `module.exports.function_name`
    b. `exports.function_name`

## Modules Best Practices
1. Never specify the extension in the path.
2. Always remember to use relative paths.
3. Use exports alias when you want to import more than one thing.
4. Never include huge codeblocks of require functions, rather make a new file and import them all to that file and include it in your main js file.

## Important Globals
1. `Console` : Can be used for debugging purposes.
2. `Timers` : setTimeout and setInterval can be used for execute the callback as required. To clear this timer, we can use clearTimeout/clearInterval.
3. `__filename` : Can be used to specify the file name of the currently executing file.
4. `__dirname` : Can be used to indentify the directory of the currently executing js file.
5. `process` : *To be duscussed later*
6. Command Line : The command line can be used to access the command line arguments. The command line arguments can be accessed from process.argv. The first argument is the node. the sesond is file path, then comes all those arguments specified with the command line.
7. `Process.nextTick` : it take the callback function and places it in the next cycle of the node.js event loop.
8. `Buffer` : *To be clarified*
9. `global` Keyword : This when used can give the variable a global scope. Usage expmple. `global.somehting = 123`. Not encouraged.

Let us discuss *`Core Modules`* in the next blog.