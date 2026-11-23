# Andrei Fedoseev

Senior PHP and Laravel engineer based in Valencia, Spain. I build APIs, queues and integrations. My open-source work focuses on AI agent infrastructure and what happens when a request, a worker or a connection fails.

## What I build

- **hindsight-php** adds long-term memory to Laravel AI SDK, Laravel MCP, Symfony AI and Neuron AI. Laravel agents can filter and cite recalled facts before generation and queue writes for retry after an outage. [Project](https://github.com/skybleak333/hindsight-php) · [Latest release](https://github.com/skybleak333/hindsight-php/releases/tag/v0.15.0) · [Hindsight Integrations Hub](https://hindsight.vectorize.io/integrations)
- **Memory Policy Audit** uses Neo4j Relate to recover the current policy and its citation when Hindsight finds only an outdated revision. It works with Laravel AI agents and MCP clients. [Live demo](https://skybleak333.github.io/memory-policy-audit/?recall=stale) · [MCP setup](https://github.com/skybleak333/memory-policy-audit#look-up-policies-from-an-mcp-client)
- **laravel-queue-lab** reproduces worker failures in CI, including a Laravel AI SDK tool running twice after provider failover and RabbitMQ redelivering a job after an acknowledgement timeout. [Experiments](https://github.com/skybleak333/laravel-queue-lab)

## Merged contributions

- **Hindsight** kept my regression test and fix for an interrupted embedding migration that mixed vectors from two models. I also co-authored the fix for concurrent retries storing the same facts twice. [Embedding migration](https://github.com/vectorize-io/hindsight/pull/6509) · [Duplicate facts](https://github.com/vectorize-io/hindsight/commit/7c54d7cba6ec7a50078fae8669c55c424d0363d1)
- **MCP PHP SDK** now reads stdio messages larger than the pipe buffer, so tool calls with large arguments get a response. [PR #707](https://github.com/modelcontextprotocol/php-sdk/pull/707)
- **OpenAI PHP** can compact the context of long Responses API conversations and count input tokens before sending a request. [Context compaction](https://github.com/openai-php/client/pull/845) · [Token counting](https://github.com/openai-php/client/pull/844)
- **Symfony AI** now returns all documents from a Redis vector search. [PR #2895](https://github.com/symfony/ai/pull/2895)
- **Symfony Messenger** now keeps fetched PostgreSQL jobs alive while they wait for their turn in a worker's batch. [PR #67993](https://github.com/symfony/symfony/pull/67993)

[More contributions](https://github.com/skybleak333/skybleak333/blob/main/CONTRIBUTIONS.md) · [LinkedIn](https://www.linkedin.com/in/andrey-fedoseev-skybleak/)
