# PID Controller

Bolin Zhao (bolin_zhao@outlook.com)

## Reflection

### PID parameters

P term:  parameter P has the biggest effect on the steering wheel maximum value. With a small number, the steering wheel will turn less as desired even when the CTE(center trajectory error) is huge.  But with a big value on P, the vehicle will hard to keep a straight line driving due to the small CTE will lead the steering wheel tuning and eventually the car will shake along the center trajectory.

I term: I which stand for integration helps to remove the static error. In the lateral controller, in general case the system does not have a static error(bias). thus, this term could be small.  

D term: for a controller with large P term which aim to reduce the CTE as fast as possible, the possible drawback is that the car will shake along the center trajectory.  The mainly reason is that only P term and I term can only "look back" but cannot know the future trend.   

The D term utilizes the differential term to "predict" the trend of the error.With the D term,  when the error increasing, the controller output will increasing as well to reduce the trend. When D term is 0.1, the car will shake along the road as a sine wave obviously. And increasing it to 1.0, the pheromone will be better. 

### Final hyperparameters

The final parameters are chosen by try and error. At first, the Kp is increasing to a value which can lead the car back to center in 1 second. Then Kd is increasing to reduce the shaking. Ki has limited affect during the observation, but a large value on Ki term will lead the car cannot back to the center. 











