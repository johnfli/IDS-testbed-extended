# Extended International Data Space Association (IDSA) testbed

The well-known [IDS-testbed](https://github.com/International-Data-Spaces-Association/IDS-testbed) extended with UIs, persistence for IDS Connectors and IDS Broker offered in the form of an easy-to-deploy docker compose network. 

## What is added?

The [IDS-testbed](https://github.com/International-Data-Spaces-Association/IDS-testbed) provided by [IDSA](https://internationaldataspaces.org/) has some limitations, which have been adressed in the present repo. To be concise, the contribution of this work extends the existing network by integrating the following features:

1. **User Interfaces (UIs) for both testbed connectors**, utilizing the [Dataspace Connector UI](https://github.com/International-Data-Spaces-Association/DataspaceConnectorUI) provided by [IDSA](https://internationaldataspaces.org/)
2. **Frontend & User Interface (UI) for the testbed broker**, utilizing the [IDS Metadata Broker Open Frontend](https://github.com/International-Data-Spaces-Association/ids-metadata-broker-open-frontend) provided by [IDSA](https://internationaldataspaces.org/)
  
3. **Persistence for both testbed connectors**, utilizing one [postgresql](https://www.postgresql.org/) per connector, in order for the data stored to persist across voluntary and involuntary container restarts.


## How to deploy?

1. Git clone this repository to your local machine

   ```sh
   git clone https://github.com/International-Data-Spaces-Association/IDS-testbed.git
   ``` 

2. Navigate into the directory
   
   ```sh
   cd IDS-testbed
   ``` 


3. Copy the provided docker-compose-johnfli.yaml into the current (IDS-testbed) directory
   
   E.g.
   ```sh
   cp ~/Downloads/docker-compose-johnfli.yaml ~/IDS-testbed/docker-compose-johnfli.yaml
   ```

4. Make sure you have installed [Docker](https://docs.docker.com/engine/install/ubuntu/) and [Docker Compose](https://docs.docker.com/engine/install/ubuntu/) on your machine. [OPTIONAL] You are also recommended to follow the [Post-installation steps for Linux](https://docs.docker.com/engine/install/linux-postinstall/). To start the testbed, run 
   
   ```sh
   docker compose -f docker-compose-johnfli.yaml up -d
   ``` 
   
   OR

   ```sh
   docker-compose -f docker-compose-johnfli.yaml up -d
   ```
   
5. Find the connectors and corresponding UIs in the following URLs:
   1. Connector A: https://localhost:9080 
      - Credentials: admin/password
      - Swagger: https://localhost:9080/api/docs
   2. Connector B: https://localhost:9081
      - Credentials: admin/password
      - Swagger: https://localhost:9081/api/docs
   3. Connector A UI: https://localhost:9090
      - Credentials: connectorauser/connectorapw
   4. Connector B UI: https://localhost:9091
      - Credentials: connectorbuser/connectorbpw

6. Run the [Postman collection](https://github.com/International-Data-Spaces-Association/IDS-testbed/blob/master/TestbedPreconfiguration.postman_collection.json) to start the tests. Current available components for testing are: Dataspace connector, DAPS, CA, Metadata Broker.
   - We offer a customized [Postman collection](https://github.com/International-Data-Spaces-Association/IDS-testbed/blob/master/TestbedPreconfiguration.postman_collection.json) for the needs of our configuration, which you may use to verify the network connectivity and functionality.

7. Test the compatibility of your own developed component following the steps of the [Testbed User Guide](./TestbedUserGuide.md).

8. Download the [Test Suite](https://gitlab.cc-asp.fraunhofer.de/ksa/ids-certification-testing) and follow the instructions to conduct automated tests for your own developed connector.


## How to build custom UI images?

### Dataspace Connector UI

- To be filled

### IDS Metadata Broker Open Frontend

- To be filled

