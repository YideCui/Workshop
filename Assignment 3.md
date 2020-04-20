# Assignment 3: Methodology

## Predicting the Agricultural Productivity in Sub-Saharan Africa: How Random Forest and Artificial Neural Network Can Improve Research and Lives

### By Michael Cui

## Introduction:
According to the definition suggested by Amartya Sen, “human development is a process of expanding the real freedoms that people enjoy.” The fundamental freedom that people should possess is access to food. However, it has been regularly and consecutively stripped away around the world recently, especially in Sub-Saharan Africa. Through mapping the depth of the food deficit based on FAO data, Sub-Saharan Africa remains the region with the highest prevalence of hunger, with the rate increasing from 20.7 percent in 2014 to 23.2 percent in 2017.【3】What influences the stark contrast in food insecurity between developed and developing countries?

The answer is holistic. Poverty, gender inequality, and many other kinds of unfreedom will lead to this severe problem. Among those factors, however, agricultural productivity is the most direct inherent of food deficit. Agriculture is considered the most vulnerable sector to yearly climate change and variability, with an enormous impact on agricultural production. A lot of factors, including soil condition, precipitation, and temperature, will affect the crop yield, which made the prediction of crop production difficult in the past. However, crop modeling plays a significant role in agricultural production. Farmers have to use this predicting method to make better decisions and reasonable plans for seasonal crop planting. In the past, the combination of simple linear regression model and traditional survey data make the process time-consuming and less accurate. In this research, through using high-resolution satellite imagery, new and improved computer model and machine learning method can be generated to achieve a more precise prediction.

In particular, two studies have been carried out by two groups to predict agricultural production using geospatial models in Sub-Saharan Africa. The first study by Valentine LeBourgeois’s group analyzed and optimized the performance of a combined Random Forest (RF) classifier approach and applied it to multisource satellite data to produce land use maps of a smallholder agricultural zone in Madagascar.【1】 The other research by Omolola M. Adisa and his group utilized the climate variables such as precipitation, temperature, and soil moisture as the dataset. Then they use artificial neural network (ANN) models for predicting maize in the major maize producing provinces of South Africa.【2】By analyzing and comparing these two studies, the central research question will be able to further investigated: how can data scientists make better prediction of agricultural production by machine learning and geospatial data for the decision makers in Sub-Saharan Africa to make have better management of land-use?


## Inquiry Type:
This research question falls under the explanatory lens. It attempts to describe “how things happen” and “what are the processes involved.” The research asks how we can better predict agricultural production in order to provide, which has to find out the factors of crop yields as well as define the significance of each factor. The broader central question is based on the scope of Sub-Saharan Africa.

To have the exploration process more organized, sub-research questions are developed in this article. The first one is, what are the key factors that influence the crop yield in Sub-Saharan Africa? This is an explanatory question. In Omolola’s research, he claims that even though socioeconomic issues such as poverty will lead to a less productive agricultural system, climate variables are more significant.【2】The second one is how can remote sensing data contribute to the prediction. This is a descriptive question. The research will answer it by investigating the application of random forest and artificial neural networks. The third question is how important the use of these improved computer models is, which falls under the evaluative lens since the comparison and discussions will be included.


## Methods:
### Method 1: Random Forest (RF)
In the article, “A Combined Random Forest and OBIA Classification Scheme for Mapping Smallholder Agriculture at Different Nomenclature Levels Using Multisource Data,” random forest and OBIA Classification are used. The study zone is a central highland at an average altitude of 1700 m in Madagascar, which scales at 60km × 60 km. The dataset is both collected from fields survey and satellite images. The ground survey was conducted during the growing peak (end of February and March) of the 2014–2015 cropping season to visit farmers’ fields in the study zone. The GPS waypoints were registered following an opportunistic sampling approach. With the combined of field databases and photo interpretation of high-resolution PLEIADES imagery, 1219 usable points are generated, including 860 cropped classes and 359 non-cropped classes. Even though it increases the resolution level, it has high special variability and the observation will be affected by the cloud coverage, which both challenge the mapping techniques. Therefore, the author uses Object-based image analysis (OBIA) for deriving objects that are made up of several pixels. This results a final population of 2314 polygons in the ground database, including 1415 crop and 899 non-crop, all of which are were recorded at different levels of detail (cropland, land cover, crop group, crop class, and crop subclass) according to the Joint Experiment for Crop Assessment and Monitoring (JECAM) nomenclature (Table 1). These polygons combined with the descriptive satellite variables, which are shown in Table 2 are hereafter referred to as the learning database.

