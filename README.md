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

## Methodology

1. **Data Cleaning**: Removed rows with missing values and corrected data type issues. Fixed swapped values in the `age` and `gender` columns, then converted them to their appropriate data types.

2. **Plotting**: Conducted exploratory data analysis (EDA) by plotting bar charts to understand data distribution, generating a correlation heatmap to explore relationships, and creating a pairwise graph for further insights.

3. **Data Processing**: Split the data into training and testing sets. Developed pipelines for numerical and categorical variables:
   - Numerical: Imputed missing values with the median and normalized using a standard scaler.
   - Categorical: Imputed missing values with the mode and applied one-hot encoding, dropping the first category to avoid multicollinearity. Applied the same preprocessing to training, testing, and validation sets. Removed one row from the validation set due to an outlier target value.

4. **Cluster Analysis**: Used an elbow plot to determine that two clusters were optimal. Cluster analysis showed Cluster 1 had a higher concentration of happiness, while Cluster 0 exhibited diverse emotions. Attempted to create six clusters, but results showed low cluster purity, indicating clustering was not effective for differentiating emotions.

5. **Modeling**: Evaluated Logistic Regression, Random Forest, and XGBoost models. Random Forest initially had the best performance with 80% accuracy. After hyperparameter tuning, XGBoost improved to 81% accuracy and 82% balanced accuracy. Ensemble models did not surpass XGBoost. Testing data accuracy reached 97%.

6. **Association Rules**: Applied association rules to identify significant relationships between social media platforms and emotional responses, assessing which platforms are more strongly associated with particular sentiments.

## Results:
The research findings indicate that certain platforms are indeed correlated with specific predominant sentiments. For instance, Instagram is associated with happiness, LinkedIn with boredom, and Twitter with anger. Additionally, the modeling reveals that Instagram and LinkedIn are among the most significant variables for predicting sentiment. Other highly relevant variables include usage time and number of likes. These results suggest that sentiment is influenced not only by the platform itself but also by factors such as the amount of time spent on the platform and the feedback received through likes.
## Conclusions:
These results demonstrate that the choice of social media platform significantly impacts our sentiments, as the data reveals a predominant sentiment associated with each platform. Moreover, the amount of time spent on these platforms also plays a crucial role in affecting mental well-being. The data reveals that prolonged usage correlates with shifts in sentiment, emphasizing the importance of moderating online time. This insight supports the practice of limiting children’s screen time, as excessive exposure to certain platforms could potentially have a detrimental effect on their emotional health. By managing both the choice of platform and the duration of use, individuals can better maintain their emotional well-being and mitigate adverse effects.
## Future work: 
Given that this research paper is an observational study, the results are limited to identifying correlations rather than establishing causality. To obtain more definitive insights into the effects of social media on users, it is essential to conduct a field experiment. Such an experimental approach would allow us to determine causal relationships, providing a more comprehensive understanding of how social media usage directly impacts sentiment and mental well-being. Observational studies, while valuable for identifying patterns, may not fully capture the complexities of social media's influence. Therefore, further experimental research is necessary to confirm causative effects and provide a clearer picture of the relationship between social media usage and emotional outcomes. Despite the limitations inherent in observational studies, the model developed from the data demonstrates strong performance with high accuracy and balanced accuracy. This suggests that the model can effectively identify user sentiment on social networks. While the results are preliminary and cannot fully capture causality, the model's robustness provides a valuable tool for further exploration and analysis of social media sentiment.
![image](https://github.com/user-attachments/assets/a8273158-0431-48a4-9e16-5e1e8db34fce)
