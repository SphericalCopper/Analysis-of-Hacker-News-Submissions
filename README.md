# Analysis-of-Hacker-News-Submissions
In this project, [Hacker News Submissions](https://news.ycombinator.com/) were analyzed to determine how a user should go about making a post in order for it to generate the most traction, measured primarily by the amount of responses from other users on the board.

The [dataset](https://www.kaggle.com/hacker-news/hacker-news-posts) used was reduced from almost 300,000 rows to approximately 20,000 rows by removing all submissions that did not receive any comments, and then randomly sampling from the remaining submissions.

We analyzed hacker news submissions of two main kinds:

- Posts that start with "Ask HN"
- Posts that start with "Show HN"

"Ask HN" posts are posts where the author asks the board a forum, such as "Is Tableau easier to use than Excel?"

"Show HN" posts are those where the author either makes a showcase of something they've done, or just wants to tell the board something of interest.

Our goals were to find out the following:

- Do "Ask HN" or "Show HN" receive more comments on average?
- Does the time of the day a submission is posted have any bearing on the amount of comments a post receives?

## Working with the Data

1. First we split the data into 2 tables for "Ask HN" and "Show HN" submissions, to compare the number of comments received by the two different types of submissions.

We saw that on average, "ask hn" posts receive about 14.04 comments, whereas "show hn" posts receive about 10.32 comments. This is a fairly significant difference, with "ask hn" posts leading by almost 40% more comments. **It's possible that this might be because "ask hn" posts inherently arouse more discussion, where people chime in with their opinions and then comment on the suggestions to the question raised.**

2. Determining correlation between no. of comments and time of the day.

The `datetime` library was used to segment the posts into hours, and then the no. of comments that were posted in the average submission that was submitted in a particular hour were tallied up, and after some manipulation the following information was deduced:

![comments by hour](https://i.gyazo.com/c7b54ff31186dddc28ebef76b5b1cd54.png)

Above, we see the top 5 most ideal times to make a "ask hn" post that generates the most responses. These times are Eastern times in the US.

The highest time by a margin was 15:00 Eastern US time. Posts submitted at this time received 38.59 comments on average, which is almost twice the amount of comments received by the next best time, which is 2:00 Eastern US time.

The popularity of posts submitted at 15:00 US time might have to do with the fact that at this time, it is evening in most of Europe, and around lunch hour in most of the US.

## Conclusions and caveats

The most ideal way to make a post that generates the most responses is by making an "Ask HN" flagged post around the 15:00-16:00 est time. This corresponds to 3a.m. - 4a.m. Singapore time, which is unfortunately a very poor choice of time for us here in South East Asia.

The 2nd best time slot was 02:00 est, which corresponds to 2.00pm Singapore Time. This might be more suitable for most of us.

It should be noted that because this data excluded the submissions which received no comments, the average number of comments per submission with the commentless submissions included might be slightly different.
