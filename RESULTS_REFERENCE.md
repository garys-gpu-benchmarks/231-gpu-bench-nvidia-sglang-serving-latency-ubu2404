# Results: 231 SGLang Serving Latency Benchmark

**Main goal:** Measure SGLang concurrent serving latency percentiles under load  
**Tools:** Every profile starts sglang.launch_server with Mistral-7B-v0.3, then bench_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_146 · recorded 2026-11-18). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.112.07
- **Run:** 2026-11-18T11:42:50Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 05:40 · benchmark 00:05 · whole run 06:01
- **Source:** run 231_20261118_114250
- **Command:** `bash run_benchmark.sh --smoke --dtype bfloat16 --input-len 64 --output-len 16 --max-total-tokens 1024 --model-name mistralai/Mistral-7B-v0.3 --max-concurrency 2 --max-running-requests 2 --num-prompts 2`

| # | Metric | Result |
|---|---|---|
| 1 | E2E latency p50, client-observed from send, ms (end_to_end_request_latency_p50_msec) | 232.5638720067218 |
| 2 | TTFT p50, client-observed from send, ms (ttft_p50_msec) | 34.640094003407285 |
| 3 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 12.376802932703868 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 11.981799005297944 |
| 5 | Request throughput (request_throughput_requests_sec) | 8.559978120922946 |
<!-- /profile:smoke -->
