The application is a simulation of a toy robot moving on a 5 x 5 unit tabletop. It is an example of a well tested, object-oriented design, employing the command design pattern. It is commonly used as a code-test. See specifications below for the full text of the test.

Environment

This application was developed on Ubuntu 16.10 x86_64. It requires Ruby 2.3 or later.

Installation

$ npm install

Testing

Made heavy use of Wallaby.js for TDD when building the Robot class
The test suite is invoked with:
$npm test

Valid commands are:

Command	Description
place X Coordinate, Y Coordinate, Direction Facing 	Places robot at position x, y, facing cardinal direction d. E.g. place 1,2,north.
Rotate left	Rotates robot 90° counter-clockwise.
Rotate right	Rotates robot 90° clockwise.
move	Advances the robot one position in the direction it is currently facing.
report	Prints the current location.
Remove Move out the Robot from the Table.
Commands resulting in the robot moving to an out-of-bounds position (x or y is less than 0 or greater than 4) will be ignored.

Design

The app implements:

The command pattern: Given the requirement for a command line interface to interact with the robot, I settled on the well established and widely used command pattern.
The null-object pattern (for positions)
The singleton pattern (for directions)

Opted to use JS class methods for PLACE, MOVE, LEFT, and RIGHT instead of reading from standard input.
Webpack and Webpack Dev Server was used to build the GUI w/ hot reloading
Made a neat little console.log hijack to show logging in the GUI
I added a render function parameter to be called every time a movement operation runs

API
.place(x, y, facing)
Place the robot at x and y, with a facing direction.

.remove()
Remove the robot from the table.

.move()
Move the robot 1 unit in the direction it's facing.

.left()
Rotate the robot to the left to face a new direction.

.right()
Rotate the robot to the right to face a new direction.

## GUI to control robot

```
$ npm install
$ npm start
```
Open <http://localhost:8080/>.
