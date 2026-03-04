# Install jar file
mvn install:install-file \
  -Dfile=/path/to/your.jar \
  -DgroupId=com.example \
  -DartifactId=yourlib \
  -Dversion=1.0 \
  -Dpackaging=jar
