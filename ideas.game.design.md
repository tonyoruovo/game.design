#### Research

##### Youtube commentators
- [SkillUp](https://www.youtube.com/@SkillUp)
- [WorthABuyreviews](https://www.youtube.com/@WorthABuyreviews)
- [theescapist](https://www.youtube.com/@theescapist)
- [ThatOneVideoGamer](https://www.youtube.com/@ThatOneVideoGamer)
- [MortismalGaming](https://www.youtube.com/@MortismalGaming)

#### Memories
- They may be like balloons visually. As more and more memories are collected, the balloon size increases.
- When respawned at a respawn point, the NPCs will relate to the player differently as they now have a memory of the player's character dying.
- Memories may be implemented as references (like pointers in a linked-list) that exist in game objects, NPCs, and the player character. These references may point to other objects, locations, or events in the game world.


#### World
- This is a strategic sandbox with a tactical world map (default view). Each significnt point within the map is a sandboxed stage/level.
    - The tactical world map is a jigsaw puzzle with a twist. Each tile is a hexagon which may or maynot be re-entrant. The entire map is a huge rubic's cube.
    - Rows and column sections are connected when the sides match. This creates a linked world map where moving off one edge of a tile may lead to another tile.
    - Linked tiles of different colors may cause a current to flow through them. This current may affect movement speed, visibility, and other factors such decreased constitution/HP at the start of each turn.
- The memories causes changes in the world over time. Just like the world's greed level at ['Black Geyser'](https://youtu.be/MjI0qqc6lw8?t=429)

#### Combat

We need a simple combat loop that is easy to learn but hard to master. Something like a rock-paper-scissors system with additional layers of complexity.
- Each target (ai against player, ai gainst ai, ai against environment, ai against objects, ai against NPCs) has the following rules
    - No health bars
    - Targets are made up of different sections which may be inidividually targeted and unraveled to "disarm" or "eliminate" the target.
    - Each section has its own properties, capabilities, and vulnerabilities. An example is that the helmet of a target may need to be destroyed before the head can be targeted with projectiles.
    - To reach certain sections of a target, the dueler may need to use movement mechanics (such as climbing onto the target, swimming into the target, jumping to a higher position) to get into position
- Every attack has a span.
    - The first 1/3 of the span can be parried
    - The first 2/3 of the span can be blocked
    - The last 1/3 of the span is guaranteed to hit unless the target dodges or performs a super parry which manifests as a deflect and gives a frame advantage to the dueler presenting a counter-attack scenario.
    - For fast attacks, the span is shorter and the parry window is smaller.
    - For slow attacks, the span is longer and the parry window is larger.
    - The speed of the attack depends on the weapon type, the dueler's stats, and the type of attack being performed.
    - Each attack has an invisible attack meter. This meter represents the powerup time for the attack. The longer the dueler holds the attack button, the more powerful the attack becomes up to a certain limit.
    - This creates a wind-up animation for each attack which creates a vulnerability window for the dueler in which the attack may be parried, blocked, prevented or countered.
- Succesive hits on a target regerates stamina faster, and, depending on the enemy type, stats and weapon type, may trigger a "frenzy" mode where the dueler gains increased attack speed and damage for a short period of time and prevents death even when their they sustain a lethal blow. This prevents decapitation or dismemberment during frenzy mode.
- The focus ring is an analog-looking GUI on the lower left that has a center point, a concentric translucent circle and a concentric ring within it. The more the translucent circle's center aligns with the center point, the more focused the dueler is. The more focused the dueler is, the more accurate their attacks become and the faster their stamina regenerates. The more out of alignment the translucent circle is from the center point, the less focused the dueler is. The less focused the dueler is, the less accurate their attacks become and the slower their stamina regenerates.
- Morale, discipline and reputation are also part of combat. This ensures that most fights/duels will not be to the death unless absolutely necessary.
