This is a simple gameloop
```c#
while (gameIsRunning)
{
	UpdateAllPositions();
	RednerWorld();
}
```
(60fps = koden måste ta 17ms att gå igenom)

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