# BREACH/PROTOCOL PATCH NOTES

## Version 0.0.8 - 2026-08-18

### 🔥 New Features
* **Main Menu Redesign:** Complete visual and functional overhaul of the main menu interface, featuring terminal-style UI animations, updated background scene, and a direct external community link panel.
* **Elevator Level Transitions:** Implemented active elevator systems for level entry and floor transitions, complete with dynamic floor displays, window motion scrollers, screen shake effects, and contextual keycard audio cues.
* **Dynamic Enemy Alert System:** Enemies now react to weapon fire noise, direct bullet impacts, and door breaches.

### ⚔️ Balance & Gameplay
* **Increased Threat Density:** Overall enemy spawn rates across floors have been increased.
* **Death Mechanics Overhaul:** Death now triggers a gradual time-deceleration phase, causing all equipped weapons and inventory items to scatter into the environment upon player elimination.
* **Movement Physics Refinement:** Implemented smooth wall-collision slide handling to eliminate snagging on level geometry. Improved crouch-slide friction, slope traversal, and movement responsiveness.
* **Breach Damage Correction:** Resolved an issue where breaching doors failed to inflict physical damage on nearby enemies.

### 🔧 Fixes & Tech
* **Interaction HUD Clean-up:** Fixed stale prompt caching where unlocked doors would continue displaying as locked if targeted during state changes. Expanded interaction detection ranges and fixed close-range interaction blocking. Fixed issue with secondary weapon input hint not displaying the correct key.
* **Audio Fixes & Additions:** Added new firing sound effects for the P-9 Rook pistol, corrected 3D spatial sound routing errors, balanced kill notification volumes, and ensured elevator sounds correctly mute while paused.
* **Interface & Menu Fixes:** Fixed mouse cursor visibility issues and blocked pause inputs when transitioning from the death screen back to the main menu. Secondary weapon indices now correctly render on the player HUD.
* **Environment & Generation:** Reduced facade clutter during procedural layout generation.
* **Performance & Weapon Systems:** Stripped out legacy attachment code, optimized weapon state transitions, and fixed animation unholster mismatches. Major bug fixing and optimization among many core systems to improve overall stability.

---

## Version 0.0.7 - 2026-06-25

### 🔥 New Features
*   Added the "S-2 Scatter," a new double-barrelled sawn-off shotgun, to improve the early game loot pool.

### ⚔️ Balance & Gameplay
*   Increased loot spawn rates and maximum loot per room, with scaling faster.
*   Adjusted all loot and enemy spawns across all rooms.
*   Credits no longer spawn in corridors or upgrade shop rooms, encouraging exploration of other room types.
*   Enemies no longer drop credits on death, incentivizing exploration over kill farming.
*   Added new enemy and loot spawn point variations, including new keycard locations.

### 🔧 Fixes & Tech
*   Minor UI fixes and font updates across the Main Menu and Gameplay scenes.
*   Updated tutorial text, images, fonts, sizes, and positioning to reflect recent balance and UI changes.
*   Added recent playtester names to the credits.
*   Improved collision and object placement in the Arcade Room for better player flow.
*   Implemented a more flexible spawn system, allowing finer control over what types of entities (enemies, weapons, credits, keycards) can appear at specific spawn points.
*   Removed a collider in the Store Room that caused inconsistent player movement.

---

## Version [0.0.6] - 2026-06-22

### 🔥 New Features
* **Modular HUD Overhaul:** Rebuilt the HUD from the ground up into a modular system. This includes dedicated modules for Dash, Interactions, Killfeed, Upgrades, Objectives, and Credits (featuring animated counting).
* **HUD & UI Enhancements:** 
    * Added screen-space object highlighting for interactable items (with options to disable it on doors and shops).
    * Added a HUD startup boot sequence animation.
    * Added dedicated displays for floor number, secondary weapons, and utility items.
    * Added keyboard navigation support to the tutorial carousel.
    * Added dedicated controller ADS (Aim Down Sights) sensitivity sliders to the options menu.
    * Added a Credits screen to the main menu.
