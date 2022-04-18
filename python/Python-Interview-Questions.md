## Python-Interview-Questions



## Question 1 :

I am not sure if my answer is adapted, but from what I understand : scripting refers to the automation of tasks that could be manually done one by one, by a program written in an interpreted (rather than compiled) programming language. Coding is a more general term, but I assume that you means what is not scripting in Python : it is writing Python modules, i.e block of codes that can be reused in Python scripts or in other Python modules.

For example, the following hello_world.py is a script:

```
#!/usr/bin/python 
print(“Hello world !”) 
```

Under Unix environment, you can execute this script : the first line calls the python engine, then all other instructions are executed by the python engine.

The following example Hello_world.py can be used in other scripts or other modules (even if I doubt of any use of this), but will not execute anything by itself:

```
class Hello_world: 
   def __init__(self): 
      self.hello_world = "Hello_world !" 
   def run(self): 
      print(self.hello_world) 
```