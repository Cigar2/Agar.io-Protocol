###### This doc is incomplete, check out this file for more information: https://github.com/forairan/Agar.io-Protocol/blob/master/Protocol.md

# Client -> Server

### Set Nickname (spawns the player)
| Offset | Data Type | Info
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (0)
| 1      | asdf      | Nickname

### Spectate
| Offset | Data Type | Info
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (1)


### Mouse Move
(1) 4: float64, 5 early: int16, 5 late and 6: int32

| Offset | Data Type            | Info
|--------|----------------------|-----------------
| 0      | uint8                | Packet ID (16)
| 1      | (1)                  | Mouse X
| 9      | (1)                  | Mouse Y
| 17     | uint32               | 0

### Split
| Offset | Data Type | Info
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (17)

### Eject Mass
| Offset | Data Type | Info
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (21)

# Server -> Client

### Update Nodes
| Offset | Data Type     | Info
|--------|---------------|-----------------
| 0      | uint8         | Packet ID (16)

### Set Border
| Offset | Data Type | Info
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (64)
| 1      | float64   | Left position
| 9      | float64   | Top position
| 17     | float64   | Right position
| 25     | float64   | Bottom position

### Reset Connection 1
| Offset | Data Type | Description
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (254)
| 1      | uint32    | Protocol version

### Reset Connection 2
| Offset | Data Type | Description
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (255)
| 1      | uint32    | Protocol version
