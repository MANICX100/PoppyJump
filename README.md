# PoppyJump

A single-page, dependency-free Flappy Bird-style garden game starring Poppy, a cream cavapoo. Jump over flower-crowned deer, collect points, and chase your local high score.

## Play

Once GitHub Pages is enabled, play at:

**https://manicx100.github.io/PoppyJump/**

You can also download the repository and open `index.html` directly. If your browser restricts local files, serve the folder from a terminal:

```sh
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Controls

| Device | Jump / start / restart |
| --- | --- |
| Keyboard | `Space`, `Enter`, `W`, or `Arrow Up` |
| Mouse or touchscreen | Click or tap the game |
| DualSense | Any button, or push either stick up |
| Generic USB controller | Any button, or push either stick up |

Press `M` on a keyboard to mute audio. Press `R` after a game over to return to the title screen.

PoppyJump uses the standard browser Gamepad API with fallbacks for non-standard USB controllers and older WebKit implementations. It supports multiple connected controllers, including XInput, DirectInput, PlayStation, Switch-style, arcade-stick, and inexpensive generic USB devices when the browser exposes them through that API.

## Features

- Responsive HTML5 Canvas rendering with no external assets or dependencies
- Procedural cavapoo, deer, flowers, butterflies, clouds, particles, and parallax scenery
- Keyboard, pointer, touchscreen, DualSense, and generic game controller input
- Local high-score persistence
- Generated Web Audio effects with graceful fallback when audio is unavailable
- Conservative JavaScript and browser APIs suitable for embedded browsers

## Publish with GitHub Pages

1. Open the repository's **Settings** on GitHub.
2. Select **Pages** under **Code and automation**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the `main` branch and `/ (root)`, then choose **Save**.
5. Wait for GitHub to publish the site at `https://manicx100.github.io/PoppyJump/`.

GitHub Pages may take a few minutes to become available after the first deployment.

## Play on PlayStation 5

1. Send the GitHub Pages URL below to a friend or another account in a PlayStation Network message. The PlayStation App can be used to send it from a phone.

   ```text
   https://manicx100.github.io/PoppyJump/
   ```

2. Open the message on the PS5 and select the link.
3. The game will open in the PS5 web view. Use any DualSense button or push either analog stick up to jump.

## Project structure

```text
.
├── index.html   # Complete game, styles, rendering, audio, and input
└── README.md    # Setup and usage documentation
```
