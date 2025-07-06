import numpy as np
import sounddevice as sd
import time

def estimate_range(freq):
    if 15000 <= freq < 17000:
        return 1.5
    elif 17000 <= freq < 18000:
        return 1.0
    elif 18000 <= freq < 19000:
        return 0.5
    elif 19000 <= freq <= 20000:
        return 0.2
    else:
        return 0

duration = 2
fs = 48000
start_freq = 15000
end_freq = 20000
step = 1000

banner = r"""
        /^ ^\
       / 0 0 \
       V\ Y /V
        / - \
        |    \
       || (__V

        MicKiller by w01f
"""

print(banner)
print(f"Testing frequencies from {start_freq} Hz to {end_freq} Hz at {fs} Hz sample rate.\n")
print("Estimated effective range will be displayed for each frequency.\n")

for freq in range(start_freq, end_freq + 1, step):
    print(f"Playing {freq} Hz for {duration} seconds...")
    t = np.linspace(0, duration, int(fs * duration), endpoint=False)
    audio = 0.5 * np.sin(2 * np.pi * freq * t)
    try:
        sd.play(audio, samplerate=fs, blocking=True)
        est_range = estimate_range(freq)
        print(f"Estimated max effective range: {est_range} meters\n")
    except Exception as e:
        print(f"Failed: {e}\n")
    time.sleep(0.5)

print("Test completed.")
