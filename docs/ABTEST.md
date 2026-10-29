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
- Variations: We will test the following texts for the buttons. "Get Started" (base config), "Sign up", "Start Settling"
