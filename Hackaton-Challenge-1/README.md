# Hackathon Challenge 1: Social Media Activity Analysis

I built this project to analyze a small social media dataset and see how different Python tools handle the same tasks. My goal was to track follower changes, find the most and least active users, and generate a report for each week.

## The dataset

I used an Excel file called `sosyal_medya_500_kullanici_sade.xlsx`. It contains 500 users and 4,000 weekly records covering eight weeks. I have starting follower counts for every user, followed by weekly post, like, comment, and follower counts. Each user has an ID such as `U0001`.

## What I did

I started by loading the Excel sheets with openpyxl. Then I stored the user data in a list, a tuple, and a dictionary to compare memory use, searching, and basic changes to the data. Searching by user ID was much faster with a dictionary. In one of my tests, the list lookup took 19.8 microseconds while the dictionary lookup took 80.2 nanoseconds.

After that, I calculated weekly follower changes by comparing each user's new follower count with their previous count. I also created an activity score. Each post adds 5 points, each comment adds 4 points, and each like adds 1 point.

I tried the weekly calculations with regular Python and NumPy. I also used pandas to filter, sort, and group the data. At the end, I printed a report for every week showing follower changes and the ten users with the most gains, most losses, highest activity, and lowest activity.

## Results

Across all eight weeks, the dataset had a net increase of 21,091 followers. Week 6 had the highest growth with 3,273 new followers in total. Week 7 had the lowest growth with 1,786.

The speed tests were interesting too. My NumPy weekly analysis took about 94 microseconds, compared with 1.43 milliseconds using regular Python. On the other hand, simple grouping by week took 423 microseconds with regular Python and 686 microseconds with pandas.

I found that the best choice depends on the task. Dictionaries made ID lookups easier and faster, NumPy helped with repeated numerical calculations, and pandas made the data analysis code easier to read. The timings are from my notebook and may vary on another machine.

## How to run it

I used Jupyter Notebook with Python, openpyxl, NumPy, and pandas.

Open `1.Ödev.ipynb` in Jupyter and run the cells in order. The notebook also needs `sosyal_medya_500_kullanici_sade.xlsx` in the same folder to load the data.
