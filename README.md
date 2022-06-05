# Academia and Sustainability- Is There Crossover?
## Shania Thomas

<br>

#### Background
The Earth is our home and we are all world-citizens. Therefore, it is imperative that we treat our home with respect, love, and care meaning we must be sustainable. What does it mean to be sustainable? The Environmental Protection Agency (EPA) defines sustainability as "sustainability is to create and maintain the conditions under which humans and nature can exist in productive harmony to support present and future generations." Since all living organisms livelihood depends on the natural environment, either directly or indirectly, it is critical that all world citizens work towards being sustainable.

## Executive Summary
<br>

#### The Problem
The overarching question I wish to answer is as follows:
> *Using Natural Language Processing techniques, can I determine if conversations within communities of Academia are encompassing language associated with sustainability?*
<br>

This is important as those within Academia in some shape or form will guide and lead future innovations, decisions, policies, and much more whether they be students soon to enter the work force, or faculty teaching the students. As we know, building a harmonious world where humans and nature coexist with minimal issue can determine what the future of our planet looks like.

#### Methods Used

To collect the data, I used Pushshifts API to collect roughly 4000 posts from two subreddits, Academia and Sustainability, 2000 posts each. I then saved these posts as a CSV. This process is shown in the notebook titled "Data_Scraping".

Initial EDA was done on this data that included Count Vectorizing which allowed for a count of all of the words that are in the posts. I then looked at a bar chart showing the frequencies of the most common word in each subreddit using engineered features such as the title of the post combined with the text of the post, and using the title by itself. I continued EDA by looking at the distributions on how many words were in the posts also by the title alone and the title concatenated with the text of the post. This process is shown in the notebook titled "EDA, cleaning, preprocessing."

To model, I used pipelines and gridsearching to automate the process. I built logistic regression models and random forests that used Natural Language Processing techniques to compare and contrast the two subreddits. The positive class in these models is Sustainability (1), and Academia is the negative class (0). This is all in attempt to find their crossover because that's where the answer to my problem statement will be. The model's success is evaluated based off its accuracy and misclassification rate at predicting which subreddit a post came from. Then, after building the most accurate model, I explored the misclassified posts to see what language is being used. I wanted to build the most accurate model _then_ explore misclassifications because while a less accurate model would provide more misclassifications to explore, it would not provide the most concrete and definitive answer to my question. This process is shown in the folder titled "Models".

#### Conclusions

In short, yes, conversations are happening within the communities of academia about sustainability! By first scraping 4000 posts from subreddits, then finding the highest frequency words in these posts during EDA, creating and training models to predict where these posts came with high accuracy, and examining the posts the model still got wrong I am able to determine that there is crossover.

The words that had the most effect on the model predicting that the post belonged in Sustainability, meaning they had the highest coefficients, are:
- sustainable
- sustainability
- plastic
- change
- green
- climate
- energy
- water
- environmental

The words that had the most effect on the model predicting the post was _not_ from Sustainability, therefore was classified as belonging to Academia are:

- masses
- hit
- dissertation
- science
- journal
- journals
- phd	
- articles
- academia
- academic

With that in mind, lets look at a couple misclassified posts:

>10 second video for climate change project \n\nHi there\n\nI am currently working on a school project on climate change . To add credibility to my work , I request you to submit a 10 second video on your thoughts . Pls upload your file to this google form .\n\n[https://forms.gle/SyjJbxVpFwkVMtpS9](https://forms.gle/SyjJbxVpFwkVMtpS9)\n\nYour contribution is greatly appreciated and thank you for your time .

>What are good methods of observation to avoid self-reporting bias in interviews? My project has to do with sustainable fashion consumption. I have come across this problem that respondents say they care for the environment or say they are shopping/using/discarding clothes in an ecofriendly way but they don’t. \nWhat could be an experimental/observational design to measure real behavior? Fake shopping experiment? Observing people when they shop? \n\nI am grateful for any input :)

>Computer science college student interested in volunteering My nephew is in his final year of engineering school computer science program. He expressed an interest in part-time volunteering role at a clean-tech organization that could leverage his skills in developing software. I’ve encouraged him to explore clean-tech as a field instead of Fintech, the field he has some internship experience. I watched this[RE: Tv show](https://www.re-tv.org/) on Prime and thought there has to be global not-for-profit organizations that could leverage his skill sets.\n\nI have two nieces who are also studying computer science. I am nudging them to find volunteer roles in clean-tech fields so they develop an interest and hopefully go on to work in that sectors after graduating. They however are looking to apply their CS knowledge, not just any role. For context, they are all located in Mumbai, India. Hope this post is okay. Thanks for any help and advice. \n\nAny ideas are greatly appreciated.

By skimming these posts, words that stand out are "climate", "change", "sustainable", "environment", "ecofriendly", "science", "clean", and others. These words contributed to the post being classified as belonging in Sustainability, but they actually came from Academia. This shows that yes, there are conversations being had within the communities of Academia that are about sustainability.

### Next Steps and Recommendations:

To further improve this model, next steps would be to gather more data from similar subreddits such as Higher Education or Sustainable, or other other platforms such as Facebook, Twitter, or other websites were posts can be tagged with hashtags or a similar methodology. Surveys could also be conducted at colleges and universities asking students and faculty if they have had a conversation about sustainability with a colleague recently. This would helpful in improving the model because some posts were misclassified most likely because there was not enough information within the title or text of the post.

This work that's been done is important and the work that can be done to improve this model is important because at the end of the day, we are all world citizens.

