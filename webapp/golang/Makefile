all: app

app: *.go go.mod go.sum
	go build -o app

restart: app
	rm -f /tmp/webapp.sock
	sudo systemctl restart isu-go
	sudo systemctl status isu-go | tail -n 5
