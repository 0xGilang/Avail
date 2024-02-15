# **Update and install packages for compiling**
```
$ sudo apt update
$ sudo apt install make clang pkg-config libssl-dev build-essential```
```
# **Create directory**
```
$ mkdir -p ${HOME}/avail-node/data
$ mkdir -p ${HOME}/avail-node/systemd
```
# **Download The Required Files**
- go to dir ~/avail-node for the setup validator
```
$ cd ~/avail-node
$ wget https://github.com/availproject/avail/releases/download/v1.8.0.0/amd64-ubuntu-2204-data-avail.tar.gz
```
- Extract binary
```
$ tar -xvzf amd64-ubuntu-2204-data-avail.tar.gz && rm amd64-ubuntu-2204-data-avail.tar.gz
$ mv amd64-ubuntu-2204-data-avail data-avail
```
# **Create a service file**
```
sudo tee /etc/systemd/system/availd.service > /dev/null <<EOF
[Unit]
Description=Avail Validator
After=network.target
StartLimitIntervalSec=0

[Service]
User=$USER
Type=simple
Restart=always
RestartSec=120
ExecStart=${HOME}/avail-node/data-avail --base-path ${HOME}/avail-node/data --chain goldberg --port 30333 --validator --name "YOUR_NAME_VALIDATOR"

[Install]
WantedBy=multi-user.target
EOF

sudo systemctl daemon-reload
sudo systemctl enable availd
```
# **Start node**
```
$ sudo systemctl start availd
```
# **Check node logs**
```
$ sudo journalctl -fu availd
```
# **The node will ouput the following when started:**
```
2023-06-03 20:36:29 Avail Node
2023-06-03 20:36:29 ✌️  version 1.6.0-99b85257d6b
2023-06-03 20:36:29 ❤️  by Anonymous, 2017-2023
2023-06-03 20:36:29 📋 Chain specification: Avail Kate Testnet
2023-06-03 20:36:29 🏷  Node name: bewildered-distance-1229
2023-06-03 20:36:29 👤 Role:Authority
2023-06-03 20:36:29 💾 Database: RocksDb at /Users/thunder/code/avail/data/chains/Avail Testnet_6831251e-0222-11ee-a2c3-c90377335962/db/full
2023-06-03 20:36:29 ⛓  Native runtime: data-avail-9 (data-avail-0.tx1.au11)
2023-06-03 20:36:35 👶 Creating empty BABE epoch changes on what appears to be first startup.
2023-06-03 20:36:35 🏷  Local node identity is: 12D3KooWPt7odw3aeq7azZDugXjNuUvQNPU58n1VRBzY1YBqsjkr
2023-06-03 20:36:35 Prometheus metrics extended with avail metrics
2023-06-03 20:36:35 💻 Operating system: macos
2023-06-03 20:36:35 💻 CPU architecture: aarch64
2023-06-03 20:36:35 📦 Highest known block at #0
2023-06-03 20:36:35 〽️ Prometheus exporter started at 127.0.0.1:9615
2023-06-03 20:36:35 Running JSON-RPC HTTP server: addr=127.0.0.1:9933, allowed origins=["http://localhost:*", "http://127.0.0.1:*", "https://localhost:*", "https://127.0.0.1:*", "https://polkadot.js.org"]
2023-06-03 20:36:35 Running JSON-RPC WS server: addr=127.0.0.1:9944, allowed origins=["http://localhost:*", "http://127.0.0.1:*", "https://localhost:*", "https://127.0.0.1:*", "https://polkadot.js.org"]
2023-06-03 20:36:35 🏁 CPU score: 724.71 MiBs
2023-06-03 20:36:35 🏁 Memory score: 41.49 GiBs
2023-06-03 20:36:35 🏁 Disk score (seq. writes): 1.91 GiBs
2023-06-03 20:36:35 🏁 Disk score (rand. writes): 454.66 MiBs
```
<img src="https://miro.medium.com/v2/resize:fit:1400/1*41gQVc240I_DMjVitORYSA.jpeg">

# **Contact Me🔥☕**
<p align="left">
<a href="https://www.github.com/0xGilang"><img height="40" width="40" align="center" src="https://avatars.githubusercontent.com/u/94946818?v=4"></a>
<a href="https://www.facebook.com/Gilangbuanasultoni" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/facebook.svg" alt="AryaTrickers2020" height="30" width="40" /></a>
<a href="https://wa.me/6282131561458?text=Halo+Bang+Gilang" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/whatsapp.svg" alt="6289694295787" height="30" width="40" /></a>
<a href="https://twitter.com/Gilangsultoni"><img height="40" width="40" align="center" src="https://static.dezeen.com/uploads/2023/07/x-logo-twitter-elon-musk_dezeen_2364_col_0.jpg"></a>

------
------

