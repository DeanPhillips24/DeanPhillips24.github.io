---
layout: base
title: Dynamic Game Levels
description: Early steps in adding levels to an OOP Game.  This includes basic animations left-right-jump, multiple background, and simple callback to terminate each level.
type: ccc
courses: { csse: {week: 14} }
---
```
// Inside the Player class

update() {
    // ... (existing code)

    // Check for speed threshold to change sprite sheet rows
    const speedThreshold = 5; // Change this threshold to your desired value

    if (Math.abs(this.currentSpeed) >= speedThreshold) {
        // Change sprite sheet rows based on speed
        if (this.currentSpeed > 0) {
            // Change sprite sheet row for moving right
            this.setFrameY(this.playerData['your_right_animation_row']); // Replace 'your_right_animation_row' with the specific row value
        } else {
            // Change sprite sheet row for moving left
            this.setFrameY(this.playerData['your_left_animation_row']); // Replace 'your_left_animation_row' with the specific row value
        }
    } else {
        // Revert to normal animation if speed is below the threshold
        this.setAnimation(this.stashKey);
    }

    // Perform super update actions
    super.update();
}
```

