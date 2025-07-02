# LinearRegression-HomePricePrediction
 “Beginner-level ML project predicting house prices and salaries using linear regression.”
reg.intercept_

de=pd.read_csv("/content/hiring.csv")
de

de['experience']=de.experience.fillna('zero')
de

de.rename(columns={'test_score(out of 10)':'test_score','interview_score(out of 10)':'interview_score','salary($)':'salary'},inplace=True)

de.columns

de['test_score']=de.test_score.fillna('zero')
de

print(de['experience'].unique())



change ={
    0:0,
    'five':5,
    'two':2,
    'seven':7,
    'three':3,
    'ten':10,
    'eleven':11
}
de['experience']=de['experience'].replace(change)

 reg =linear_model.LinearRegression()
reg.fit(de[['experience','test_score','interview_score']],de.salary)



reg.predict(pd.DataFrame({'experience':[2],'test_score':[9],'interview_score':[6]}))
