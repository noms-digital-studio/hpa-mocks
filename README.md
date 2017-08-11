# HPA Mocks

# To build and run the fat JAR
```
./gradlew clean shadowJar
java -jar build/libs/hpa-mocks-all.jar --root-dir src/main/resources --port 9090
```

# To run via Gradle
```
./gradlew clean run
```

# To view default mappings
```
curl http://localhost:9090/__admin/
```

# Example request
```
curl -H "Authorization: token" http://localhost:9090/prisoners?firstName=john&lastName=smith
```


# Mappings

Must include the Authorization header (any value):

* GET lastName=surnamea > one match Firsta Surnamea
* GET lastName=sunameb > one match Firstb Surnameb
* GET lastName=surname% > the above two matches NB url encode % as %25 - todo define wildard operator
* GET anything else > 0 results response 
 
Without the Authorization header

* GET anything > 401 response
* POST /api/users/login > access token response
