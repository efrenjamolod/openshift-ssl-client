# OpenShift Image Scanner

To create OCP objects:
```
oc process -f template.yml | oc create -f -
```
To build and run the image:
```
mvn clean package
oc start-build ssl-client --from-file=target/ssl-client-0.0.1-SNAPSHOT.jar
```
After the build completes, a deployment will be triggered with a secure route exposed.
Hit the /secured endpoint on the route!