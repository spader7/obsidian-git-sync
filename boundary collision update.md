
```C#
public void Update(float deltaTime)
{
	Vector2f newPosition = shape.Position + velocity
	if (newPosition.Y + shape.Origin.Y > 600)
	{
		velocity = new Vector2f(velocity.X -velocity.Y)		
	}
	else if (newPosition.X - shape.Origin.X < 0 ||
			 newPosition.X + sape.Origin.X > 800)
	{
		velocity  = new Vector2f(-velocity.X, velocity.Y);
	}
	else
	{
		shape.Position = newPosition;
	}
}
```

- velocity = new Vector2f(velocity.x, -velocity.y)
	reverses the direction of the ball, makes it bounce of the wall.