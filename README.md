# Academic System Evaluation

This is a laundry list (some might call it awesome list) of systems papers and how they do evaluations (dataset, workload)

---
### [CryptDB, SOSP'11](https://people.csail.mit.edu/nickolai/papers/popa-cryptdb-cacm.pdf)

Applications

1. [phpBB](https://github.com/phpbb/phpbb)
2. [HotCRP](https://github.com/kohler/hotcrp)
3. grad-apply (MIT EECS application)
4. [TPC-C](http://www.tpc.org/tpcc/detail.asp)
5. OpenEMR
6. web app (MIT 6.02)
7. PHP Calendar
8. `sql.mit.edu` traces

---
### [Spark Streaming (Discretized Stream), SOSP'13](http://dl.acm.org/citation.cfm?id=2522737)

Microbenchmark

1. Grep + No data specification
2. WordCount + No data specification
3. TopKCount + No data specification

Real Applications
1. Video Distribution Monitoring + Conviva (data?)
2. Crowdsourced Traffic Estimation + Mobile Millennium (data from "Scaling the Mobile Millennium system in the cloud")

---
### [CherryPick, NSDI'17](https://www.usenix.org/conference/nsdi17/technical-sessions/presentation/alipourfard)

Applications

1. [TPC-DS](http://www.tpc.org/tpc_documents_current_versions/pdf/tpc-ds_v2.3.0.pdf) on Spark SQL with scale factor 20.
2. [TPC-H](http://www.tpc.org/tpc_documents_current_versions/pdf/tpc-h_v2.17.1.pdf) on Hadoop with scale factor 100.
3. [TeraSort](http://sortbenchmark.org/YahooHadoop.pdf) with 300 GB data.
4. [SparkReg](https://github.com/databricks/spark-perf), a regression workload in SparkML with 250k examples, 10k features and 5 iterations.
5. [SparkKm](https://github.com/databricks/spark-perf), a clustering algorithm in SparkML with 250k observations with 10k features.

---
### Motivation

System research is hard. You spent months and years building a system, and you have to evaluate it scientifically.
This is one of the key different, in my opinion, between academic systems and industrial systems.
Academic systems require **extensive** quantitative measurements and **rigourous** qualitative analysis while
industrial systems often focus more on the practicality for their target applications.

Designing a proper evaluation methodology is art. Researchers need to identify representative workloads.
Synthetic data without convincing argument of the data generation is likely causing critics during the review process.
But getting real-world traces and data demands close connection with companies, which is a luxury not every researcher has.

For some problems, there are available benchmark suites, such as TPC series for database queries.
However, for more problems in academic research, especially if they are targeting at problems in the near future,
these existing benchmarks may becomes a poor fit.

In this repository, I will summarize applications used in some recent work with references/links to the dataset.
As the list grows, systems researchers may become resourceful, or learns the unfortunate lack of.
