# README

The inspiration for this [React app](https://react.dev) comes from the React tutorial and Temporal.

## Event Sourced Tic-Tac-Toe Game

![](static/tic-tac-toe.gif)

### Overview

This README provides an overview of the Event Sourced Tic-Tac-Toe Game, a unique implementation of the classic Tic-Tac-Toe game that utilizes the principles of event sourcing. Event sourcing is an architectural pattern in which changes to the application state are stored as a sequence of events. In the context of a Tic-Tac-Toe game, this means that every move made by a player is recorded as an event, rather than just updating the game state.

### Event Sourcing in Tic-Tac-Toe

In a traditional Tic-Tac-Toe game, the game's state (i.e., the positions of 'X's and 'O's on the board) is directly modified after each player's turn. However, in an event-sourced version, the game state is not directly modified. Instead, each action (like placing an 'X' or 'O') is captured as an immutable event. These events are then applied in sequence to derive the current state of the game.

### Key Features

1. **Immutable Event Log**: Every action in the game is recorded as an event. This log provides a complete history of the game from start to finish.

2. **State Reconstruction**: The current state of the game board can be reconstructed at any point by replaying the events.

3. **Audit and Replay**: The event log allows for auditing of the game's history and the ability to replay the game from any point in time.

4. **Fault Tolerance**: In case of system failures, the game state can be recovered by replaying the events from the event store.

5. **Querying Past States**: It is possible to query past states of the game without additional storage, simply by replaying events up to a certain point.

### Architecture

The game consists of the following components:

- **Event Store**: A storage mechanism for all the game events.
- **Game Board Representation**: A service or method to apply events to the game state.
- **Event Producer**: Component that captures player actions and converts them into events.
- **Event Consumer**: Component that applies events to the game state.

### How to Play

Players interact with the game as they would with a traditional Tic-Tac-Toe game. The difference is in how the game processes and stores these interactions. Every move results in an event being sent to the event store. The game state is updated by applying these events in sequence.

### Technical Requirements

To run the Event Sourced Tic-Tac-Toe game, you'll need:

- A modern web browser (for web-based implementations).
- Event store setup (can be a simple database or a specialized event storage system).
- Server/backend environment capable of handling the event sourcing logic (if implemented as a web application).

### Setup and Installation

```bash
npm start
```

Then open:

```bash
http://localhost:3000
```