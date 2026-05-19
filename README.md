# real-time-chess
Project based on the prachub exercise.

# Link to the exercise

https://prachub.com/interview-questions/design-a-real-time-chess-service

# Long description

Design an online chess service that supports real-time two-player games.

The system should allow users to create or join a chess game, make legal moves, see the opponent's moves with low latency, and finish games by checkmate, timeout, resignation, draw, or abandonment.

Focus especially on:

- How to represent and persist game state.
- How to validate and order moves correctly.
- How to track each player's remaining clock time accurately.
- How to recover when a client disconnects, crashes, or reconnects from another device.
- How to scale the service to many concurrent games while preserving correctness.
- Assume real-time play is required, so moves should usually reach the opponent in under a few hundred milliseconds. State any additional assumptions you need.