* **Utility Item Slot:** Added a dedicated Utility Item inventory slot for inhalers and future utility items, complete with custom input bindings for quick equipping and auto-using.
* **Dual-Type Weapon Classification:** Implemented a dual-type weapon classification system (e.g., classifying the .50 Magistrate as both a Revolver and a Shotgun) to allow upgrades to affect multiple weapon categories.
* **New Upgrades:**
    * **Vendor Uplink:** Marks nearby vendors on the compass when using a utility item (each stack increases search range).
    * **Munitions Spooler:** Newly acquired handguns and revolvers overflow their magazine capacity to 125% (+25% per stack).
    * **Recycler Optics:** Critical hits have a 30% chance to refund 1 round to the magazine (+10% chance per stack).
    * **Momentum Transfer Grip:** Hitting an enemy with a thrown weapon grants +50% fire rate for 2 seconds (+0.5s per stack).
    * **Volatile Power Cells:** Thrown weapons explode on impact (includes custom VFX and icons).
    * **Magnetic Actuator:** Increases the range which weapons can be picked up.

### ⚔️ Balance & Gameplay
* **Floor Progression:** Floor numbers now increment predictably by 10s instead of being randomized. Completing a floor now rewards the player with bonus credits.
* **Economy & Loot:** Increased the value of credit pickups found throughout levels. Lowered weapon spawn rates, indirectly increasing the availability of credits and inhalers.
* **Combat & Weapons:**
    * Enemies now drop weapons towards the player upon death, facilitating smoother weapon-chaining combos.
    * Improved iron sight alignment and zeroing for the .44 Warden and P-9 Rook.
    * Enabled scroll wheel wrapping for weapon swapping.
    * Improved the responsiveness of equipping and using the Drift Inhaler.
    * Adjusted the layout and size of Upgrade Shop item cards to improve readability.
    * Rebalanced the "Endorphin Synthesizer" upgrade.
    * Updated default controller input bindings.
    * Rotated backroom doors in the Arcade Room to improve combat and movement flow.

### 🔧 Fixes & Tech
* **Combat & Hit Detection:**
    * Fixed a bug where penetrating bullets could deal damage to the same target multiple times.
    * Fixed a bug preventing bullet damage to enemies at point-blank range.
    * Fixed thrown weapons failing to deal damage when thrown at point-blank range.
    * Fixed an issue where enemies would shoot over the player's head while the player was crouching.
    * Fixed the center aim point for the V-33 Hornet burst rifle.
    * Fixed breached doors continuing to deal damage to enemies after settling on the ground.
    * Added line-of-sight checks to the "Volatile Power Cells" explosion to prevent damage through solid walls.
* **Enemies & AI:**
    * Fixed enemies failing to chase players when taking damage from outside their detection range.
    * Fixed enemies not appearing on the compass when transitioning directly from patrol to attack.
    * Fixed an issue where dead enemy bodies could trigger and open doors.
* **Upgrades & Shop:**
    * Fixed a bug that caused duplicate items to appear in the Upgrade Shop.
    * Fixed an issue where the "Munitions Spooler" effect applied to weapons that were dropped and re-acquired.
    * Fixed a bug where the "Momentum Transfer Grip" upgrade triggered when hitting dead bodies with thrown weapons.
    * Fixed a bug where the "Recycler Optics" upgrade triggered multiple times with shotguns.
* **Inhalers & Items:**
    * Fixed an issue where picking up an inhaler would temporarily disable the crosshair.
    * Fixed a bug where consuming the final charge of an inhaler failed to re-equip the player's previous weapon.
    * Fixed an issue where inhalers would repeatedly auto-use if the player had no other weapons equipped.
* **UI, Audio & Tech:**
    * Unified and optimized world-space interaction icons for weapons, credits, and keycards to ensure visual consistency.
    * Upgraded all upgrade icons to higher-resolution textures.
    * Fixed a UI error on compass elements when rapidly killing enemies immediately after alerting them.
    * Added an input grace timer to the death screen to prevent accidental restarts or main menu exits.
    * Improved pause menu layout and buttons, and added fading to death screen input hints.
    * Separated interaction layers for doors and weapon pickups, allowing pickup-distance buffs to apply exclusively to weapons.
    * Implemented audio timeouts for kill and hitmarker sound effects to prevent audio spamming when hitting or killing multiple enemies simultaneously.
    * Deprecated and removed legacy XP, leveling, and damage popup systems from the UI.
    * Added support for biome-specific wall material overrides.
    * Updated physics materials on dropped weapons and breached doors for more realistic physical behavior.

