# Results: 231 SGLang Serving Latency Benchmark

**Main goal:** Measure SGLang concurrent serving latency percentiles under load  
**Tools:** Every profile starts sglang.launch_server with Mistral-7B-v0.3, then bench_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_142 · recorded 2026-11-16). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · Intel(R) Xeon(R) Platinum 8452Y · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-16T12:33:04Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 08:14 · benchmark 00:05 · whole run 08:39
- **Source:** run 231_20261116_123304
- **Command:** `bash run_benchmark.sh --smoke --dtype bfloat16 --input-len 64 --output-len 16 --max-total-tokens 1024 --model-name mistralai/Mistral-7B-v0.3 --max-concurrency 2 --max-running-requests 2 --num-prompts 2`

| # | Metric | Result |
|---|---|---|
| 1 | E2E latency p50, client-observed from send, ms (end_to_end_request_latency_p50_msec) | 376.68659212067723 |
| 2 | TTFT p50, client-observed from send, ms (ttft_p50_msec) | 65.00471895560622 |
| 3 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 19.514736750473578 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 19.423986319452524 |
| 5 | Request throughput (request_throughput_requests_sec) | 5.2840129251704955 |
<!-- /profile:smoke -->
