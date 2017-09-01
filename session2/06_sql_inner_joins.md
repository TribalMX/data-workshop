# INNER JOINS

In the previous lesson, you learned the basics of SQL joins using a data about college football players. All of the players in the players table match to one school in the teams table. But what if the data isn’t so clean? What if there are multiple schools in the teams table with the same name? Or if a player goes to a school that isn’t in the teams table?

If there are multiple schools in the teams table with the same name, each one of those rows will get joined to matching rows in the players table. Returning to the previous example with Michael Campanaro, if there were three rows in the teams table where school_name = 'Wake Forest', the join query above would return three rows with Michael Campanaro.

It’s often the case that one or both tables being joined contain rows that don’t have matches in the other table. The way this is handled depends on whether you’re making an inner join or an outer join.

We’ll start with inner joins, which can be written as either JOIN benn.college_football_teams teams or INNER JOIN benn.college_football_teams teams. Inner joins eliminate rows from both tables that do not satisfy the join condition set forth in the ON statement. In mathematical terms, an inner join is the intersection of the two tables.

## Joining tables with identical column names

