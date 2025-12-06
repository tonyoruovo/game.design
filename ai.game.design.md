### Programming Patterns for Game AI
These are software engineering patterns used to structure AI code for clarity, flexibility, and performance. A comprehensive resource is the book Game Programming Patterns by Bob Nystrom.

- State Pattern / Finite State Machines (FSMs): A fundamental pattern for AI decision-making. The AI has a limited number of distinct states (e.g., Patrolling, Chasing, Attacking) and transitions between them based on events or conditions. This is useful for simple, reactive behaviors.
- Command Pattern: Encapsulates an action as an object. The AI engine can issue commands (e.g., MoveCommand, AttackCommand) without needing to know the implementation details, which decouples the AI logic from the actor's specific movement or attack methods.
- Strategy Pattern: Allows the AI to switch between different algorithms or behaviors at runtime. For example, a single NPC could use a "stealth" strategy or an "aggressive" strategy depending on the situation, with the core AI logic remaining the same.
- Component Pattern: Structures an AI agent by composing it of multiple smaller, modular components (e.g., a MovementComponent, a HealthComponent, an AIComponent). This promotes reusability and a clean separation of concerns.
- Observer Pattern: Allows different parts of the game (e.g., the AI, the UI) to be notified of changes in game state (e.g., "player spotted," "health low") without being tightly coupled. The AI can react to events without constantly polling for changes.
- Object Pool Pattern: Improves performance by reusing pre-created AI agents or related objects (like bullets or special effects) instead of constantly creating and destroying them, which can be computationally expensive.
### AI-Based Game Design Patterns
These patterns focus on the role AI plays in the overall game experience and how players interact with it. 
- AI as Adversary: The most common pattern, where the AI controls NPCs that oppose the player, such as enemies in an FPS or opponents in a strategy game.
- AI as Role-Model: The player must observe and learn from the AI's behavior to succeed, such as in the game Spy Party where the player learns to mimic the AI-controlled NPCs.
- AI as Trainee: The player is tasked with training the AI, providing a core gameplay loop focused on the AI's learning process.
- AI is Visualized: The AI's internal workings or decision-making process is made visible to the player as a gameplay element.
- AI is Editable / Guided: The player can modify or influence the AI's behavior or rules, allowing for a form of co-creation or strategic guidance.
- AI as Co-creator: The AI system works alongside the human designer to generate content, such as procedural level generation or dynamic narrative creation. 
For an in-depth look at programming patterns, the resource [Game Programming Patterns](https://gameprogrammingpatterns.com/contents.html) offers detailed explanations and examples. 