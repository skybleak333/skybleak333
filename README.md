# Andrei Fedoseev

Senior PHP and Laravel engineer based in Valencia, Spain. I build backends for AI agents, with a focus on tracing answers to their sources and keeping queued work consistent through retries.

## Try my projects

- **Memory Policy Audit** checks the text and citations an agent gets when memory is stale or policies conflict. Run seven cases in the browser or test your own saved recall in CI. [Run the evaluation](https://skybleak333.github.io/memory-policy-audit/#evaluation) · [Compare publication cutoffs](https://skybleak333.github.io/memory-policy-audit/?as-of=2026-11-05&compare-known-on=2026-11-05&known-on=2026-11-10&recall=stale) · [CLI setup](https://github.com/skybleak333/memory-policy-audit#evaluate-policy-decisions-in-ci)
- **hindsight-php** gives Laravel, Symfony and Neuron agents long-term memory. The PHP client indexes Markdown in Hindsight 1.3 and retrieves passages with their source IDs. It also verifies signed webhooks. [Knowledge bank example](https://github.com/skybleak333/hindsight-php#knowledge-banks) · [Webhooks](https://github.com/skybleak333/hindsight-php#webhooks) · [Hindsight Integrations Hub](https://hindsight.vectorize.io/integrations)
- **laravel-queue-lab** reproduces failures with real Laravel workers. One test kills an AI worker after it queues an invoice email. Another interrupts the email provider's response and recovers the original receipt on retry. [Worker crash](https://github.com/skybleak333/laravel-queue-lab#experiment-7-an-invoice-outbox-through-a-worker-crash-and-failover) · [Lost provider response](https://github.com/skybleak333/laravel-queue-lab#experiment-8-an-invoice-email-after-a-lost-provider-response)

## Merged contributions

- **Hindsight** kept my fix and regression test for embedding migrations that mixed vectors from two models. I also co-authored a fix for retries that stored the same facts twice. [Embedding migration](https://github.com/vectorize-io/hindsight/pull/6509) · [Duplicate facts](https://github.com/vectorize-io/hindsight/commit/7c54d7cba6ec7a50078fae8669c55c424d0363d1)
- **OpenAI PHP** supports request-scoped tracing headers and reports HTTP failures from audio, downloads and agent events. I also added context compaction and token counting. [Tracing](https://github.com/openai-php/client/pull/864) · [HTTP errors](https://github.com/openai-php/client/pull/867) · [Compaction](https://github.com/openai-php/client/pull/845) · [Token counting](https://github.com/openai-php/client/pull/844)
- **MCP PHP SDK** reads stdio messages larger than the pipe buffer, so tools can receive large arguments. [PR #707](https://github.com/modelcontextprotocol/php-sdk/pull/707)
- **Bunny** lets RabbitMQ consumers open channels again after a failed reconnect. The fix followed a confirmed production hang. [PR #237](https://github.com/jakubkulhan/bunny/pull/237)
- **Symfony** keeps prefetched PostgreSQL jobs reserved while they wait for their turn and returns the full set of matching documents from its Redis vector store. [Messenger](https://github.com/symfony/symfony/pull/67993) · [Symfony AI](https://github.com/symfony/ai/pull/2895)

[More contributions](https://github.com/skybleak333/skybleak333/blob/main/CONTRIBUTIONS.md) · [LinkedIn](https://www.linkedin.com/in/andrey-fedoseev-skybleak/)
