# Matlab Tutorial
A showcase of the most useful features of Matlab, for first-year university students

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

# Launch a Projectile

Let's launch a cannonball!
Say the cannonball is shot like this:

* At an angle of `theta` degrees
* At a velocity of `vel` metres per second

Let's ignore air resistance is this case.
High-school physics tells us:

1. The x-component of the ball's velocity stays constant
2. The y-component of the ball's velocity decreases linearly, so the y-component of its position is a quadratic

We're going to plot the path of the ball as it flies through the ~air~ airless void.
To do this, we're going to need the equations for `x(t)` and `y(t)`.

* `x(t) = vel * cos(theta) * t`
* `y(t) = -g/2 * t^2 + vel * sin(theta) * t`

Now we can copy the code from above where we plotted a sine function, and tweak it.

```octave
vel = 20;
theta = 60*(pi/180);

g = 9.81;

t = linspace(0,5,1000);

x = vel * cos(theta) * t;
y = -g/2 * t.^2 + vel * sin(theta) * t;

plot(x,y);
```


# Balance a Chemical Reaction


# Write Your English Essay

# Write a Function
