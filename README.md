# SpecterLink

SpecterLink is an advanced telemetry and capture server that runs locally using Flask and exposes a public link securely via Cloudflare Tunnels (`cloudflared`). It is designed to capture target details such as IP address, GPS location, device information (OS, browser, screen resolution, etc.), and even a photo if camera access is granted. After capture, it seamlessly redirects the target to a destination URL of your choice.

## Features
- **Public URL Generation:** Automatically spins up a Cloudflare Tunnel to provide a secure public URL.
- **Data Capture:** Logs IP address, precise GPS coordinates, device platform, browser specs, language, screen resolution, CPU cores, and RAM.
- **Photo Capture:** Attempts to capture a photo from the target's camera (requires target permission).
- **Custom Redirection:** Redirects the target to an arbitrary URL after the telemetry is collected.

## Prerequisites

Before running SpecterLink, ensure you have the following installed on your system:
1. **Python 3.x**
2. **cloudflared**: You must have the Cloudflare Tunnel daemon installed and accessible in your system's PATH. 
   - Download it here: [Cloudflare Tunnel Downloads](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/downloads/)

## Installation

1. **Clone or Download** the SpecterLink directory to your local machine.
2. **Navigate** to the project directory:
   ```bash
   cd path/to/SpecterLink
   ```
3. **Install Python Dependencies:**
   Install the required Python packages using pip:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

You can start SpecterLink by running the main Python script. By default, it redirects targets to `https://google.com`.

```bash
python specterlink
```

### Custom Redirect URL

If you want to redirect the target to a specific website after they visit your link, use the `-r` or `--redirect` flag:

```bash
python specterlink -r "https://your-custom-url.com"
```

### Output & Captures

- When the server starts, it will display a `trycloudflare.com` URL in the terminal. Send this link to your target.
- Once the target visits the link, their data will be printed directly to the terminal.
- Any captured photos will be saved automatically in the `captures/` directory within the project folder.

## Disclaimer
This tool is intended for educational purposes, security research, and authorized penetration testing only. Ensure you have explicit permission before using this tool against any targets. The developer assumes no liability for misuse.
