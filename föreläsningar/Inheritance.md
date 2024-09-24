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