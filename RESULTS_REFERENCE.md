# Results: 231 SGLang Serving Latency Benchmark

**Main goal:** Measure SGLang concurrent serving latency percentiles under load  
**Tools:** Every profile starts sglang.launch_server with Mistral-7B-v0.3, then bench_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_140 · recorded 2026-11-13). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 PCIe (81559 MiB) · Intel(R) Xeon(R) Platinum 8352Y CPU @ 2.20GHz · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-13T22:22:37Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 08:27 · benchmark 02:39 · whole run 11:38
- **Source:** run 231_20261113_222237
- **Command:** `bash run_benchmark.sh --smoke --dtype bfloat16 --input-len 64 --output-len 16 --max-total-tokens 1024 --model-name mistralai/Mistral-7B-v0.3 --max-concurrency 2 --max-running-requests 2 --num-prompts 2`

| # | Metric | Result |
|---|---|---|
| 1 | E2E latency p50, client-observed from send, ms (end_to_end_request_latency_p50_msec) | 513.5109522379935 |
| 2 | TTFT p50, client-observed from send, ms (ttft_p50_msec) | 81.72706514596939 |
| 3 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 27.089804286758106 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 26.998627930879593 |
| 5 | Request throughput (request_throughput_requests_sec) | 3.8764318138638036 |
<!-- /profile:smoke -->
