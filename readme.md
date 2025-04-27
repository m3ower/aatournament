# Pattern Punisher & Strategic Exploiter

## Iterated Prisoner's Dilemma Tournament Strategies

### Part 1: Pattern Punisher

Pattern Punisher is an adaptive strategy for the Iterated Prisoner's Dilemma that analyzes opponent behavior and adjusts its response accordingly. The algorithm balances cooperation with strategic defection to maximize points while avoiding exploitation.

#### Key Features

- **Initial Trust**: Starts with cooperation to establish potential mutual benefit
- **Pattern Recognition**: Detects alternating patterns and strategic shifts in opponent behavior
- **Adaptive Response**: Adjusts behavior based on opponent's historical cooperation rate
- **Forgiveness Mechanism**: Periodically forgives defections to break cycles of mutual defection
- **Endgame Awareness**: Becomes more strategic in final rounds when total rounds are known

#### Strategy Logic

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

### Part 2: Strategic Exploiter

Strategic Exploiter builds on the Pattern Punisher foundation while adding opponent selection capabilities. This enhanced strategy identifies the most profitable opponents and allocates rounds strategically across them.

#### Additional Features

- **Opponent Selection**: Intelligently chooses which opponents to play against based on their cooperation patterns
- **Round Allocation**: Distributes available rounds across opponents to maximize total points
- **Multi-tier Classification**: Categorizes opponents into highly cooperative, moderately cooperative, neutral, and defective groups
- **Balance Management**: Ensures proper exploration of all opponents while focusing on the most profitable ones

#### Advanced Logic

1. **Tiered Opponent Classification**:
   - High cooperation (≥65%): Primary focus for most rounds
   - Medium cooperation (50-65%): Secondary focus with cautious exploitation
   - Low cooperation (≤35%): Minimal interaction after initial assessment
   - Neutral (35-50%): Moderate engagement with adaptive play

2. **Round Distribution Strategy**:
   - Ensures all opponents receive minimum exploration rounds (5-20)
   - Allocates bulk of rounds (up to 80) to highly cooperative opponents
   - Distributes remaining rounds based on cooperation rates and point efficiency
   - Respects maximum 200-round limit per opponent

3. **Enhanced Decision Making**:
   - Maintains the core Pattern Punisher strategy for deciding individual moves
   - Adds opponent-specific exploitation patterns (e.g., defecting every 4th move with cooperative opponents)
   - Implements different forgiveness cycles based on opponent categories
   - Dynamically adjusts play style based on observed opponent behavior

This two-part strategy maintains consistency in core decision-making principles while adding the strategic opponent selection capability required for the second part of the tournament.