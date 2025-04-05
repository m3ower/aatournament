# Pattern Punisher

## Iterated Prisoner's Dilemma Strategy

### Overview

Pattern Punisher is an adaptive strategy for the Iterated Prisoner's Dilemma that analyzes opponent behavior and adjusts its response accordingly. The algorithm balances cooperation with strategic defection to maximize points while avoiding exploitation.

### Key Features

- **Initial Trust**: Starts with cooperation to establish potential mutual benefit
- **Pattern Recognition**: Detects alternating patterns and strategic shifts in opponent behavior
- **Adaptive Response**: Adjusts behavior based on opponent's historical cooperation rate
- **Forgiveness Mechanism**: Periodically forgives defections to break cycles of mutual defection
- **Endgame Awareness**: Becomes more strategic in final rounds when total rounds are known

### Strategy Logic

The strategy makes decisions based on several factors:

1. **Opponent Cooperation Rate Analysis**:
   - High cooperation (≥70%): Mostly cooperate with occasional defection
   - Low cooperation (≤30%): Mostly defect with periodic cooperation
   - Medium cooperation: Use modified Tit-for-Tat with forgiveness

2. **Pattern Detection**:
   - Identifies alternating patterns and responds optimally
   - Tracks recent behavior separately from overall history
   - Adjusts to changing opponent strategies

3. **Cycle Breaking**:
   - Cooperates every 4 rounds after a defection
   - Tests uncooperative opponents with periodic cooperation (every 7 rounds)
   - Prevents getting locked in mutual defection loops
