# SQL JOINS

## Intro to SQL joins: relational concepts

Up to this point, we’ve only been working with one table at a time. The real power of SQL, however, comes from working with data from multiple tables at once. If you remember from a previous lesson, the tables you’ve been working with up to this point are all part of the same schema in a relational database. The term “relational database” refers to the fact that the tables within it “relate” to one another—they contain common identifiers that allow information from multiple tables to be combined easily.

To understand what joins are and why they are helpful, let’s think about Twitter.

Twitter has to store a lot of data. Twitter could (hypothetically, of course) store its data in one big table in which each row represents one tweet. There could be one column for the content of each tweet, one for the time of the tweet, one for the person who tweeted it, and so on. It turns out, though, that identifying the person who tweeted is a little tricky. There’s a lot to a person’s Twitter identity—a username, a bio, followers, followees, and more. Twitter could store all of that data in a table like this:

Let’s say, for the sake of argument, that Twitter did structure their data this way. Every time you tweet, Twitter creates a new row in its database, with information about you and the tweet.

But this creates a problem. When you update your bio, Twitter would have to change that information for every one of your tweets in this table. If you’ve tweeted 5,000 times, that means 5,000 changes. If many people on Twitter are making lots of changes at once, that’s a lot of computation to support. Instead, it’s much easier for Twitter to store everyone’s profile information in a separate table. That way, whenever someone updates their bio, Twitter would only have to change one row of data instead of thousands.

In an organization like this, Twitter now has two tables. The first table—the users table—contains profile information, and has one row per user. The second table—the tweets table—contains tweet information, including the username of the person who sent the tweet. By matching—or joining—that username in the tweets table to the username in the users table, Twitter can still connect profile information to every tweet.

## The anatomy of a join

In the previous lesson on conditional logic, we worked with a table of data on college football players—benn.college_football_players. This table included data on players, including each player’s weight and the school that they played for. However, it didn’t include much information on the school, such as the conference the school is in—that information is in a separate table, benn.college_football_teams.

Let’s say we want to figure out which conference has the highest average weight. Given that information is in two separate tables, how do you do that? A join!

```SELECT teams.conference AS conference,
       AVG(players.weight) AS average_weight
  FROM benn.college_football_players players
  JOIN benn.college_football_teams teams
    ON teams.school_name = players.school_name
 GROUP BY teams.conference
 ORDER BY AVG(players.weight) DESC```

### Aliases in SQL




