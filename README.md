# Matlab Tutorial
A showcase of the most useful features of Matlab, for first-year university students

**Things to cover:**
- Tour of important things in Matlab GUI 
- Assigning variables, creating arrays, simple math operations, and vector math
   - linspace, colon operator, []
- Writing functions
- Loops / conditionals
- Plotting

# 📈Look At This Graph!📉

1. Make a new *script* by clicking on the "New Script" button
![Script Button](./images/new_script_button.png)
2. Type these commands into the blank document:
```octave
t = linspace(0,4*pi,1000);
s = sin(t);
plot(t,s);
```
3. Press the big green **Run** button ![Run Button](./images/run_button.png)
    * Name this new file and save it somewhere you won't forget ![Save](./images/save_as.png)
    * Click on "Change Folder" if this window comes up ![Change Folder](./images/change_folder.png)
4. Look at your cool graph!

Matlab lets you make mathematical graphs really easily.
Matlab also helps you do your homework! Let's see how...


# Balance a Chemical Reaction

# Launch a Projectile

# Write Your English Essay

# Write a Function
There are a few different ways to create functions in Matlab. The most common way is to create a new file, starting with the **function** keyword. Note that the name of the file must match the name of the function. Eg. for the function below, I'd make a file called *hello.m.* Also, make sure that the file is saved in your working directory.

```octave
function hello(name)
    fprintf('Hello, %s\n', name) 
end
```
other things we can do:
   - make the function RETURN the greeting, instead of printing it
   - add other greeting options, besides hello
      - could add a second input argument, use if/else, or switch/case statements
   - ensure that the 'name' input is actually a string
