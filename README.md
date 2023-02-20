## Task "Delivering by drones"
**The project is not ready for review**
### Build
To build the service (create JAR) use following command:
```
./gradlew build
```
### Run
Command to run service:
```
java -jar build/libs/drontask-0.1.jar
```
DB H2 console available at http://localhost:8080/api/v1/h2-console  
### Implementation Notes
#### REST API requests
##### Get a list of drones available for delivery parcel with a total weight:  &lt;weight-in-grams&gt;

Example

http://localhost:8080/api/v1/dron/available?weight=450

Result

```
[
{"id": 8,"imei": "SERIALNUMBER0008","model": "Heavyweight","maxweight": 500,"battery": 30,"state": "IDLE"}
. . .
{"id": 8,"imei": "SERIALNUMBER0018","model": "Heavyweight","maxweight": 450,"battery": 80,"state": "IDLE"}
]
```
#### Additional db table
to be written
#### Battery checker
to be written
### Dron :: Finite-state machine
```mermaid
graph TD;
    IDLE-->LOADING;
    LOADING-->LOADED;
    LOADING-->IDLE;
    LOADED-->DELIVERING;
    DELIVERING-->DELIVERED;
    DELIVERED-->RETURNING;
```
### Next tasks in the project development (TODO)
- **exception handling** and understandable detailed messages when errors occur during entity validation ( maxweight > 600, battery > 100, ....);
- define logs dir relative to application jar path (not to the current dir);
- define BatteryChecker interval in app properties;
- create command **shutdown** service;
- handle **kill** service PID;
- jUnit tests;
