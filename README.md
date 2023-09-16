# More-than-Gloves
 We developed a model to predict the winner of a potential match based on examining the dataset containing UFC fights and fighters from 1993 to 2021. This model was trained using a vast pool of data, encompassing statistics and outcomes of numerous fights over the years. These data included the fighters' past performances, technical abilities, career statistics, and more.

Our model utilized various machine learning techniques to predict the outcome of a possible match based on the fighters' past performances. These predictions are made by analyzing the data related to the fighters' previous fights, strategies, and other factors. Machine learning techniques are employed to process this data and make predictions about the winning fighter.

DATA SET DESCRIPTION

This dataset encompasses the history of UFC fights, containing information about each fight, including fighter details, fight specifics, and the winner. Each row compiles the average statistics of both fighters. Fighters are represented as "red" and "blue" (red for the red corner, blue for the blue corner). For example, the red fighter has statistics that include the damage inflicted on their opponents and the damage received from their opponents in all of their previous fights. The same information is available for the blue fighter. The target variable is "Winner," which is the only column that determines who won.

COLUMN DESCRIPTIONS

- R_ and B_: Prefixes indicating red and blue corner fighter statistics, respectively.
- opp: Columns containing the average damage inflicted by the opponent on the fighter.
- KD: Knockdowns.
- SIG_STR: Significant strikes landed within significant strike attempts.
- SIG_STR_pct: Percentage of significant strikes landed.
- TOTAL_STR: Total strikes landed within total strike attempts.
- TD: Takedowns.
- TD_pct: Takedown percentage.
- SUB_ATT: Submission attempts.
- PASS: Number of times the guard was passed.
- REV: Reversals achieved.
- HEAD: Significant strikes to the head.
- BODY: Significant strikes to the body.
- CLINCH: Significant strikes in the clinch position.
- GROUND: Significant strikes on the ground.
- win_by: Method of victory.
- last_round: Last round of the fight (e.g., 1 if it ended in the first round due to knockout).
- last_round_time: Time when the fight ended in the last round.
- Format: Fight format (3 rounds, 5 rounds, etc.).
- Referee: Referee's name.
- date: Date of the fight.
- location: Location of the event.
- Fight_type: Weight class and whether it's a title match.
- Winner: The winner of the fight.
- Stance: Fighter's stance.
- Height_cms: Height in centimeters.
- Reach_cms: Reach in centimeters.
- Weight_lbs: Weight in pounds.
- age: Fighter's age.
- title_bout: A Boolean value indicating whether it's a title match or not.
- weight_class: Weight class of the fight (Bantamweight, Heavyweight, Women's Flyweight, etc.).
- no_of_rounds: Number of rounds scheduled for the fight.
- current_lose_streak: Current losing streak of the fighter.
- current_win_streak: Current winning streak of the fighter.
- draw: Number of draws in the fighter's UFC career.
- wins: Number of wins in the fighter's UFC career.
- losses: Number of losses in the fighter's UFC career.
- total_rounds_fought: Average number of rounds the fighter has fought.
- total_time_fought (seconds): Total time spent fighting in seconds.
- total_title_bouts: Total number of title bouts the fighter has participated in.
- win_by_Decision_Majority: Number of fights won by majority decision.
- win_by_Decision_Split: Number of fights won by split decision.
- win_by_Decision_Unanimous: Number of fights won by unanimous decision.
- win_by_KO/TKO: Number of fights won by KO/TKO.
- win_by_Submission: Number of fights won by submission.
- win_by_TKO_Doctor_Stoppage: Number of fights won by TKO due to doctor stoppage.


Data Reading and Inspection:
Reading a CSV file into a Pandas DataFrame.
ınspecting the data using the check_df function, which displays information about the DataFrame's shape, data types, head, tail, missing values, and quantile statistics.

Data Preprocessing:
Drop columns with "opp" in their names.
Remove rows where the "Winner" column has the value "Draw."
Mapping the "Winner" column to binary values, with 'Red' mapped to 0 and 'Blue' mapped to 1.

Feature Selection:
You identify categorical, high-cardinality categorical, and numerical columns using the grab_col_names function.
You perform analysis on categorical and numerical columns using cat_summary and num_summary functions, respectively.
You analyze the relationship between categorical variables and the target variable.
Handling Outliers:

Define functions for finding and replacing outliers based on the interquartile range (IQR).
Check for outliers in numerical columns and replace them if found.

Handling Missing Values:
Identify columns with missing values using the missing_values_table function.
Fill missing values in numerical columns with their means.
Fill missing values in categorical columns with the mode.

Encoding Categorical Variables:
You encode categorical columns using LabelEncoder for machine learning models.

Scaling Numerical Variables:
You standardize numerical columns to have zero mean and unit variance.

Model Building and Hyperparameter Tuning:
Split the data into training and testing sets.
Define a set of machine learning models 
Perform hyperparameter optimization for each model using GridSearchCV.

Ensemble Learning (Voting Classifier):
Create a Voting Classifier that combines the predictions of multiple models.
Evaluate the ensemble model's performance using cross-validation.
