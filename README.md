Consul Backup and Restore tool.

This will use consul-api (Go library) to recursively backup and restore all your
key/value pairs.

You need to set up your Go environment and "go get github.com/armon/consul-api"
and "go get github.com/docopt/docopt-go"

a "go build" will generate executable named "consul-backup"


Usage:
consul-backup [-i IP:PORT] [--restore] <filename>
consul-backup -h | --help
consul-backup --version

Options:
-h --help     Show this screen.
--version     Show version.
-i, --address=IP:PORT  The HTTP endpoint of Consul [default: 127.0.0.1:8500].
-r, --restore     Activate restore mode

Dockerized Version
==================
This app is Dockerized.

to build following changes docker build -t consul-backup .

To backup consul-kv simply run

`docker run --rm -d -v /tmp:/tmp consul-backup app -i <CONSUL-URL>:8500 /tmp/backup_consul`

To restore consul-kv simply run

`docker run --rm -d -v /tmp:/tmp consul-backup app -i <CONSUL-URL>:8500 --restore /tmp/backup_consul`
