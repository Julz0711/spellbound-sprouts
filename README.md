# Spellbound Sprouts

A 3D gardening and survival game made with Unity. Grow herbs and defensive plants during the day, survive enemy waves at night, and gather the ingredients needed to progress through the cauldron's recipes.

## Gameplay

- **Prepare by day:** plant on garden tiles, choose seeds and tools, and harvest plants.
- **Defend at night:** fight enemies while defensive plants attack or apply effects such as poison and slow.
- **Collect resources:** manage dropped items and the supplies needed for planting.
- **Complete recipes:** bring the required ingredients to the cauldron to earn rewards and work toward the win condition.
- **Survive the cycle:** nights end after the wave has finished spawning and its enemies are defeated; a new day restores some health.

The project includes menu, gameplay, death, and win scenes, plus pause and settings interfaces.

## Open in Unity

1. Clone the repository:

   ```sh
   git clone https://github.com/Julz0711/spellbound-sprouts.git
   ```

2. In Unity Hub, add the cloned project and open it with **Unity 2022.3.1f1**, the version recorded in [ProjectVersion.txt](ProjectSettings/ProjectVersion.txt).
3. Let Unity restore packages and import assets.
4. Open [Assets/Scenes/Menu.unity](Assets/Scenes/Menu.unity) and press **Play**.

The project uses **HDRP 14.0.8**, the **Input System 1.6.1**, AI Navigation, and TextMesh Pro. Package restoration also includes a Git-based editor integration, so initial setup needs network access.

## Interaction

The player uses camera-relative movement and cursor-based interaction. Click enemies to attack, garden tiles to plant or harvest, and the cauldron to interact with its recipes. The mouse wheel cycles seeds. Planting is restricted to daytime.

Input actions define movement, tool selection, seed shortcuts, and skipping the day. Check the project's Input System bindings for the exact keyboard/controller mappings.

## Build

Open Unity's **File → Build Settings**, choose your target platform, and install its build-support module if needed. Keep the enabled scenes in their recorded order:

| Index | Scene |
| --- | --- |
| 0 | `Menu` |
| 1 | `Main` |
| 2 | `Death` |
| 3 | `Win` |

Some transitions use build indices, so changing the order also requires updating the scene-transition code.

## Code map

| Path | Responsibility |
| --- | --- |
| [Assets/Scripts/GameManager.cs](Assets/Scripts/GameManager.cs) | Shared game state and creation/removal of enemies, plants, and drops. |
| [Assets/Scripts/Player.cs](Assets/Scripts/Player.cs) | Movement, attacks, tools, planting, and player health. |
| [Assets/Scripts/TimeManager.cs](Assets/Scripts/TimeManager.cs) | Day/night progression and wave completion. |
| [Assets/Scripts/Plants/](Assets/Scripts/Plants/) | Herbs and defensive plant behaviors. |
| [Assets/Scripts/Enemies/](Assets/Scripts/Enemies/) | Enemy behavior. |
| [Assets/Scripts/UI/Cauldron.cs](Assets/Scripts/UI/Cauldron.cs) | Recipe requirements, rewards, and the win condition. |
| [Assets/Scripts/StatusEffects/](Assets/Scripts/StatusEffects/) | Poison and slow effects. |
