---
layout: post
title: Spark Release 3.5.3
categories: []
tags: []
status: publish
type: post
published: true
meta:
  _edit_last: '4'
  _wpas_done_all: '1'
---

Spark 3.5.3 is the third maintenance release containing security and correctness fixes. This release is based on the branch-3.5 maintenance branch of Spark. We strongly recommend all 3.5 users to upgrade to this stable release.

### Notable changes

- [[SPARK-49176]](https://issues.apache.org/jira/browse/SPARK-49176) - Fix `spark.ui.custom.executor.log.url` docs by adding K8s
- [[SPARK-49182]](https://issues.apache.org/jira/browse/SPARK-49182) - Stop publish site/docs/{version}/api/python/_sources
- [[SPARK-49197]](https://issues.apache.org/jira/browse/SPARK-49197) - Redact `Spark Command` output in `launcher` module
- [[SPARK-43242]](https://issues.apache.org/jira/browse/SPARK-43242) - diagnoseCorruption should not throw Unexpected type of BlockId for ShuffleBlockBatchId
- [[SPARK-46037]](https://issues.apache.org/jira/browse/SPARK-46037) - When Left Join build Left, ShuffledHashJoinExec may result in incorrect results
- [[SPARK-46632]](https://issues.apache.org/jira/browse/SPARK-46632) - EquivalentExpressions throw IllegalStateException
- [[SPARK-48965]](https://issues.apache.org/jira/browse/SPARK-48965) - toJSON produces wrong values if DecimalType information is lost in as[Product]
- [[SPARK-49038]](https://issues.apache.org/jira/browse/SPARK-49038) - Spark UI is showing wrong timing metrics for min and median time.
- [[SPARK-49039]](https://issues.apache.org/jira/browse/SPARK-49039) - Reset checkbox when executor metrics are loaded in the Stages tab
- [[SPARK-49179]](https://issues.apache.org/jira/browse/SPARK-49179) - Fix v2 multi bucketed inner joins throw AssertionError
- [[SPARK-49183]](https://issues.apache.org/jira/browse/SPARK-49183) - V2SessionCatalog.createTable should respect PROP_IS_MANAGED_LOCATION
- [[SPARK-49193]](https://issues.apache.org/jira/browse/SPARK-49193) - Improve the performance of RowSetUtils.toColumnBasedSet
- [[SPARK-49200]](https://issues.apache.org/jira/browse/SPARK-49200) - Fix null type non-codegen ordering exception
- [[SPARK-49300]](https://issues.apache.org/jira/browse/SPARK-49300) - Fix Hadoop delegation token leak when tokenRenewalInterval is not set.
- [[SPARK-49333]](https://issues.apache.org/jira/browse/SPARK-49333) - Shutdown timeout thread while cleaning up SparkExecuteStatementOperation
- [[SPARK-49352]](https://issues.apache.org/jira/browse/SPARK-49352) - Avoid redundant array transform for identical expression
- [[SPARK-49359]](https://issues.apache.org/jira/browse/SPARK-49359) - allow StagedTableCatalog implementations to fall back to non-atomic write
- [[SPARK-49381]](https://issues.apache.org/jira/browse/SPARK-49381) - Fix `SPARK-41388` test case to assert the result
- [[SPARK-49385]](https://issues.apache.org/jira/browse/SPARK-49385) - Fix `getReusablePVCs` to use `podCreationTimeout` instead of `podAllocationDelay`
- [[SPARK-49402]](https://issues.apache.org/jira/browse/SPARK-49402) - Fix Binder integration in PySpark documentation
- [[SPARK-49476]](https://issues.apache.org/jira/browse/SPARK-49476) - Base64 nullability change
- [[SPARK-49480]](https://issues.apache.org/jira/browse/SPARK-49480) - NullPointerException from SparkThrowableHelper.isInternalError method
- [[SPARK-49509]](https://issues.apache.org/jira/browse/SPARK-49509) - Use Platform.allocateDirectBuffer instead of ByteBuffer.allocateDirect
- [[SPARK-49152]](https://issues.apache.org/jira/browse/SPARK-49152) - V2SessionCatalog should use V2Command
- [[SPARK-49211]](https://issues.apache.org/jira/browse/SPARK-49211) - V2 Catalog can also support built-in data sources
- [[SPARK-49246]](https://issues.apache.org/jira/browse/SPARK-49246) - TableCatalog#loadTable should indicate if it's for writing
- [[SPARK-49275]](https://issues.apache.org/jira/browse/SPARK-49275) - Fix return type nullness of the xpath expression
- [[SPARK-49408]](https://issues.apache.org/jira/browse/SPARK-49408) - Poor performance in ProjectingInternalRow

### Dependency changes

- [[SPARK-45590]](https://issues.apache.org/jira/browse/SPARK-45590) - okio-1.15.0 CVE-2023-3635

You can consult JIRA for the [detailed changes](https://s.apache.org/spark-3.5.3).

We would like to acknowledge all community members for contributing patches to this release.
