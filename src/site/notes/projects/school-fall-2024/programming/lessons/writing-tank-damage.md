---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/programming/lessons/writing-tank-damage/"}
---


#  Making Damage Possible

## Links and useful resources

- [Typescript Language Home](https://www.typescriptlang.org/)
- [Typescript Playground](https://www.typescriptlang.org/play/)
- [Arduino Language Reference](https://docs.arduino.cc/language-reference/)


- ***[[projects/school-fall-2024/programming/programming-projects/tank-battle-game\|Project index: tank-battle-game]]*** 
## Concept summary and lesson


- Giving tanks "hit points" 
- Noting when the tank is destroyed 
- Applying bullet damage on impact 
- Applying collision damage on impact 

### Hit Points

The tanks can only take a certain amount of damage before they're destroyed. We'll represent this as hit points, and they will be another part of the Tank class on the server. The sensor data should also contain the current tank's health, and the health of any enemy tanks that are scanned by the radar.

### Tank destruction

When a tank's hit points are zero or less, the tank is destroyed. At that point, it should be removed from the update cycle, but the tank's dead body should stay on the field to be used as cover. 

- A dead tank can still collide with bullets and other tanks
- A dead tank returns a radar signature as usual
- A dead tank's drive velocity, gun angle and radar angle are all fixed at zero
- A dead tank can take any amount of damage without further destruction (for now)
- A dead tank can be *pushed* by other tanks! For this purpose, it should just act like a rock as far as the physics is concerned.
    - We'll need to have a coefficient of friction and a mass set
- A dead tank's graphic on-screen should show that it's dead somehow, maybe with a different color or fill.

### Bullet damage

The bullets already have a damage function, so we just need to call that when a bullet hits a tank, and apply the result to the tank. If we plan ahead for different armor types, we want to know not only the bullet's damage, but also where it came from (in case armor is unequally distributed on the tank). The tank's damage function should take a number and a direction.
- May be fun to add some knockback: higher power bullets apply larger impulse.

### Collision damage

When a tank crashes into something, it should take damage. Once again, the damage should depend on not only the absolute amount, but the direction. Most tanks should have tougher armor on the front so that they can ram other tanks and end up winning.

Damage from a collision should depend on the relative velocity at impact. It needs to be a kinetic energy approximation, so that faster hits have damage that grows quadratically.

On collision, the damage is applied to both sides equally, but the tank itself applies its directional armor before deducting hit points.

## Examples/demo

*Code will go here when we finish the coding session today*

