# OOP 4 Pillars
## Abstraction
Abstraction is the concept of hiding the complex bits of a process behind a simple interaction. A user on a site knows they need to click a button to submit a form, but they don't need to know about onClick function or the POST request that happens when that button is clicked. Abstraction means a user never has to think about what's behind the scenes.
A non-coding example would be the keys on a piano. The only thing a pianist needs to understand is: I hit a key and a sound is produced. The piano key is an abstraction of the hammer that strikes a string inside the body of the piano as the damper on the string is released.

## Encapsulation
Encapsulation is the principle of wrapping attributes and methods of a particular object within a single class, not only to keep them together, but also to keep them secure. Say you have a user with a bank account saved on your site. You wouldn't want that user's balance to be exposed and vulnerable to be changed. You want the user to go through the proper channels to change their account balance. So while the balance itself is a private, secure attribute, you may have a depositAmount() method within that class. The user can call that method to change the balance.
For a real-world anaolgy, think of a car. The car is the encapsulation of "methods" like acceleration, cruise control, braking, and turning. Meanwhile the steering wheel, gas pedal, brake pedal, and cruise control button are all forms of abstraction that are encapsulated within the car.

```csharp
public class User
{
  public string username;
  private int accountNumber;
  private int accountBalance;
  
  public User (string username, int accountNumber)
  {
    this.username = username;
    this.accountNumber = accountNumber;
    this.accountBalance = 0;
  }
  
  public void withdrawDeposit(int amountToDeposit)
  {
    this.accountBalance = this.accountBalance + amountToDeposit;
  }
}
```

## Inheritance
Inheritance is the concept of creating a new class that uses attributes and methods from an existing class. Using another music analogy, let's take the concept of sound and turn it into a coding example. Say we have a class named Sound, and within this class we have qualities like volume, frequency, and vibrato. We could then create an Instrument class which inherits all the attributes and methods from Sound and then construct some attributes and methods within Instrument that would be unique to it. So in Instrument we could have name, classification (string, brass, woodwind, electric, etc), and yearCreated. Now our Instrument class contains its own unique properties as well as all those it inhereited from the Sound class.
Another example would be with shapes. All shapes have a height and width, but different shapes handle measurements like area differently. So if we create a base Shape class, we can inherit its properties when we create new shapes like below.

```csharp
public class Shape
{
  public int height;
  public int width;
  
  public Shape (int height, int width)
  {
    this.height = height;
    this.width = width;
  }
}

public class Rectangle:Shape
{
  public int Area()
  {
    return height*width;
  }
}
```

## Polymorphism
Polymorphism is the principle of one thing taking many forms. One of the simplest ways to understand this would be with shapes. Let's take a class called RightTriangle and a class called Rectangle. Both of these classes will have properties for height and width as well as a method that calculates their area().So these two classes have the exact same names for their properties and methods, however the area() method returns something different depending on the class it's in. The area of a right triangle is (base * height) / 2 but the area of a rectangle is simple (width * height). So this is an example of how the method area() can take on multiple forms based on what it is encapsulated within.

```csharp
public class Shape
{
  public int height;
  public int width;
  
  public Shape (int height, int width)
  {
    this.height = height;
    this.width = width;
  }
}

public class Rectangle:Shape
{
  public int Area()
  {
    return height*width;
  }
}

public class RightTriangle:Shape
{
  public int Area()
  {
    return (height*width)/2;
  }
}
```
