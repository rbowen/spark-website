---
layout: post
title: Spark Release 3.4.3
categories: []
tags: []
status: publish
type: post
published: true
meta:
  _edit_last: '4'
  _wpas_done_all: '1'
---

Spark 3.4.3 is a maintenance release containing security and correctness fixes. This release is based on the branch-3.4 maintenance branch of Spark. We strongly recommend all 3.4 users to upgrade to this stable release.

### Notable changes

  - [[SPARK-45580]](https://issues.apache.org/jira/browse/SPARK-45580): Handle case where a nested subquery becomes an existence join
  - [[SPARK-46029]](https://issues.apache.org/jira/browse/SPARK-46029): Escape the single quote, _ and % for DS V2 pushdown
  - [[SPARK-46092]](https://issues.apache.org/jira/browse/SPARK-46092): Don't push down Parquet row group filters that overflow
  - [[SPARK-46182]](https://issues.apache.org/jira/browse/SPARK-46182): Track `lastTaskFinishTime` using the exact task finished event
  - [[SPARK-46189]](https://issues.apache.org/jira/browse/SPARK-46189): Perform comparisons and arithmetic between same types in various Pandas aggregate functions to avoid interpreted mode errors
  - [[SPARK-46239]](https://issues.apache.org/jira/browse/SPARK-46239): Hide `Jetty` info
  - [[SPARK-46275]](https://issues.apache.org/jira/browse/SPARK-46275): Protobuf: Return null in permissive mode when deserialization fails
  - [[SPARK-46286]](https://issues.apache.org/jira/browse/SPARK-46286): Document `spark.io.compression.zstd.bufferPool.enabled`
  - [[SPARK-46330]](https://issues.apache.org/jira/browse/SPARK-46330): Loading of Spark UI blocks for a long time when HybridStore enabled
  - [[SPARK-46339]](https://issues.apache.org/jira/browse/SPARK-46339): Directory with batch number name should not be treated as metadata log
  - [[SPARK-46369]](https://issues.apache.org/jira/browse/SPARK-46369): Remove `kill` link from `RELAUNCHING` drivers in `MasterPage`
  - [[SPARK-46400]](https://issues.apache.org/jira/browse/SPARK-46400): When there are corrupted files in the local maven repo, skip this cache and try again
  - [[SPARK-46417]](https://issues.apache.org/jira/browse/SPARK-46417): Do not fail when calling hive.getTable and throwException is false
  - [[SPARK-46466]](https://issues.apache.org/jira/browse/SPARK-46466): Vectorized parquet reader should never do rebase for timestamp ntz
  - [[SPARK-46598]](https://issues.apache.org/jira/browse/SPARK-46598): OrcColumnarBatchReader should respect the memory mode when creating column vectors for the missing column
  - [[SPARK-46628]](https://issues.apache.org/jira/browse/SPARK-46628): Use SPDX short identifier in `license` name
  - [[SPARK-46700]](https://issues.apache.org/jira/browse/SPARK-46700): Count the last spilling for the shuffle disk spilling bytes metric
  - [[SPARK-46704]](https://issues.apache.org/jira/browse/SPARK-46704): Fix `MasterPage` to sort `Running Drivers` table by `Duration` column correctly
  - [[SPARK-46747]](https://issues.apache.org/jira/browse/SPARK-46747): Avoid scan in getTableExistsQuery for JDBC Dialects
  - [[SPARK-46763]](https://issues.apache.org/jira/browse/SPARK-46763): Fix assertion failure in ReplaceDeduplicateWithAggregate for duplicate attributes
  - [[SPARK-46779]](https://issues.apache.org/jira/browse/SPARK-46779): `InMemoryRelation` instances of the same cached plan should be semantically equivalent
  - [[SPARK-46786]](https://issues.apache.org/jira/browse/SPARK-46786): Fix `MountVolumesFeatureStep` to use `ReadWriteOncePod` instead of `ReadWriteOnce`
  - [[SPARK-46794]](https://issues.apache.org/jira/browse/SPARK-46794): Remove subqueries from LogicalRDD constraints
  - [[SPARK-46801]](https://issues.apache.org/jira/browse/SPARK-46801): Do not treat exit code 5 as a test failure in Python testing script
  - [[SPARK-46817]](https://issues.apache.org/jira/browse/SPARK-46817): Fix `spark-daemon.sh` usage by adding `decommission` command
  - [[SPARK-46861]](https://issues.apache.org/jira/browse/SPARK-46861): Avoid Deadlock in DAGScheduler
  - [[SPARK-46862]](https://issues.apache.org/jira/browse/SPARK-46862): Disable CSV column pruning in the multi-line mode
  - [[SPARK-46888]](https://issues.apache.org/jira/browse/SPARK-46888): Fix `Master` to reject `/workers/kill/` requests if decommission is disabled
  - [[SPARK-46893]](https://issues.apache.org/jira/browse/SPARK-46893): Remove inline scripts from UI descriptions
  - [[SPARK-46945]](https://issues.apache.org/jira/browse/SPARK-46945): Add `spark.kubernetes.legacy.useReadWriteOnceAccessMode` for old K8s clusters
  - [[SPARK-47063]](https://issues.apache.org/jira/browse/SPARK-47063): CAST long to timestamp has different behavior for codegen vs interpreted
  - [[SPARK-47072]](https://issues.apache.org/jira/browse/SPARK-47072): Fix supported interval formats in error messages
  - [[SPARK-47085]](https://issues.apache.org/jira/browse/SPARK-47085): Reduce the complexity of toTRowSet from n^2 to n
  - [[SPARK-47125]](https://issues.apache.org/jira/browse/SPARK-47125): Return null if Univocity never triggers parsing
  - [[SPARK-47146]](https://issues.apache.org/jira/browse/SPARK-47146): Possible thread leak when doing sort merge join
  - [[SPARK-47177]](https://issues.apache.org/jira/browse/SPARK-47177): Cached SQL plan do not display final AQE plan in explain string
  - [[SPARK-47187]](https://issues.apache.org/jira/browse/SPARK-47187): Fix hive compress output config does not work
  - [[SPARK-47236]](https://issues.apache.org/jira/browse/SPARK-47236): Fix `deleteRecursivelyUsingJavaIO` to skip non-existing file input
  - [[SPARK-47305]](https://issues.apache.org/jira/browse/SPARK-47305): Fix PruneFilters to tag the isStreaming flag of LocalRelation correctly when the plan has both batch and streaming
  - [[SPARK-47318]](https://issues.apache.org/jira/browse/SPARK-47318): Adds HKDF round to AuthEngine key derivation to follow standard KEX practices
  - [[SPARK-47368]](https://issues.apache.org/jira/browse/SPARK-47368): Remove inferTimestampNTZ config check in ParquetRowConverter
  - [[SPARK-47370]](https://issues.apache.org/jira/browse/SPARK-47370): Add migration doc for TimestampNTZ type inference on Parquet files
  - [[SPARK-47385]](https://issues.apache.org/jira/browse/SPARK-47385): Fix tuple encoders with Option inputs
  - [[SPARK-47434]](https://issues.apache.org/jira/browse/SPARK-47434): Fix `statistics` link in `StreamingQueryPage`
  - [[SPARK-47494]](https://issues.apache.org/jira/browse/SPARK-47494): Add migration doc for the behavior change of Parquet timestamp inference since Spark 3.3
  - [[SPARK-47503]](https://issues.apache.org/jira/browse/SPARK-47503): Make makeDotNode escape graph node name always
  - [[SPARK-47521]](https://issues.apache.org/jira/browse/SPARK-47521): Use `Utils.tryWithResource` during reading shuffle data from external storage
  - [[SPARK-47537]](https://issues.apache.org/jira/browse/SPARK-47537): Fix error data type mapping on MySQL Connector/J
  - [[SPARK-47646]](https://issues.apache.org/jira/browse/SPARK-47646): Make try_to_number return NULL for malformed input
  - [[SPARK-47666]](https://issues.apache.org/jira/browse/SPARK-47666): Fix NPE when reading mysql bit array as LongType
  - [[SPARK-47824]](https://issues.apache.org/jira/browse/SPARK-47824): Fix nondeterminism in pyspark.pandas.series.asof

### Dependency Changes

While being a maintenance release we did still upgrade some dependencies in this release they are:

  - [[SPARK-45445]](https://issues.apache.org/jira/browse/SPARK-45445): Upgrade snappy to 1.1.10.5
  - [[SPARK-47428]](https://issues.apache.org/jira/browse/SPARK-47428): Upgrade Jetty to 9.4.54.v20240208
  - [[SPARK-47844]](https://issues.apache.org/jira/browse/SPARK-47844): Update ORC to 1.8.7

You can consult JIRA for the [detailed changes](https://s.apache.org/spark-3.4.3).

We would like to acknowledge all community members for contributing patches to this release.



