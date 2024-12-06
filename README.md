-- Query 1: Select top 5 records from the startups table

select * from startups
limit 5; 

--ANS: There are 10 columns

-- Query 2: Total number of companies in the table

select count(name) from startups; 

-- ANS: Total: 70 companies

-- Query 3: Total value of all companies

select sum(valuation) from startups;

-- Total value: 974,455,790,000

-- Query 4: What is the highest amount raised by a startup?

select name, max(raised) from startups;

-- Highest raised: 11,500,000,000

-- Query 5: Maximum amount of money raised, during ‘Seed’ stage

select name, max(raised) from startups
where stage = 'seed';

-- ANS: None (No data)

-- Query 6: What year was the oldest company on the list founded?

select name, min(founded) from startups;

-- ANS: Oldest founded: 1994

-- Query 7: Average valuation of all startups

select avg(valuation) from startups;

-- ANS: AVG valuation: 15,974,685,081.9672

-- Query 8: Return the average valuation in each category

select category, avg(valuation) from startups group by category;

-- Query 9: Name of each category with the total number of companies

select category, count(name) from startups
group by category;

-- Query 10: Name of each category with more than 3 companies

select category, count(name) from startups
group by category
having count(name) > 3;

-- Query 11: What is the average size of a startup in each location?

select location, avg(employees) from startups
group by location;