---

## Version [0.0.5] - 2026-04-27

### 🔥 New Features
* **Expanded Arsenal:** Integrated the V-33 Hornet Burst Rifle into the loot pool.
* **Augmentation Suite:** Implemented several new player upgrades, including Displacement Capacitor, Auto-Doc Subroutine, Ocular Euphoria, Adrenal Override, Endorphin Synthesizer, Gyro Stabilizers, and Hydraulic Legs.
* **Urban Expansion:** Added several new environments, including the Market Room, multiple Arcade variants, a Drug Lab, and several new Apartment layouts.
* **Economy System:** Introduced a functional Credits system. Players can now collect currency from fallen hostiles and world containers to be used at specialized terminals.
* **Upgrade Terminals:** Added functional Upgrade Shops within the levels featuring randomized stock, purchase animations, and dedicated audio feedback.
* **Ballistic Decals:** Implemented a high-performance decal system for persistent bullet holes and blood pooling.
* **Tutorial Expansion:** Updated the training interface with dedicated modules for the upgrade and credit systems.

### ⚔️ Balance & Gameplay
* **Projectile Overhaul:** Transitioned all firearms from hitscan to a projectile-based ballistic system for enhanced combat depth.
* **Combat Calibration:** Adjusted damage values, penetration depth, and critical hit multipliers across the entire weapon roster.
* **Hostile Intelligence:** Overhauled enemy state machines for better flow between patrolling and engagement. Enemies now utilize a wider variety of weapons and exhibit improved attack timings and ranges.
* **Survival Tuning:** Increased base health regeneration rates and decreased the delay required for auto-healing to trigger.
* **Resource Management:** Weapons now initialize with a single magazine; adjusted spawn weights for credits and medical inhalers.
* **Inhaler Refinement:** Increased the duration and charge capacity of the Drift Inhaler.
* **Environmental Interaction:** Improved door breaching physics. Doors opened by the player will no longer be automatically closed by passing enemies.
* **Zone Density:** Increased enemy population in early floors and optimized level generation parameters for better layout variety.
* **Movement Polish:** Increased base controller sensitivity and refined slide and air control multipliers.

### 🔧 Fixes & Tech
* **Performance Optimization:** Executed a major sweep to reduce memory allocation, disabled unused 2D physics systems, and transitioned audio assets to streaming to improve frame stability.
* **Feedback Systems:** Enhanced player damage feedback with refined screen shake, vignettes, and impact particles.
* **Collision Pass:** Resolved numerous collision errors in the Bank, Noodle Shop, and Apartment sectors, including fixes for "invisible" window barriers.
* **AI Bug Fixes:** Resolved a critical error where melee hostiles could occasionally kill players in a single strike. Fixed issues preventing ranged enemies from attacking at close proximity.
* **UI/UX Polish:** Overhauled the Main Menu visual identity and HUD layout. Improved the compass system with better tracking for keycards and elevators.
* **Ballistic Correction:** Fixed a bug causing projectiles to deviate from the crosshair and resolved an issue where player colliders would rotate incorrectly upon taking damage.
* **Lighting & Visuals:** Refreshed lighting for the Main Menu and central atrium; updated hologram shaders and particle materials for better visual consistency.
* **Navigation:** Fixed navigation mesh errors to prevent enemies from becoming stuck on environmental props.
* **Audio Mastering:** Balanced volume levels for weapons and added cooldowns to repetitive player impact sounds.

---

## Version 0.0.4 - 2026-03-07

### 🔥 New Features
*   Added an exit game button to the main menu.

### ⚔️ Balance & Gameplay
*   Improved door opening and closing animations for smoother transitions.
*   Breached doors now instantly eliminate enemies caught in the blast, feature new impact sound effects, and no longer impede player movement.
*   Implemented new enemy patrol behaviors, including random, static, and room-specific patrols, enhancing tactical variety.

### 🔧 Fixes & Tech
*   Fixed an issue where the cursor remained locked when returning to the main menu.
*   Temporarily disabled control rebinding in the main menu as it is being reimplemented.
*   Fixed an issue with UI sounds in the Main Menu.

---

## Version 0.0.3 - 2026-03-05

