MOOS is [publish-subscribe](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) [middleware](https://en.wikipedia.org/wiki/Message-oriented_middleware).

An MOOSApp ([[#CMOOSApp|`CMOOSApp`]]) communicates with the [[#MOOSDB]] and:

- publishes messages([[#CMOOSMsg|`CMOOSMsg`]]),
- registers for messages.


The MOOSDB will manages the incoming messages and send messages to all subscribed apps.
## MOOS Relationships
```mermaid
erDiagram  
 CMOOSApp }o--|| MOOSDB : connects
 MOOSDB ||--o{ CMOOSMsg : manages
 CMOOSMsg }o--o{ CMOOSApp: publishes
```

## MOOSDB
The MOOSDB is more a blackboard than a database. 
It keeps tracks of the message it receives.

Each message is unique by its name, see [[#CMOOSMsg Class|message class definition]].

## CMOOSApp
### `CMOOSApp` Lifecycle
```mermaid
stateDiagram-v2
 [*] --> OnStartup 

 OnStartup --> OnConnect : after it connects to MOOSDB
 state fork_state <<fork>>
 OnConnect --> fork_state : Run loop
 fork_state --> OnNewMail
 OnNewMail --> OnNewMail
 note left of OnNewMail : Runs at CommsTick speed

 fork_state --> Iterate
 Iterate --> Iterate
 note right of Iterate : Runs at AppTick speed

 fork_state --> [*] : quit
```
### `CMOOSApp` Class
The following is a non-exhaustive class diagram of `CMOOSApp`:
```mermaid
classDiagram
	class CMOOSApp{
		-string : name
		+Notify()
		+Register()
	}
```

## CMOOSMsg
### `CMOOSMsg` Class