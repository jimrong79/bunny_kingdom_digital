# bunny_kingdom_digital

A digital adaptation of the board game "Bunny Kingdom," implemented using Pygame. This project aims to bring the strategic gameplay of drafting cards, expanding territories, and building prosperous fiefs to your computer.

## Game Overview

Bunny Kingdom is a card drafting and territory control game where players strive to build the most valuable fiefs over 4 rounds. The player with the most Golden Carrots (Victory Points) at the end of the game wins.

### Game Flow
The game is played over **4 rounds**. Each round consists of three phases:

1.  **Exploration Phase (Card Drafting):**
    *   Players are dealt a hand of cards (10 cards in a 4-player game, 12 cards in a 3-player game).
    *   Each turn, players choose 2 cards from their hand to keep (and will play/place them), then pass their remaining hand to the next player.
    *   The passing direction alternates each round:
        *   Rounds 1 & 3: Pass to the left.
        *   Rounds 2 & 4: Pass to the right.
    *   This continues until all cards from the initial deal have been drafted.

2.  **Construction Phase:**
    *   After all cards for the round have been drafted, players use their acquired Building cards to place tokens (cities, farms, sky towers, camps) on the board or claim territories with Territory cards.
    *   **Important Rule:** Each territory can only hold one token (e.g., a city, a farm, a camp). You cannot place multiple tokens on a single territory. Territories with pre-existing cities also count as having a token.

3.  **Harvest Phase (Scoring):**
    *   At the end of each round, players score their fiefs.
    *   A **Fief** is a group of connected territories controlled by a player.
    *   The score for each fief is calculated as: **Total Strength** (sum of city strengths in the fief) × **Total Wealth** (number of *different* types of resources in the fief). For example, a fief with one fish and two carrots has a Wealth of 2.
    *   Players accumulate Golden Carrots from this phase after each of the 4 rounds.

### Final Scoring
After the 4th round's Harvest Phase, players reveal their **Parchment cards**. These cards provide additional Golden Carrots based on fulfilled missions or collected treasures.

## Board & Territories

The game is played on a 10x10 grid. Each square (e.g., A1, C5, J10) represents a unique territory, and each territory has a corresponding Territory Card.

### Territory Types:
*   **Fields, Forests, Seas:** These territories inherently produce basic resources (Carrots, Wood, Fish, respectively). They start without tokens but contribute their resource if part of a player's fief.
*   **Plains, Mountains:** These territories do not produce resources by themselves but can be valuable for building or fulfilling Parchment card objectives.
*   **Already-Established Cities:** Some territories begin the game with a city of Strength 1. This city counts as a token, so no other buildings can be placed on it unless the existing city is replaced or upgraded (if specific game rules allow for upgrades).

## Card Types

1.  **Territory Cards:**
    *   Represent a specific coordinate on the 10x10 board.
    *   Playing a Territory Card allows a player to claim control of that territory by placing one of their bunny tokens on it (only one territory card per territory).
2.  **Building Cards:**
    *   Allow players to construct various buildings during the Construction Phase. These buildings are tokens.
    *   **Cities (Strength 1, 2, or 3):** Placed on a territory a player controls. They increase the Strength of a fief.
    *   **Farms:** Placed on a territory a player controls. They produce basic resources (Carrot, Fish, Wood) or luxury resources. Luxury resource farms may have placement restrictions (e.g., must be on a Mountain, or on a territory that produces a specific basic resource).
    *   **Sky Towers:** Placed on a territory a player controls. They connect two of a player's otherwise separate fiefs, allowing them to be scored as one larger fief.
    *   **Camps:** Allow a player to claim an *empty* territory (a territory without any tokens, including pre-established cities). Camps count as a token. If another player (or the same player) later plays the specific Territory Card for that space, the camp is removed, and the new player's token takes precedence.
3.  **Parchment Cards:**
    *   Kept secret by the player until the end of the game.
    *   **Missions:** Award Golden Carrots for achieving specific objectives (e.g., controlling certain numbers of territory types, multiply the Golden Carrots provided by Treasure cards).
    *   **Treasures:** Provide a direct, unconditional number of Golden Carrots.
4.  **Provision Cards:**
    *   When played during the Exploration Phase (as one of the two chosen cards), the player immediately draws 2 cards from the top of the main deck and plays them. These two new cards are effectively the cards played for that turn.

## Technologies Used (Planned)
*   **Python**
*   **Pygame** (for graphics, input handling, and game loop)

## How to Play (High-Level Summary)
1.  **Setup:** Initialize the game board, shuffle and deal cards, prepare player components.
2.  **Play 4 Rounds:**
    *   **Exploration Phase:** Draft cards by selecting 2 and passing the rest.
    *   **Construction Phase:** Place buildings and claim territories using drafted cards.
    *   **Harvest Phase:** Calculate and award Golden Carrots for fiefs.
3.  **End Game Scoring:** Reveal and score Parchment cards.
4.  **Determine Winner:** The player with the most Golden Carrots wins!

## Future Enhancements (Potential)
*   Full graphical user interface for the game board, cards, and player actions.
*   AI opponents for single-player mode.
*   Networking capabilities for online multiplayer.
*   Sound effects and thematic music.
*   Game state saving and loading functionality.
*   Tutorial mode or rulebook integration.