### 🔥 New Features
*   Implemented a new tutorial carousel system in the Main Menu to provide basic onboarding information. This includes new UI icons, a dedicated menu tab, and will automatically display on first game load.
*   Implemented a basic scoring system, including score breakdown and high score tracking on the death screen. The player HUD now displays current score and time survived. The death screen now features a fade-in effect, and the pause menu is disabled upon player death.
*   Implemented floor number displays outside elevators to indicate current level.
*   Enemies now appear as elements on the player's compass.
*   Significantly improved weapon throwing mechanics:
    *   Thrown weapons now deal damage, bounce back off enemies, and have distinct throw and impact sounds.
    *   Weapon pickups now auto-equip when picked up and auto-swap when thrown.
    *   Optimized collision detection for thrown weapons, especially in slow motion.
    *   Improved physics materials for thrown weapons.
*   Introduced the new Training Grounds scene, accessible via a new menu card. The scene has been filled with content, updated materials, adjusted lighting, skybox, and now features atmospheric height fog. Refillable weapon spawn points have been added to the Training Grounds.
*   Implemented level incrementation for procedural level generation.
*   Enemies can now correctly open and close doors to navigate between rooms and corridors.
*   Implemented enemy ragdolls, with weapons now dropping upon enemy death.

### ⚔️ Balance & Gameplay
*   Improved enemy melee animations, speed, and hit detection. Enemies now have slight randomized movement speed variations to prevent clumping. Enhanced enemy pathing. Adjusted melee enemy stats: reduced attack range, decreased attack cooldown, increased movement acceleration and stopping distance, decreased turning speed.
*   Implemented unholster time for weapons, allowing for more precise weapon swap animations and timing.
*   Pistols and revolvers now fire on "Press" instead of "Press and Hold." Movement speed is no longer affected while aiming with any weapon.
*   Significant adjustments to player movement and stamina:
    *   Player run speed decreased (12 -> 8).
    *   Player walk speed decreased (5 -> 4).
    *   Slide force, boost duration, and steer multiplier increased.
    *   Stamina cost for jumping and sliding increased.
    *   Movement is now allowed while sliding.
    *   Slide end velocity no longer changes.
    *   Camera tilt transition speed decreased.
    *   Breathing amplitude decreased.
    *   Reloading is now allowed while unholstering.
    *   Auto-reloading has been temporarily disabled (will return as an option).
    *   Healing screen effects disabled.
*   **Weapon Balance:**
    *   The .50 Magistrate Revolver now fires 6 shots per bullet in a tight, shotgun-like spread.
    *   The Breach-12 Shotgun now spawns with 8 shots and no extra magazine.
    *   The player now auto-heals slowly 30 seconds after taking damage (temporary until healing items are implemented).
    *   Shock Stick attack speed decreased (0.7s -> 0.8s).
    *   Shock Stick and Katana range decreased (2m -> 1m).
    *   Katana attack speed increased (0.7s -> 0.5s).
    *   Revolver ADS positioning improved, weapon sway lowered, ADS accuracy increased, hip fire accuracy decreased.
*   **New Weapons:**
    *   Added the .50 Magistrate Revolver to the loot pool.
    *   Added new weapons: EX-6 Pulsar (Revolver), P-9 Rook (Pistol), MX-5 Stryker (SMG), .44 Warden (Revolver), Breach-12 (Shotgun), and new Katana and Knife types.

### 🔧 Fixes & Tech
*   Fixed general collision issues, a floor tile seam, Z-fighting visual artifacts, and an issue where players could go out of bounds in the Training Grounds. Fixed issues with the Drift Inhaler and pausing functionality in the Training Grounds.
*   Implemented a new "Ragdoll" layer for enemies, improving collision detection and impact effects when enemies are defeated.
*   Keycards now pulse with light to improve visibility and have had clipping issues resolved in the Store Room.
*   Significant improvements to time scaling mechanics, ensuring consistent behavior for slow-motion effects, mouse sensitivity, head bobbing, breathing, and jump timers regardless of frame rate. The game now properly pauses on death, and the Drift Inhaler has been re-added to the player's starting loadout.
*   Fixed a trigger collider issue on elevator floor interactables.
*   Added temporary fixes to prevent the player from getting stuck in small gaps.
*   **Audio Overhaul:**
    *   New menu music, gameplay music, and interaction sounds added.
    *   Improved 3D audio falloff and range checks.
    *   Weapon firing and handling sound volumes have been adjusted.
    *   Randomized pitch for interaction sound effects.
    *   Increased audio voice count for richer soundscapes.
    *   Decreased overall music volume, with reactive effects sensitivity adjusted accordingly.
    *   Improved enemy footstep sounds with separate settings for sprinting.
    *   New corridor light flicker sound effects.
    *   New shooting sound for the Revolver.
    *   New door sounds for all interactable and breachable doors.
    *   New interact and locked sounds for elevator buttons.
    *   Improved audio balance across the game.
    *   Fixed issues with interaction timers in slow-motion.
