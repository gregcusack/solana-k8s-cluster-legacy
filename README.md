docker containers for solana validators
Builds off of: https://github.com/yihau/solana-local-cluster


build containers here with:
bootstrap:
```
sudo docker build -t solana-bootstrap-validator:latest -f bootstrap-validator/Dockerfile .
```

validator:
```
sudo docker build -t solana-validator:latest -f validator/Dockerfile .
```

Run bootstrap:
````
docker run -it -d --name bootstrap --network=solana-cluster --ip=192.168.0.101 solana-bootstrap-validator:latest
```

Run validator:
```
docker run -it -d --name validator --network=solana-cluster --ip=192.168.0.102 solana-validator:latest
```
