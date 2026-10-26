# Data plan - Secret Knock Door Lock

**Team:** Hammad khalid, Jawad Nazar

## Sensor

The finished device will use an **Adafruit MAX9814 electret microphone amplifier module** connected to an ESP32-S3 analog input. The MAX9814 converts knocking sounds into an analog signal that the ESP32 can sample. All training and testing recordings will be collected with this same microphone module, gain setting, and ESP32. For final data collection, the microphone will be fixed in its intended position on or beside the door rather than held in different positions.

## Classes

The device must distinguish four classes:

1. **Secret knock:** the correct number of knocks with the trained rhythm.
2. **Other knocking:** knocks with the wrong count, timing, or rhythm, including attempts that sound similar to the secret pattern.
3. **Other sounds:** speech, music, footsteps, door movement, and ordinary nearby impacts that are not deliberate door knocks.
4. **Nothing happening:** a quiet room with no knocking or other significant activity.

“Other knocking” and “other sounds” must not unlock the door.

## Collection

Hammad Khalid, Jawad Nazar both will coordinate recording, with each team member contributing knock examples. We aim to collect at least **30 examples per class** across three separate sessions. Secret-knock and other-knock examples will include different people, soft/medium/firm taps, slow/normal/fast overall speeds, and small variations in rhythm and knocking position. Other sounds and nothing-happening examples will be recorded in quiet and normally active room conditions, including speech at different distances from the microphone. The microphone will remain fixed in its intended door-mounted position, with its position and gain setting recorded and kept consistent.

Before training, we will reserve approximately **20% of each class** for testing. These test recordings will be kept separate and will not be used for training or threshold tuning. Where practical, the test set will include a different recording session and a person not represented in the corresponding training examples, so that testing checks generalization rather than only repeated recordings from the same session.

## Risk

**Secret knock** and **other knocking** are most likely to be confused. Both produce similar short, loud impulses at the microphone, especially when the knock force and distance are similar. The main difference may be the number and timing of the impulses rather than their sound. Incorrect knock segmentation, background noise, or natural timing variation could therefore cause an incorrect pattern to be accepted or the correct pattern to be rejected.

## Waiting for

We are waiting for the **Adafruit MAX9814 microphone amplifier module** (DigiKey part **[1528-1713-ND](https://www.digikey.fi/en/products/detail/adafruit-industries-llc/1713/4990777)**) to arrive. The expected delivery date is **30/11/2026**. Data collection will begin once it arrives; the ESP32-S3 and servo are already available.