*   Fixed multiple level generation bugs, including out-of-bounds corridors and facades, overlapping lights, and navigation mesh baking issues in various rooms and elevators. Improved placement of large props in Slums Biome.
*   Implemented visual variations for enemies through mesh and material swapping.
*   Fixed an issue where changing displays could prevent the game from loading previously set resolutions.
*   Generated and applied new icons for all existing weapons.
*   Adjusted the position of the stamina UI element. Fixed overlapping UI elements on the player HUD.
*   Improved enemy blood effects.
*   Fixed holes in enemy colliders, improving hit detection.
*   Implemented weapon baking for skinned mesh renderers, significantly improving performance, collision detection, and interactions for weapons.
*   **Weapon & Loot Spawning Fixes:** Fixed issues with enemies being able to block shots with their weapon, enemies getting killed by spawned or dropped weapons, weapons not being able to spawn with no extra ammo, and dropped weapons not correctly clearing on level transitions. Fixed layer issues on weapon pickup graphics.
*   **Room & Environment Improvements:** Improved lighting, layout, loot spawns, enemy spawns, keycard spawns, materials and collisions for most rooms, including the Bank Room, Pipes Room, Micro Apartment Room, and Noodle Shop Room. Adjusted spawning probabilities for facade doorways. Fixed collision on elevator pillars and lights. Fixed enemies getting stuck inside the Noodle Shop Room.
*   Improved Main Menu visuals with new menu card graphics and fixed the patch notes scroll view.
*   Keycard pivot, lighting, materials, and rotations improved for better placement.
*   Fixed entity spawning rotation issues.
*   Improved iron sights for the Hand Cannon Revolver and separated submeshes for animations.

---

## Version 0.0.2 - 2026-02-06

### 🔥 New Features
*   Implemented a foundational system for Keycard interactions, including updated models and a dedicated UI element to indicate acquisition.
*   Introduced functional Elevators, complete with interactable buttons and doors, integrated into level generation.
*   Implemented a new, robust system for deterministic spawning of items, keycards, and enemies within generated levels, allowing for varied placement based on density curves and room data.
*   Expanded level generation with new environment objects: corridor lights, security cameras, and additional room layouts ('Bank' and 'Pipes').
*   Implemented randomized broken and flickering corridor lights in level generation for added atmosphere.
*   Integrated volumetric lighting and fog into the environment, significantly enhancing atmosphere. An option to toggle volumetric lighting has been added to the pause menu.
*   Implemented a new Security Scanner system for bank room entrances, featuring player detection, distinctive sounds, and dynamic lighting.
*   Introduced the Shock Stick melee weapon, complete with new sound effects and added to initial player loadouts.
*   Introduced the Drift Inhaler item, complete with new model, animations, icons, and smoke particle effects.
*   Integrated muzzle flash behavior for custom weapons, specifically for the Inhaler smoke effect.
*   Implemented an enemy attack system, including behaviors and states for melee and ranged enemy types.
*   Integrated fundamental enemy types with basic state machines (Patrol, Chase) and animation controllers.
*   Reworked the core door interaction system to support diverse door types (single, double, sliding, unique) and lay the groundwork for expanded breachable door functionality.
*   Introduced 16 new interactable door designs and 6 new breachable door variants, integrated into rooms like the Micro Apartment and Tearing Doc Room.
*   Implemented initial breachable doors, utilizing a new dual-interaction system for standard open/close actions and a dedicated 'breach' command. This system supports future complex interactables.
*   Integrated new music tracks and optimized music playback to transition seamlessly between songs.
*   Added a 'Current Special' UI element, serving as a placeholder for future utility items.
*   Introduced a dedicated 'Patch Notes' section in the Main Menu for viewing update information.

