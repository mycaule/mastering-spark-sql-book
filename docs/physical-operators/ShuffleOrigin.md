# ShuffleOrigin

`ShuffleOrigin` describes where a [ShuffleExchangeLike](ShuffleExchangeLike.md#shuffleOrigin) comes from (where it was created).

`ShuffleOrigin` is used (_supported_) by [AQEShuffleReadRule](../adaptive-query-execution/AQEShuffleReadRule.md#supportedShuffleOrigins)s.

## <span id="ENSURE_REQUIREMENTS"> ENSURE_REQUIREMENTS

The default `ShuffleOrigin` of [ShuffleExchangeExec](ShuffleExchangeExec.md#shuffleOrigin) physical operator

Supported by [AQEShuffleReadRule](../adaptive-query-execution/AQEShuffleReadRule.md#supportedShuffleOrigins)s:

* [CoalesceShufflePartitions](../adaptive-query-execution/CoalesceShufflePartitions.md)
* [OptimizeShuffleWithLocalRead](../adaptive-query-execution/OptimizeShuffleWithLocalRead.md)
* [OptimizeSkewedJoin](../adaptive-query-execution/OptimizeSkewedJoin.md)

## <span id="REBALANCE_PARTITIONS_BY_COL"> REBALANCE_PARTITIONS_BY_COL

Supported by [AQEShuffleReadRule](../adaptive-query-execution/AQEShuffleReadRule.md#supportedShuffleOrigins)s:

* [CoalesceShufflePartitions](../adaptive-query-execution/CoalesceShufflePartitions.md)
* [OptimizeSkewInRebalancePartitions](../adaptive-query-execution/OptimizeSkewInRebalancePartitions.md)

## <span id="REBALANCE_PARTITIONS_BY_NONE"> REBALANCE_PARTITIONS_BY_NONE

Supported by [AQEShuffleReadRule](../adaptive-query-execution/AQEShuffleReadRule.md#supportedShuffleOrigins)s:

* [CoalesceShufflePartitions](../adaptive-query-execution/CoalesceShufflePartitions.md)
* [OptimizeShuffleWithLocalRead](../adaptive-query-execution/OptimizeShuffleWithLocalRead.md)
* [OptimizeSkewInRebalancePartitions](../adaptive-query-execution/OptimizeSkewInRebalancePartitions.md)

## <span id="REPARTITION_BY_COL"> REPARTITION_BY_COL

Indicates a user-specified repartition operator

Used to create a [ShuffleExchangeExec](ShuffleExchangeExec.md) physical operator when:

* [BasicOperators](../execution-planning-strategies/BasicOperators.md) execution planning strategy is executed to plan the following logical operators:

    * [RepartitionByExpression](../logical-operators/RepartitionOperation.md#RepartitionByExpression) with the partition expressions defined

* [WithCTEStrategy](../execution-planning-strategies/WithCTEStrategy.md) execution planning strategy is executed to plan the following logical operators:

    * [CTERelationRef](../logical-operators/CTERelationRef.md)

Supported by [AQEShuffleReadRule](../adaptive-query-execution/AQEShuffleReadRule.md#supportedShuffleOrigins)s:

* [CoalesceShufflePartitions](../adaptive-query-execution/CoalesceShufflePartitions.md)

## <span id="REPARTITION_BY_NUM"> REPARTITION_BY_NUM

Indicates a user-specified repartition operator with a defined partition number

Used to create a [ShuffleExchangeExec](ShuffleExchangeExec.md) physical operator when:

* [BasicOperators](../execution-planning-strategies/BasicOperators.md) execution planning strategy is executed to plan the following logical operators:

    * [Repartition](../logical-operators/RepartitionOperation.md#Repartition) with `shuffle` enabled
    * [RepartitionByExpression](../logical-operators/RepartitionOperation.md#RepartitionByExpression) with the number of partitions defined
