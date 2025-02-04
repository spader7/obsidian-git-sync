#Programmering1 
- Readonly
  - Value is set only once, when the instance is created.
		readonly variables are usually in ALL CAPS
		readonly evaluates during runtime, but only allows the value or instance to be set once.
		- can be static or non-static
- const 
  - value is set only once, when the program is compiled. it is a constant
		cont variables are usually in ALL CAPS 
```

### const
```c#
float const GRAVITY = 500.0f
velocite += new vector2f (0.0f 1.0f) * Gravty * deltatime
```
- const makes GRAVITY a constant and cant be changed during run-time.
### readonly
```c#
public readonly name = Console.Readline();


static class Sword
{
private readonly int damage;
public void woodSword
{
	damage = 10;
}
}
```
### Immutablity
- immutability: not possible to change.
- most bugs are the result of an object having a different state than the programmer expected. Imulate objects are less error-prone
  - Design classes to have as few midifiable states as possible.
  - split class into several to reduce number of states for each class
  - - use const and readonly as often as possible
	 ### BALL
  +radius : int {readOnly}
  +posiiton: vec2

immuteable member variables are arked wih {readOnly} in a class diagram