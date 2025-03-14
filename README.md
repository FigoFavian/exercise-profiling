add README.md
# REFLECTION 

# Preprofiling

## Jmeter all-student-name.jmx Test Plan Result GUI:
a. View Result Tree
![Screenshot 2025-03-14 163123](https://github.com/user-attachments/assets/eb86fa12-5d8c-4555-8a98-643625bc2290)
b. Summary Report
![Screenshot 2025-03-14 163214](https://github.com/user-attachments/assets/08ba4604-a204-413e-8078-636b550342de)
c. View Results in Table
![Screenshot 2025-03-14 163241](https://github.com/user-attachments/assets/aa2af888-81e7-4627-b89c-a517aab75d5d)
d. Graph Result
![Screenshot 2025-03-14 163324](https://github.com/user-attachments/assets/45331fe8-7c02-4f21-9650-4896beae995c)

## Jmeter highest-gpa.jmx Test Plan Result GUI:
a. View Result Tree
![Screenshot 2025-03-14 163545](https://github.com/user-attachments/assets/11a229b1-4643-430d-b003-d0116b052046)
b. Summary Report
![Screenshot 2025-03-14 163635](https://github.com/user-attachments/assets/12fbaca8-ac56-415c-bc06-3eb0b4678867)
c. View Results in Table
![Screenshot 2025-03-14 163657](https://github.com/user-attachments/assets/8d1cdcc8-cee5-42ea-b851-b1845d765132)
d. Graph Result
![Screenshot 2025-03-14 163734](https://github.com/user-attachments/assets/1de906e3-8b46-46b6-9c89-acb191f597f6)

## Jmeter testresult2.jtl for all-student-name.jmx Test Plan Result Command:
![Screenshot 2025-03-14 125332](https://github.com/user-attachments/assets/552ef0bd-ecad-4874-8759-ebdfe690c038)

## Jmeter testresult3.jtl for highest-gpa.jmx Test Plan Result Command:
![Screenshot 2025-03-14 134459](https://github.com/user-attachments/assets/7ea9e9f9-cba6-4db1-b73d-627a1cb5de85)

# Postprofiling

## Jmeter all-student-name.jmx Test Plan Result GUI: 
a. View Result Tree
![Screenshot 2025-03-14 191912](https://github.com/user-attachments/assets/ed8d9883-621b-466a-bd7e-d2c034947114)
b. Summary Report
![Screenshot 2025-03-14 191946](https://github.com/user-attachments/assets/5663a820-eb6d-4f6f-8d41-b72b1a4d86ed)
c. View Results in Table
![Screenshot 2025-03-14 192010](https://github.com/user-attachments/assets/d23bd452-c3f5-4f44-b2ed-09dffb3f5c27)
d. Graph Result
![Screenshot 2025-03-14 192032](https://github.com/user-attachments/assets/c2fdafb6-173b-4f85-bbaa-0ecac58d94f5)

## Jmeter highest-gpa.jmx Test Plan Result GUI:
a. View Result Tree
![Screenshot 2025-03-14 192210](https://github.com/user-attachments/assets/8429637e-e880-4285-a17a-9f76a5a4392a)
b. Summary Report
![Screenshot 2025-03-14 192224](https://github.com/user-attachments/assets/c03b7e2f-3a30-422a-b281-cef27227a836)
c. View Results in Table
![Screenshot 2025-03-14 192242](https://github.com/user-attachments/assets/1b02b189-6ea0-4793-af8e-327e1e6badd8)
d. Graph Result
![Screenshot 2025-03-14 192258](https://github.com/user-attachments/assets/106725ec-c5f6-476c-b582-f600c19c4783)

## Jmeter testresult2.jtl for all-student-name.jmx Test Plan Result Command:
![Screenshot 2025-03-14 192804](https://github.com/user-attachments/assets/b1cb61f8-356e-4e92-866c-3dc492b5c6d4)

## Jmeter testresult3.jtl for highest-gpa.jmx Test Plan Result Command:
![Screenshot 2025-03-14 192837](https://github.com/user-attachments/assets/1ed6219c-c7f6-4ead-9afa-a17c3c0082ce)

By comparing the JMeter Pre to Post Profiling, there are improvement in the speed of the tests. 
As you can see from the images itself, the test executed had a 20% performance improvement for /all-student-name and /highest-gpa endpoints.
This was done by making a new branch called "optimize", inside there I improved some methods in StudentService class.

### 1.What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?

JMeter focuses on user-level performance testing by simulating traffic, for example thousands of users, to measure how an app handles load, response times, or scalability.
It is like stress testing the system from the outside. IntelliJ Profiler is about the code itself. It shows which methods or processes hog CPU, memory, or cause bottlenecks.
While JMeter tells us how does the app perform under pressure and the Profiler shows why is a specific part slow.

### 2.How does the profiling process help you in identifying and understanding the weak points in your application?

Profiling tracks every detail during app execution. It highlights resource heavy methods, memory leaks, and even inefficient loops.
If a database query runs 1,000 times in a loop, the profiler flags it letting you refactor it into a single optimized query.

### 3.Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?

Intellij Profiler is effective since it integrates with the IDE which means profiling while coding is doable, seeing real time data like CPU spikes or memory usage.
Features like flame graphs or method level timers make it easy to spot issues.

### 4.What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?

a. Tests might not mirror real-world use, such as a wrong JMeter thread counts.

b. A slow API in JMeter could stem from bad code, network latency, and database design.

Solution -> By Replicating realistic scenarios, profile multiple times, and cross checking metrics like logs or monitoring tools.

### 5.What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?

a. Directly links performance issues to your code giving a code level clarity.

b. No need for external tools like debug and profile in one place.

c. Quickly test optimizations, like swapping a loop with streams.

### 6.How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?

Inconsistencies often come from environment differences like local against production DB or tool focus like JMeter detects slow APIs

Solution -> Align test environments and Use both tools like JMeter to flag issues and Profiler into the cause of the performance issue itself.

### 7.What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?

By optimizing heavy algorithms, reducing database calls, and fixing memory leaks. Using unit or integration tests confirms changes  that don’t break features.
And then running JMeter again post optimization to verify improvements which it did worked (The speed improved 20%)
