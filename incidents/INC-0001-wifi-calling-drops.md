# INC-0001 Wi-Fi Calling Drops

## Symptom
Calls disconnect while moving upstairs.

## Investigation
- RSSI dropped below -80 dBm
- Client remained attached to AP-1
- Roaming delay observed

## Root Cause
Transmit power imbalance between APs.

## Resolution
Reduced AP-1 transmit power from High to Medium.

## Lessons Learned
Proper AP overlap is critical for seamless roaming.
