#föreläsningar
```c#
bool keyPressed += (s, e) =>
{
	if (e,Code == Keyboard.key.space)
	{
		keyPressed = true;
	}
}
```

```c#
window.ketReleased += (s, e) =>
{
	if (e,Code == Keyboard.key.space)
	{
		keyPressed = false;
	}
}
```