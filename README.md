# AWS_IOT_ROBOT_JAVA
AWS IOT Robot: Project in Java for the AWS IoT service to be used on any internet connectivity capable device.

### Prerequisities

- Maven is the only requirement for building the project. Dependencies are managed by Maven.
- Register an IoT device on the AWS IoT dashboard and generate and attach the necessary certificates and policies to it.
- Download the client certificate, client private and the root CA certificate 

Add the following dependencies to the POM file of your Maven project.
```
<dependency>
    <groupId>com.amazonaws</groupId>
    <artifactId>aws-iot-device-sdk-java</artifactId>
    <version>1.0.0</version>
</dependency>
<dependency>
    <groupId>com.googlecode.json-simple</groupId>
    <artifactId>json-simple</artifactId>
    <version>1.1</version>
</dependency>
```

## Use the AWS IoT device SDK

[API documentation](http://aws-iot-device-sdk-java-docs.s3-website-us-east-1.amazonaws.com)

## Config file

```
AWS_IOT_MQTT_HOST = <Your personal endpoint, e.g. *.iot.*.amazonaws.com>
AWS_IOT_MQTT_PORT = <Your personal enpoint port, e.g 8883>
AWS_IOT_MQTT_CLIENT_ID = <Your client id, e.g. RaspberryPi>
AWS_IOT_MY_THING_NAME = <Your thing name, e.g. RaspberryPi>
AWS_IOT_ROOT_CA_FILENAME = <Your root CA certificate filename, e.g. root-ca.pem>
AWS_IOT_CERTIFICATE_FILENAME = <Your certificate filename, e.g. client-cert.pem>
AWS_IOT_PRIVATE_KEY_FILENAME = <Your private key filename, e.g. private-key.pem>
AWS_IOT_PUBLISH_TOPIC_NAME=<Topic where you will publish messages for device, e.g. MyTopic>
AWS_IOT_SUBSCRIBE_TOPIC_NAME=<Topic where device will publish messages for you, e.g. DeviceTopic>
AWS_IOT_QOS_LEVEL=<0|1>
```
## Installing

Creating the package is as simple as

```
mvn clean package
```
This will create an jar (Shade-Plugin) with all dependencies baked into the jar-file.

## Running

```
java -jar AwsIotRobotManager.jar PATH_TO_CONFIG_FILE
```
