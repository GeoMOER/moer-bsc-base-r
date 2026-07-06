---
title: "Environmental modelling"
header:
  image:  /assets/images/unit_images/u06/header.png
  image_description: ""
  caption: ""
---

Environmental modelling is the process of identifying and quantifying the relationships between a response variable Y and a set of predictor variables X₁, X₂, ..., Xₙ, based on theoretical knowledge, empirical data, or both.

The core objective is to:  
•	Determine which variables are relevant to explaining or predicting Y  
•	Construct a model that includes these variables with interpretable or predictive structure  
•	Quantify the magnitude and direction of their effects on Y  
•	Use the model to analyze how changes in the predictors would affect Y  

In other words, environmental modelling is the process of using mathematical or computational models to represent, simulate, and predict how different components of the environment—such as air, water, soil, vegetation, and species—interact over space and time. It can be used for predicting future environmental conditions (e.g., climate change, pollution), which can help in supporting environmental policy and management decisions.  

Environmental models differ in how they represent the relationship between a response variable Y and explanatory variables. The three main types are:

## 1. Mechanistic Models

Physical (mechanistic) models are based on known laws of physics, chemistry, or biology. They describe processes using equations derived from theoretical principles (e.g., energy balance, fluid flow, mass conservation). They are used when the underlying mechanisms are well understood — for example, modelling how temperature changes with elevation using the adiabatic lapse rate. 

```
# Temperature as a function of elevation using a standard lapse rate
elevation <- seq(0, 3000, by = 100)      # meters
T0 <- 20                                 # sea-level temperature in °C
lapse_rate <- -6.5 / 1000                # °C per meter

temperature <- T0 + lapse_rate * elevation

plot(elevation, temperature, type = "l",
     xlab = "Elevation (m)", ylab = "Temperature (°C)",
     main = "Temperature vs. Elevation (Physical Model)")
```


## 2. Statistical Models

Statistical models use observed data to estimate a mathematical relationship between Y (the dependent variable) and one or more predictors (independent variables). The model form is specified by the user (e.g., linear, logistic), and model parameters such as intercept and slope are estimated from data. The most simple form is the linear model in an additive form:

$$
{\displaystyle y_{i}=\alpha +\beta x_{i}+\varepsilon _{i}.}
$$

where $y_{i}$ is your dependent variable, $\alpha $ is the y-intercept,$\beta $ is the slope for the independent variable x_{i} and $\varepsilon _{i}$ is the error term

Suppose we want to answer the question, whether fuel efficiency depends on car weight, engine power, and transmission type


```
set.seed(1)

n <- 25
altitude <- round(runif(n, min = 0, max = 3000)) 
temperature <- 20 - 0.0065 * altitude + rnorm(n, mean = 0, sd = 3)
temperature <- round(temperature, 1)
geo_data <- data.frame(altitude, temperature)
geo_data

plot(geo_data$altitude, geo_data$temperature)

model <- lm(temperature ~ altitude, data = geo_data)
summary(model)

abline(model, col = "red", lwd = 2)

```
The coefficients table given by `summary()` gives you estimates for the intercept and the slope of the variables, when wt and horsepower are both 0, and transmission is automatic (the first factor level). In other words, a linear model describes how the average outcome changes when predictors change, holding all others constant.

There are different types of models you can use, see the chapter [Modeling](https://bookdown.org/igisc/EnvDataSci/modeling.html) by *Environmental Data Science* for a nice summary and explanation.

```
# Simulated data: Insect abundance vs. temperature
data <- data.frame(
  abundance   = c(5, 0, 3, 7, 2, 0, 4, 8, 1, 6),
  temperature = c(22, 16, 20, 25, 18, 15, 21, 26, 17, 23)
)

# Fit Poisson regression (appropriate for count data)
model <- glm(abundance ~ temperature, data = data, family = poisson())
summary(model)

# Predict for new temperature values
new_data <- data.frame(temperature = seq(15, 27, by = 1))
predicted <- predict(model, newdata = new_data, type = "response")
plot(new_data$temperature, predicted, type = "l",
     xlab = "Temperature (°C)", ylab = "Predicted Abundance",
     main = "Predicted Insect Abundance vs. Temperature")

```
Note: the new_data must have the same variable names (=colnames) as in the model definition.  

Statistical models can include many more variables and interactions. For example, in species distribution modelling (SDM), one might model species presence or abundance based on environmental predictors like temperature, precipitation, and forest cover. These models are often used to estimate potential current — and under environmental change, future — species distributions.

⚠️ Note: Species Distribution Models must be interpreted with care. It is rarely possible to include all relevant predictors, especially those relating to biotic interactions or dispersal limitations.

In both mechanistic and statistical models, the estimated coefficients and model structure can be used to make predictions for new combinations of predictor values.

## 3. Machine Learning Models
Machine learning (ML) models learn patterns from data without requiring the user to specify a functional form. These models focus on prediction and can capture complex, nonlinear interactions, often at the cost of interpretability.

In supervised ML, the algorithm is trained on a dataset with known outcomes (X and Y), and adjusts internal rules or weights to minimize prediction error. Performance is typically evaluated using techniques like cross-validation to avoid overfitting. Once validated, the trained model can be used to predict Y for new data.

Examples of ML methods used in environmental modelling include random forests, boosted regression trees, support vector machines, and neural networks. If you want to dive deeper into this, take [this course](https://geomoer.github.io/moer-bsc-project-seminar-SDM/)

## 4. Evaluate the models

When we build a model for air quality, we need a way to quantify how good the predictions are.

For this, we compare a part of the observed values $y_i$ with the model predictions $\hat{y}_i$ using error measures.

**IMPORTANT**: the data used for testing must not be used in generating/training the model!

Two common  measures are MAE and RMSE.

### Mean Absolute Error (MAE)

This measure is defined as:  

$$
\mathrm{MAE} = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|
$$

It measures the average magnitude of prediction errors, or in other words, by how much the predictions deviate from the observed value on average, with units being the same as in the data (beware of any transformations you did before modelling, though).

## Root Mean Squared Error (RMSE)

This measure is defined as:
$$ \mathrm{RMSE} = \sqrt{ \frac{1}{n} \sum_{i=1}^{n} \left( y_i - \hat{y}_i \right)^2 } $$

This measurement penalizes large errors more strongly. It thus is a better indicator on how your model is performing in predicting extreme events. 




