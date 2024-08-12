---
layout: post
title: Spark Release 3.5.2
categories: []
tags: []
status: publish
type: post
published: true
meta:
  _edit_last: '4'
  _wpas_done_all: '1'
---

Spark 3.5.2 is the second maintenance release containing security and correctness fixes. This release is based on the branch-3.5 maintenance branch of Spark. We strongly recommend all 3.5 users to upgrade to this stable release.

### Notable changes

- [[SPARK-45988]](https://issues.apache.org/jira/browse/SPARK-45988): Fix `pyspark.pandas.tests.computation.test_apply_func` in Python 3.11
- [[SPARK-45989]](https://issues.apache.org/jira/browse/SPARK-45989): Fix `pyspark.pandas.tests.connect.computation.test_parity_apply_func` in Python 3.11
- [[SPARK-46411]](https://issues.apache.org/jira/browse/SPARK-46411): Change to use bcprov/bcpkix-jdk18on for test
- [[SPARK-47368]](https://issues.apache.org/jira/browse/SPARK-47368): Remove inferTimestampNTZ config check in ParquetRowConverter
- [[SPARK-47370]](https://issues.apache.org/jira/browse/SPARK-47370): Add migration doc: TimestampNTZ type inference on Parquet files
- [[SPARK-47435]](https://issues.apache.org/jira/browse/SPARK-47435): SPARK-45561 causes mysql unsigned tinyint overflow
- [[SPARK-47440]](https://issues.apache.org/jira/browse/SPARK-47440): SQLServer does not support LIKE operator in binary comparison
- [[SPARK-47473]](https://issues.apache.org/jira/browse/SPARK-47473): Correctness issue of converting postgres INFINITIES timestamps
- [[SPARK-47494]](https://issues.apache.org/jira/browse/SPARK-47494): Add migration doc for the behavior change of Parquet timestamp inference since Spark 3.3
- [[SPARK-47537]](https://issues.apache.org/jira/browse/SPARK-47537): Use MySQL Connector/J for MySQL DB instead of MariaDB Connector/J
- [[SPARK-47666]](https://issues.apache.org/jira/browse/SPARK-47666): Fix NPE when reading mysql bit array as LongType
- [[SPARK-47770]](https://issues.apache.org/jira/browse/SPARK-47770): Fix `GenerateMIMAIgnore.isPackagePrivateModule` to return false instead of failing
- [[SPARK-47774]](https://issues.apache.org/jira/browse/SPARK-47774): Remove redundant rules from `MimaExcludes`
- [[SPARK-47847]](https://issues.apache.org/jira/browse/SPARK-47847): Deprecate spark.network.remoteReadNioBufferConversion
- [[SPARK-48016]](https://issues.apache.org/jira/browse/SPARK-48016): Fix a bug in try_divide function when with decimals
- [[SPARK-48068]](https://issues.apache.org/jira/browse/SPARK-48068): `mypy` should have `--python-executable` parameter
- [[SPARK-48083]](https://issues.apache.org/jira/browse/SPARK-48083): session.copyFromLocalToFs failure with 3.5 client <> 4.0 server
- [[SPARK-48084]](https://issues.apache.org/jira/browse/SPARK-48084): pyspark.ml.connect.evaluation not working in 3.5 client <> 4.0 server
- [[SPARK-48086]](https://issues.apache.org/jira/browse/SPARK-48086): Different Arrow versions in client and server
- [[SPARK-48087]](https://issues.apache.org/jira/browse/SPARK-48087): Python UDTF incompatibility in 3.5 client <> 4.0 server
- [[SPARK-48088]](https://issues.apache.org/jira/browse/SPARK-48088): Skip tests being failed in client 3.5 <> server 4.0
- [[SPARK-48089]](https://issues.apache.org/jira/browse/SPARK-48089): Streaming query listener not working in 3.5 client <> 4.0 server
- [[SPARK-48090]](https://issues.apache.org/jira/browse/SPARK-48090): Streaming exception catch failure in 3.5 client <> 4.0 server
- [[SPARK-48109]](https://issues.apache.org/jira/browse/SPARK-48109): Enable `k8s-integration-tests` only for `kubernetes` module change
- [[SPARK-48116]](https://issues.apache.org/jira/browse/SPARK-48116): Run `pyspark-pandas*` only in PR builder and Daily Python CIs
- [[SPARK-48132]](https://issues.apache.org/jira/browse/SPARK-48132): Run `k8s-integration-tests` only in PR builder and Daily CIs
- [[SPARK-48133]](https://issues.apache.org/jira/browse/SPARK-48133): Run `sparkr` only in PR builders and Daily CIs
- [[SPARK-48138]](https://issues.apache.org/jira/browse/SPARK-48138): Disable a flaky `SparkSessionE2ESuite.interrupt tag` test
- [[SPARK-48167]](https://issues.apache.org/jira/browse/SPARK-48167): Skip known behaviour change by SPARK-46122
- [[SPARK-48178]](https://issues.apache.org/jira/browse/SPARK-48178): Run `build/scala-213/java-11-17` jobs of branch-3.5 only if needed
- [[SPARK-48192]](https://issues.apache.org/jira/browse/SPARK-48192): Enable TPC-DS and docker tests in forked repository
- [[SPARK-48930]](https://issues.apache.org/jira/browse/SPARK-48930): Redact `awsAccessKeyId` by including `accesskey` pattern
- [[SPARK-49054]](https://issues.apache.org/jira/browse/SPARK-49054): Column default value should support current_* functions
- [[SPARK-47305]](https://issues.apache.org/jira/browse/SPARK-47305): PruneFilters incorrectly tags isStreaming flag when replacing child of Filter with LocalRelation
- [[SPARK-47307]](https://issues.apache.org/jira/browse/SPARK-47307): Spark 3.3 produces invalid base64
- [[SPARK-47318]](https://issues.apache.org/jira/browse/SPARK-47318): AuthEngine key exchange needs additional KDF round
- [[SPARK-47385]](https://issues.apache.org/jira/browse/SPARK-47385): Tuple encoder produces wrong results with Option inputs
- [[SPARK-47398]](https://issues.apache.org/jira/browse/SPARK-47398): AQE doesn't allow for extension of InMemoryTableScanExec
- [[SPARK-47434]](https://issues.apache.org/jira/browse/SPARK-47434): Streaming Statistics link redirect causing 302 error
- [[SPARK-47455]](https://issues.apache.org/jira/browse/SPARK-47455): Fix Resource Handling of `scalaStyleOnCompileConfig` in SparkBuild.scala
- [[SPARK-47463]](https://issues.apache.org/jira/browse/SPARK-47463): An error occurred while pushing down the filter of if expression for iceberg datasource.
- [[SPARK-47503]](https://issues.apache.org/jira/browse/SPARK-47503): Spark history sever fails to display query for cached JDBC relation named in quotes
- [[SPARK-47507]](https://issues.apache.org/jira/browse/SPARK-47507): Upgrade ORC to 1.9.3
- [[SPARK-47521]](https://issues.apache.org/jira/browse/SPARK-47521): Use `Utils.tryWithResource` during reading shuffle data from external storage
- [[SPARK-47561]](https://issues.apache.org/jira/browse/SPARK-47561): Fix analyzer rule order issues about Alias
- [[SPARK-47633]](https://issues.apache.org/jira/browse/SPARK-47633): Cache miss for queries using JOIN LATERAL with join condition
- [[SPARK-47636]](https://issues.apache.org/jira/browse/SPARK-47636): Use Java 17 instead of 17-jre image in K8s Dockerfile
- [[SPARK-47646]](https://issues.apache.org/jira/browse/SPARK-47646): try_to_number fails with NPE for malformed input
- [[SPARK-47676]](https://issues.apache.org/jira/browse/SPARK-47676): Clean up the removed `VersionsSuite` references
- [[SPARK-47762]](https://issues.apache.org/jira/browse/SPARK-47762): Add pyspark.sql.connect.protobuf into setup.py
- [[SPARK-47824]](https://issues.apache.org/jira/browse/SPARK-47824): Nondeterminism in pyspark.pandas.series.asof
- [[SPARK-47828]](https://issues.apache.org/jira/browse/SPARK-47828): DataFrameWriterV2.overwrite fails with invalid plan
- [[SPARK-47840]](https://issues.apache.org/jira/browse/SPARK-47840): Remove foldable propagation across Streaming Aggregate/Join nodes
- [[SPARK-47895]](https://issues.apache.org/jira/browse/SPARK-47895): group by all should be idempotent
- [[SPARK-47904]](https://issues.apache.org/jira/browse/SPARK-47904): Preserve case in Avro schema when using enableStableIdentifiersForUnionType
- [[SPARK-47910]](https://issues.apache.org/jira/browse/SPARK-47910): Memory leak when interrupting shuffle write using zstd compression
- [[SPARK-47921]](https://issues.apache.org/jira/browse/SPARK-47921): Fix ExecuteJobTag creation in ExecuteHolder
- [[SPARK-47927]](https://issues.apache.org/jira/browse/SPARK-47927): Nullability after join not respected in UDF
- [[SPARK-48019]](https://issues.apache.org/jira/browse/SPARK-48019): ColumnVectors with dictionaries and nulls are not read/copied correctly
- [[SPARK-48037]](https://issues.apache.org/jira/browse/SPARK-48037): SortShuffleWriter lacks shuffle write related metrics resulting in potentially inaccurate data
- [[SPARK-48105]](https://issues.apache.org/jira/browse/SPARK-48105): Fix the data corruption issue when state store unload and snapshotting happens concurrently for HDFS state store
- [[SPARK-48128]](https://issues.apache.org/jira/browse/SPARK-48128): BitwiseCount / bit_count generated code for boolean inputs fails to compile
- [[SPARK-48172]](https://issues.apache.org/jira/browse/SPARK-48172): Fix escaping issues in JDBCDialects
- [[SPARK-48173]](https://issues.apache.org/jira/browse/SPARK-48173): CheckAnalsis should see the entire query plan
- [[SPARK-48179]](https://issues.apache.org/jira/browse/SPARK-48179): Pin `nbsphinx` to `0.9.3`
- [[SPARK-48184]](https://issues.apache.org/jira/browse/SPARK-48184): Always set the seed of dataframe.sample in Client side
- [[SPARK-48197]](https://issues.apache.org/jira/browse/SPARK-48197): avoid assert error for invalid lambda function
- [[SPARK-48237]](https://issues.apache.org/jira/browse/SPARK-48237): After executing `test-dependencies.sh`, the dir `dev/pr-deps` should be deleted
- [[SPARK-48241]](https://issues.apache.org/jira/browse/SPARK-48241): CSV parsing failure with char/varchar type columns
- [[SPARK-48248]](https://issues.apache.org/jira/browse/SPARK-48248): Fix nested array to respect legacy conf of inferArrayTypeFromFirstElement
- [[SPARK-48265]](https://issues.apache.org/jira/browse/SPARK-48265): Infer window group limit batch should do constant folding
- [[SPARK-48273]](https://issues.apache.org/jira/browse/SPARK-48273): Late rewrite of PlanWithUnresolvedIdentifier
- [[SPARK-48286]](https://issues.apache.org/jira/browse/SPARK-48286): Analyze &#39;exists&#39; default expression instead of &#39;current&#39; default expression in structField to v2 column conversion
- [[SPARK-48294]](https://issues.apache.org/jira/browse/SPARK-48294): Make nestedTypeMissingElementTypeError case insensitive
- [[SPARK-48297]](https://issues.apache.org/jira/browse/SPARK-48297): Char/Varchar breaks in TRANSFORM clause
- [[SPARK-48237]](https://issues.apache.org/jira/browse/SPARK-48237): After executing `test-dependencies.sh`, the dir `dev/pr-deps` should be deleted
- [[SPARK-48241]](https://issues.apache.org/jira/browse/SPARK-48241): CSV parsing failure with char/varchar type columns
- [[SPARK-48248]](https://issues.apache.org/jira/browse/SPARK-48248): Fix nested array to respect legacy conf of inferArrayTypeFromFirstElement
- [[SPARK-48265]](https://issues.apache.org/jira/browse/SPARK-48265): Infer window group limit batch should do constant folding
- [[SPARK-48273]](https://issues.apache.org/jira/browse/SPARK-48273): Late rewrite of PlanWithUnresolvedIdentifier
- [[SPARK-48286]](https://issues.apache.org/jira/browse/SPARK-48286): Analyze &#39;exists&#39; default expression instead of &#39;current&#39; default expression in structField to v2 column conversion
- [[SPARK-48294]](https://issues.apache.org/jira/browse/SPARK-48294): Make nestedTypeMissingElementTypeError case insensitive
- [[SPARK-48297]](https://issues.apache.org/jira/browse/SPARK-48297): Char/Varchar breaks in TRANSFORM clause
- [[SPARK-48308]](https://issues.apache.org/jira/browse/SPARK-48308): Unify getting data schema without partition columns in FileSourceStrategy
- [[SPARK-48428]](https://issues.apache.org/jira/browse/SPARK-48428): IllegalStateException due to nested column aliasing
- [[SPARK-48481]](https://issues.apache.org/jira/browse/SPARK-48481): OptimizeOneRowPlan should not be effective for streaming DataFrame
- [[SPARK-48484]](https://issues.apache.org/jira/browse/SPARK-48484): V2Write use the same TaskAttemptId for different task attempts
- [[SPARK-48498]](https://issues.apache.org/jira/browse/SPARK-48498): Always do char padding in predicates
- [[SPARK-48608]](https://issues.apache.org/jira/browse/SPARK-48608): Spark 3.5: fails to build with value defaultValueNotConstantError is not a member of object org.apache.spark.sql.errors.QueryCompilationErrors
- [[SPARK-48642]](https://issues.apache.org/jira/browse/SPARK-48642): False reported SparkOutOfMemoryError caused by killing task on spilling
- [[SPARK-48666]](https://issues.apache.org/jira/browse/SPARK-48666): A filter should not be pushed down if it contains Unevaluable expression
- [[SPARK-48709]](https://issues.apache.org/jira/browse/SPARK-48709): Varchar resolution mismatch for DataSourceV2 CTAS
- [[SPARK-48719]](https://issues.apache.org/jira/browse/SPARK-48719): Wrong result in regr_slope & regr_intercept aggregate with tuples has NULL
- [[SPARK-48791]](https://issues.apache.org/jira/browse/SPARK-48791): Perf regression due to accumulator registration overhead using CopyOnWriteArrayList
- [[SPARK-48843]](https://issues.apache.org/jira/browse/SPARK-48843): Infinite loop with GlobalLimit/BindParameters
- [[SPARK-48845]](https://issues.apache.org/jira/browse/SPARK-48845): GenericUDF Can not CatchException From Child UDFs
- [[SPARK-48863]](https://issues.apache.org/jira/browse/SPARK-48863): ClassCastException: class org.apache.spark.unsafe.types.UTF8String cannot be cast to class org.apache.spark.sql.catalyst.util.ArrayData when parsing JSON with "spark.sql.json.enablePartialResults" enabled
- [[SPARK-48871]](https://issues.apache.org/jira/browse/SPARK-48871): Fix INVALID_NON_DETERMINISTIC_EXPRESSIONS validation in CheckAnalysis
- [[SPARK-48921]](https://issues.apache.org/jira/browse/SPARK-48921): ScalaUDF in subquery should run through analyzer
- [[SPARK-48991]](https://issues.apache.org/jira/browse/SPARK-48991): FileStreamSink.hasMetadata handles invalid path
- [[SPARK-49000]](https://issues.apache.org/jira/browse/SPARK-49000): Aggregation with DISTINCT gives wrong results when dealing with literals
- [[SPARK-49005]](https://issues.apache.org/jira/browse/SPARK-49005): Use `17-jammy` instead of `17` to prevent Python 3.12
- [[SPARK-49065]](https://issues.apache.org/jira/browse/SPARK-49065): Rebasing in legacy formatters/parsers must support non JVM default time zones
- [[SPARK-49094]](https://issues.apache.org/jira/browse/SPARK-49094): ignoreCorruptFiles file source option is partially supported for orc format
- [[SPARK-49099]](https://issues.apache.org/jira/browse/SPARK-49099): Refactor CatalogManager.setCurrentNamespace
- [[SPARK-45587]](https://issues.apache.org/jira/browse/SPARK-45587): Skip UNIDOC and MIMA in build GitHub Action job
- [[SPARK-45593]](https://issues.apache.org/jira/browse/SPARK-45593): Building a runnable distribution from master code running spark-sql raise error "java.lang.ClassNotFoundException: org.sparkproject.guava.util.concurrent.internal.InternalFutureFailureAccess"
- [[SPARK-47172]](https://issues.apache.org/jira/browse/SPARK-47172): Upgrade Transport block cipher mode to GCM
- [[SPARK-47299]](https://issues.apache.org/jira/browse/SPARK-47299): Use the same `versions.json` in the dropdown of different versions of PySpark documents
- [[SPARK-47734]](https://issues.apache.org/jira/browse/SPARK-47734): Fix flaky pyspark.sql.dataframe.DataFrame.writeStream doctest by stopping streaming query
- [[SPARK-47825]](https://issues.apache.org/jira/browse/SPARK-47825): Make `KinesisTestUtils` & `WriteInputFormatTestDataGenerator` deprecated
- [[SPARK-47897]](https://issues.apache.org/jira/browse/SPARK-47897): ExpressionSet performance regression in scala 2.12
- [[SPARK-48081]](https://issues.apache.org/jira/browse/SPARK-48081): Fix ClassCastException in NTile.checkInputDataTypes() when argument is non-foldable or of wrong type
- [[SPARK-48292]](https://issues.apache.org/jira/browse/SPARK-48292): Revert [SPARK-39195][SQL] Spark OutputCommitCoordinator should abort stage when committed file not consistent with task status
- [[SPARK-48391]](https://issues.apache.org/jira/browse/SPARK-48391): Use addAll instead of add function in TaskMetrics to accelerate
- [[SPARK-48424]](https://issues.apache.org/jira/browse/SPARK-48424): Make dev/is-changed.py to return true if it fails
- [[SPARK-48586]](https://issues.apache.org/jira/browse/SPARK-48586): Remove lock acquisition in doMaintenance() by making a deep copy of file mappings in RocksDBFileManager in load()
- [[SPARK-48610]](https://issues.apache.org/jira/browse/SPARK-48610): Remove ExplainUtils.processPlan synchronize
- [[SPARK-48806]](https://issues.apache.org/jira/browse/SPARK-48806): Pass actual exception when url_decode fails
- [[SPARK-47481]](https://issues.apache.org/jira/browse/SPARK-47481): Fix Python linter
- [[SPARK-48535]](https://issues.apache.org/jira/browse/SPARK-48535): Update doc to log warning for join null related config usage
- [[SPARK-48934]](https://issues.apache.org/jira/browse/SPARK-48934): Python datetime types converted incorrectly for setting timeout in applyInPandasWithState

### Dependency changes

- [[SPARK-45445]](https://issues.apache.org/jira/browse/SPARK-45445): Upgrade snappy to 1.1.10.5
- [[SPARK-46335]](https://issues.apache.org/jira/browse/SPARK-46335): Upgrade Maven to 3.9.6 for MNG-7913
- [[SPARK-47083]](https://issues.apache.org/jira/browse/SPARK-47083): Upgrade `commons-codec` to 1.16.1
- [[SPARK-47111]](https://issues.apache.org/jira/browse/SPARK-47111): Upgrade `PostgreSQL` JDBC driver to 42.7.2 and docker image to 16.2
- [[SPARK-47182]](https://issues.apache.org/jira/browse/SPARK-47182): Exclude `commons-(io|lang3)` transitive dependencies from `commons-compress` and `avro-*`
- [[SPARK-47428]](https://issues.apache.org/jira/browse/SPARK-47428): Upgrade Jetty to 9.4.54.v20240208
- [[SPARK-47432]](https://issues.apache.org/jira/browse/SPARK-47432): Add `pyarrow` upper bound requirement, `<13.0.0`
- [[SPARK-47790]](https://issues.apache.org/jira/browse/SPARK-47790): Upgrade `commons-io` to 2.16.1
- [[SPARK-48494]](https://issues.apache.org/jira/browse/SPARK-48494): Update airlift:aircompressor to 0.27
- [[SPARK-48920]](https://issues.apache.org/jira/browse/SPARK-48920): Upgrade ORC to 1.9.4

You can consult JIRA for the [detailed changes](https://s.apache.org/spark-3.5.2).

We would like to acknowledge all community members for contributing patches to this release.
