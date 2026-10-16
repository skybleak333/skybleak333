# Andrei Fedoseev

Senior backend engineer based in Valencia, Spain.

I build PHP/Laravel services: APIs, background jobs, SSO integrations, and the systems that keep releases running reliably.

## Recent work

- **[laravel-queue-lab](https://github.com/skybleak333/laravel-queue-lab):** reproducible experiments with Laravel queue workers on a real broker. When a job outlives RabbitMQ's acknowledgement timeout, the worker exits and jobs run twice. When the broker freezes, `queue:work` with the default timeouts waits until it is back, even with heartbeats on. In maintenance mode, `rabbitmq:consume` ignores SIGTERM until `artisan up`.
- **[vyuldashev/laravel-queue-rabbitmq#680](https://github.com/vyuldashev/laravel-queue-rabbitmq/pull/680)** (under review): fixes `rabbitmq:consume` for the Worker API changes in Laravel 11.52+, 12.59+ and 13.x. With the released v15.0.2 it doesn't process jobs on Laravel 13.31+.
- **[Analysis of issue #664](https://github.com/vyuldashev/laravel-queue-rabbitmq/issues/664#issuecomment-6211004087):** tested the reported worker hang on RabbitMQ 3.13 with package versions from v14.1.0 to the current `master`; the workers exit, and the real problem is redelivery.

## Engineering interests

- **Queues and workers:** retries, connection failures, recovery, and safe restarts.
- **Release reliability:** what happens when old and new application versions run together.
- **AI-assisted development:** understanding, testing, and reviewing the code that coding tools produce.

## Stack

PHP · Laravel · PostgreSQL · Redis · RabbitMQ · Docker · Kubernetes

[Connect on LinkedIn](https://www.linkedin.com/in/andrey-fedoseev-skybleak/)
