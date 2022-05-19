# linode-tools

An opinionated set of shell scripts to help manage Linode instances.

## Usage

```
$ export LINODE_API_TOKEN=3f...b1

$ linode-list
Label | ID | IPv4 | IPv6 | Region  | Status

$ linode-query -l purple
Querying linode purple...not found

$ linode-create -l purple
Querying linode purple...not found
Querying SSH keys...ok
Creating linode purple...ok

 Label: purple
    ID: 36406452
Status: provisioning
  IPV4: 74.207.246.120
  IPV6: 2600:3c01::f03c:93ff:fe1f:a1c9
Region: us-west
 Image: linode/debian11
  Type: g6-nanode-1
Create: yes

$ linode-create -l purple
Querying linode purple...ok

 Label: purple
    ID: 36406452
Status: running
  IPV4: 74.207.246.120
  IPV6: 2600:3c01::f03c:93ff:fe1f:a1c9
Region: us-west
 Image: linode/debian11
  Type: g6-nanode-1
Create: no

$ linode-list
Label  | ID       | IPv4            | IPv6                           | Region  | Status
purple | 36406452 | 74.207.246.120  | 2600:3c01::f03c:93ff:fe1f:a1c9 | us-west | running

$ linode-delete -l purple
Querying linode purple...ok

 Label: purple
    ID: 36406452
Status: running
  IPV4: 74.207.246.120
  IPV6: 2600:3c01::f03c:93ff:fe1f:a1c9
Region: us-west
 Image: linode/debian11
  Type: g6-nanode-1

Deleting linode purple...ok

 Label: purple
    ID: 36406452
Delete: yes
```

## Install

```sh
mkdir -p "$HOME/.local"
git clone https://github.com/vjagaro/linode-tools.git "$HOME/.local/linode-tools"
echo >> "$HOME/.profile"
echo 'PATH="$HOME/.local/linode-tools/bin:$PATH"' >> "$HOME/.profile"
```

These scripts depend on `curl` and `jq` being installed:

```sh
sudo apt-get install -y curl jq
```
