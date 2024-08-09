#### opt-6.7b: Fitted ratios
```
python -m flexgen.flex_opt --model facebook/opt-6.7b --percent 100 0 83 17 100 0 --gpu-batch-size 1 --num-gpu-batches 1 --prompt-len 512 --gen-len 1288 --log-file bench_reallocate_suites.md
model size: 12.386 GB	cache size: 0.879 GB	hidden size (p): 0.014 GB
peak gpu mem: 12.862 GB	projected: False
prefill latency: 0.216 s	prefill throughput: 2374.814 token/s
decode latency: 176.143 s	decode throughput: 7.307 token/s
total latency: 176.359 s	total throughput: 7.303 token/s
```
#### opt-6.7b: Reallocate before generate
```
python -m flexgen.flex_opt --model facebook/opt-6.7b --percent 100 0 83 17 100 0 --gpu-batch-size 1 --num-gpu-batches 1 --prompt-len 512 --gen-len 1288 --reallocate-timing 1 --log-file bench_reallocate_suites.md
model size: 12.386 GB	cache size: 0.879 GB	hidden size (p): 0.014 GB
peak gpu mem: 12.862 GB	projected: False
prefill latency: 0.248 s	prefill throughput: 2064.681 token/s
decode latency: 171.303 s	decode throughput: 7.513 token/s
total latency: 171.551 s	total throughput: 7.508 token/s
```
#### opt-6.7b: Reallocate-in-flight (every token)
```
python -m flexgen.flex_opt --model facebook/opt-6.7b --percent 100 0 83 17 100 0 --gpu-batch-size 1 --num-gpu-batches 1 --prompt-len 512 --gen-len 1288 --reallocate-timing 2 --log-file bench_reallocate_suites.md
model size: 12.386 GB	cache size: 0.879 GB	hidden size (p): 0.014 GB
peak gpu mem: 12.862 GB	projected: False
prefill latency: 0.446 s	prefill throughput: 1147.501 token/s
decode latency: 169.244 s	decode throughput: 7.604 token/s
total latency: 169.690 s	total throughput: 7.590 token/s
```
#### opt-6.7b: Reallocate-in-flight (after some tokens)
```
python -m flexgen.flex_opt --model facebook/opt-6.7b --percent 100 0 83 17 100 0 --gpu-batch-size 1 --num-gpu-batches 1 --prompt-len 512 --gen-len 1288 --reallocate-timing 3 --log-file bench_reallocate_suites.md
model size: 12.386 GB	cache size: 0.879 GB	hidden size (p): 0.014 GB
peak gpu mem: 12.862 GB	projected: False
prefill latency: 0.242 s	prefill throughput: 2119.436 token/s
decode latency: 175.538 s	decode throughput: 7.332 token/s
total latency: 175.780 s	total throughput: 7.327 token/s
```
#### opt-6.7b: Reallocate before generate, with punish
```
python -m flexgen.flex_opt --model facebook/opt-6.7b --percent 100 0 83 17 100 0 --gpu-batch-size 1 --num-gpu-batches 1 --prompt-len 512 --gen-len 1288 --reallocate-timing 1 --include-reallocate-punish true --log-file bench_reallocate_suites.md
model size: 12.386 GB	cache size: 0.879 GB	hidden size (p): 0.014 GB
peak gpu mem: 12.862 GB	projected: False
prefill latency: 0.256 s	prefill throughput: 1997.914 token/s
decode latency: 173.787 s	decode throughput: 7.406 token/s
total latency: 174.043 s	total throughput: 7.400 token/s
```
#### opt-6.7b: Reallocate-in-flight (every token), with punish
```
python -m flexgen.flex_opt --model facebook/opt-6.7b --percent 100 0 83 17 100 0 --gpu-batch-size 1 --num-gpu-batches 1 --prompt-len 512 --gen-len 1288 --reallocate-timing 2 --include-reallocate-punish true --log-file bench_reallocate_suites.md
model size: 12.386 GB	cache size: 0.879 GB	hidden size (p): 0.014 GB
peak gpu mem: 12.862 GB	projected: False
prefill latency: 0.565 s	prefill throughput: 906.960 token/s
decode latency: 173.988 s	decode throughput: 7.397 token/s
total latency: 174.553 s	total throughput: 7.379 token/s
```
#### opt-6.7b: Reallocate-in-flight (after some tokens), with punish
```
python -m flexgen.flex_opt --model facebook/opt-6.7b --percent 100 0 83 17 100 0 --gpu-batch-size 1 --num-gpu-batches 1 --prompt-len 512 --gen-len 1288 --reallocate-timing 3 --include-reallocate-punish true --log-file bench_reallocate_suites.md
model size: 12.386 GB	cache size: 0.879 GB	hidden size (p): 0.014 GB
peak gpu mem: 12.862 GB	projected: False
prefill latency: 0.314 s	prefill throughput: 1633.142 token/s
decode latency: 174.309 s	decode throughput: 7.383 token/s
total latency: 174.623 s	total throughput: 7.376 token/s
```
#### opt-13b: Fitted ratios
```
python -m flexgen.flex_opt --model facebook/opt-13b --percent 34 66 0 95 0 100 --gpu-batch-size 64 --num-gpu-batches 6 --prompt-len 384 --gen-len 128 --log-file bench_reallocate_suites.md
model size: 23.921 GB	cache size: 150.000 GB	hidden size (p): 1.875 GB
peak gpu mem: 13.994 GB	projected: False
prefill latency: 81.451 s	prefill throughput: 1810.373 token/s
decode latency: 1666.649 s	decode throughput: 29.261 token/s
total latency: 1748.099 s	total throughput: 28.117 token/s
```
#### opt-13b: Reallocate before generate
```
python -m flexgen.flex_opt --model facebook/opt-13b --percent 34 66 0 95 0 100 --gpu-batch-size 64 --num-gpu-batches 6 --prompt-len 384 --gen-len 128 --reallocate-timing 1 --log-file bench_reallocate_suites.md
```
#### opt-13b: Reallocate-in-flight (every token)
```
python -m flexgen.flex_opt --model facebook/opt-13b --percent 34 66 0 95 0 100 --gpu-batch-size 64 --num-gpu-batches 6 --prompt-len 384 --gen-len 128 --reallocate-timing 2 --log-file bench_reallocate_suites.md
```
#### opt-13b: Reallocate-in-flight (after some tokens)
```
python -m flexgen.flex_opt --model facebook/opt-13b --percent 34 66 0 95 0 100 --gpu-batch-size 64 --num-gpu-batches 6 --prompt-len 384 --gen-len 128 --reallocate-timing 3 --log-file bench_reallocate_suites.md
```
#### opt-13b: Reallocate before generate, with punish
```
python -m flexgen.flex_opt --model facebook/opt-13b --percent 34 66 0 95 0 100 --gpu-batch-size 64 --num-gpu-batches 6 --prompt-len 384 --gen-len 128 --reallocate-timing 1 --include-reallocate-punish true --log-file bench_reallocate_suites.md
model size: 23.921 GB	cache size: 150.000 GB	hidden size (p): 1.875 GB
peak gpu mem: 14.131 GB	projected: False
prefill latency: 76.291 s	prefill throughput: 1932.808 token/s
decode latency: 1824.675 s	decode throughput: 26.727 token/s
total latency: 1900.966 s	total throughput: 25.856 token/s
```
#### opt-13b: Reallocate-in-flight (every token), with punish
```
python -m flexgen.flex_opt --model facebook/opt-13b --percent 34 66 0 95 0 100 --gpu-batch-size 64 --num-gpu-batches 6 --prompt-len 384 --gen-len 128 --reallocate-timing 2 --include-reallocate-punish true --log-file bench_reallocate_suites.md
```
#### opt-13b: Reallocate-in-flight (after some tokens), with punish
```
python -m flexgen.flex_opt --model facebook/opt-13b --percent 34 66 0 95 0 100 --gpu-batch-size 64 --num-gpu-batches 6 --prompt-len 384 --gen-len 128 --reallocate-timing 3 --include-reallocate-punish true --log-file bench_reallocate_suites.md
model size: 23.921 GB	cache size: 150.000 GB	hidden size (p): 1.875 GB
peak gpu mem: 14.486 GB	projected: False
prefill latency: 84.619 s	prefill throughput: 1742.586 token/s
decode latency: 6211.748 s	decode throughput: 7.851 token/s
total latency: 6296.367 s	total throughput: 7.806 token/s
```
#### opt-30b: Fitted ratios
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --log-file bench_reallocate_suites.md
model size: 55.803 GB	cache size: 111.562 GB	hidden size (p): 1.162 GB
peak gpu mem: 5.571 GB	projected: False
prefill latency: 87.857 s	prefill throughput: 932.423 token/s
decode latency: 436.395 s	decode throughput: 11.366 token/s
total latency: 524.252 s	total throughput: 9.766 token/s
```
#### opt-30b: Reallocate before generate
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --reallocate-timing 1 --log-file bench_reallocate_suites.md
model size: 55.803 GB	cache size: 111.562 GB	hidden size (p): 1.162 GB
peak gpu mem: 5.571 GB	projected: False
prefill latency: 94.277 s	prefill throughput: 868.925 token/s
decode latency: 465.742 s	decode throughput: 10.650 token/s
total latency: 560.020 s	total throughput: 9.143 token/s
```
#### opt-30b: Reallocate-in-flight (every token)
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --reallocate-timing 2 --log-file bench_reallocate_suites.md
