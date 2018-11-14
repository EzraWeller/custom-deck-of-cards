Fork of the original [deck of cards](https://deck-of-cards.js.org/) by Juha Lindstedt & contributors.

Add custom cards by editing the SVGs in "example - Fighting Game"/fighting_game_faces/, or add your own folder.

Customize the cards in the deck by editing "example - Fighting Game"/example.css, starting at line 206.

Change the size of the deck and other deck functions at dist/deck.js, line 924.

Test in a browser with "example - Fighting Game"/index.html

### Fighting Game Rules

Players split their decks in two: their "move" deck and their "resource" deck. The resource deck is the player's health pool — if they are forced to draw from it and no cards are left, they lose. (Resources currently not implemented)

At the start of the game, players draw 5 moves.

Turns are played simultaneously: Both players choose a move to play, reveal their moves at the same time, then draw a replacement move. Players repeat this loop, attempting to link moves into each other by navigating startup, hitstun, and recovery well.

- 2 startup move vs. 3 startup move: 2 startup wins, so the 2 startup move hits
- The hit has 6 hitstun and only 3 recovery, giving that player +3
- Next they play a 3 (-3 for the advantage) startup move and 1 startup move: 3 startup wins because of the +3, so it hits
- etc.
- Players can pass without playing a move if they want

If one player is able to deal 10 or more damage straight, without being damaged by the other player, they score a "knockdown": the board is cleared of moves (into the discard pile), and the next pair of moves resets to 0 frame advantage. Whenever a player is damaged, they draw 1 resource for each point of damage. Drawn resources are revealed, while unplayed moves are hidden. If a player's entire move deck is in play or in the discard pile, they shuffle all their moves back into their move deck.
