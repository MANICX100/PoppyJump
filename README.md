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

## Access from a PlayStation 5 with PS5Prxy

The PS5 does not provide a normal user-facing web browser. [LiEnby's PS5Prxy](https://github.com/LiEnby/PS5Prxy/) is an unofficial Windows proxy that intercepts the PlayStation manual/help request and returns a local `ps5.html` launcher page.

> [!IMPORTANT]
> PS5Prxy v0.3 was released in November 2020 and its author only confirmed it on PS5 firmware 2.02. Current PS5 firmware may behave differently or block this method. PoppyJump does not bypass console security, modify the console, or guarantee that this old proxy technique still works.

### 1. Publish PoppyJump

Enable GitHub Pages using the instructions above and confirm that this URL opens on your PC:

```text
https://manicx100.github.io/PoppyJump/
```

### 2. Prepare PS5Prxy on a Windows PC

1. Download `PS5Prxy.0.3.zip` from the [PS5Prxy v0.3 release](https://github.com/LiEnby/PS5Prxy/releases/tag/v0.3).
2. Extract the archive to a folder on a Windows PC connected to the same local network as the PS5.
3. Keep `ps5.html` in the same working directory as `PS5Prxy.exe`.
4. To launch PoppyJump automatically, replace the contents of `ps5.html` with:

```html
<!doctype html>
<meta charset="utf-8">
<title>Opening PoppyJump</title>
<p>Opening PoppyJump…</p>
<script>location.replace('https://manicx100.github.io/PoppyJump/');</script>
```

The original v0.3 `ps5.html` can alternatively prompt for a URL. If you keep that page, enter the GitHub Pages URL when prompted.

### 3. Find the PC's local address

Open Command Prompt on the PC and run:

```bat
ipconfig
```

Find the active network adapter and note its **IPv4 Address**, for example `192.168.1.50`. Do not use the example address unless it is actually assigned to your PC.

### 4. Start the proxy

1. Run `PS5Prxy.exe` from its extracted folder. Run it as Administrator if Windows prevents it from listening for other devices.
2. Allow it through Windows Defender Firewall for **Private networks** if prompted.
3. Leave its console window open. It should report `PS5Prxy running on port 8080`.

### 5. Configure the PS5 network

Menu names can vary by PS5 firmware.

1. Go to **Settings → Network → Settings → Set Up Internet Connection**.
2. Highlight the active Wi-Fi or wired connection, open its advanced settings, and set **Proxy Server** to **Use**.
3. Enter the Windows PC's IPv4 address as the proxy address.
4. Enter `8080` as the port.
5. Save the connection settings and test the connection.

### 6. Open PoppyJump

1. On the PS5, open **Settings → User's Guide, Health and Safety, and Other Information → User's Guide**. On older firmware this may appear simply as the help/manual page.
2. PS5Prxy should log a request for `manuals.playstation.net` and serve `ps5.html`.
3. The launcher should redirect to PoppyJump. Use any DualSense button or either analog stick up to jump.

If it does not load:

- Confirm the PC and PS5 are on the same network and client isolation is disabled.
- Confirm `PS5Prxy.exe` is still running and Windows Firewall permits private-network access.
- Verify the PS5 proxy address matches the PC's current IPv4 address and the port is `8080`.
- Verify GitHub Pages is enabled and the game URL works on another device.
- Remember that newer PS5 firmware may no longer support PS5Prxy's 2020 interception method.

### Restore normal PS5 networking

When finished, return to the PS5 connection's advanced settings and set **Proxy Server** to **Do Not Use**, then close PS5Prxy on the PC. Only route console traffic through software and computers you trust.

## Project structure

```text
.
├── index.html   # Complete game, styles, rendering, audio, and input
└── README.md    # Setup and usage documentation
```

## Credits

PS5 browser access instructions reference the unofficial, MIT-licensed [LiEnby/PS5Prxy](https://github.com/LiEnby/PS5Prxy/) project and its [v0.3 release notes](https://github.com/LiEnby/PS5Prxy/releases/tag/v0.3). PoppyJump is not affiliated with Sony Interactive Entertainment or the PS5Prxy author.