![Table 1](https://github.com/YideCui/Image-for-DATA/blob/master/Images/Table%201.jpeg?raw=true)
Table 1: Number of polygons per class in the learning database for each level of the JECAM nomenclature

![Table 2](https://github.com/YideCui/Image-for-DATA/blob/master/Images/Table%202.jpeg?raw=true)
Table 2: Description of the variables extracted to build the learning database

Random Forest (RF) is found to be useful and effective, especially in the assessment of land use. As the classification accuracy is estimated internally and does not require an independent validation set, all ground samples can be used for RF training, which can be crucial in study areas where ground data can be challenging to gather. In this study, RF was trained at each nomenclature level using the entire learning database to obtain classifiers at different nomenclature levels. In this article, instead of the classical approach, Valentine uses a hierarchical approach. After separating the data into cropland and non-cropland at level 1, the author then builds classifiers for discrimination, respectively, for the following nomenclature levels, which improves the accuracy of the whole model. Through the McNemar’s test, both level 1 and 5 have the p-value lower than 0.001, which show the significance of on hierarchical approach the prediction. However, level 1 has an overall accuracy of 91.7, while level 5 has 64.4 for crop classes and 80.2 for non-crop classes.

The maps obtained from the hierarchical approach at level 1 (cropland) and 5 (crop subclass) are shown respectively in Figures 1 and 2. The cropland map allows for the identification of the central production basin and the hydrological network, especially in the eastern part of the area, due to the systematic use of lowlands for irrigated agriculture. The crop subclass map shows that irrigated rice dominated almost all the watercourses. With these mapping techniques, the agricultural public policymakers can easily classify the rainfed areas from irrigated areas, as well as acquire other information on acreage and locations, which further help them develop more effective policies to assuage food deficit problem in Sub-Saharan Africa.【1】

![Figure 1](https://github.com/YideCui/Image-for-DATA/blob/master/Images/Figure%201.jpeg?raw=true)
Figure 1: Maps acquired at level 1 via the hierarchical classification approach

![Figure 2](https://github.com/YideCui/Image-for-DATA/blob/master/Images/Figure%202.jpeg?raw=true)
Figure 2: Maps acquired at level 5 via the hierarchical classification approach

###Method 2: Artificial Neural Network (ANN)
In the article, “Application of Artificial Neural Network for Predicting Maize Production in South Africa,” artificial neural network (ANN) models were used. The study zone is focusing on the north-eastern part of South Africa between longitude 22◦ E to 33◦ E and latitude −32◦ S to −24◦ S, including four provinces. There are seven input data used in the study: Normalized Difference Vegetation Index (NDVI), Potential Evapotranspiration (PET), Precipitation (PRE), Minimum Temperature (TMN), Maximum Temperature (TMX), Soil Moisture (SM), Size of land cultivated for maize production (LAND). The dependent variable is the maize production per province. Most of the datasets are collected from the Climate Research Unit. As the independent variables are diverse and interrelated with each other, the standard regression model might not be useful in this case.

The application of ANN often resolves the complex relations and strong nonlinearity between crop production and different interrelated predictor parameters. ANNs are designed to simulate the way the human brain processes information. Thus, it does not involve pre-established physical relationships but still can extract information from imprecise and non-linear data by training itself and learning from the fed date. Below (Equation 1) is the mathematical model where: y is the output, x1-xn represents the input variables, w1-wn represents the weights of the combination which generates the output. And θ(.) is the unit step function

![Equation 1](https://github.com/YideCui/Image-for-DATA/blob/master/Images/Equation%201.jpeg?raw=true)
Equation 1

Because there is no standard method for the selection of variables in the neuron network, through testing various variable combinations, the author generated the best combination for the model. Each province has its own unique but best-fit variable combinations as well as hidden neurons. For instance, in the FS province, the combination of TMX, Land, and SM variables at different automated two hidden neurons with vector (8,9) ranked first within this group with 76.64% accuracy and has a root mean squared error (RMSE) of 0.038. Overall, the dataset will be divided into two segments: 80% used for model training and the remaining 20% for testing. After processing the data and training the neural network, the results are shown in the form of network topology. (Figure 3 (A)(B)(C)(D))

![Figure 3](https://github.com/YideCui/Image-for-DATA/blob/master/Images/Figure%203.jpeg?raw=true)
Figure 3: Neural network topology for the best combined variables for (A) FS: Free State, (B) NW: North West, (C) MP: Mpumalanga and (D) KZN: KwaZulu-Natal provinces.

After the author generated the predicting results, he then compares these results with the testing data that has not been fed in the program. The adjusted R square value, with 0.75 in the FS, 0.67 in the NW, 0.86 in MP and 0.82 in KZN shows the accuracy level of the prediction. The detailed prediction is shown in Table 3.

![Table 3](https://github.com/YideCui/Image-for-DATA/blob/master/Images/Table%203.jpeg?raw=true)
Table 3: Projected maize productions for four provinces respectively

Even though the accuracy level is not perfect for the prediction, the model still helps the decision-makers to get prepared. For instance, even though the number is not that precise, the trend is correct. The decline of predicted maize production can indeed warn the small-scale farmers to prevent loss of production and potential aggravated famine, which further assuage food security and achieve human development.【2】


## Discussion:
Though these two sources make great strides towards answering the central research question, there are still many gaps in the area. For instance, the study zone in LeBourgeois’s article is too small. His mapping can be further expanded by using it in other cities and countries in Sub-Saharan Africa. Also, as both of the articles use the machine learning method, the correlations between the factors and crop yields are ignored. Consequently, it is hard to tell which factor is most significant to the agricultural production.

Valentine Lebourgeois uses the random forest to map smallholder agriculture and land use. And Omolola Adisa pays more attention to predicting the crop yield by applying ANNs. In the real world, the combination of both two is the key to improve agricultural productivity in Sub-Saharan Africa. A map is not enough; it is not valid until people use it to improve production. Similarly, the prediction of crop yields will not work until people find out the smarter way to use their land and make the prevention to the potential famine. I guess the gap is hidden between the two. Mapping is the tool, and production is the goal. Lebourgeois does not mention how to use the map, and Adisa does not mention what we can do to prevent the predicting decline of maize yield. By combining both of them, we can find a way to improve the whole agricultural system in Sub-Saharan Africa.

My research question is, “how can data scientists make a better prediction of agricultural production by machine learning and geospatial data for the decision-makers in Sub-Saharan Africa to make have better management of land-use?” These two articles effectively solve the first half of the question: to use data science to predict agricultural production. How decision-maker makes a better decision based on the maps and prediction is still a question that needs to be answered.


## Reference:
【1】Lebourgeois, V., Dupuy, S., Vintrou, É., Ameline, M., Butler, S., & Bégué, A. (2017). A Combined Random Forest and OBIA Classification Scheme for Mapping Smallholder Agriculture at Different Nomenclature Levels Using Multisource Data (Simulated Sentinel-2 Time Series, VHRS and DEM). Remote Sensing, 9(3), 259. doi: 10.3390/rs9030259

【2】Adisa, Omolola, et al. “Application of Artificial Neural Network for Predicting Maize Production in South Africa.” Sustainability, vol. 11, no. 4, 2019, p. 1145., doi:10.3390/su11041145.

【3】Roser, Max, and Hannah Ritchie. “Hunger and Undernourishment.” Our World in Data, 8 Oct. 2019, ourworldindata.org/hunger-and-undernourishment.
