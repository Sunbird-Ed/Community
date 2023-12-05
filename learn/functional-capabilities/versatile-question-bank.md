# Versatile Question Bank

Question Bank is a collection of questions that can be created by the creator for repeated use by users. Users can discover the questions on the learning apps and consume them using question set player. **Question set player** has the following capabilities-

1. Supports online and offline consumption
2. Embeddable across learning apps

Questions can be created using **question set editor** which has the following capabilities -

1. Multiple question set categories to choose from and organized into different categories such as -
   1. Quiz - Test knowledge of participating users using time-bound standalone quizzes and their scores' analysis
   2. Practice Test - Allows users to practice questions on important topics inside courses
   3. Surveys - Allows users to take surveys for the creator
   4. Assessments - Enable assessments inside courses for users to get a good understanding of topics and provide rewards using scores as well
2. Different types of Questions can be utilized for the categories above-
   1. Multiple choice questions: The Multiple Choice Question (MCQ) allows users to select one or more correct answer(s) from a number of potential answers. There are various Layout template options in this question type
   2. Subjective questions - Allows users to enter text in response to questions given by the creator
   3. Fill in the blanks: Allows users to type their responses into empty response boxes that have been inserted by the creator (To be developed)
   4. Match the following: Allows users to match questions to the correct responses to pair associated items (To be developed)
   5. Math questions - Math questions are backed by MathJax, which understands mathematical syntax and rules. Create open-ended math questions which have equations, expressions, etc.
   6. Chemistry Questions - Powered by LATEX, LATEX is used all over the world for scientific documents, books, as well as many other forms of publishing.
3. Configurable behaviors -
   1. Scoring - Creators can provide different scores to different questions or can also choose the questions to be auto scored
   2. Single or Multiple sections - Creator can choose to enable sections
   3. Instructions - Provide users with instructions before a question set. The Creator can also give instruction before each section as well
   4. Shuffle questions - Choose to auto shuffle questions to each user
   5. Duration - Set the time for a particular question
   6. Layout - Choose different layouts for questions to be displayed in
      1. Horizontal
      2. Vertical
      3. Grid
      4. 2-Column
      5. 3 -Column
   7. Common Latex library which can process inline latex content

Question set player emits **telemetry data** (i.e. signals) for each action performed by the user. This makes a rich data pool available, which can be aggregated to get all types of insights. It is through these insights that various actors can make informed decisions. Data Dashboards are available on the consumption interfaces to show progress at the individual or institutional level. For example, imagine a set of tests held at engineering colleges helps identify the concepts where most students are weak. The aggregated data across geography made available to the right stakeholders at the right time, helps arrive at timely interventions and long-term plans (like maybe the base of this concept isn’t understood well during high school, and the intervention is to be done then).

The above capabilities of Question bank are derived from components of Sunbird InQuiry. You can find details by clicking on the link below

{% hint style="info" %}
Further details on [versatile-question-bank.md](product-and-developers-guide/versatile-question-bank.md "mention")
{% endhint %}

Note: The complete capabilities of inQuiry are not yet integrated within ED. If you are using inQuiry BB for your instance you have to validate the workflows.
