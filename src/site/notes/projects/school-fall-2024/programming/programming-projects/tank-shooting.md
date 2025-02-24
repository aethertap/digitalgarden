---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/programming-projects/tank-shooting/"}
---


# Shooting the tank's gun

I liked the way it worked in jsbattle; your gun has basically a power output level. Shooting with more power does more damage, but requires a longer recharge.

Give the guns a recharge rate. Every frame, that much energy gets replaced. The gun can only fire with the firing energy is full, so the more you use for your shot, the longer it takes to recharge before you can shoot again.

In jsbattle, the bullets all went the same speed. I think it might be fun to play with having the speed depend on the power of the shot. That would let targeted tanks prioritize which shots to dodge, and it would also add some tactical fun - a well-designed sequence might fire several shots while driving through an arc, so that the shots will all hit the same spot at the same instant. 

Kinetic energy = $\frac{1}{2}mv^2$, so I can just use that. The speed difference will be the square root of the energy difference, so it won't be a huge gap.

## Bullets

The bullet needs to be a small `Body` with `isSensor` set to be true. It will have to make itself disappear when it collides with something (including the arena walls). Each bullet will have velocity and position included by matter-js, so that's really all I have to worry about. 

An alternative way to do it would be to just use a little sprite to show the position of the bullet, and cast a ray that goes:
- *behind* its current position
- along its flight path
- the amount of distance that the bullet flew this timestep

That would give me approximate continuous collision detection with other things that aren't bullets. To be able to shoot bullets out of the air, I'd have to have the full collision bodies.

## Options

### Shoot bullets out of the air

I think it would be awesome to be able to shoot down other bullets. A perfectly-aimed and timed shot should eliminate a threat.

### Limited range

It could be interesting (fun?) to make the gun's range depend on the shot power. 

### Speed based on energy

The damage is always based on the shot energy, but the speed of the bullet could also be (and it could be done so that the kinetic energy is what determines both)

### Air resistance

Matter-js already includes air resistance, I think it might be interesting to have that turned on. It would complicate nearly everything, so maybe that's only in advanced levels (the game could take place on asteroids or something until later, when they get to a planet with an atmosphere).

