## A/B Test: IOU Creation Button Wording

**A/B Test Name:** +IOU vs. +New IOU Button

**User Story Number:** US4 - Golden Path (#12)

**Metrics:** +IOU Button Click-Through Rate (CTR), Adoption, and IOU Creation Success Rate.

**Hypothesis:**

Changing the navigation bar button text from "+IOU" to "+New IOU" will increase the click-through rate because it more clearly communicates that clicking the button allows users to create a new IOU.

**What problem are we trying to solve? Its impact?**

One of the most important features of our IOU app is allowing users to create and send IOUs to their friends. However, new users may not immediately understand what the "+IOU" button does.

If users do not understand how to create an IOU, they may not complete the Golden Path. This could negatively affect user adoption and engagement.

We will use Firebase Analytics to determine how many users see the button compared to how many click it. If the click-through rate is low, this may indicate that the button is unclear or difficult to understand.

Our experiment focuses on changing only the button's text so that we can determine whether clearer wording increases user interaction.

**Experiment:**

We will conduct an A/B test using Firebase Remote Config and Firebase A/B Testing.

Eligible users will be randomly divided into two groups:

- Group A (50%): The navigation button displays "+IOU".
- Group B (50%): The navigation button displays "+New IOU".

All other elements of the application will remain identical, including button location, color, functionality, and navigation behavior.

The test will target authenticated users who can access the IOU dashboard. We will aim to run the experiment for at least two weeks to collect enough data to compare the variations.

We will use Firebase Analytics to track the following custom events:

- `iou_button_impression`: Recorded when the +IOU button is displayed.
- `iou_button_click`: Recorded when a user clicks the button.
- `iou_created`: Recorded after an IOU is successfully saved to Firebase Firestore.

FlutterFlow's automatically logged `screen_view` and action events will also help us understand navigation behavior.

Our primary metric will be CTR, calculated as:

CTR = (Button Clicks / Button Impressions) × 100

We will compare CTR between the two groups and use successful IOU creation events as a secondary metric to determine whether increased clicks lead to more completed actions.

**Variations:**

**Variation A - Control**

The existing navigation bar includes a button labeled "+IOU".

```text
+-----------------------------+
|         IOU Dashboard       |
|                             |
|     What I Owe              |
|     Owed to Me              |
|                             |
| Home     [+IOU]     Friends |
+-----------------------------+
```

**Variation B - Experimental**

The navigation bar is identical, except the button text is changed to "+New IOU".

```text
+-----------------------------+
|         IOU Dashboard       |
|                             |
|     What I Owe              |
|     Owed to Me              |
|                             |
| Home   [+New IOU]   Friends |
+-----------------------------+
```

Both variations will open the exact same IOU creation screen.

The only variable being tested is the wording of the button. Keeping everything else identical will help determine whether button wording affects user behavior.

**Expected Outcome:**

We predict that Variation B will have a higher click-through rate because the wording more clearly explains the button's purpose. If the difference is meaningful and the experiment has sufficient data, we will consider using the better-performing version in the final application.




## A/B Test: Different Sign up Button Text
User Story #1
Metric: New Sign ups
Hypothesis: We are trying to solve the problem of users downloading the app but never making it by the landing page. We believe that our signup button might be too bland or not enough of a hook that gets users past the first page. 
Experiment: Our audience will be 50% of our users to capture a large amount of users who haven't signed up yet. We are using such a large percentage as a good amount of users might never see the change if they are already logged in. We will use firebase remote config and firebase A/B tests to remotely set the text of the button. We will need to track how many new signups come from each variation. 
Variations: We will test the following texts for the buttons. "Get Started" (base config), "Sign up", "Start Settling"
