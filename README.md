# Teaching-Locations-Palletization
In this exercise we pick up objects from a pallet and put them into another place one up to another.
First we define the variables which are necessary to perform the task, the thickness of the objects and the
gap between two objects. Then we load the suitable tool for this exercise.
Then we define the object frame. In order to do that before programming, we teach locations to the robot.
We use special end-effector for that and guide the robot motion with the teach pendant. We define the
origin as the origin of the frame, xaxis is a point for the X direction, xypoint is to define the Y axis. During
recording the xypoint we make sure that it is as far as from the X as possible to get better result.

in the program we use the points differently because if we put these locations into the frame
command the Z axis is defined outwards. So to correct this we put xaxis as the origin, the origin is the X
direction and xypoint is the Y direction.
To define the frame this way it is a good methodology because if we have too much locations to record it
is enough to define the object frame and not all of the object location which could be really time
consuming.
If the frame is defined properly the transformation matrix is a pure translation as follows which is really
easy to represent in the programming language.
After defining the frame, the only thing is to make a loop to pick the object and place it to the dropf
location which is also recorded previously. The first loop is for the rows while the second loop is the
columns. In each iteration the recorded grasppos is shifted with the predefined variables as it can be seen
in the code. This operation corresponds to the pure translation mentioned before. Then we grasp the
object with closei which is a synchronous command as mentioned before. Then we approach the dropf
location with the distance defined by the thickness and the counter. First the counter is 1 so we drop the
first object with openi. In the second iteration the counter is 2, so the distance now is two times the
thickness. This makes possible to put the objects one on another.
After all the objects are packed the robot goes to the waiting location which is recorded previously.
