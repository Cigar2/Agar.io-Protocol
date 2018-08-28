# Client -> Server

# Server -> Client

## Added in protocol 18 (Battle Royale)

### Game starting
| Offset | Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (176)
| 1        | uint32    | Time to start

### Start Game
| Offset | Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (177)

### Update Game
| Offset | Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (178)
| 1        | uint16    | Players alive
| 3        | uint16    | Game status

#### Read game status (Type 0: waiting for players) 

#### Read game status (Type 1: survive!) 
| Offset | Type | Info
|----------|-----------|-----------------
| 5        | uint8     | Phase (0)
| 6        | int32     | Red zone X
| 10       | int32     | Red zone Y
| 14	   | uint32     | Red zone radius
| 18	   | uint32     | Shrink time (0)

#### Read game status (Type 2)
| Offset | Type | Info
|----------|-----------|-----------------
| 5        | uint8     | Phase (1: safe area shrinking in x, 2: go to safe area)
| 6        | int32     | Red zone X
| 10       | int32     | Red zone Y
| 14	   | uint32     | Red zone radius
| 18	   | uint32     | Shrink time
| 22       | int32      | Target zone X
| 26       | int32      | Target zone Y
| 30	   | uint32     | Target zone radius

### Player death
| Offset | Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (179)
| 1        | uint8     | Death type

#### Read player death (Type 0: player1 ate player2)
| Offset | Type | Info
|----------|-----------|-----------------
| 2        | null-utf8-string     | Killed nickname
| ?        | null-utf8-string     | Killer nickname

#### Read player death (Type 1: player was eaten by a virus)
| Offset | Type | Info
|----------|-----------|-----------------
| 2        | null-utf8-string     | Killed nickname

#### Read player death (Type 2: player couldn't get away)
| Offset | Type | Info
|----------|-----------|-----------------
| 2        | null-utf8-string     | Killed nickname

#### Read player death (Type 3: player died)
| Offset | Type | Info
|----------|-----------|-----------------
| 2        | null-utf8-string     | Killed nickname

### Battle result
| Offset | Type | Info
|----------|-----------|-----------------
| 0        | uint8     | Packet ID (180)
| 1        | uint32    | Final position
| 5        | uint32    | Total kills
| 7        | uint16    | Player count (read below while (playerCount--))
| ?        | null-utf8-string    | Player nickname
| ?        | uint32    | Player position
