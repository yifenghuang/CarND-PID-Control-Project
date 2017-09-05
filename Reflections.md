# Reflection
___
## Effects of P,I,D terms
*Describe the effect each of the P, I, D components had in your implementation.*

The final parameters I used were: 
K_P = 0.09, K_I = 0, K_D = 1.5.  

The proportional term can make the car driving into centerline. Bigger K_P will make the system react faster but have some risk to overshoot.

The derivative term can make driving smoothly. When K_D is small or zero the car will drive like a 'S'. This is because the overshoot by the effect of K_P.

The integral term can reduce the systemic bias or called static error.

The throttle equals 0.6 - 0.5*abs(steer_value). This can make the car slower a little bit when cornering

## Design
___
*Describe how the final hyperparameters were chosen.*

I tuned the PID values by trial and error.  

First, I set all parameters to 0. Then I set K_P as a  value and run the simulator. K_P need to be big enough to make the car turn into the correct direction and have some overshoot. At the same time the K_P should not too big or the overshoot will too much to force the car out of the track.

Next, I set K_D as a value. Then I can see the overshoot is smaller then before. Increasing the K_D will produce smooth driving behavior, but a big K_D will make the steering slower.

In this case the simulator won't have any systemic bias like camera mounting error or some unbalenced hardware error. So I set K_I as zero. 