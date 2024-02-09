# [Introduction MapReduce](https://www.youtube.com/watch?v=WtZ7pcRSkOA&ab_channel=MIT6.824%3ADistributedSystems)
[Article used](https://pdos.csail.mit.edu/6.824/papers/mapreduce.pdf)

So, MapReduce it's a confusing topic to talk about but with the litle to no kowledge that i have, i'll try to explain it the way i think it work's based on the course lectures.

## What's it?

At first, MapReduce it's a programming model that's focused on dealing with a large amount of data income, so it deals with processing and generating large data sets in a parallel and distributed way.
It has 2 main functions (in quotes):

-> Map Function/Process

It's responsible to take the key pair data input from the user side and generate intermediate key pair values (more generically) for example: (It's similar to sorting data)

It recieves the data of all Students and map them by name and make a relationship (Student, Name) for every ocurrence (but don't count them), after everything's done, it generate the output (intermediate key pair).

-> Reduce Function/Process

It takes the intermediate key pair values and sort them, calculating how many times the same pair ocurred, and also eliminating every pair that seems too small or irelevant along the process.


## How does it work?

Basically, TO DO
