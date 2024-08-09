#### opt-30b: Fitted ratios
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --log-file bench_reallocate_30b.md
model size: 55.803 GB	cache size: 111.562 GB	hidden size (p): 1.162 GB
peak gpu mem: 5.571 GB	projected: False
prefill latency: 94.824 s	prefill throughput: 863.914 token/s
decode latency: 480.561 s	decode throughput: 10.321 token/s
total latency: 575.385 s	total throughput: 8.898 token/s
```
#### opt-30b: Reallocate before generate
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --reallocate-timing 1 --log-file bench_reallocate_30b.md
model size: 55.803 GB	cache size: 111.562 GB	hidden size (p): 1.162 GB
peak gpu mem: 5.571 GB	projected: False
prefill latency: 92.107 s	prefill throughput: 889.396 token/s
decode latency: 420.234 s	decode throughput: 11.803 token/s
total latency: 512.341 s	total throughput: 9.993 token/s
```
#### opt-30b: Reallocate-in-flight (every token)
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --reallocate-timing 2 --log-file bench_reallocate_30b.md
model size: 55.803 GB	cache size: 111.562 GB	hidden size (p): 1.162 GB
peak gpu mem: 5.571 GB	projected: False
prefill latency: 133.302 s	prefill throughput: 614.543 token/s
decode latency: 3075.243 s	decode throughput: 1.613 token/s
total latency: 3208.545 s	total throughput: 1.596 token/s
```
#### opt-30b: Reallocate-in-flight (after some tokens)
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --reallocate-timing 3 --log-file bench_reallocate_30b.md
model size: 55.803 GB	cache size: 111.562 GB	hidden size (p): 1.162 GB
peak gpu mem: 5.571 GB	projected: False
prefill latency: 99.043 s	prefill throughput: 827.114 token/s
decode latency: 1706.199 s	decode throughput: 2.907 token/s
total latency: 1805.243 s	total throughput: 2.836 token/s
```
#### opt-30b: Reallocate before generate, with punish
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --reallocate-timing 1 --include-reallocate-punish true --log-file bench_reallocate_30b.md
model size: 55.803 GB	cache size: 111.562 GB	hidden size (p): 1.162 GB
peak gpu mem: 5.571 GB	projected: False
prefill latency: 98.453 s	prefill throughput: 832.072 token/s
decode latency: 436.841 s	decode throughput: 11.354 token/s
total latency: 535.294 s	total throughput: 9.565 token/s
```
#### opt-30b: Reallocate-in-flight (every token), with punish
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --reallocate-timing 2 --include-reallocate-punish true --log-file bench_reallocate_30b.md
model size: 55.803 GB	cache size: 111.562 GB	hidden size (p): 1.162 GB
peak gpu mem: 6.011 GB	projected: False
prefill latency: 117.844 s	prefill throughput: 695.156 token/s
decode latency: 2629.028 s	decode throughput: 1.887 token/s
total latency: 2746.872 s	total throughput: 1.864 token/s
```
#### opt-30b: Reallocate-in-flight (after some tokens), with punish
```
python -m flexgen.flex_opt --model facebook/opt-30b --percent 12 78 0 100 0 100 --gpu-batch-size 32 --num-gpu-batches 5 --prompt-len 512 --gen-len 32 --reallocate-timing 3 --include-reallocate-punish true --log-file bench_reallocate_30b.md
model size: 55.803 GB	cache size: 111.562 GB	hidden size (p): 1.162 GB
peak gpu mem: 5.571 GB	projected: False
prefill latency: 96.773 s	prefill throughput: 846.514 token/s
decode latency: 1193.460 s	decode throughput: 4.156 token/s
total latency: 1290.233 s	total throughput: 3.968 token/s
```
