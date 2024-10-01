
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

