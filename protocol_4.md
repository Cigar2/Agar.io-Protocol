# Client -> Server

## Mouse Move
| Position | Data Type            | Info
|----------|----------------------|-----------------
| 0        | uint8                | Packet ID (16)
| 1        | float64              | Mouse X
| 9        | float64              | Mouse Y
| 17       | uint32               | 0

## Split
| Position | Data Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (17)

## Eject Mass aka Feed
| Position | Data Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (21)

# Server -> Client
