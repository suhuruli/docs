---
description: Supported Spice ML Model Types
---

# Model Type Specification

Spice ML supports various models and open source frameworks. The model type specified in the manifest (see [.](./ "mention")) dictates the framework. If a model or framework requires additional parameters, they can be provided within the model YAML, specifically the `model` key in `metadata`.&#x20;

### AutoGluon

[Autogluon](https://auto.gluon.ai) is an open source framework that provides automated ML automates machine learning tasks and enables users to easily achieve strong predictive performance. For time series models, Autogluon produces multi-step ahead _probabilistic_ forecasts via a range of models: simple forecasting tools, tree-based methods, deep learning models, and ensembles. AutoGluon will train several models, rank their performance on internal validation data and metrics, and produce the best model (possibly a weighted ensemble) for use in inference, entirely under-the-hood.&#x20;

To use the AutoGluon framework on SpiceAI, use an `autogluon` type in the [.](./ "mention") and, optionally, provide hyperparameters for underlying prediction models. For example, in the abbreviated Manifest below, we define our time series predictor to use two models: a basic trend-normalised neural network model (`DLinear`) using default parameters and, a [theta](https://doi.org/10.1016/S0169-2070\(00\)00066-2) forecasting model with additive decomposition and a seasonality of twelve periods (relative to the input time increment).  If not specified, a set of baseline models are used.&#x20;

```yaml
// Rest of fields defined above.
type: autogluon
metadata:
  model:
    hyperparameters:
      DLinear: {}
      Theta:
        decomposition_type: additive
        seasonal_period: 12
```

### Darts

[Darts](https://unit8co.github.io/darts/) is a popular, easy to use, open-source framework for time-series forecasting. It provides a large suite of time series models. To use Darts on SpiceAI, use a `darts` type in the [.](./ "mention") and, optionally, specify a model architecture (from [Darts](https://unit8co.github.io/darts/generated\_api/darts.models.forecasting.html)), and, optionally, parameters to use with the model architecture. For example, in the abbreviated Manifest below, we define a random forest model, and specify both a (possible parameters are those passed to `__init__` method, e.g. for [Random Forest](https://unit8co.github.io/darts/generated\_api/darts.models.forecasting.random\_forest.html#darts.models.forecasting.random\_forest.RandomForest)). &#x20;

```yaml
// Rest of fields defined above.
type: darts
metadata:
  model:
    // From class name in Darts, `darts.models.forecasting.random_forest.RandomForest`
    model_type: RandomForest
    
    // From __init__ method for RandomForest in Darts
    parameters:
      max_depth: 3
      n_estimators: 50
```
