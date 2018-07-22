# Client -> Server

## Mouse Move
(1) 4: float64, 5 early: int16, 5 late and 6: int32

| Position | Data Type            | Info
|----------|----------------------|-----------------
| 0        | uint8                | Packet ID (16)
| 1        | (1)                  | Mouse X
| 9        | (1)                  | Mouse Y
| 17       | uint32               | 0

## Split
| Position | Data Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (17)

## Eject Mass
| Position | Data Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (21)

# Server -> Client

## Update Nodes
| Position | Data Type     | Info
|----------|---------------|-----------------
| 0        | uint8         | Packet ID (16)

## Set Border
Sets the map border.

| Position | Data Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (64)
| 1        | float64   | Left position
| 9        | float64   | Top position
| 17       | float64   | Right position
| 25       | float64   | Bottom position
