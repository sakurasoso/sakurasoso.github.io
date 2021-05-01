## Draw and Play Video Game

**Project description:** This is an IOS mobile game that can turn your creative maze drawn on paper into a real playable video game. Players can control the ball through the complicated wall by shaking the phone to get the treasure and win the game.

### 1. Toolkits

The game part of this project is implemented using Sprite Kit.
The gravity control of the game used the CoreMotion suite time in IOS.
The core part of performing image recognition is implemented using Opencv.


### 2.Game initialization
It is easy to add game objects and physical effects through the powerful Sprite Kit and Gameplay Kit.

A snippet of game to add a X mark object to game.
```swift
func addGoal(px:CGFloat, py:CGFloat ) {
    self.goal = SKSpriteNode(imageNamed: "Xmark_px")
    self.goal!.name = "Xmark"
    self.goal!.position = CGPoint(x: px, y: py)
    self.goal!.zPosition = -1
    self.goal!.physicsBody = SKPhysicsBody(texture: (self.goal?.texture)!, size:(self.goal?.texture)!.size())
    self.goal!.setScale(1)
    self.goal!.physicsBody?.isDynamic = false
    self.goal!.physicsBody?.allowsRotation = false
    self.goal!.physicsBody?.affectedByGravity = false
    self.goal!.physicsBody?.pinned = true
    self.goal!.physicsBody?.categoryBitMask = 0
    self.goal!.physicsBody?.fieldBitMask = 0
    self.goal!.physicsBody?.collisionBitMask = 0
    self.goal!.physicsBody?.contactTestBitMask = 1
    self.addChild(self.goal!)
}
```

### 3. Gravity control
By turning on the accelerometer of the iPhone, we can connect the game world with the real world.

```swift
if let data = self.motion.accelerometerData {
                self.accmx = data.acceleration.x
                self.accmy = data.acceleration.y
```

### 4. demo
\
<img src="images/dap_demo.gif?raw=true" alt="drawing" width="400"/>

### 5. Other Contributors
Kyle Rosenau 
Matthew Alonso
Vihn Nguyen

### 6. Special Thanks
Scott Fairbanks

For more details see [Our project](https://github.com/sakurasoso/Draw-and-Play-Video-Game?organization=sakurasoso&organization=sakurasoso).
