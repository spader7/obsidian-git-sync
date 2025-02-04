#Programmering1 
- Inheritance should be used when the child class represents a more specific version of the thing represents by the parent.
- Ex. Vehicle => Car => Volvo

####Inheritance in code
```c#
class A
{
public int a
}
class B : A
{
	public int b
}
class C : B
// class B : A ärver från A
```
":" gör att ma ärver.

good class
```c#
class Entity
{
Sprite sprite = new sprite();
position = vector2f...
velocity = vector2f...
}
class Bulllet : entity
{
Entity entity = new Bullet();
entity.Position = new vector2f();
entity.Velocity = new vector2f();

Bullet bullet = new bullet();
bullet.position = new vector2f();
bullet.velocity = new vector2f();
}
```