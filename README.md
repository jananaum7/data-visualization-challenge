# Pymaceuticals Inc. --- 
### Analysis 
mouse_id_timepoint = clean_df["Drug Regimen"].value_counts() 
mouse_id_timepoint.plot(kind="bar", figsize=(6.5,4.5), color='steelblue') 
plt.xlabel("Drug Regimen") 
plt.ylabel("# of Observed Mouse Timepoints") 
plt.xticks(rotation=90) 
plt.show 
1. The code generates a bar plot showing the number of observations for each drug 
regimen in your dataset. It counts the occurrences of each regimen and displays them as 
bars, with the height of each bar representing the number of observations. The plot 
includes labeled axes and rotates the x-axis labels for clarity. Capomulin and Ramicane 
have the highest number of observations, indicating that these drug regimens were 
administered to the most mice or were recorded the most frequently in the dataset. This 
suggests a higher level of data collection or interest in these treatments. 
____________________________________________________________________________________ 
gender = clean_df['Sex'].value_counts() 
gender.plot.pie( 
autopct='%1.1f%%',  
colors=['steelblue', 'darkorange'],  
startangle=0, 
ylabel='Count',   
) 
plt.axis('equal') 
plt.show() 
2. The code generates a pie chart showing the distribution of male versus female mice in 
the study. It counts the unique mice by gender, revealing that males make up 50.6% of the 
total and females make up 49.4%. This indicates a nearly equal representation of both 
genders in the study. 
____________________________________________________________________________________ 
cor_coe = st.pearsonr(avg_tumor_volume['Weight (g)'],  
avg_tumor_volume ['Tumor Volume (mm3)'])[0] 
  
print(f"The correlation coefficient between mouse weight and average weight tumor 
volume is {cor_coe:.2f}") 
  
(slope, intercept, rvalue, pvalue, stderr) = st.linregress(avg_tumor_volume ['Weight (g)'],  
                                                          avg_tumor_volume['Tumor Volume (mm3)']) 
  
x = avg_tumor_volume['Weight (g)'] * slope + intercept 
  
plt.scatter(avg_tumor_volume['Weight (g)'], avg_tumor_volume['Tumor Volume (mm3)'], 
color='steelblue') 
plt.plot(avg_tumor_volume['Weight (g)'], x , "r-") 
  
plt.xlabel("Weight (g)") 
plt.ylabel("Average Tumor Volume (mm3)") 
plt.show() 
  
3. The analysis shows a strong positive correlation (0.84) between mouse weight and 
average tumor volume, indicating that as mouse weight increases, tumor volume tends to 
increase as well. The linear regression line, which slopes upwards, visually confirms this 
relationship, reflecting a clear upward trend in tumor volume with increasing mouse 
weight.
