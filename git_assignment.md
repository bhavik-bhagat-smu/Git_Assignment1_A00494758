---
title: "Git Assignment 1"
author: "Bhavik Bhagat (A00494758)"
geometry: margin=1in
header-includes:
  - \usepackage{fvextra}
  - \DefineVerbatimEnvironment{Highlighting}{Verbatim}{breaklines,commandchars=\\\{\}}
---

# Git Assignment Documentation

### 1. Repository Initialization and Status Check
```bash
mkdir Git_Assignment1_A00494758
cd Git_Assignment1_A00494758
git init
git status
```

![Screenshot 1: Repository Initialization and Status Check](q1.png)

***
### 2. File Creation and Version Control
```bash
touch countries.txt
echo "USA" > countries.txt
echo "Canada" >> countries.txt
echo "Mexico" >> countries.
touch shapes.txt
echo "Circle" >> shapes.txt
echo "Square" >> shapes.txt
echo "Triangle" >> shapes.txt
cat countries.txt shapes.txt
git status
git commit -m "Adding Countries and Shapes"
touch numbers.txt
echo "One" > numbers.txt
echo "Two" >> numbers.txt
echo "Three" >> numbers.txt
git add numbers.txt
git commit -m "Adding numbers"
git log
```

![Screenshot 2.1: File Creation (Countries and Shapes)](q2_1.png)
![Screenshot 2.2: Commit History for Countries and Shapes](q2_2.png)

***
### 3. Branch Creation and Commit
```bash
git checkout -b LearnAnalytics
touch languages.txt
echo "R" > languages.txt
echo "Python" >> languages.txt
echo "NumPy" >> languages.txt
git add languages.txt
git commit -m "Add: languages to Learn-Analystics branch"
git log
```

![Screenshot 3: Branch Creation and Initial Commit on LearnAnalytics](q3.png)

***
### 4. Merging Conflicting Changes
```bash
git checkout -b user1
```

Make changes
```bash
git add countries.txt
git commit -m "change: countries to European Countries"
```
![Screenshot 4.1: User 1 changes in countries.txt](q4_1.png)

```bash
git checkout main
git checkout -b user2
```

Make changes
```bash
git add countries.txt
git commit -m "change: countries to Asian Countries"
``` 
![Screenshot 4.2: User 2 changes in countries.txt](q4_2.png)


```bash
git checkout -b combine_countries
git merge user1
git add countries.txt
git commit -m "change: resolved merge conflicts by keeping all countries"
```
![Screenshot 4.3: Resolved Merge Conflicts in combine_countries branch](q4_3.png)

***
### 5. Stashing and Applying Changes
```bash
git checkout main
git checkout -b user3
echo "Australia" >> countries.txt
echo "Brazil" >> countries.txt
```

![Screenshot 5.1: Changes to be stashed in user3 branch](q5_1.png)


```bash
git stash
git checkout main
echo "UK" >> countries.txt
git add countries.txt
git commit -m "add: UK"
```

![Screenshot 5.2: Committing UK to main branch](q5_2.png)

```bash
git checkout user3
git stash pop
git add countries.txt
git commit -m "add: Australia and Brazil"
```
![Screenshot 5.3: Applying stashed changes to user3 branch after main update](q5_3.png)

***
### 6. Advanced Git Workflow
```bash
git checkout main
git checkout -b bugfix
touch bugfix.txt
echo "Bugfix" >> bugfix.txt
git add bugfix.txt
git commit -m "add: bugfix"
touch random.txt
echo "Random" >> random.txt
git add random.txt
git commit -m "add: random"
```

![Screenshot 6.1: Bugfix branch commits](q6_1.png)

```bash
git checkout main
git reflog
git cherry-pick 39ab44f
ls -la
```

In this case, cherry-pick took the bugfix.txt file from the bugfix branch and added it to the main branch.

![Screenshot 6.2: Cherry-picking onto main branch](q6_2.png)
![Screenshot 6.3: Verification of cherry-picked file in main branch](q6_3.png)
***