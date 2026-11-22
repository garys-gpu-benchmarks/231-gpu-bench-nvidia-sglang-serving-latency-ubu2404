# Results: 231 SGLang Serving Latency Benchmark

**Main goal:** Measure SGLang concurrent serving latency percentiles under load  
**Tools:** Every profile starts sglang.launch_server with Mistral-7B-v0.3, then bench_serving.py

Reference results from the validation run on the system shown in each section (recorded 2026-11-22). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 80GB HBM3 (81559 MiB) · Intel(R) Xeon(R) Platinum 8470 · Ubuntu 24.04.5 LTS · kernel 6.8.0-149-generic · driver 595.112.07
- **Run:** 2026-11-22T11:50:51Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 05:54 · benchmark 00:02 · whole run 06:11
- **Source:** run 231_20261122_115051
- **Command:** `bash run_benchmark.sh --smoke --dtype bfloat16 --input-len 64 --output-len 16 --max-total-tokens 1024 --model-name mistralai/Mistral-7B-v0.3 --max-concurrency 2 --max-running-requests 2 --num-prompts 2`

| # | Metric | Result |
|---|---|---|
| 1 | E2E latency p50, client-observed from send, ms (end_to_end_request_latency_p50_msec) | 213.03281199652702 |
| 2 | TTFT p50, client-observed from send, ms (ttft_p50_msec) | 40.373030002228916 |
| 3 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 10.836170198551068 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 10.795035981573164 |
| 5 | Request throughput (request_throughput_requests_sec) | 9.282772994232733 |
<!-- /profile:smoke -->
