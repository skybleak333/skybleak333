# Andrei Fedoseev

Senior backend engineer based in Valencia, Spain.

I build PHP/Laravel services: APIs, background jobs, SSO integrations, and the systems that keep releases running reliably.

## Recent work

- **Bug reports with reproductions and patches for [Hindsight](https://github.com/vectorize-io/hindsight)**, an agent memory server with ~59k stars that doesn't take outside pull requests. The maintainer fixed all three within four days: [#6231](https://github.com/vectorize-io/hindsight/issues/6231), 500 errors on malformed input (shipped in v1.2.0); [#6235](https://github.com/vectorize-io/hindsight/issues/6235), ids that could never be read again; [#6280](https://github.com/vectorize-io/hindsight/issues/6280), a bank clone that silently took over another bank's alias ([fixed with thanks](https://github.com/vectorize-io/hindsight/pull/6318)). Latest: [#6335](https://github.com/vectorize-io/hindsight/issues/6335), concurrent restores that store every fact twice.
- **[hindsight-php](https://github.com/skybleak333/hindsight-php):** a PHP client for [Hindsight](https://github.com/vectorize-io/hindsight) agent memory, with long-term memory for Laravel AI SDK agents. One middleware recalls what the agent knows about the user before it answers and stores the exchange after it. [v0.2](https://github.com/skybleak333/hindsight-php/releases/tag/v0.2.0) stores memories through the Laravel queue, so they wait out an outage of the Hindsight API, and a retry never stores one twice: every attempt carries the same operation ID. `Hindsight::fake()` makes agent memory testable without a server. CI runs the tests against real Hindsight 1.1 and 1.2 servers.
- **[laravel-queue-lab](https://github.com/skybleak333/laravel-queue-lab):** reproducible experiments with Laravel queue workers on a real broker. When a job outlives RabbitMQ's acknowledgement timeout, the worker exits and jobs run twice. When the broker freezes, `queue:work` with the default timeouts waits until it is back, even with heartbeats on. In maintenance mode, `rabbitmq:consume` ignores SIGTERM until `artisan up`.
- **[vyuldashev/laravel-queue-rabbitmq#680](https://github.com/vyuldashev/laravel-queue-rabbitmq/pull/680)** (under review): fixes `rabbitmq:consume` for the Worker API changes in Laravel 11.52+, 12.59+ and 13.x. With the released v15.0.2 it doesn't process jobs on Laravel 13.31+.
- **[Analysis of issue #664](https://github.com/vyuldashev/laravel-queue-rabbitmq/issues/664#issuecomment-6211004087):** tested the reported worker hang on RabbitMQ 3.13 with package versions from v14.1.0 to the current `master`; the workers exit, and the real problem is redelivery.
- **[Independent check of PR #674](https://github.com/vyuldashev/laravel-queue-rabbitmq/pull/674#issuecomment-6239412564)** in the same package: the heartbeat fix works on a frozen broker, and `--wait-timeout=0` brings the bug back.
- **[Measurements for php-amqplib#1227](https://github.com/php-amqplib/php-amqplib/issues/1227#issuecomment-6239409018):** the proposed heartbeat fix helps polling consumers but breaks clients that only publish.

## Engineering interests

- **Queues and workers:** retries, connection failures, recovery, and safe restarts.
- **Release reliability:** what happens when old and new application versions run together.
- **AI-assisted development:** understanding, testing, and reviewing the code that coding tools produce.

## Stack

PHP · Laravel · PostgreSQL · Redis · RabbitMQ · Docker · Kubernetes

[Connect on LinkedIn](https://www.linkedin.com/in/andrey-fedoseev-skybleak/)
