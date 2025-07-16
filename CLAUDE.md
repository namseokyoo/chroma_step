# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is **크로마 스텝 (Chroma Step)**, a web-based rhythm game built with Three.js and vanilla JavaScript. The game involves stepping on colored tiles that match mission requirements while maintaining combos and managing time.

## Architecture

### Single-File Structure
- **index.html** - Complete self-contained game with embedded CSS and JavaScript
- No build system, package manager, or external dependencies beyond Three.js CDN

### Core Components
- **Three.js Scene Management** - 3D rendering with orthographic camera, lighting, and shadow mapping
- **Game State System** - Manages MENU, PLAYING, PAUSED, and GAMEOVER states
- **Tile Grid System** - Dynamic infinite grid generation around player position
- **Mission System** - Color-based objectives with combo scoring
- **Theme System** - Multiple color palettes stored in COLOR_THEMES object
- **Local Storage** - Persists high scores, color sparks, and theme preferences

### Key Game Mechanics
- **Dynamic World Generation** - Tiles spawn in GRID_RADIUS around player position
- **Tile Lifecycle** - Tiles deactivate when stepped on, then reactivate after TILE_RESPAWN_TIME
- **Mission Matching** - Player must step on tiles matching currentMission[0] color
- **Combo System** - Successful matches increase combo multiplier, failures reset to 1
- **Time Management** - Time decreases constantly, rewards given for correct matches

### Data Structures
- **tiles Map** - Stores tile objects keyed by "gridX,gridY" coordinates
- **gameData** - Score, time, combo, missions, high score, and color sparks
- **gameSettings** - Current theme selection
- **player** - Position, target position, and grid coordinates

## Development

### Running the Game
Open index.html directly in a web browser - no build process required.

### Code Organization
- Lines 1-116: HTML structure and CSS styling
- Lines 167-277: Initialization and setup
- Lines 278-432: Game loop and core mechanics
- Lines 433-702: Helper functions and event handlers

### Key Configuration
- **GAME_CONFIG** (lines 198-205) - All game balance parameters
- **COLOR_THEMES** (lines 189-194) - Available color palettes
- **Game mechanics constants** - Tile size, respawn time, scoring multipliers

### Testing
No automated testing framework - test manually by opening index.html in browser.

### Korean Language Support
UI text is in Korean. Game title: "크로마 스텝" (Chroma Step)