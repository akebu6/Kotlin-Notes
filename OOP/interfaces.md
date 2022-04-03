# Basics
- An interface is a collection of methods that describes the behavior of an object.
- To implement the interface, an object should implement all the methods from it.
- The behavior of an object is stiff, and it cannot change during the execution of a program.
- With the interface implementation, you can be sure that an object can do the job it accepts
- You can also choose which object will do the work because they can do it a bit differently.

### One-method interface
- One method stands for only one skill of an object, but in many situations, this is enough to make an interface effective.


### Complex interface
<img src="https://ucarecdn.com/c6bf67dc-e609-40d3-8d5b-eb82b5b1a163/" width=400px height=400px />
- There is no preferential difference between one-method and complex interfaces, but if you go with complex, the question is: how big can they get?


### Responsibility of an interface
- We want our objects to communicate through simple interfaces even when they have a lot of methods
- All of these methods should be necessary to do the job right. 
- If there is no need for some methods, we can move them to a new interface, or even remove them completely. 
- For example, we can add to our AUDIOPLAYER a method REWIND, but there is no need to have a method RECORD there because it is not related to playing music.
