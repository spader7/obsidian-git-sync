simple & fast multimedia Library
originally written for c++ but has been translated to c#

```console
dotnet new console -o MyFIrstGame
cd MyFirstGame
dotnet add package CSFML --version 2.5.0
dotnet add package SFML.Net --version 2.5.0
```
```c#
Clock frameClock = new Clock();
while (gameIsRunning)
{
	float deltaTime = frameClock.Restart().AsSeconds();
UpdateAllPositions(deltaTime);
RenderWorld():
}
```
using SF