# magic8bot

Automated cryptocurrency trading requires exchange data, strategy signals, and order execution to work together. magic8bot is a TypeScript bot that runs on Node.js and uses MongoDB to store trading data.

**Trading can lose money. Review your configuration and monitor the bot whenever it is running.**

## Features

- Sync trade data from an exchange into MongoDB.
- Generate OHLCV candles from trade data.
- Calculate trading signals with the implemented strategies and technical indicators.
- Open and close positions through the order component.
- Connect through the included `coinbasepro` and `binance` adapters, or add an adapter under `src/exchange/adapters` for another CCXT-supported exchange.

The strategy and indicator selection is limited. Check exchange API compatibility before using an adapter; an included adapter does not guarantee that an exchange still accepts its requests.

## Installation

Install Node.js with npm and make sure MongoDB is running and reachable. From your local checkout of magic8bot:

```sh
cd magic8bot
npm install
cp .env-sample .env
```

Edit `.env` using `.env-sample` as the reference for the available settings. Configure the database connection and any exchange credentials required by your setup. Keep credentials out of version control.

The upstream UI is optional and is not needed to start the bot. It is a separate project, not part of this installation.

## Usage

Start the bot from the project directory:

```sh
npm --loglevel=info run start:dev
```

The `--loglevel=info` argument controls npm's logging; the bot reads its configuration from `.env`. The `start:dev` script starts the development process.

Review the selected exchange, trading pair, and strategy parameters before starting. Default parameters may underperform a buy-and-hold strategy. Stop the process with `Ctrl+C` if you need to interrupt it, and verify any open orders or positions directly with the exchange afterward.

<!-- seorepo:network:start -->
## More tools from our network

- [**octo-cli**](https://github.com/boostlyapi/octo-cli) — CLI на Go для публикации данных из PostgreSQL, MSSQL и MySQL через бессерверные веб-сервисы в OpenFaaS или Knative. Конфигурация сервиса задаётся в YAML.
- [**tool**](https://github.com/boostlyapi/tool) — CLI на Go для Apache Kafka: чтение и отправка сообщений в JSON, просмотр топиков, управление смещениями consumer groups и базовое администрирование.
- [**docker-ikev2-vpn-server**](https://github.com/Cabral-it/docker-ikev2-vpn-server) — Docker-based IKEv2 VPN server with shared-secret authentication and .mobileconfig generation for iOS and macOS, based on gaomd/docker-ikev2-vpn-server.
- [**akrobateo**](https://github.com/Dyooooou/akrobateo) — A Go Kubernetes operator that exposes LoadBalancer services through node hostPorts using DaemonSets and synchronizes their load balancer addresses.
- [**node-hnsn**](https://github.com/ghb13/node-hnsn) — A TypeScript node for decentralized document timestamping with Bitcoin and IPFS, with an HTTP API for signed work claims and file uploads.
- [**wg-access-server**](https://github.com/EngHirsi/wg-access-server) — A WireGuard VPN server with a web UI for user authentication, one-click device registration, QR-code setup, and configurable network isolation.
<!-- seorepo:network:end -->

## License

MIT. This project is based on [magic8bot/magic8bot](https://github.com/magic8bot/magic8bot), which is distributed under the MIT License. Retain the upstream copyright and permission notice in copies or substantial portions of the software. See `LICENSE` for the license text.
