Any Learning involves the following steps:
    
    
               1)Data Preprocessing
               2)Selecting the best ML-model
               3)Visualizing the data
               4)predecting the outcome of the model





This is a simple Linear Regression code using python.

         A simple linear regressor is of the form: y=ax+b
         
                                              where y-dependent variable
                                                    x-independent variable
               
               
It involves step by step procedure to build a simple Linear Regression Model which Predects the Salary Of the CEO.



step-1:.........................IMPORTING LIBRARIES.............................

Pythons Offers Different Libraries which makes the coding easy.They are:

a)Pandas library

b)scikit-learn library

c)Numpy library

d)matplotlib library

                              import numpy as np
                              import matplotlib.pyplot as plt
                              import pandas as pd

step-2:..........................Importing Dataset.............................

                                 dataset = pd.read_csv('Salary_Data.csv')
                                 
step-3:.....................Data Preprocessing.............................

It involves the splitting the data and dividing it into dependent(y) and independent variables(x).

                          
                             X = dataset.iloc[:, :-1].values
                             y = dataset.iloc[:, 1].values
                             
step-4:.............Splitting the data into Training set and Test set......................

here me make use of sklearn libraray.

                           from sklearn.cross_validation import train_test_split
                           X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 1/3, random_state = 0)
here test_size parameter is used to specify the size of training set and test set.

step-5:.............................Feature Scaling......................

It is used to convert the naming variables into intigers(name,salary,post == 0,1,2)

                     from sklearn.preprocessing import StandardScaler
                     sc_X = StandardScaler()
                     X_train = sc_X.fit_transform(X_train)
                     X_test = sc_X.transform(X_test)
                     sc_y = StandardScaler()
                     y_train = sc_y.fit_transform(y_train)
                     
step-6:.............................Fitting Simple Linear regression to the Training set........................

                           from sklearn.linear_model import LinearRegression
                           regressor = LinearRegression()
                           regressor.fit(X_train, y_train)

step-7:............................Predecting the test set results..................................

                               y_pred = regressor.predict(X_test)

step-8:........................Visualising the Training set results.................................


                   plt.scatter(X_train, y_train, color = 'red')
                   plt.plot(X_train, regressor.predict(X_train), color = 'blue')
                   plt.title('Salary vs Experience (Training set)')
                   plt.xlabel('Years of Experience')
                   plt.ylabel('Salary')
                   plt.show()

                            
