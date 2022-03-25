## Running JUnits

The service includes a JUnit to showcase how unit testing can be implemented for Camel Quarkus implementations.

Run the JUnits with the command below:

```shell script
./mvnw clean test
```

## Running the service (in dev mode)

>**Note**: the stub needs to be up and running for a successful end-to-end execution. Refer to the stub's Readme doc for instructions to run it.

Run it locally executing the command below:

```shell script
./mvnw clean compile quarkus:dev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.


## Test with cURL

You can send a `GET` request with the following `curl` command:

```
curl \
-X GET \
http://localhost:8080/camel/individual/details/123
```

## Discover and test with the Swagger UI

You can display the Swagger UI by:
 1. Entering its URL in your browser's address bar
 2. via the dev UI (SmallRye OpenApi tile) 


To open the Swagger UI by opening the URL in a browser, enter:

 - http://localhost:8080/camel/openapi.json

Click on the service to try, and hit the `Try it out` button, scroll down and then click `Execute`


Or, from your running Camel Quarkus terminal, press `[d]`, it will open the dev UI in your default brower. Find the SmallRye tile, and click **Swagger UI**


<br>

## Deploying to Openshift

Ensure you create/switch-to the namespace where you want to deploy the stub.

Run the following command to trigger the deployment:
```shell script
./mvnw mvn clean package -DskipTests -Dquarkus.kubernetes.deploy=true
```

To test the stub once deployed, open a tunnel with the following command:
```
oc port-forward service/simple 8080
```

Open the Swagger UI by opening the URL in a browser

 - http://localhost:8080/camel/openapi.json

Click on the service to try, and hit the `Try it out` button, scroll down and then click `Execute`


You can also send a `GET` request with the following `curl` command:

```
curl \
-X GET \
http://localhost:8080/camel/individual/details/123
```
