
#### Custom delegate
```C#
delegate Food MyRecipe(List<Ingredient> ingredients);
MyRecipe cook = Bake;
//
vs
Food cake = Bake(cakeIngredient);
//stores the result
```

```c#
Func<T, R>, Action<T>, Predicate<T>, etc
```
Delegates

### eventhandler
```c#
window.Keypressed += (s, e) =>
// window.Keypressed is an eventHandler<KeyEventArgs>
// (s, e) is an Action<object, Keypressed>
// += we can assign additional functions to the same delegate vairable (adds them together as a list).
```

- eventHandler<KeyEventArgs> is a publisher.
	+= subscribes to the event
	- (s, e)
	- s: variable containing the "sender"
	- e: variable containing the argument