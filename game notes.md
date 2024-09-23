important for a game to feel responsive

### Immutablity
- immutability: not possible to change.
- most bugs are the result of an object having a different state than the programmer expected. Imulate objects are less error-prone
  - Design classes to have as few midifiable states as possible.
  - split class into several to reduce number of states for each class
  - - use const and readonly as often as possible
	 ### BALL
  +radius : int {readOnly}
  +posiiton: vec2

immuteable member variables are arked wih {readOnly} in a class diagram