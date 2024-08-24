# Analyzing Social Media's Impact on Emotional Well-Being and Preventive Measures
## Business Problem
The rise of social media has sparked concerns about its impact on mental health. While social media can enhance social connectivity and provide entertainment, excessive or negative interactions may lead to emotional distress. Research indicates that social media can have the opposite effect of its intended purpose.  Instead of making people feel more connected and social, it has led to decreased social interactions and increased emotional distress.  This study aims to identify specific social media usage patterns that influence emotional well-being, helping to develop strategies for healthier digital habits. Additionally, the study will identify which users are more affected and which social media networks have the most negative impact.
## Data Set

This dataset includes user demographics, social media activity, and dominant emotional states. Key features are:

- **Age**: User's age
- **Gender**: User's gender (Female, Male, Non-binary)
- **Platform**: Social media platform used (e.g., Instagram, Twitter, Facebook, LinkedIn, Snapchat, WhatsApp, Telegram)
- **Daily Usage Time (minutes)**: Time spent on the platform daily
- **Posts Per Day**: Number of posts made per day
- **Likes Received Per Day**: Number of likes received daily
- **Comments Received Per Day**: Number of comments received daily
- **Messages Sent Per Day**: Number of messages sent daily
- **Dominant Emotion**: User's dominant emotional state (e.g., Happiness, Sadness, Anger, Anxiety, Boredom, Neutral)

## Data Source: 
The data was compiled by Emirhan BULUT and can be found on Kaggle: [Kaggle](https://www.kaggle.com/datasets/emirhanai/social-media-usage-and-emotional-well-being/data).
## Projected Data Analytics Approach

1. **Data Preprocessing**: Clean the data, engineer new features, normalize numerical values, and one-hot encode categorical variables.
2. **Exploratory Data Analysis (EDA)**: Identify trends and relationships between social media usage and emotional states. Extract insights for OLS regressions.
3. **Predictive Modeling**: Apply OLS regressions to determine variables affecting users' mental states. Use machine learning algorithms to predict dominant emotional states based on social media usage patterns.
4. **Model Evaluation**: Evaluate model performance using metrics such as accuracy, precision, recall, and F1 score.
5. **Cluster Analysis**: Cluster users to identify distinct groups and analyze the impact on their emotional well-being.

# Hypotheses

1. **H1**: Certain social media platforms may have a more negative impact on users, with Instagram potentially being particularly detrimental.
2. **H2**: Time spent on social media may not directly correlate with dominant emotions, but feedback received from social media activity does.

**Practical Implications**

1. **Policymakers**: Develop guidelines for healthier social media use, establish protections for vulnerable groups, and collaborate with platforms and mental health organizations.
2. **Educators and Counselors**: Create digital literacy programs, integrate findings into curricula, and offer support services for affected individuals.
3. **Social Media Platforms**: Use insights to enhance user experience, implement proactive measures like content moderation, and focus on user mental health.
4. **General Public**: Raise awareness, encourage discussions to destigmatize mental health issues related to social media, and promote a healthier digital environment.

## Methodology:
1.	Data Cleaning: I addressed inconsistencies by removing rows with missing values, as these did not contribute meaningful information. I identified and corrected data type issues by examining the dataset thoroughly. It became apparent that two columns, age and gender, had some of their values swapped. After rectifying this error, I converted the columns to their appropriate data types.
2.	Plotting: I conducted exploratory data analysis by first plotting bar charts to understand the data distribution and identify any patterns that could support my hypothesis. Following this, I generated a correlation heatmap to explore the relationships between different variables, and finally, I produced a pairwise graph for further analysis.
3.	Data Processing: I split the data into training and testing sets and developed two pipelines to process numerical and categorical variables. For the numerical variables, I imputed missing values using the median and applied normalization using a standard scaler (mean of 0 and standard deviation of 1). For the categorical variables, I imputed missing values using the mode and performed one-hot encoding, dropping the first category for each variable to prevent multicollinearity. The same preprocessing steps were applied to the training, testing, and validation data. In the validation set, I removed one row because it contained a target value not present in the other two datasets.
4.	Cluster Analysis: I conducted cluster analysis by examining an elbow plot to determine the optimal number of clusters based on the numerical data. The plot indicated that the ideal number of clusters is two. After performing the clustering, the results revealed that individuals in Cluster 1 tend to have a higher concentration of happiness, whereas those in Cluster 0 are more likely to exhibit other sentiments. An analysis of the cluster means showed that people in Cluster 1 generally have higher numerical values for the numerical features. Additionally, I attempted to create six clusters to assess how well the numerical variables could differentiate between sentiments. The results indicated very low cluster purity, meaning that each cluster contained a diverse range of dominant emotions, suggesting that clustering is ineffective for determining someone’s emotions.
5.	Modeling: I employed three different models: Logistic Regression, Random Forest, and XGBoost. Among these, Random Forest initially performed the best, achieving 80% accuracy. I then conducted hyperparameter tuning to explore whether the models could be further optimized for higher accuracy. After tuning, the performance of XGBoost improved, yielding an 81% accuracy and an 82% balanced accuracy. I also experimented with ensemble models, but they did not outperform the tuned XGBoost model. Finally, I tested the model on the testing data, which suprisingly resulted in a 97% accuracy.
6.	Association Rules: To explore associations between categorical variables, I use association rules to identify if specific social media websites are significantly associated with particular sentiments. This approach helps to determine whether certain platforms exhibit stronger relationships with particular emotional responses.
## Results:
The research findings indicate that certain platforms are indeed correlated with specific predominant sentiments. For instance, Instagram is associated with happiness, LinkedIn with boredom, and Twitter with anger. Additionally, the modeling reveals that Instagram and LinkedIn are among the most significant variables for predicting sentiment. Other highly relevant variables include usage time and number of likes. These results suggest that sentiment is influenced not only by the platform itself but also by factors such as the amount of time spent on the platform and the feedback received through likes.
## Conclusions:
These results demonstrate that the choice of social media platform significantly impacts our sentiments, as the data reveals a predominant sentiment associated with each platform. Moreover, the amount of time spent on these platforms also plays a crucial role in affecting mental well-being. The data reveals that prolonged usage correlates with shifts in sentiment, emphasizing the importance of moderating online time. This insight supports the practice of limiting children’s screen time, as excessive exposure to certain platforms could potentially have a detrimental effect on their emotional health. By managing both the choice of platform and the duration of use, individuals can better maintain their emotional well-being and mitigate adverse effects.
## Future work: 
Given that this research paper is an observational study, the results are limited to identifying correlations rather than establishing causality. To obtain more definitive insights into the effects of social media on users, it is essential to conduct a field experiment. Such an experimental approach would allow us to determine causal relationships, providing a more comprehensive understanding of how social media usage directly impacts sentiment and mental well-being. Observational studies, while valuable for identifying patterns, may not fully capture the complexities of social media's influence. Therefore, further experimental research is necessary to confirm causative effects and provide a clearer picture of the relationship between social media usage and emotional outcomes. Despite the limitations inherent in observational studies, the model developed from the data demonstrates strong performance with high accuracy and balanced accuracy. This suggests that the model can effectively identify user sentiment on social networks. While the results are preliminary and cannot fully capture causality, the model's robustness provides a valuable tool for further exploration and analysis of social media sentiment.
![image](https://github.com/user-attachments/assets/a8273158-0431-48a4-9e16-5e1e8db34fce)
