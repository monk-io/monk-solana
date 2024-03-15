# monk-solana

This repository contains Monk.io template to deploy Solana (https://github.com/solana-labs/solana).

## Prerequisites

- Install Monk
- Register and Login Monk
- Add Cloud Provider

## Clone Repository

```bash
git clone https://github.com/monk-io/monk-solana
```

## Load Template

```bash
cd monk-solana
monk load MANIFEST
```

## Deploy

```bash
➜ monk run solana/stable
? Select tag to run [local/solana/stable] on: prod
✔ Starting the run job: local/solana/stable... DONE
✔ Preparing nodes DONE
✔ Checking/pulling images...
✔ [================================================] 100% docker.io/solanalabs/solana:stable sergtest2-3
✔ Checking/pulling images DONE
✔ Starting containers DONE
✔ Runnable templates/local/solana/stable connections graph updating DONE
✔ Runnable templates/local/solana/stable connections graph has been updated DONE
✔ Runnable templates/local/solana/stable services initialization DONE
✔ Runnable templates/local/solana/stable services have been initialized DONE
✔ Host ports have been added to container f4b1b192618c74952ece0815644c51d8-lana-stable-solana-node DONE
✔ New container f4b1b192618c74952ece0815644c51d8-lana-stable-solana-node created DONE
✔ Container f4b1b192618c74952ece0815644c51d8-lana-stable-solana-node network has been configured DONE
✔ Container f4b1b192618c74952ece0815644c51d8-lana-stable-solana-node has been started DONE
✔ Started local/solana/stable
🔩 templates/local/solana/stable
 └─🧊 Peer sergtest
    └─🔩 templates/local/solana/stable
       └─📦 f4b1b192618c74952ece0815644c51d8-lana-stable-solana-node running
          ├─🧩 docker.io/solanalabs/solana:stable
          ├─💾 /var/lib/monkd/volumes/solana -> /usr/bin/config/
          ├─🔌 open (public) UDP 34.82.164.115:8000 -> 8000
          ├─🔌 open (public) TCP 34.82.164.115:8902 -> 8902
          ├─🔌 open (public) TCP 34.82.164.115:8901 -> 8901
          ├─🔌 open (public) UDP 34.82.164.115:8003 -> 8003
          ├─🔌 open (public) TCP 34.82.164.115:8900 -> 8900
          ├─🔌 open (public) UDP 34.82.164.115:8007 -> 8007
          ├─🔌 open (public) TCP 34.82.164.115:8001 -> 8001
          ├─🔌 open (public) UDP 34.82.164.115:8008 -> 8008
          ├─🔌 open (public) UDP 34.82.164.115:8004 -> 8004
          ├─🔌 open (public) UDP 34.82.164.115:8006 -> 8006
          ├─🔌 open (public) UDP 34.82.164.115:8009 -> 8009
          ├─🔌 open (public) UDP 34.82.164.115:8002 -> 8002
          ├─🔌 open (public) UDP 34.82.164.115:8001 -> 8001
          ├─🔌 open (public) UDP 34.82.164.115:8005 -> 8005
          ├─🔌 open (public) TCP 34.82.164.115:9900 -> 9900
          └─🔌 open (public) TCP 34.82.164.115:8899 -> 8899

💡 You can inspect and manage your above stack with these commands:
        monk logs (-f) local/solana/stable - Inspect logs
        monk shell     local/solana/stable - Connect to the container's shell
        monk do        local/solana/stable/action_name - Run defined action (if exists)
💡 Check monk help for more!
```

## Check health

```bash
curl http://{{IP}}:8899 -X POST -H "Content-Type: application/json" -d '
{
  "jsonrpc": "2.0",
  "id":1,
  "method": "getVersion"
}'
```

## Variables

You could check details of configuration here: https://docs.solanalabs.com/operations/setup-a-validator#create-a-validator-startup-script
