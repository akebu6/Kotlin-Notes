# Singleton
- is a creational design pattern that allows you to keep only one instance of an object and provide global access to it.
- What does it mean and why you might have to use it? Well, it solves two problems:

**a.** Keeping only one instance of an object is useful when you want to control access to some shared resources. When you create one object of a class, if you use singleton pattern, you will always have that same object. In case you'll try to create another one, the code will return the first initiated object each time.

**b.** Providing global access point to allow all clients to use the initiated instances. When you address this problem, you also should squeeze all the code regarding the first problem in one class, to avoid it being scattered all over your code.

<img src="https://ucarecdn.com/fbe8dd71-892f-43c2-9471-d689d90cf806/" width="500px" height="300px" />
