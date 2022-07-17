# Welcome!

### About this case
Below, you'll find 3 exercises we've chosen to represent the work you may encounter in this role. There is no single right answer — we've left these intentionally open-ended to see how you think.

After testing this challenge with our team, we estimate that it will take around **60 minutes** to complete these exercises. We will give personalized feedback for your submission.

We designed this hiring challenge to:
1. Learn as much as we can about how you work.
2. Require as little of your time as possible. By limiting this to an hour, we hope this is manageable with your busy schedule.
3. Introduce you to the types of challenges you might encounter in this role.

### Background
For this case study, we want to evaluate your coding and database proficiency.

There is an API available to pull stock prices by Alpha Vantage. You can read more about the Time Series Daily endpoint [here](https://www.alphavantage.co/documentation/#daily), which is what we’ll be using for this challenge. Fill out the form [here](https://www.alphavantage.co/support/#api-key) to receive your API key. Note that standard API key is limited to 5 calls per minute (500 per day).

In Part 1, you'll convert one set of transactions to an alternate set of transactions using prices retrieved from the API. Then in Part 2, you’ll write a query that will summarize the performance for a fund containing multiple investors. Finally in Part 3, we want to hear how you would turn this into a fully functioning application, and about your overall thought process.

### Part 1: Pull Data
*20 min*

Write code that will take in an index fund symbol and a CSV file containing transaction data, call the Alpha Vantage API to get historical prices for the specified symbol, then convert each transaction using the historical prices for the specified symbol. Use the transactions.csv file to represent the expected input and output format:
- This code should be written in Python.
- The inputs should be:
  - A string containing a file path to open with the CSV
  - A string representing the symbol for an index fund (e.g. QQQ, VOO, FNILX)
- For each row, use the Alpha API to pull the "high" price for the index fund for the day and calculate how many of shares would have been bought that day to invest the same amount of money.
- The output should be an array with an entry corresponding to each row of the CSV. Each entry should resemble the original CSV row except with the specified index fund and price instead of the original investment.
 
> For example with an input of the symbol "QQQ" the row:
> - SELL   2020-12-17    AA      85          23.21
> 
> should have a corresponding output of:
> - SELL   2020-12-17    QQQ   6.3387  311.00

The deliverable for this section is code that should be able to run to accomplish this task.

### Part 2: Query Data
*20 min*

The CSV file in Part 1 is a set of transactions. Each of these transactions was executed by a single trader, and each trader is a part of a single fund (a fund will contain multiple traders). See dummy.sqlite for some example data.

Write a SQL query that will summarize overall activity for each fund.

- This query should be able to run against the provided database structure
- For each fund it should return the total value for all transactions for the following time periods: current year, and lifetime. For this exercise we want the total value of all the transactions, there is no need to treat SELL transactions as a negative number, for example.

> For example, if we ran the query on 2/1/22, the "Ankina Fund" should have the current year total as 8216.73 and the lifetime total as 98625.1459
 
The deliverable for this section is valid SQL syntax that can be executed in the provided database.

### Part 3: Discussion (Architecture & Reflection)
*20 min*

We want to hear how you would turn this into a fully functioning application, and about your overall thought process. Please respond to the following prompts:
1. Are there any changes you would make to the database structure from Part 2? How could we extend this database to compare overall performance with the index fund prices from Part 1?
2. We want to implement a simple front end to display the data fetched in Part 2. Describe how you would structure the code to accomplish this and what technologies would be involved.
3. Describe how we could deploy this code to run in a production environment.
4. What decision points did you come to? What led you to the choices you made?
5. What would you do if these tasks (Parts 1, 2, and 3) were a real application and you weren't as limited by time? Are there any questions you would have asked?

The deliverable for this section is a document in whatever format you prefer (plain text, markdown, pdf, etc.) that addresses these prompts.

### Submitting your work
Add any deliverables to the directory, then commit and push your changes with `git commit` and `git push`.

Finally, navigate to the exercise landing page (you can find the link in your email), check that the latest commit shown is accurate, and then click the submit button below. This will notify the engineers on our team that your work is ready for review.
