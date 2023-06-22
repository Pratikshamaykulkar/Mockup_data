# Mockup_data
## About Project:
 This is Codecademy Project. Here by using SQL query we perform some operation using two tables.
 
 Two tables: users, progress\
 Table users includes user_id, email_domain, country, city, postal, mobile_app, sign_up_at\
 Table progress includes user_id, learn_cpp, learn_sql, learn_html, learn_javascript, learn_java

 # Command used

  1. SELECT * from Users;
  2. SELECT * from progress;

  3. SELECT email_domain, COUNT(*) 
      FROM users
      WHERE email_domain like '%.edu'
      GROUP by 1
      ORDER by 2 desc 
      LIMIT 25;

4.   SELECT count(*)
      FROM users
      WHERE city = 'newyork';

5. SELECT COUNT(*) AS mobile_app_learners_count
    FROM users
    WHERE mobile_app = 'mobile-user';

Task 3.

  SELECT sign_up_at,
  strftime('%H', sign_up_at)
  FROM users
  GROUP BY 1;


Task 4.

SELECT u.email_domain,p.learn_sql,p.learn_cpp,p.learn_html,p.learn_javascript,p.learn_java, COUNT(*) AS course_count
FROM users u JOIN progress p ON u.user_id = p.user_id WHERE u.email_domain LIKE '%.edu'
GROUP BY u.email_domain,     p.learn_sql,p.learn_cpp,p.learn_html,p.learn_javascript,p.learn_java
 ORDER BY course_count DESC;






