# Skrrripted

Skrrripted is a rocket league TAS tool. It allows you to apply frame-perfect inputs to multiple cars at one time and manipulate the physics data of each car and the ball.

# Installation

**Before proceeding, ensure you have the RLBotGUI installed, downloadable from [https://rlbot.org/](https://rlbot.org)**

Clone or download this repository, and copy its root folder to `AppData/Local/RLBotGUI/MyBots`.

# Getting Started

With the app installed, open the RLBotGUI and you should see "Skrrripted" as an available bot. Add the number of bots you need to any team and start the game.

Once you've started a game with a Skrrripted bot for the first time, the app should create the `~/Documents/Skrrripted/script.json` file. This file is what you need to edit to write your scripts.

Once you've finished editing a script, you can pause and unpause the game to reload the script file.

# Customizing Your Script

The layout of a script should look like this:

```json
{
   "ball": [
      "<instruction>",
      "<instruction>",
      "<instruction>",
      "<instruction>"
   ],
   "drones": [
      [
         "<instruction>",
         "<instruction>"
      ],
      [
         "<instruction>",
         "<instruction>",
         "<instruction>"
      ],
      [
         "<instruction>",
         "<instruction>",
         "<instruction>",
         "<instruction>",
         "<instruction>"
      ]
   ]
}
```

As you can see, scripts are mostly made up of instructions. In this template, the ball is given 4 instructions. There are 3 drones (cars), one with 2 instructions, one with 3 instructions, and one with 5 instructions. When adding bots to the game, the app will assign each bot an instruction set from the `drones` array.

Instructions follow a custom syntax largely based on the way Minecraft commands are structured. Most instructions use ticks, a unit of time equal to 1/60th of a second. If an instruction has a `duration` argument, it should control the duration in ticks that the instruction should be active.

A list of all instructions and  their arguments:

### `wait <duration>`

`wait` delays the start time of all instructions after it.

### `boost <duration>`

`boost` activates the car's boost.

### `handbrake <duration>`

`boost` activates the car's handbrake.

### `jump <duration>`

`jump` activates the car's jump.

### `roll <direction> <intensity> <duration>`

`roll` controls the car's air roll (roll). `direction` can either be `left` or `right`. `intensity` controls how sharply the car should roll.

### `spin <direction> <intensity> <duration>`

`spin` controls the car's air spin (yaw). `direction` can either be `left` or `right`. `intensity` controls how sharply the car should spin.

### `steer <direction> <intensity> <duration>`

`steer` controls the car's on-ground steering. `direction` can either be `left` or `right`. `intensity` controls how sharply the car should turn.

### `throttle <direction> <intensity> <duration>`

`throttle` controls the car's on-ground throttle. `direction` can either be `forwards` or `backwards`. `intensity` controls how much throttle should be applied.

### `tilt <direction> <intensity> <duration>`

`tilt` controls the car's air tilt (pitch). `direction` can either be `forwards` or `backwards`. `intensity` controls how sharply the car should tilt.

### `position <x> <y> <z>`

`position` sets the car's position. `x` controls the position on the X axis. `y` controls the position on the Y axis. `z` controls the position on the Z axis.

### `rotation <roll> <pitch> <yaw>`

`position` sets the car's rotation. `roll` controls the rotation along the X axis. `pitch` controls the rotation along the Y axis. `yaw` controls the rotation along the Z axis.

### `velocity <x> <y> <z>`

`position` sets the car's velocity. `x` controls the velocity on the X axis. `y` controls the controls the velocity on the Y axis. `z` controls the controls the velocity on the Z axis.

### `angular-velocity <roll> <pitch> <yaw>`

`angular-velocity` sets the car's angular velocity. `roll` controls the speed of rotation along the X axis. `y` controls the speed of rotation along the Y axis. `z` controls the speed of rotation along the Z axis.

# Known Issues

When starting from the kickoff, the script output will not always be consistent. To fix this, simply pause and unpause the game after the clock starts counting up or down again.
