## A/B Test: Highlighting the Create IOU Navigation Icon

**A/B Test Name:** Highlighted vs. Standard Create IOU Icon

**User Story Number:** US4 - Golden Path (#12)

**Metrics:** Create IOU Icon Click-Through Rate (CTR), Adoption, and IOU Creation Success Rate.

**Hypothesis:**

Adding a circular background behind the Create IOU navigation icon will increase its click-through rate because it will make the icon more noticeable and help users identify it as an important action.

**What problem are we trying to solve? Its impact?**

One of the main features of our IOU app is allowing users to create and send IOUs to friends. Since our app uses an icon-based navigation bar, some users may overlook the icon used to create a new IOU.

If users have difficulty finding the option to create an IOU, they may never complete the Golden Path. This could reduce adoption and engagement.

We will first use Firebase Analytics to measure how frequently users see and click the Create IOU icon. A low click-through rate could suggest that the action is not noticeable enough.

Our experiment will test whether highlighting the icon improves interaction without changing the navigation layout or functionality.

**Experiment:**

We will use Firebase Remote Config and Firebase A/B Testing to compare two versions of the navigation icon.

All authenticated users will be eligible for the experiment and randomly assigned to one of two groups:

- **Group A (50%):** The existing Create IOU navigation icon without any additional background.
- **Group B (50%):** The same navigation icon with a filled circular background to make it stand out.

Both versions will have the same icon, size, location, and functionality. The only difference will be the circular background.

We will configure a Firebase Remote Config parameter called `highlight_create_icon` to control which version appears.

We will use Firebase Analytics to record the following custom events:

- `iou_button_impression`: Recorded when the navigation icon becomes visible.
- `iou_button_click`: Recorded when the user clicks the icon.
- `iou_created`: Recorded when a new IOU is successfully saved to Firebase Firestore.

FlutterFlow's automatically logged screen views and action events will provide additional information about navigation behavior.

Our primary metric will be the click-through rate:

**CTR = (Icon Clicks / Icon Impressions) × 100**

We will compare CTR between the two groups. We will also track successful IOU creations to determine whether increased clicks lead to more users completing the Golden Path.

The experiment will run for at least two weeks, with the final duration depending on the number of users and events collected. If there is insufficient data, we will consider the result inconclusive.

**Variations:**

**Variation A — Control**

The current navigation bar uses the existing Create IOU icon without a highlighted background.

Mockup:

`[ Create IOU: + ]`

No circular background. The icon uses the same styling as the existing navigation controls.

**Variation B — Experimental**

The navigation bar uses the exact same icon, but with a filled circular background behind it.

Mockup:

`[ Create IOU: ⊕ ]`

The circular background adds visual emphasis while keeping the icon itself unchanged.

Both versions will remain in the exact same navigation bar position and open the same IOU creation screen. No text labels will be added.

**Expected Outcome:**

We predict that the highlighted version will receive more clicks because it draws attention to one of the application's most important features.

If the highlighted icon produces a meaningful increase in CTR without reducing successful IOU creation, we will consider adopting that design in the final application.

## A/B Test: Different Sign up Button Text
- User Story #1
- Metric: New Sign ups
- Hypothesis: We are trying to solve the problem of users downloading the app but never making it by the landing page. We believe that our signup button might be too bland or not enough of a hook that gets users past the first page. 
- Experiment: Our audience will be 50% of our users to capture a large amount of users who haven't signed up yet. We are using such a large percentage as a good amount of users might never see the change if they are already logged in. We will use firebase remote config and firebase A/B tests to remotely set the text of the button. We will need to track how many new signups come from each variation. 
- Variations: We will test the following texts for the buttons. "Get Started" (base config), "Get Started Free", "Join [X]+ Members", "Create My Account in 30 Seconds"

## A/B Test: +IOU vs. +New IOU Button

A/B Test Name: +IOU vs. +New IOU Button

User Story Number: US4 - Golden Path (#12)

Metrics: Create IOU Button Click-Through Rate (CTR), Adoption, and IOU Creation Success Rate.

Hypothesis:

Changing the button text from "+IOU" to "+New IOU" will increase the click-through rate because it makes the purpose of the button easier for users to understand.

What problem are we trying to solve? Its impact?

One of the main features of our IOU app is allowing users to create and send IOUs to friends. New users might not immediately understand what the "+IOU" button does.

If users do not understand how to create an IOU, they might not complete the Golden Path. This could reduce engagement and the number of IOUs created.

We want to see whether changing the button wording makes users more likely to click and create a new IOU.

Experiment:

We will use Firebase Remote Config and Firebase A/B Testing to compare two versions of the Create IOU button.

All authenticated users will be eligible and randomly divided into two groups:

Group A (50%): The button displays "+IOU".

Group B (50%): The button displays "+New IOU".

We will use a Firebase Remote Config parameter named create_iou_button_text to control which version users see.

Firebase Analytics will track three custom events:
- iou_button_impression: Records when users see the button.
- iou_button_click: Records when users click the button.
- iou_created: Records when users successfully create an IOU.
We will calculate CTR by dividing the number of button clicks by the number of button impressions and multiplying by 100.

We will compare CTR and successful IOU creation between the two groups. The experiment will run for at least two weeks, depending on the number of users and events collected.

Variations:

Variation A - Control

The existing button displays "+IOU".

Mockup: [ +IOU ]

Variation B - Experimental

The button displays "+New IOU".

Mockup: [ +New IOU ]

**A/B Test: Personalized Welcome Message**
A/B Test Name: Personalized vs. Standard Welcome Message

User Story Number: US1 - User Sign Up

Metrics: First IOU Creation Rate, User Engagement, and First Session Completion Rate.

Hypothesis
Displaying a personalized welcome message that includes the user's name will make users feel more welcomed and encourage them to explore the app and create their first IOU.

What problem are we trying to solve? Its impact?
When users first sign up for our IOU app, they may not immediately understand what to do next or feel motivated to explore its features. A generic welcome message might not create enough excitement or encourage users to begin using the app.

Since creating and sending IOUs is the main purpose of our application, we want to encourage new users to complete their first IOU as soon as possible.

By testing a personalized welcome message, we hope to make the experience feel more welcoming and encourage users to engage with the app.

Experiment
We will use Firebase Remote Config and Firebase A/B Testing to compare two different welcome messages shown to newly registered users.

Newly registered users will be randomly assigned to one of two groups:

Group A (50%): Displays the standard welcome message.
Group B (50%): Displays a personalized welcome message that includes the user's name.
We will configure a Firebase Remote Config parameter called welcome_message to control which message is displayed.

Firebase Analytics will track the following events:

welcome_message_impression: Recorded when the welcome message is displayed.
first_iou_created: Recorded when a user successfully creates their first IOU.
welcome_screen_completed: Recorded when a user finishes the welcome screen and continues into the app.
We will compare first IOU creation rates and engagement between the two groups to determine whether personalization encourages users to begin using the app.

The experiment will run for at least two weeks, with the final duration depending on the number of new users and events collected. If insufficient data is collected, we will consider the results inconclusive.

Variations
Variation A - Control
The existing welcome screen displays a standard, non-personalized message.

Mockup:

Welcome to IOU!

Variation B - Experimental
The welcome screen displays a personalized message using the user's name.

Mockup:

Welcome, [Name]! Ready to keep track of what you owe and what you're owed?

Both versions will use the same screen layout, colors, fonts, and functionality. The only difference will be the welcome message.

Expected Outcome
We predict that users who receive the personalized welcome message will be more likely to engage with the app and create their first IOU.

If the personalized version produces a meaningful increase in first IOU creation without negatively affecting onboarding completion, we will consider adopting it in the final application.

Both buttons will have the same color, position, and functionality. The only difference will be the wording.

Expected Outcome:

We expect the "+New IOU" button to receive more clicks because users will better understand its purpose. If this version increases CTR and successful IOU creation, we will consider using it in the final app.
