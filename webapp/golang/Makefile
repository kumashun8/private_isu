all: app

app: *.go go.mod go.sum
	go build -o app

restart: app restart-app restart-nginx

restart-app: app
	rm -f /tmp/webapp.sock
	sudo systemctl restart isu-go
	sudo systemctl status isu-go | tail -n 5

restart-nginx:
	sudo nginx -s reload
	sudo systemctl status nginx | tail -n 5