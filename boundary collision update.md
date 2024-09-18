
```C#
public void Update(float deltaTime)
{
	Vector2f newPosition = shape.Position + velocity
	if (newPosition.Y + shape.Origin.Y > 600)
}
```

- velocity = new Vector2f(velocity.x, -velocity.y)
	reverses the direction of the ball, makes it bounce of the wall.