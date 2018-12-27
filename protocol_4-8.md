###### Source: https://github.com/forairan/Agar.io-Protocol/blob/master/Protocol.md

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

### Spectate free roam (Q key pressed)
| Offset | Data Type | Info
|--------|-----------|-----
| 0      | uint8     | Packet ID (18)

### Q key released
| Offset | Data Type | Info
|--------|-----------|-----
| 0      | uint8     | Packet ID (19)

### Eject Mass
| Offset | Data Type | Info
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (21)

# Server -> Client

### Update Nodes
(1) before 6: uint32, on + after: uint16

| Offset | Data Type     | Info
|--------|---------------|-----------------
| 0      | uint8         | Packet ID (16)
| 1      | uint16        | Number of nodes to be destroyed
| 2...?  | Destruct Data | Nodes' ID marked for destruction
| ?...?  | Node Data     | Data for all nodes
| ?      | uint32        | Always 0; terminates the node data listing
| ?      | uint16        | Always 0; discarded by the client
| ?      | (1)           | Number of nodes marked for destroying
| ?...?  | Destruct Data | Node ID of each destroyed node (uint32)

### Set Border
| Offset | Data Type | Info
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (64)
| 1      | float64   | Left position
| 9      | float64   | Top position
| 17     | float64   | Right position
| 25     | float64   | Bottom position

### Reset Connection 1
Sent at the beginning of a conneciton, before reset connection 2. Server must send Clear Nodes and Set Border packets to keep the client connected.
| Offset | Data Type | Description
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (254)
| 1      | uint32    | Protocol version

### Reset Connection 2
Sent directly after reset connection 1.
| Offset | Data Type | Description
|--------|-----------|-----------------
| 0      | uint8     | Packet ID (255)
| 1      | uint32    | Protocol version
