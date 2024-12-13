#föreläsningar
#delegates
## Remember: coupling is bad - event reduce coupling

## event orientation.

- what is a event.
  - "once every 10 seconds..."
  - the ghost moves forward and turns 90 degrees....

## subscribing and unsubscribing to event handles.
```C# 
+= //for subscribing
+= //for unsubscribing
```

- ## *event handler* keep track of subscribers.
- publisher and subscriber, independent from each other.
  - publisher sends the signal of an event.
  - subscriber reacts to a signal and makes an action.
  - it shouldn't matter in which order a subscriber uses the publishers event.

### eventhandler.
```c#
window.Keypressed += (s, e) =>
// window.Keypressed is an eventHandler<KeyEventArgs>
// (s, e) is an Action<object, Keypressed>
// += we can assign additional functions to the same delegate vairable (adds them together as a list).
```

- ## description.
	- window.Keypressed is a publisher;
	- += subscribes to the event
	- (s, e)
	- s: variable containing the "sender"
	- e: variable containing the argument
## encapsulation
- shouldn't invoke events outside of the publishers class
```C#
class Door
{
	public event OpenHandler OpenEvent;
}

class Key
{
	public void Update() {
	door.OpenEvent?.Invoke();
	}
}
```
- Keyword: event
#delegates
  - prevents invoking a delegate from outside the publisher
  - similar to readonly, but for delegates
## how it should look
```C#
class Door {
	public Door(key key) {
	key.Keypickup += OpenDoor;
	}
}
class Key {
	public event KeyPickupHandler KeyPickup;
	...
	public void Update(){
		if (CollidedWith<Player>()) KeyPickup?.Invoke();
	}
}
```
- Publisher is the owner of the event.
  - example. key is the owner of keypickup. door subscribes to keypickup
# scheduled events
- triggered when a certain amount of time has passed.
- can either fire once or as a part of a regular interval.
- simple solution: Entity without any Sprite.
```C#
public event Action<Game> Action;
oublic float Frequency {get; set;}
private float timeLeft;

...if ((timeLeft -= deltaTime) > 0) return;
	Action?.Invoke(game);
	timeLeft += Frequency;
	//fire at regular intevral
```


###skräp
```c#
if ()
```