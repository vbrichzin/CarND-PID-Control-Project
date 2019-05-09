# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Reflection

1. Describe the effect each of the P, D, I components had in the implementation.

The proportional component P of the PID controller leads to the vehicle steering back into the center of the road in order to reduce the CTE of the off-center position. In playing around with the chosen P value I was able to observe a stronger or less strong effect of this "pulling" into the road center.
The differential component D of the PID controller is looking at the differential values of the CTE and through that is acting to counteract oversteering from the P component of the controller. In playing around with the chosen D value I was able to observe a stronger or less strong "counter-steering" around the center of the road, leading to less stable conditions at higher values.
The integral component I of the PID controller is summing the historic total of the CTE error and acting on that, which helps in counteracting a systematic bias possible from an off-center position of the wheels mounted to the car as was described in the lesson.

2. Describe how the final hyperparameters (P, I, D components) were chosen.

The hyperparameters were actually chosen manually. Already with the first set of values chosen (0.1, 0.001, 1.0) I was lucky and got some encouraging results. The I value was chosen small on purpose as it sums the CTE error over a long time and bigger values might put too much weight on the I component of the controller. The D value was chosen bigger than the P value as it acts already on the differential which should be smaller than the difference the P value is acting on.
In tuning the parameters some more I arrived at P=0.14, I=0.001 and D=2.0. With these values I was even able to increase the throttle value to 0.35 leading to a maximum speed of roughly 40mph.
No Twiddle or SGD is used which certainly would provide even better hyperparameters especially necessary for higher speed settings tuning efforts.
