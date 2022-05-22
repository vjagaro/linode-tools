# linode-tools

Simplified Linode instance tools.

## Usage

Configure:

```sh
cat >config <<EOF
LINODE_API_TOKEN=aa02....d9c2
LINODE_LABEL=label
LINODE_IMAGE=linode/debian11
LINODE_TYPE=g6-nanode-1
LINODE_CONNECT_METHOD=ipv4
LINODE_DOMAIN=domain.com
LINODE_DOMAIN_RECORD=name
EOF

export LINODE_TOOL_CONFIG=config
```

Check the status:

```sh
linode-tool status
```

Create the instance and associated domain records:

```sh
linode-tool create
```

Run `script.sh` on the instance:

```sh
linode-tool -s script.sh update
```

SSH into the instance:

```sh
linode-tool ssh
```

Delete the instance and associated domain records:

```sh
linode-tool delete
```

Get help and usage information:

```sh
linode-api --help
linode-create --help
linode-delete --help
linode-dns --help
linode-list --help
linode-query --help
linode-tool --help
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
