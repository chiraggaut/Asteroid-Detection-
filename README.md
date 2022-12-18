<h1>Asteroid Diameter Prediction using Machine Learning & Neural Networks</h1>

We have used different algorithms to test and evaluate the model's performance with the same dataset. The diameter of an asteroid is one the most important physical parameter of an asteroid; it is used to calculate many other physical and basic parameters of the asteroid, like calculating the rotation period of an asteroid, and also used to detect if an asteroid is potentially hazardous or not if it is found to be a Near Earth Object
<h2>Dataset Description</h2>
The dataset we have used is officially maintained by NASA Jet Propulsion Laboratory. In this dataset, we have considered all types of asteroids, such as asteroids that are grouped as Near Earth Objects(NEO) and Potentially Hazardous Objects(PHA); we have also considered all the possible asteroid orbit classes as mentioned in the official website of JPL(Jet Propulsion Laboratory). The columns of the dataset also contain all the physical and basic properties of an asteroid. The dataset consists of 839714 rows and 31 columns. The columns consist of orbital details of the asteroid like semi-major axis(a), eccentricity(e), inclination(i), perihelion distance(q), condition code of orbit, orbital period, and a number of observations used, aphelion distance (Q). The column also consists of some essential characteristics of asteroids like it is physically hazardous or not(PHA), whether it falls under a near-earth object or not (NEO), its absolute magnitude(H), and geometric albedo value(albedo). The whole dataset is available on the official website of NASA’s Jet Propulsion Laboratory
<h2>Exploratory Data Analysis</h2>
A large number of NULL values was present in the dataset, which needed to be dealt with accordingly. The columns were of different data types which needed to be converted into numerical values. Label Encoding was applied to ‘pha’ & ‘neo’ which had values Y/N; ‘class’ was an object type with 11 different values so we applied one-hot encoding to make the data more suitable for running algorithms. Plotted various plots to understand the distribution of data.
<h2>Outliers</h2>
There we plenty of outliers in the dataset. ‘e’, ‘om’, ‘w’, ‘data_arc’, ‘ma’, and ‘diameter’ had a major amount of outliers. These outliers were removed from the dataset using the quantile method by removing values above the 99 percentile and below 0.01 percentile, except diameter, in which only values above the 99 percentile were removed.
<h2>Splitting of Data</h2>
Stratified Splitting was applied to the dataset to make it ready for models. For applying stratified split, the corresponding row shouldn't have unique values or classes having less than two values. So to bypass this we grouped the 'diameter' into 5 groups each with a certain range associated with it so that a Stratified split can be executed. 20% of the data was kept for testing and the remaining 80% was taken for training. The diameter in both the test and train was dropped and kept as the target dataset.
Feature Scaling in both training and testing datasets was done using Scikit Learn’s Standard Scaler
<h2>Applying Models</h2>
Various machine learning models were applied to the clean dataset. Hyperparameter Tuning was done on each model to get the most accurate results possible. Scikit Learn’s Grid Search CV was used to determine the correct parameters
<h3>● ElasticNet</h3> ○ Mean square error: 1.3694016972923255 ○ Root mean square error: 1.1702143809116026 ○ R2 Score: 0.8389064229364398
<h3>● Random Forest</h3> ○ Mean square error: 0.2834287927095259 ○ Root mean square error: 0.5323803083412514 ○ R2 Score: 0.9666580243396345
<h3>● Gradient Boosting</h3> ○ Mean square error: 0.2579893529981839 ○ Root mean square error: 0.5079265232277045 ○ R2 Score: 0.9696506672943614
<h3>● ADA Boost</h3> ○ Mean square error: 1.7620771877787496 ○ Root mean square error: 1.3274325548888537 ○ R2 Score: 0.7927128922049363
<h3>● XG BOOST</h3> ○ Mean square error: 0.2716591263311855 ○ Root mean square error: 0.5212092922532996 ○ R2 Score: 0.9680425834952721
<h3>● LGBM Regressor</h3> ○ Mean square error: 0.2642560656098385 ○ Root mean square error: 0.5140584262609051 ○ R2 Score: 0.9689134642128719
<h3>● Bagging Regressor</h3> ○ mean square error: 1.7385813822533702 ○ root mean square error: 1.318552760511831 ○ R2 Score: 0.7954768900629476
<h3>● Multi-Layer Perceptor Regressor</h3> ○ Mean square error: 0.32965359284930806 ○ Root mean square error: 0.27379804448499884 ○ R2 Score: 0.9682133074568802
<h3>● Sequential Regressor</h3> ○ Root mean square error: 0.2698747217655182 ○ R2 Score: 0.9683013054282881

<h2>Conclusion</h2>
Space researches could proceed further with the help of machine learning algorithms. Here we accept the MultiLayer Perceptron algorithm to be the best to tackle these types of a problem after all types of evaluation. The model discussed in this paper could be improved further with higher scores and accuracy and fewer errors with the help of other machine learning algorithms or with advanced processing techniques to pre-process data or through deep learning.
The Best Results were obtained by using Gradient Boosting Regression with the mean squared error of 0.2579893529981839 and an R2 score of 0.969650667294361
