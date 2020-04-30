---
title: Continuous Performance Tracking for Better “Everything”! Demo Notes
tags: lecture, co337
description: View the slide with "Slide Mode".
---

#### 1st Demo: Benchmarks

<!-- .slide: style="font-size:70%" --> 

```bash
cd ~/Talks/MoreVMs-2020/src/benchmarks
ll src
ant jar
java -version
java -cp benchmarks.jar Harness Mandelbrot 100 500
java -XX:TieredStopAtLevel=1 -cp benchmarks.jar Harness Mandelbrot 100 500
```

- back to slides 💻

---

#### 2nd Demo: ReBench

 1. show `rebench.conf` file
     - benchmark suites: collection of benchmarks
     - executors: the VMs to excute them
     - experiments: combining both for what we want to measure

---


```bash
rebench --help

rebench rebench.conf
## abort, takes too long

## let's just run the one we are interested in
rebench rebench.conf s:steady-java:Mandelbrot

## perhaps lets grab some extra *invocations*
rebench -in 4 rebench.conf s:steady-java:Mandelbrot

## all data persisted locally
cat benchmark.data | less
```
 
 3. back to slides 💻

---

#### 3rd Demo: ReBenchDB

- open https://rebench.stefan-marr.de/
  - collects benchmark results per project
- can do time line
- but often more important, runs custom R reports: 
https://rebench.stefan-marr.de/compare/SOMns/48866c61d83336e41cc27d36db98f4f37a1781f6/8159324b8129135c90f0a4ce074b9163d8d1af56
- R is, ehm, slow
- the best part for me is really that it uses my R scripts, which I also use for papers.


1. back to slides 💻

---

#### 4th Demo ReBench to PDF

```bash
mate paper.tex
# line 25 \input{gen-eval}
# line 43 \Overview{}
# line 51ff \Speedup*

mate evaluation.Rnw
# bottom: generate plot, and macros

make
open paper.pdf
```

1. back to slides 💻
