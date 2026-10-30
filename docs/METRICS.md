[Heart Framework](https://docs.google.com/presentation/d/1AUJrHF3kT1cQchIVecXfpMSDDq3OQvybpZZ9cgKUMS4/edit?usp=sharing)


# Metrics

- Metric 1: NPS (Net Promoter Score)
  To collect our net promotor score, we are gonna prompt our users after their 3rd settled IOU slip with the question “How likely are you to recommend IOU to a friend? (0 to 10)”. Then using that data we will be able to calculate our NPS by using the base calculation for it.  

- Metric 2: Adoption (New Sign Ups)
  Built into firebase auth directly we can see when users sign up. But we would take it a step further adding a custom firebase analytics trigger for when onboarding is complete. This would allow us to see how many users make it past the first screen and then see how many of those users actually send a IOU slip. 

