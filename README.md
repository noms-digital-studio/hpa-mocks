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
curl http://localhost:9090/prisoners?given_name=john&surname=smith
```