### ⚔️ Balance & Gameplay
*   Increased player control responsiveness, crouch transition speed, and camera tilt transition speed.
*   Increased weapon inventory size from 2 to 3, preparing for future utility item additions.
*   Adjusted initial weapon loadout.
*   Melee enemies now deal damage to the player.
*   Increased the attack duration for melee enemies.
*   Enhanced enemy weapon animations and behavior for both pistol and melee enemy types.
*   Reduced overall enemy health.
*   Sped up Revolver animations, adjusted reload timing, aim point and distance for a more fluid experience.
*   Improved Drift Inhaler slo-mo effects with smoother visual transitions, new sound effects, and enhanced bloom.
*   Disabled the hue shift post-processing effect during slow motion for improved visual clarity.
*   Adjusted room generation probabilities for the Slums Biome.
*   Adjusted the open/close speeds for numerous doors.

### 🔧 Fixes & Tech
*   Optimized enemy controller code.
*   Adjusted Bank Booth collisions.
*   Fixed various code warnings and optimizations across several core systems.
*   Resolved an issue causing intermittent failures in vertical facade generation during level creation.
*   Fixed a crash when regenerating levels while an interactable object was highlighted.
*   Implemented runtime NavMesh generation.
*   Addressed various errors and optimized model settings for NavMesh baking.
*   Temporarily addressed an issue where enemies could occasionally spawn outside of navigable areas.
*   Fixed an issue with the initial lighting manager setup.
*   Fixed a material display error during level generation.
*   Fixed an issue with the frame rate counter displaying incorrectly during slo-motion.
*   Resolved a bug causing music tracks to loop incorrectly.
*   Adjusted weapon camera settings for improved rendering of weapons and post-processing effects.
*   Resolved a bug affecting melee weapon animations.
*   Improved scaling of generic pick-up weapons.
*   Temporarily disabled ambient sounds.
*   Fixed Z-fighting artifacts on vertical facades.
*   Optimized vertical facade generation by removing unnecessary collisions, improving performance.
*   Fixed missing collisions on specific facade elements.
*   Resolved collision issues with vertical void fog elements.
*   Addressed a minor physics warning related to player death.
*   Added a keybind for toggling the FPS counter, now disabled by default.
*   Resolved a null reference error in the weapon effects system related to bullet graphics.
*   Fixed an issue causing instant despawning of Inhaler smoke particles.
*   Ensured the Pause Menu's fading animations function correctly during slow motion.
*   Improved physics collision and interpolation for breachable doors to enhance slow-motion interactions.
*   Enhanced overall lighting and materials, including wall textures and emission effects, for a more consistent and stylized aesthetic.
*   Revitalized the Tearing Doc Room with updated lighting, materials, and layout.
*   Ensured audio reactor effects function correctly during slow motion.
*   Made adjustments to the main audio mixer.
*   Added new alarm sound effects for the Bank Entrance Scanner.
*   Adjusted edge detection visuals for weapons and characters, enhancing their appearance.
*   Resolved an issue with emoji text rendering.
*   Addressed various interaction and collision issues for breachable doors.
*   Fixed an edge case crash related to the alternate interaction system.
*   Corrected door opening direction logic for breachable doors.
*   Applied lighting improvements to several room layouts.
*   Updated additional legacy materials to utilize the new stylized toon shader.
*   Resolved rendering issues affecting certain UI elements in the Main Menu.

---

## Version 0.0.1 - 2026-01-19

### 🔥 New Features
* Implemented procedural Level Generation.
* Added a new Weapon system and mechanics.
* Introduced Weapon Throwing and dropping capabilities.
* Added new environmental Facades to levels.

### ⚔️ Balance & Gameplay
* Updated mechanics for the Shotgun, Turret, and Target.
* Refined player movement, including sliding and item interaction physics.
* Improved weapon collection and interaction systems.

### 🔧 Fixes & Tech
* Overhauled rendering settings, including improvements to Edge Detection and Ambient Occlusion.
* Updated anti-aliasing to SMAA to reduce visual artifacts and smooth edges.
* Improved texture quality on corridors to reduce visual banding at a distance.
* Optimized general graphics and rendering performance.

---
