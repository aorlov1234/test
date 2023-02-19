## Task "Delivering by drones"
**not ready for review**
### Build
To build the service (create JAR) use following command:
```
./gradlew build
```
### Run
Ccommand to run service:
```
java -jar build/libs/drontask-0.1.jar
```
DB H2 console available at 'http://localhost:8080/api/v1/h2-console'  
### Implementation Notes
#### REST API requests
to be written
#### Additional db table
to be written
#### Battery checker
to be written

### Next steps in task development
to be written
- define logs dir relative to application dir (not to the current dir)
- define BatteryChecker interval in app properties
- create command **shutdown** service ;
- handle **kill** service pid;
