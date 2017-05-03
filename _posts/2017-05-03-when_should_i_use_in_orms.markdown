---
layout: post
title:  "When should I use '?' in ORMs?"
date:   2017-05-03 18:03:28 +0000
---


I've finished Dynamic ORM lessons (and labs), and I've got a dilema because of #{string interpolation} and ?, bound parameter.

At first, the lesson told me that it is better for me to use bound parameter than string interpolation, like below.
```
BOUND PARAMETERS
Bound parameters protect our program from getting confused by SQL injections and special characters. Instead of interpolating variables into a string of SQL, we are using the ? characters as placeholders. Then, the special magic provided to us by the SQLite3-Ruby gem's #execute method will take the values we pass in as an argument and apply them as the values of the question marks.
```
(brought from [here](https://learn.co/tracks/full-stack-web-dev-with-react/orms-and-activerecord/orms/mapping-ruby-classes-to-database-tables))

However, when I started dynamic ORMs, the example codes, e.g codealongs, started to use only string interpolation! This situation threw me into confusion. So, I asked to instructor.

And here's the solution.

1. When we use SELECT commands, or bring data from DB, it is ok to use string interpolation. There's no big difference between using string interpolation and bound params.
2. However, when we use INSERT or UPDATE commands, or put data into DB, we should use ?(bound parameter) to avoid  [potential dangerous consequences](https://xkcd.com/327/).

Question solved. 
Good Night;)
