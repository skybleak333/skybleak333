# Andrei Fedoseev

Senior backend engineer in Valencia, Spain. I build PHP/Laravel services: APIs, queues and background jobs, SSO integrations, and the systems that keep releases running reliably.

In open source, I look for bugs in the tools I use and report them with a reproduction, a failing test and, where I can, a fix.

## Open source

- **[Hindsight](https://github.com/vectorize-io/hindsight)** (~60k stars, no outside pull requests): five bug reports with reproductions, four with patches and one with a failing test; the maintainer fixed all five, each within four days. For [#6337](https://github.com/vectorize-io/hindsight/issues/6337), concurrent retries that stored facts twice, the [fix](https://github.com/vectorize-io/hindsight/pull/6433) keeps my failing test, and the [merged commit](https://github.com/vectorize-io/hindsight/commit/7c54d7cba6ec7a50078fae8669c55c424d0363d1) lists me as co-author. [#6335](https://github.com/vectorize-io/hindsight/issues/6335) was fixed in [#6408](https://github.com/vectorize-io/hindsight/pull/6408), which follows my patch, and [#6409](https://github.com/vectorize-io/hindsight/pull/6409); [#6280](https://github.com/vectorize-io/hindsight/issues/6280) was [fixed with thanks](https://github.com/vectorize-io/hindsight/pull/6318); [#6231](https://github.com/vectorize-io/hindsight/issues/6231) shipped in v1.2.0; [#6235](https://github.com/vectorize-io/hindsight/issues/6235). Open: [#6444](https://github.com/vectorize-io/hindsight/issues/6444), the follow-ups #6408 left, with tests and a patch.
- **[hindsight-php](https://github.com/skybleak333/hindsight-php):** long-term memory for Laravel AI SDK agents on the open-source [Hindsight](https://github.com/vectorize-io/hindsight) server. It stores memories through the Laravel queue, and a retry never stores one twice; `Hindsight::fake()` makes it testable, and [v0.3](https://github.com/skybleak333/hindsight-php/releases/tag/v0.3.0) ships a Laravel Boost skill for coding agents. CI runs against real Hindsight 1.1 and 1.2 servers.
- **[php-amqplib#1248](https://github.com/php-amqplib/php-amqplib/pull/1248)** (under review): fixes [#1227](https://github.com/php-amqplib/php-amqplib/issues/1227) in the main PHP AMQP client. The heartbeat check counted the client's own writes, so a consumer whose network dropped never noticed. Reproduced with toxiproxy; opt-in, so proxies that send heartbeats differently (AMQProxy before 3.2.1) aren't affected. [#1249](https://github.com/php-amqplib/php-amqplib/pull/1249) fixes [#1243](https://github.com/php-amqplib/php-amqplib/issues/1243): the error handler around socket calls turned unrelated deprecations into exceptions.
- **[laravel-queue-lab](https://github.com/skybleak333/laravel-queue-lab):** reproducible experiments with Laravel workers on a real RabbitMQ broker: jobs that run twice after an acknowledgement timeout, a frozen broker that `queue:work` doesn't notice, and `rabbitmq:consume` ignoring SIGTERM in maintenance mode.
- **[vyuldashev/laravel-queue-rabbitmq#680](https://github.com/vyuldashev/laravel-queue-rabbitmq/pull/680)** (under review): fixes `rabbitmq:consume` for the Worker API changes in Laravel 11.52+, 12.59+ and 13.x. With the released v15.0.2 it doesn't process jobs on Laravel 13.31+. [#684](https://github.com/vyuldashev/laravel-queue-rabbitmq/pull/684) builds on it: in maintenance mode a paused `rabbitmq:consume` ignored SIGTERM, `queue:restart` and `--max-time`.
- **Queue reliability checks for other people's issues:** an [analysis of #664](https://github.com/vyuldashev/laravel-queue-rabbitmq/issues/664#issuecomment-6211004087) (the reported hang is really redelivery), an [independent check of PR #674](https://github.com/vyuldashev/laravel-queue-rabbitmq/pull/674#issuecomment-6239412564), and [measurements for php-amqplib#1227](https://github.com/php-amqplib/php-amqplib/issues/1227#issuecomment-6239409018).

## Engineering interests

- **Queues and workers:** retries, connection failures, recovery, and safe restarts.
- **Release reliability:** what happens when old and new application versions run together.
- **AI-assisted development:** understanding, testing, and reviewing the code that coding tools produce.

## Stack

PHP · Laravel · PostgreSQL · Redis · RabbitMQ · Docker · Kubernetes

[Connect on LinkedIn](https://www.linkedin.com/in/andrey-fedoseev-skybleak/)
