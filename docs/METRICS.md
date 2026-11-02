[Heart Framework](https://docs.google.com/presentation/d/1AUJrHF3kT1cQchIVecXfpMSDDq3OQvybpZZ9cgKUMS4/edit?usp=sharing)


# Metrics

- Metric 1: NPS (Net Promoter Score)
  To collect our net promotor score, we are gonna prompt our users after their 3rd settled IOU slip with the question “How likely are you to recommend IOU to a friend? (0 to 10)”. Then using that data we will be able to calculate our NPS by using the base calculation for it.  

- Metric 2: Adoption (New Sign Ups)
  Built into firebase auth directly we can see when users sign up. But we would take it a step further adding a custom firebase analytics trigger for when onboarding is complete. This would allow us to see how many users make it past the first screen and then see how many of those users actually send a IOU slip. 

- Metric 3: Retention (WAU Weekly Active Users)
  Using Firebase Analytics we will track our weekly active users. We can create a custom firebase triggers whenever a user completes an action related to an IOU either sending it or settling it or anything else associated with one such as viewing their IOUs. This will allow us to track how many unique users return and actively use IOU each week. By comparing WAU over time, we can measure how well we retain users and determine whether users continue finding value in the app after their initial sign-up.

- Metric 4: Task Success (Click-Through Rate)
We will use Firebase Analytics to track how often users click the "+New IOU" button compared to how often the button appears. We will create custom events for button views and clicks. This will help us see whether users understand how to create a new IOU and which button wording works better.

- Metric 5: IOU Settlement Rate: Measures the percentage of IOUs that users have marked as settled. Data is collected through Firebase Firestore by tracking each IOU's status. The metric is calculated by dividing the number of settled IOUs by the total number of IOUs created and multiplying by 100. This helps determine whether users are successfully resolving their debts through the app.

