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
First, we'll use the equations of projectile motion to plot the path.
Then, we'll pretend we don't know those equations, and we'll make Matlab do the thinking!

## Equations of Projectile Motion

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

## Make Matlab do the Thinking

This method starts out like the first method:
```octave
vel = 20;
theta = 60*(pi/180);

g = 9.81;

t = linspace(0,5,1000);
```

We'll start with the exact equations for velocity, then we'll let Matlab calculate position.

```octave
vx = vel * cos(theta);
vy = vel * sin(theta) - g * t;
```

Then, we'll use a ➿*loop*➿ to calculate the `x` and `y` components of position!
To do that, we'll need to figure out the time-step between points in `t`.

```octave
time_step = (t(end)-t(1))/(length(t)-1);

x = zeros(size(vx));
y = zeros(size(vy));

for ii = 1:(length(vx)-1)
    x(ii+1) = x(ii) + time_step * vx(ii);
    y(ii+1) = y(ii) + time_step * vy(ii);
end

plot(x,y);
```

Try writing these three blocks of code in a single script, then run the script. Do you get the right shape?

# Balance a Chemical Reaction


# Write Your English Essay

😩 Nope

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

# Draw a Picture
In this example, we'll learn more about plotting, and indexing matrices and vectors

Let's start out with a 100x100 matrix of zeros:
```octave
picture = zeros(100); % this is equivalent to: picture = zeros(100,100);
```
This will look like an all black image:
```octave
figure; subplot(1,3,1)
imshow(picture)
title('A blank picture :(')
```
I'll use a for loop to add horizontal stripes, and then vertical stripes.
```octave
for ii = 1:10:100
    picture(ii, :) = 1;
end
subplot(1,3,2)
imshow(picture)

for jj = 1:10:100
    picture(:, jj) = 1;
end
subplot(1,3,3)
imshow(picture)

sgtitle('Masterpiece')
```

![My Picture](./images/picture.png)
