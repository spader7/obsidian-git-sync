#delegates
##Remember: coupling is bad - event reduce coupling

##event orientation.

- what is a event.
  - "once every 10 seconds..."
  - the ghost moves forward and turns 90 degrees....

##subscribing and unsubscribing to event handles.

- ##*event handler* keep track of subscribers.
- publisher and subscriber, independent from each other.
  - publisher sends the signal of an event.
  - subscriber reacts to a signal and makes an action.

### eventhandler
```c#
window.Keypressed += (s, e) =>
// window.Keypressed is an eventHandler<KeyEventArgs>
// (s, e) is an Action<object, Keypressed>
// += we can assign additional functions to the same delegate vairable (adds them together as a list).
```

- ##descripiton
	- window.Keypressed is a publisher;
	- += subscribes to the event
	- (s, e)
	- s: variable containing the "sender"
	- e: variable containing the argument
##encapsulation
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
##how it should look
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



###skräp
```c#
if ()
```