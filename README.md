# Circom Setup

Install Rust + Circom + NodeJS + SnarkJS:
```
docker run --rm -it --name ubuntu ubuntu:latest bash
apt update
apt install curl git build-essential nodejs npm vim
npm install -g snarkjs
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
. "$HOME/.cargo/env"
cd usr/src
git clone https://github.com/iden3/circom.git
cd circom
cargo build --release
cargo install --path circom
```

# Compile a circuit
```bash
circom circuit.circom --r1cs --wasm --sym --c
```

# Paillier encryption scheme
```circom
(g ** message % n2) * (random ** n % n2) % n2
```
