Hello welcome to my Github for my Retro PS2 survival game, i have seperated my personal code into branches to show which work is mine in the project, they are all labled as they are in the project. 

My work focuses on four main systems, the UI System, the Inventory System, the Interaction System and the Deposit System. 

UI System: 
The UI system serves as a visual bridge between the player and the game’s core mechanics. Built using Unity's UI Toolkit and Canvas system in screen-space overlay mode, it dynamically updates through event-driven methods. Inventory slots are updated in real-time based on inventory changes via UnityEvents, with individual UIInventorySlot components reflecting data from their assigned InventorySlot. The system also features contextual prompts and feedback messages triggered by interactions or environmental cues, and uses Unity's Post Processing Stack and script-driven effects for immersive styling such as screen flickering and retro distortion.

Inventory Systems:
The inventory system is built around a modular and extensible architecture using InventorySlot and InventorySystem classes. Each InventorySlot holds references to an InventoryItemData ScriptableObject and a stack size, allowing for flexible item definitions and stacking behavior. The system supports item addition, removal, splitting stacks, and conditional stacking using logic like RoomLeftInStack() and HasFreeSlot(). Events are used to trigger UI updates when the inventory state changes. Inventory is designed to work closely with the deposit and interaction systems, allowing dynamic gameplay integration.


Interaction Systems:
The interaction system is interface-driven, centered around the IInteractable interface which includes an interaction prompt and a polymorphic Interact() method. The Interactor script uses a collider sphere and layer masks to detect nearby interactable objects, and listens for key input (e.g., E key) to trigger interactions. This approach makes the system modular and scalable, allowing any object implementing IInteractable to be used in the environment. It is also directly tied into the UI system for on-screen prompts, and supports condition-based interactions such as requiring specific inventory items.


Deposit System:
The deposit system enables players to transfer specific items from their inventory into designated deposit zones in the environment. It works by scanning the player's InventorySystem for matching item data and quantities, and removes the appropriate amount upon successful interaction. Deposits can trigger further events, such as UI feedback, game progression, or world state changes. The system is implemented in a way that integrates smoothly with both the interaction system for input handling, and the inventory system for checking and modifying item quantities using defined slot logic.

There is also some other code in there that i developed and refined while working on the project that i felt needed to be highlighted. 
