# Git Assignment

## Bhavik Bhagat - A00494758



### 1. Repository Initialization and Status Check
```bash
mkdir Git_Assignment1_A00494758
cd Git_Assignment1_A00494758
git init
git status
```

![q1](q1.png)


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

![q2_1](q2_1.png)
![q2_2](q2_2.png)


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

![q3](q3.png)


### 4. Merging Conflicting Changes
```bash
git checkout -b user1
```

Make changes
```bash
git add countries.txt
git commit -m "change: countries to European Countries"
```
![q4_1](q4_1.png)

```bash
git checkout main
git checkout -b user2
```

Make changes
```bash
git add countries.txt
git commit -m "change: countries to Asian Countries"
``` 
![q4_2](q4_2.png)


```bash
git checkout -b combine_countries
git merge user1
git add countries.txt
git commit -m "change: resolved merge conflicts by keeping all countries"
```
![q4_3](q4_3.png)


### 5. Stashing and Applying Changes
```bash
git checkout main
git checkout -b user3
echo "Australia" >> countries.txt
echo "Brazil" >> countries.txt
```

![q5_1](q5_1.png)


```bash
git stash
git checkout main
echo "UK" >> countries.txt
git add countries.txt
git commit -m "add: UK"
```

![q5_2](q5_2.png)

```bash
git checkout user3
git stash pop
git add countries.txt
git commit -m "add: Australia and Brazil"
```
![q5_3](q5_3.png)


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

![q6_1](q6_1.png)

```bash
git checkout main
git reflog
git cherry-pick 39ab44f
ls -la
```

In this case, cherry-pick took the bugfix.txt file from the bugfix branch and added it to the main branch.

![q6_2](q6_2.png)
![q6_3](q6_3.png)