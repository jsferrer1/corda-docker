# Corda Docker

## Build
```
git clone git@github.com:corda/samples.git

cd samples/cordapp-example

./gradlew clean workflows-kotlin:deployNodes
```

## Corda Tool Network Builder
- either download from [link](https://software.r3.com/artifactory/corda-releases/net/corda/corda-tools-network-builder/4.1/corda-tools-network-builder-4.1.jar) or
- build from source
```
git clone git@github.com:corda/corda.git

./gradlew clean assemble
```

## Start the Nodes
```
cd workflows-kotlin/build/nodes

java -jar ~/corda/tools/network-builder/build/libs/network-builder.jar -d .

docker ps
```

## Test the Flows
```
ssh user1@localhost -p 32773

flow start ExampleFlow$Initiator iouValue: 50, otherParty: "O=PartyB,L=New York,C=US"
```

## Tear down
```
docker system prune -a
docker volume prune
```

## References:
[corda-network-builder](https://docs.corda.net/network-builder.html#quickstart-local-docker)
[cordapp-tutorial](https://docs.corda.net/releases/release-V4.0/tutorial-cordapp.html)