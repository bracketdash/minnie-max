# MinnieMax

A minimalist JavaScript utility framework for 2-player deterministic games.

![Minnie Max](./logo.png)

## API

### `new MinnieMax(config)`

**Config object properties:**

- `el`:  
  Required. Mounting element for the control bar.

- `localStorageKey`:  
  Required. Key to use for localStorage.

- `initialMovesAhead`:  
  Required. Number of moves to simulate in the minimax search.

- `initialState`:  
  Required. The initial game state.

- `getMoves({ minnie, state, player })`:  
  Required. Returns an array of all legal moves for the given player and state.

- `getNextState({ minnie, state, player, move })`:  
  Required. Returns a new `{ state, player }` after applying the move.

- `getStateScore({ minnie, state, player, movesRemaining, currPlayer })`:  
  Required. Returns a numeric score for the given state from the perspective of the given player.

- `isGameOver({ minnie, state })`:  
  Required. Returns `true` if the game is over in the given state.

- `onChange({ minnie })`:  
  Optional. Fires after a change to `movesAhead` or the game state.

- `onReady({ minnie })`:  
  Optional. Fires after the control bar has been mounted.

### `getScoredMoves(state, player): Promise<Array<{ move, score }>>`

Returns a Promise that resolves to an array of all legal moves for the given state and player, each paired with a numeric score. The returned array is sorted in descending order of score (best moves first).

### `getState(): { state, player }`

Returns the current game state.

### `pushState(state, player)`

Adds the given state and player to the game history and stores it in `localStorage`.

## Example Projects

- [Boop Helper](https://github.com/bracketdash/boop)
- [Mancala Helper](https://github.com/bracketdash/mancala-helper)
- [Squadro Helper](https://github.com/bracketdash/squadro)
- [Quarto Helper](https://github.com/bracketdash/quarto)
