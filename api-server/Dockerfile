FROM debian:buster-slim

ARG BNC_VERSION=0.8.1

WORKDIR /api-server

COPY --from=testnet-binaries /binaries/cli/testnet/${BNC_VERSION}/linux/tbnbcli ./

RUN echo 12345678 | ./tbnbcli keys add key

EXPOSE 8080

ENTRYPOINT ["./tbnbcli", "api-server", "--chain-id", "Binance-Dev", "-laddr", "tcp://0.0.0.0:8080", "--node"]