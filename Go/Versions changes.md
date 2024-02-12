# [V - 1.22](https://www.youtube.com/watch?v=HXdBwGRjv_4)

## For loop
Here we have a change that basically changes how for loops variables are scoped.

Before, we had a problem that every loop interation (that had a concurrent func running) would have the same instance of the for loop scope variable:
![image](https://github.com/JoaoGumiero/Study-Notes/assets/132496314/e314dcb6-f814-427d-9835-3c383bea70c3)
So, in simple words, the loop scope variables would finish early than the concurrent method, causing the problem.
![image](https://github.com/JoaoGumiero/Study-Notes/assets/132496314/027fde93-8288-4d7b-be21-87ccfeb0837d)
So, here the value of X it's setted to be the last value of the slice by the time the for loop runs. Resulting in the number 5 been printed 5 times.

Another example would be this code:
![image](https://github.com/JoaoGumiero/Study-Notes/assets/132496314/1f731f87-ec08-4a4b-839d-3e784ef29a30)
Here we have a for loop that will iterate from 0 to 9, each time it will append the memory address of the scope variable in the slice.

If we make a iteration to printout every content of the slice we'll notice that each time the value stored is the same. 10
![image](https://github.com/JoaoGumiero/Study-Notes/assets/132496314/2b015971-712f-4d01-a68d-cb74a9a6d3f7)

Afterwards, if you remove the pointer "*" from the *id you can see that each value points to the same space in memory.
![image](https://github.com/JoaoGumiero/Study-Notes/assets/132496314/272a9b86-743a-4d53-b5e7-1f8dd89d813c)

In general, this problem mainly occur in go because of cocurrent closures inside for loops.
![image](https://github.com/JoaoGumiero/Study-Notes/assets/132496314/bdba47e4-4d67-4a36-981c-5dd4bee316fe)

Before, this problem would be resolved if you passed the actual value of the for loop iteration variable as a parameter to the concurrent function within the iteration.
And passing our looping variablea when we envoque it.
![image](https://github.com/JoaoGumiero/Study-Notes/assets/132496314/9c2b83a6-994f-4de1-80cd-5f6bdc908b4c)

Or you could atribute the value to a local variables instead.
![image](https://github.com/JoaoGumiero/Study-Notes/assets/132496314/7384f4fb-5eb0-4bcd-8d34-8a11531faabc)

## std net/http package
Now they've added a specified routing mechanism to the mux router, it's easy to specify routes based on methods or path parameters.
![image](https://github.com/JoaoGumiero/Study-Notes/assets/132496314/6383468b-c48c-4d6b-a621-8e3070164f0a)

### What's good about this change?
Basically, now the std router can be used to make more advanced routing based on methods or path parameters, so now we don't need to import external packages/libs to do that work for us (chi, gorilla, fiber, and so on).

That's good because the less dependencies our code have with external code, the better, we don't leave breaches for data leakes and stuff.


## CPU and Memory Performance Improvement



