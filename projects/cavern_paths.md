---
layout: project
type: project
image: img/cavern_paths/Cavern Path Image Cropped.png
title: "Optimizing Cavern Paths"
date: May 2022
published: true
labels:
  - Java
  - Eclipse
  - Shortest Path
summary: "For my Object-Oriented Programming and Data Structures course, my partner and I developed code in Java for a game optimizing paths in a cavern."
---
<div style="display: flex; justify-content: center; align-items: center;">
  <video width="630" height="300" src="https://github.com/jennjkim/jennjkim.github.io/assets/94199268/3a4a161f-66ff-4988-8648-891bf6401c02" controls></video>
</div>

The above is a demo video of the game running, with comparison of pre and post-optimized paths:

For my Object-Oriented Programming and Data Structures course, my partner and I developed code for a game in Java where the objective was to: 

1) Find a hidden orb in a cavern with the shortest number of steps possible. 
2) Escape from the cavern given a set time.
3) While fleeing the cavern, collect as much gold as possible (this acts a bonus for the total score at the end, where the total score was based on the time it took to leave the cave and also the gold collected.)

We found an optimal solution for the final score. My partner and I wrote code that was organized into two main methods: `find(FindState state)` for finding the orb inside the cavern and `flee(FleeState state)` for escaping the cavern. While coding, we used linked lists and knowledge of shortest path algorithms.

**Finding the Orb (`find` method):**
- When coding the `find` method, my partner and I used various algorithms, including depth-first search (DFS), optimized minimum distance, and optimized sorting of distances, to explore the cavern and find the orb.
- We had a `visitedIDs` list to keep track of visited node IDs to avoid revisiting nodes.

**Escaping the Cavern (`flee` method):**
- The `flee` method focused on escaping the cavern before a collapse while collecting as much gold as possible.
- We utilized Dijkstra's algorithm to find the shortest path to the exit.
- We wrote helper methods to handle gold collection and path traversal.
- For example, we had a `pathInfo` class that encapsulated information about paths and distances between the current location, gold nodes, and the exit.

We also had further helper methods for traversing nodes, finding the minimum distance node for paths, and managing paths with gold. The overall strategy was to efficiently navigate the cavern, prioritize escaping, and collect gold if it could be done within the time constraints.

For reference, here is a code snippet of a method called optimizedFlee that guided the character to escape the cavern while making efficient decisions based on the number of steps left.

```java
    /** Traverses the cavern by choosing the neighbors with the smallest distance to the Orb by
    using helper getminID(). **/
    
    private static void optimizedMinDist(FindState state, ArrayList<Long> visitedIDs) {
        if (state.distanceToOrb() == 0) return;
        long currNodeID= state.currentLoc();
        visitedIDs.add(currNodeID);
        for (NodeStatus w : state.neighbors()) {
            long minID= getMinID(state);
            long wID= w.getId();
            if (!visitedIDs.contains(wID) && minID == wID) {
                state.moveTo(wID);
                optimizedMinDist(state, visitedIDs);
                if (state.distanceToOrb() == 0) return;
                state.moveTo(currNodeID);
            }
        }
    }
```

Ultimately, completing this project helped me understand the significance of implementing concepts like DFS and shortest path algorithms to a fun concept. While working on code to optimize the character's actions, I also gained a better appreciation of the utilization of data structures like linked lists. Finally, the project also served as a valuable opportunity to further develop my skills in Java and object-oriented programming. 






