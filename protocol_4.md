# Client -> Server

## Mouse move
Sent when the player's mouse moves.
X and Y positions' data types:
- float64 at protocol 4
- int16 at early protocol 5
- int32 at late protocol 5 and newer

| Position | Data Type            | Description
|----------|----------------------|-----------------
| 0        | uint8                | Packet ID (16)
| 1        | float64              | Mouse X
| 9        | float64              | Mouse Y
| 17       | uint32               | 0


# Server -> Client
