sudo docker run --name postgres15 -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=secret -d postgres:15-alpine

brew install golang-migrate

migrate create -ext sql -dir db/migration -seq init_schema
migrate -path db/migration -database "postgresql://root:secret@UbuntuServer:5432/simple_bank?sslmode=disable" -verbose up



brew install sqlc

sqlc init  
make sqlc