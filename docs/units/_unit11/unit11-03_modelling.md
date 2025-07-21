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

1) Mechanistic Models

Physical (mechanistic) models are based on known laws of physics, chemistry, or biology. They describe processes using equations derived from theoretical principles (e.g., energy balance, fluid flow, mass conservation). They are used when the underlying mechanisms are well understood — for example, modelling how temperature changes with elevation using the adiabatic lapse rate. 

```{r}
# Temperature as a function of elevation using a standard lapse rate
elevation <- seq(0, 3000, by = 100)      # meters
T0 <- 20                                 # sea-level temperature in °C
lapse_rate <- -6.5 / 1000                # °C per meter

temperature <- T0 + lapse_rate * elevation

plot(elevation, temperature, type = "l",
     xlab = "Elevation (m)", ylab = "Temperature (°C)",
     main = "Temperature vs. Elevation (Physical Model)")
```


2. Statistical Models
Statistical models use observed data to estimate a mathematical relationship between Y (the dependent variable) and one or more predictors (independent variables). The model form is specified by the user (e.g., linear, logistic), and model parameters such as intercept and slope are estimated from data. There are different types of models you can use, see the chapter [Modeling](https://bookdown.org/igisc/EnvDataSci/modeling.html) by *Environmental Data Science* for a nice summary and explanation.

```{r}
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

3. Machine Learning Models
Machine learning (ML) models learn patterns from data without requiring the user to specify a functional form. These models focus on prediction and can capture complex, nonlinear interactions, often at the cost of interpretability.

In supervised ML, the algorithm is trained on a dataset with known outcomes (X and Y), and adjusts internal rules or weights to minimize prediction error. Performance is typically evaluated using techniques like cross-validation to avoid overfitting. Once validated, the trained model can be used to predict Y for new data.

Examples of ML methods used in environmental modelling include random forests, boosted regression trees, support vector machines, and neural networks. If you want to dive deeper into this, take [this course](https://geomoer.github.io/moer-bsc-project-seminar-SDM/)

