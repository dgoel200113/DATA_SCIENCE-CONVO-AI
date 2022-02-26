# DATA_SCIENCE-CONVO-AI
Project Name: House Prices: Advanced Regression Techniques

The main aim of this project is to predict the house price based on various features using the RAPIDS library

Link to Kaggle Notebook: https://www.kaggle.com/dhruvgoel200113/dhruvgoel-102083029-ds-assign1

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# About the dataset

These are the various parameters given in the Dataset. We need to preprocess the data given to us to build an effective model.

SalePrice - the property's sale price in dollars. This is the target variable that you're trying to predict.

MSSubClass: The building class

MSZoning: The general zoning classification

LotFrontage: Linear feet of street connected to property

LotArea: Lot size in square feet

Street: Type of road access

Alley: Type of alley access

LotShape: General shape of property

LandContour: Flatness of the property

Utilities: Type of utilities available
LotConfig: Lot configuration

LandSlope: Slope of property

Neighborhood: Physical locations within Ames city limits

Condition1: Proximity to main road or railroad

Condition2: Proximity to main road or railroad (if a second is present)

BldgType: Type of dwelling

HouseStyle: Style of dwelling

OverallQual: Overall material and finish quality

OverallCond: Overall condition rating

YearBuilt: Original construction date

YearRemodAdd: Remodel date

RoofStyle: Type of roof

RoofMatl: Roof material

Exterior1st: Exterior covering on house

Exterior2nd: Exterior covering on house (if more than one material)

MasVnrType: Masonry veneer type

MasVnrArea: Masonry veneer area in square feet

ExterQual: Exterior material quality

ExterCond: Present condition of the material on the exterior

Foundation: Type of foundation

BsmtQual: Height of the basement

BsmtCond: General condition of the basement

BsmtExposure: Walkout or garden level basement walls

BsmtFinType1: Quality of basement finished area

BsmtFinSF1: Type 1 finished square feet

BsmtFinType2: Quality of second finished area (if present)

BsmtFinSF2: Type 2 finished square feet

BsmtUnfSF: Unfinished square feet of basement area

TotalBsmtSF: Total square feet of basement area

Heating: Type of heating

HeatingQC: Heating quality and condition

CentralAir: Central air conditioning

Electrical: Electrical system

1stFlrSF: First Floor square feet

2ndFlrSF: Second floor square feet

LowQualFinSF: Low quality finished square feet (all floors)

GrLivArea: Above grade (ground) living area square feet

BsmtFullBath: Basement full bathrooms

BsmtHalfBath: Basement half bathrooms

FullBath: Full bathrooms above grade

HalfBath: Half baths above grade

Bedroom: Number of bedrooms above basement level

Kitchen: Number of kitchens

KitchenQual: Kitchen quality

TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)

Functional: Home functionality rating

Fireplaces: Number of fireplaces

FireplaceQu: Fireplace quality

GarageType: Garage location

GarageYrBlt: Year garage was built

GarageFinish: Interior finish of the garage

GarageCars: Size of garage in car capacity

GarageArea: Size of garage in square feet

GarageQual: Garage quality

GarageCond: Garage condition

PavedDrive: Paved driveway

WoodDeckSF: Wood deck area in square feet

OpenPorchSF: Open porch area in square feet

EnclosedPorch: Enclosed porch area in square feet

3SsnPorch: Three season porch area in square feet

ScreenPorch: Screen porch area in square feet

PoolArea: Pool area in square feet

PoolQC: Pool quality

Fence: Fence quality

MiscFeature: Miscellaneous feature not covered in other categories

MiscVal: Value of miscellaneous feature

MoSold: Month Sold

YrSold: Year Sold

SaleType: Type of sale

SaleCondition: Condition of sale

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

I have done the following things in my project:

1) Handling Null values: Many features had a lot of missing values, I have removed features in which more than 40% of the data was missing and used median imputation to fill the                          remaining missing values for numerical features and filled the missing categorical values with 'missing'

2) Seperating Numerical(Discrete and Continous) and Categorical features : This was done to help process the data more easily

3) Temporal Variables: From the Dataset we have 4 year variables. We have to extract information from the datetime variables like no of years or no of days. The temporal                                variables were: ['YearBuilt', 'YearRemodAdd', 'GarageYrBlt', 'YrSold']. I subtracted the features from the date sold to find out the number of years that                        each feature depicts.

4) Applying Log tranformation to continous features: This was done to ensure that the data follows gaussian distribution which is better for the model

5) MinMaxScaler: I used the minmaxscaler to normalize the data however the accurary decreased so I decided to opt out of it, couldnt understand the reason behind it.

6) Encoding: Since most of the features had a large number of unique values I used a label encoder instead of the one-hot encoder. if I had used a one-hot encoder the number of              parameters would have increased dramatically and created sparse data.

7) Removing highly correlated features: There was an error occuring with the rapids library while trying to display the heatmaps, so I referred another notebook to identify the                                         correlated features and removed them manually.  

8) Train-Test Split: Since the testing data didnt have a saleprice column I used some of the training data to evaluate my model.

9) Model Training: I used the following linear regression algorithms to train the model: ['svd', 'eig', 'qr', 'svd-qr', 'svd-jacobi']

10) Model Evaluation: Used the metrics: MSE, R2 Score, MAE to evalute the model and found that the svd eig and qr algorithms were yeilding the highest R2 scores

