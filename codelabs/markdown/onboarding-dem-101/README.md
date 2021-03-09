summary: DEM 101
id: dem-101
categories: onboarding
tags: dem, onboarding
status: Published
authors: sergio.hinojosa

# DEM 101

## Introduction 

Everything about DEM 101 for PoC.

Duration: 10

## DEM 101
Duration: 10
```java
package com.compuware.apm.datatypes.api.timeseries.config.keys;

import com.compuware.apm.pwh.api.ts2.metrics.key.RootMetricKey;
import com.compuware.apm.pwh.api.ts2.metrics.key.TsmMetricKey;

public final class PizzaMetric {

        private PizzaMetric() {}

        public static final TsmMetricKey PIZZA = TsmMetricKey.of(RootMetricKey.EXTENSION, "pizza key");
}
```

## Pizza 2
