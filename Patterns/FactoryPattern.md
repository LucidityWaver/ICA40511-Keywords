###Factory Method Pattern

Links to other explanations:
* https://github.com/iluwatar/java-design-patterns/blob/master/factory-method/index.md
* http://www.oodesign.com/factory-method-pattern.html

When to use this pattern:
http://stackoverflow.com/questions/14575457/factory-classes

Simplified, the factory method design pattern allows subclasses to decide on implementation details rather than the superclass. One advantage is that this allows the code to refer to a single superclass instead of each specific subclass. Another advantage is that another developer (a client) using your code does not write code to instantiate the class, making it more robust.

This pattern can also be used for implementation rather than inheritance.
That simplification is not quite correct, but it's a good starting point.

An example of this would be an abstract Bag class. Different bags have different properties but we largely use them the same. We know each bag will have a type and a capacity, so the Bag class might contain getType() and getCapacity() methods.

We could create an abstract class Bag, with abstract methods as below:
```
public abstract class Bag {
	public abstract String getType();
	public abstract double getCapacity();
}
```
We can then define the carry weights using the subclasses:
```
public class Backpack extends Bag {
	
	@Override
	protected String getType() {
		return "Backpack";
	}
	@Override
	protected String getCapacity() {
		return 10; //Kilograms (kg)
	}
}
```
Normally, we instantiate (create) objects like this:
```
public void main(String[] args) {
	Backpack b = new Backpack();
	b.getType();
}
```
But then we would have to do the same for every type of bag, which could require remembering the names and implementations of many different classes (e.g. satchels, suitcases, purses and clutch bags).

Instead, we can create a factory class to handle instantiation of Bag objects.
```
public class getBagFactory {
	private getBagFactory() { 	} //Cannot create a getBagFactory object
	
	public static Bag getBag(String bagType) {
		if (bagType == null) {
			return null
		}
		if(bagType.equalsIgnoreCase("BACKPACK")) {  
			return new Backpack();  
		}   
		else if(bagType.equalsIgnoreCase("SATCHEL")){  
			return new Satchel();  
		}   
		else if(bagType.equalsIgnoreCase("PURSE")) {  
			return new Purse();  
		}
		return null; //If not equal to one of the above.
	}
}
```

We can also put more complicated logic inside the factory class and the factory method might return a different object based on the arguments provided. If the developer or client were only specifying the weight capacity of the bag, we could give them a new bag based on these values:
```
public class getBagFactory {
	private getBagFactory() { 	} //Cannot create a getBagFactory object
	
	public static Bag getBag(double weightCapacity) {
		if (weightCapacity == null) {
			return null
		}
		if (weightCapacity > 0 && weightCapacity <= 5.50) {
			return new Purse();
		} else if(weightCapacity > 5.50 && weightCapacity <= 10.00) {
			return new Satchel();
		} else if(weightCapacity > 10.00 && weightCapacity <= 20.00) {  
			return new Backpack();
		}
		return null; //If not within range of one of the above.
	}
}
```

By doing this, we never need to call new Backpack(), new Purse(), etc, and the client doesn't need to know the exact implementation of the subclasses.
Instead, the client calls the getBag() method on the public getBagFactory class:
```
public void main(String[] args) {
	Bag aBackpack = getBagFactory.getBag(17.50);
	System.out.println(aBackpack.getType()); //Prints 'Backpack'
	Bag aPurse = getBagFactory.getBag(3.75);
	System.out.println(aPurse.getType()); //Prints 'Purse'
}
```
A more accurate description of the factory design pattern:
Used to define an interface for creating an object, but lets subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses based on input.

Use the Factory Method pattern when
-	The class of objects a class will make are not known to the class.
-	The subclasses should specify the objects that the must be made.
-	classes delegate responsibility to one of several helper subclasses, and you want to localize the knowledge of which helper subclass is the delegate

The factory method design pattern promotes loose-coupling.
External code only interacts with an abstract class or interface, so it will work with any classes that implement the interface or extend the abstract class.
