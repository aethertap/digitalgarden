---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/physics/lessons-outline/"}
---


# Rotational motion
## Building a Concept Map of Motion
### Basic Concepts

- Position: Where an object is located, relative to a reference point. It is a vector quantity, meaning it has both magnitude (distance) and direction [1].
- Velocity: The rate at which an object's position changes with time. Its magnitude is speed [1].
- Acceleration: The rate at which an object's velocity changes with time. It can involve changes in speed, direction, or both [2].
- Mass: A measure of an object's inertia, or resistance to changes in velocity [2].
- Force: A push or pull that can cause an object to accelerate. It is a vector quantity [2].
- Newton's Laws of Motion (Translational)
- First Law: An object at rest stays at rest, and an object in motion stays in motion at a constant velocity, unless acted upon by a net force [3].
- Second Law: An object's acceleration is equal to the net force acting on it divided by its mass (F = ma) [4, 5].
- Third Law: For every force, there is an equal and opposite reaction force [6, 7].

### Rotational Motion Analogs

- Angular Position: An object's orientation relative to a reference orientation [8].
- Angular Velocity: The rate at which an object's angular position changes with time [9].
- Angular Acceleration: The rate at which an object's angular velocity changes with time [10].
- Rotational Mass (Moment of Inertia): A measure of an object's resistance to changes in angular velocity [11].
- Torque: A twist or spin that can cause an object to undergo angular acceleration [12].
- Newton's Laws of Motion (Rotational)
- First Law: A rigid, non-wobbling object not subject to any outside torques rotates at a constant angular velocity [12].
- Second Law: The net torque acting on a rigid, non-wobbling object is equal to its rotational mass times its angular acceleration (τ = I α) [13].
- Third Law: For every torque, there is an equal and opposite reaction torque [14].

### Momentum

- Linear Momentum: A measure of an object's translational motion and its resistance to changes in that motion. It is equal to the object's mass times its velocity (p = m v) [15].
- Angular Momentum: A measure of an object's rotational motion and its resistance to changes in that motion. It is equal to the object's rotational mass times its angular velocity (L = I ω) [16].
### Impulse

- Impulse: The change in an object's momentum due to a force applied over time (Δp = F t) [17].
- Angular Impulse: The change in an object's angular momentum due to a torque applied over time (ΔL = τ t) [18].
### Work and Energy

- Work: The transfer of energy to an object by applying a force over a distance or a torque over an angle [19, 20].
- Energy: The capacity to do work. It can take various forms, including kinetic, potential, thermal, and others [21].
### Key Relationships and Insights

- Force and Acceleration: Force is the cause of acceleration, and acceleration requires a force [22].
- Torque and Angular Acceleration: Torque is the cause of angular acceleration, and angular acceleration requires a torque [23].
- Momentum and Impulse: Changes in momentum are caused by impulses [24].
- Angular Momentum and Angular Impulse: Changes in angular momentum are caused by angular impulses [18].
- Work and Energy Transfer: Work is a mechanism for transferring energy [21].
- Conservation Laws: Energy, momentum, and angular momentum are conserved quantities [15, 21, 25].
### Examples

Applying a force to a skating object over time changes its momentum, which is a measure of its tendency to keep moving [26].

Exerting a torque on a seesaw over time changes its angular momentum, affecting its rotational motion [18].


### The connection between rotational work and translational work

Imagine a mass at the end of a long, massless pole. You are trying to push the mass forward by applying a torque to the opposite end of the pole. in an infinitesimal slice of time, the mass will move a tiny distance forward in a straight path. Therefore, the work done on the mass in that instant is equal to the force applied to it by its end of the lever, times the distance it moved. The force applied at the mass end is scaled down by the length of the lever arm though, due to mechanical advantage.

However, its distance of motion is *scaled up by exactly the same factor* for the same reason. For small angles, *sin(x) = x*. Since the distance traveled at the end of the lever arm is $r\cdot sin(\alpha)$, defining a torque as $f\cdot d$ and then applying it over angle $\alpha$ gives you $f\cdot d \cdot sin(\alpha)$. Then you get the equation $work = f\cdot d \cdot sin(\alpha)$ but $f\cdot d$ is torque, and $\alpha = sin(\alpha)$ for tiny angles, so it becomes $work = \tau \cdot \alpha$.

# Springs

Springs are *elastic*, meaning that they can be stretched and will then return to their original shape. The more you deform them, the harder they resist. This leads to *Hooke's Law*, which says that the *restoring force* of a spring is proportional to the distance it's been deformed: $F = -kd$. $k$ is the *spring constant*, which is a number that basically says "for every distance you stretch the spring, it will be this much harder to keep going." The unit of $k$ is $N \over m$, which makes sense (newtons per meter), but it simplifies to the weird unit $kg \over {s^2}$, which is very non-intuitive.

Springs have an *elastic limit*, which is the point where they can't recover from being deformed any farther. If you moosh a spring past its elastic limit, you will leave a permanent change in it. As long as you stay within the elastic limit, the spring can last essentially forever, barring the effects of other parts of the real world (like corrosion and metal impurities).

## Bobbing on a spring

If you put a weight on the end of a spring and then give it a bump so that it bounces up and down, it will keep bouncing back and forth for quite a while (in a perfectly elastic spring without friction, it would go forever). This is a visual demonstration of conversion back and forth between kinetic energy and elastic potential energy. The kinetic energy of the weight is enough to pull the spring past its neutral point, but the force increases and the weight does work to stretch the spring. That work is stored as elastic potential energy in the spring, and once all of the kinetic energy is spent, that potential energy gets released as the spring returns toward neutral and accelerates the weight in the other direction. However, by the time it gets to neutral again, the weight is going at its top speed, so the cycle just has to repeat in the other direction, and it keeps going until friction kills it.

So, what happens with momentum in that situation? Clearly the mass gains momentum as it moves, and the momentum must be transferred somewhere because it's conserved. Where does it come from and where does it go? The answer is simply that it comes from whatever the spring is attached to, and it goes right back there. Imagine that one end of the spring is attached to a massive cannon ball, and the other is attached to a little steel marble. The whole contraption is floating in space. Now you pull the marble to get it moving back and forth. You'll see the marble move *much* farther than the cannon ball, but *both* of them will be moving in response to the force from the spring. The cannon ball is moving so slowly and such a small amount that its *kinetic energy* is barely changing (remember kinetic energy equals the force times the distance moved, which is basically zero here), but its *momentum* will exactly match the marble's.

