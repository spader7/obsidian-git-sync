This is a simple gameloop
```c#
while (gameIsRunning)
{
	UpdateAllPositions();
	RednerWorld();
}
```
(minst 60fps = koden måste ta 17ms att gå igenom)

delta time: △t = v ×△s
```c#
class Asteroid 
{
	public float Position;
	public float Speed;
}
public void Update(float deltaTime) 
{
	Position += Speed * deltaTime;
}
```
Delta time is used for when fps drops or is to high so taht the game loop takes different time. 

from 1D to 2D
```c#
class Asteroid 
{
	public float Positiony;
		public float Positionx;
	public float Speedx;
	public float Speedy;
	public void Update(float deltaTime) 
	{
		PositionX += SpeedX * deltaTime;  
		PositionY += SpeedY * deltaTime;  
	}
}
```

```c#
while (window.IsOpen) {
	window.DispatchEvents();
	window.Clear(newcolor(131, 197, 235));
	window.Draw(girl);
	window.Dispatch();
}
```
- window.clear:
  clears the screen and makes it ready to print a new screen image
- 