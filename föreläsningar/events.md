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





###skräp
```c#
if ()
```