# Data-Mining-Project1

## Introduction

In this repository, I uploaded my team-project on the Seoul National University(SNU) Statistic department Data-mining course team project result. Our team project's goal was to apply the statistical methods in regression problem, and our topic is

<center>**Predictive Model for Property Damage Costs Caused by Fires**</center>

## Proposal

We have explored the property damage costs caused by fires. Our goal was to predict the damage costs by the variables related to the fires.

## DataSet

We used fire incident data provided by the Seoul Metropolitan Fire & Disaster Headquarters through the Fire Safety Big Data Platform, along with population data from the Seoul Open Data Portal. The data sources are as follows:

- Fire Incident Data: 22,042 fire incidents in Seoul from 2017 to 2021.
- Building Information: Building structure, number of floors, total floor area, building area, and facility type.
- Fire Information: Date and time of occurrence, response time, fire suppression time, location, ignition source, and cause of fire.
- Weather Data: Hourly temperature, precipitation, wind speed, humidity, snowfall, visibility, and wind direction.
- Population Data: Daily total population, daytime population, and nighttime population from 2018 to 2021.

We processed the data as follows:

- Selected building fire incidents with available property damage information.
- Combined fire incident data with population data.
- Removed observations with missing values in population, weather, and building area information.
- Removed outliers in building area variables, including zero values and values exceeding 426,719.

- After preprocessing, we obtained 15,257 fire incidents with 34 variables for predicting property damage costs.

### Variables (Independent variables)

- Building information: 건물구조조, 지상층수, 지하층수, 연면적, 바닥면적, 시설장소대분류명, 발화층명, 화재보험의무가입대상여부, 방화관리대상여부, 다중이용업여부
- Fire information: 화재발생연도, 화재발생월, 화재발생시, 요일, 시군구명, 발화열원명, 발화요인대분명, 최초착화물대분류명, 출동 소요시간, 화재진압시간, 현장소방서거리, 현장안전센터거리, 현장소방지역대거리
- Weather data: 시간단위기온, 시간단위강수량, 시간단위풍속, 시간단위습도, 시간단위적설량, 시간단위가시거리, 풍향
- Population data: 총생활인구수, 주간인구수, 야간인구수

## Modeling

We have tried following Models : 

- Linear Regression: with variable selection (forward selection)
- Ridge and LASSO regression, with or without interaction
- PCR and PLS
- Natural Spline
- Generalized Additive Model
- Spline with LASSO


## Modeling Result

We compared 10 fold Cross Validation MSE and AIC, BIC. 

<img width="701" alt="Comparison metrics" src="https://github.com/DongHyun-Park-1021/Data-Mining-Project1/Modeling/Results">

## Model Performance and Inference

The best model was GAM, which dominated Cross Validation MSE and AIC, BIC of the other models. This is mainly because the relation to the independent variables are quite nonlinear as the EDA result says. Thus, the nonparametric method predicted better to the linear regression methods.
