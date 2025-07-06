# MicKiller by w01f

An experimental script for generating high-frequency tones (15kHz–20kHz) via your laptop’s speaker, with estimated effective range for microphones.  
**Purpose:** Test the response of microphones (built-in or external) and study how far ultrasonic/near-ultrasonic signals from consumer devices can reach.

---

## Features

- Plays a series of high-frequency tones (15,000–20,000 Hz)
- Displays the estimated maximum range at which built-in mics can detect each tone (based on typical laptop hardware, e.g., Dell XPS)
- Simple, cross-platform (Linux/Windows) Python script

---

## Hardware & Effect Notes

- **Laptop speakers** (like Dell XPS) can generally output 16–18kHz at low volume; above that, sound energy drops rapidly.
- **Built-in microphones** can often detect up to 20kHz, but only if the speaker can actually produce the tone.
- **Typical effective range:** 0.2–1.5 meters depending on frequency and hardware.

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/zenzue/MicKiller.git
cd mickiller
````

### 2. Install Python and pip

Most systems have Python 3.x preinstalled, but make sure you have it and `pip`:

#### **Ubuntu/Debian**

```bash
sudo apt update
sudo apt install python3 python3-pip python3-numpy portaudio19-dev
pip3 install sounddevice numpy
```

#### **Arch/Manjaro**

```bash
sudo pacman -Syu
sudo pacman -S python python-pip python-numpy portaudio
pip install --user sounddevice numpy
```

#### **Windows**

1. Download and install [Python 3](https://www.python.org/downloads/)
2. Open Command Prompt and run:

```sh
pip install sounddevice numpy
```

If you have issues, install [PortAudio binaries for Windows](http://files.portaudio.com/download.html).

---

## Usage

```bash
python mickiller.py
```

* The script will display a wolf head banner, then play tones from 15kHz to 20kHz.
* For each tone, you’ll see the estimated maximum range where a mic might pick up the signal.
* You can change the frequency range or step in the script variables.

---

## Disclaimer

* **Use for educational, ethical testing only!**
* Very high frequencies can sometimes be irritating to animals or rare individuals with sensitive hearing.
* Results will vary greatly by device and environment.

---

## Credits

* ASCII wolf by \[various authors, modified by w01f]
* Script by \[w01f]

---

## License

MIT License. See `LICENSE` file.

```
