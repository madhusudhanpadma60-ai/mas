Git & GitHub Lab Programs – Questions 3 to 10
Below are all 8 programs (Q3–Q10) in an easy lab-examination format.

I have kept the same folder structure, similar HTML/CSS/JavaScript code and simple Git commands wherever possible. You can copy these into your practical record.

Q3. Student Management System – Git and GitHub
Aim: Develop a Student Management System, track source files using Git, maintain commit history and push the project to GitHub.
1. Project structure
StudentManagementSystem/
│
├── index.html
├── style.css
├── script.js
└── README.md


2. index.html

<html>
<head>
<title>Student Management</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<h2>Student Management System</h2>

<input id="name" placeholder="Student Name">
<input id="roll" placeholder="Roll Number">
<input id="course" placeholder="Course">

<button onclick="addStudent()">Add Student</button>
<button onclick="searchStudent()">Search Student</button>

<ul id="list"></ul>

<script src="script.js"></script>
</body>
</html>



3. style.css

body {
    text-align: center;
    font-family: Arial;
}

input, button {
    padding: 10px;
    margin: 5px;
}



4. script.js

let students = [];

function addStudent() {
    let name = document.getElementById("name").value;
    let roll = document.getElementById("roll").value;
    let course = document.getElementById("course").value;

    students.push({name, roll, course});

    document.getElementById("list").innerHTML +=
        "<li>" + name + " - " + roll + " - " + course + "</li>";
}

function searchStudent() {
    let roll = document.getElementById("roll").value;
    let s = students.find(x => x.roll === roll);

    alert(s ? s.name + " - " + s.course : "Not Found");
}



5. README.md
Student Management System

Features:
1. Add Student
2. Search Student

Technologies:
HTML, CSS, JavaScript


6. Git commands
git init
git add .
git commit -m "Initial student project"
git status
git log --oneline


Create an empty GitHub repository named StudentManagementSystem.
git branch -M main
git remote add origin https://github.com/USERNAME/StudentManagementSystem.git
git push -u origin main


Output:
Initialized empty Git repository
[main] Initial student project
Writing objects: 100%
Branch main set up to track origin/main



Q4. Student Registration and Student Search – Branching and Merging
Aim: Create separate branches for student registration and student search, implement features and merge them into the main branch.

Use the same Q3 project and code.
Step 1: Create registration branch
git checkout -b student-registration


Add registration code in script.js:
function addStudent() {
    let name = document.getElementById("name").value;
    let roll = document.getElementById("roll").value;

    students.push({name, roll});

    alert("Student Registered");
}


git add .
git commit -m "Added student registration"


Step 2: Create search branch
git checkout main
git checkout -b student-search


Add search code in script.js:
function searchStudent() {
    let roll = document.getElementById("roll").value;
    let s = students.find(x => x.roll === roll);

    alert(s ? s.name : "Student Not Found");
}


git add .
git commit -m "Added student search"


Step 3: Merge branches
git checkout main
git merge student-registration
git merge student-search


Step 4: Push to GitHub
git push origin main
git push origin student-registration
git push origin student-search


Output:
Switched to branch 'main'
Merge made by the 'ort' strategy.
Merge successful
Everything pushed to GitHub



Q5. Git Merge Conflict Resolution in README.md
Aim: Create two branches modifying the same line in README.md, merge them, resolve the conflict and push to GitHub.

Use the same Q3 project.
Step 1: Create first branch
git checkout main
git checkout -b branch1


Modify README.md:
Student Management System - Version 1


git add README.md
git commit -m "Updated README in branch1"


Step 2: Create second branch
git checkout main
git checkout -b branch2


Modify the same line:
Student Management System - Version 2


git add README.md
git commit -m "Updated README in branch2"


Step 3: Merge branches
git checkout main
git merge branch1
git merge branch2


Merge conflict occurs
Step 4: Resolve conflict
Open README.md.

You will see something similar to:
<<<<<<< HEAD
Student Management System - Version 1
=======
Student Management System - Version 2
>>>>>>> branch2


Replace it with:
Student Management System
Version 1 and Version 2


Save the file.
Step 5: Commit and push
git add README.md
git commit -m "Resolved merge conflict"
git push origin main


Output:
CONFLICT (content): Merge conflict in README.md

[main] Resolved merge conflict
Everything pushed to GitHub




Q6. Library Management System – Stage Selected Files Individually
Aim: Create a Library Management System using HTML, CSS and JavaScript files. Stage selected files individually and commit them using meaningful messages.
1. Project structure
LibraryManagementSystem/
│
├── index.html
├── style.css
├── script.js
└── README.md


2. index.html

<html>
<head>
<title>Library Management</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<h2>Library Management System</h2>

<input id="name" placeholder="Book Name">
<input id="roll" placeholder="Book ID">
<input id="course" placeholder="Author">

<button onclick="addStudent()">Add Book</button>
<button onclick="searchStudent()">Search Book</button>

<ul id="list"></ul>

<script src="script.js"></script>
</body>
</html>



3. style.css
Use the same Q3 CSS code.
body {
    text-align: center;
    font-family: Arial;
}

input, button {
    padding: 10px;
    margin: 5px;
}


4. script.js
let books = [];

function addStudent() {
    let name = document.getElementById("name").value;
    let id = document.getElementById("roll").value;
    let author = document.getElementById("course").value;

    books.push({name, id, author});

    document.getElementById("list").innerHTML +=
        "<li>" + name + " - " + id + " - " + author + "</li>";
}

function searchStudent() {
    let id = document.getElementById("roll").value;
    let b = books.find(x => x.id === id);

    alert(b ? b.name : "Book Not Found");
}


5. README.md
Library Management System

Features:
1. Add Book
2. Search Book

Technologies:
HTML, CSS, JavaScript


6. Git commands
git init
git status

git add index.html
git commit -m "Added HTML file"

git add style.css
git commit -m "Added CSS file"

git add script.js
git commit -m "Added JavaScript file"

git add README.md
git commit -m "Added documentation"


Output:
[main] Added HTML file
[main] Added CSS file
[main] Added JavaScript file
[main] Added documentation



Q7. Employee Management System – Local Repository and GitHub
Aim: Create a local repository for Employee Management System, connect it to GitHub and push the project.
1. Project structure
EmployeeManagementSystem/
│
├── index.html
├── style.css
├── script.js
└── README.md


2. index.html

<html>
<head>
<title>Employee Management</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<h2>Employee Management System</h2>

<input id="name" placeholder="Employee Name">
<input id="roll" placeholder="Employee ID">
<input id="course" placeholder="Department">

<button onclick="addStudent()">Add Employee</button>
<button onclick="searchStudent()">Search Employee</button>

<ul id="list"></ul>

<script src="script.js"></script>
</body>
</html>



3. style.css
Use the same CSS code from Q3.
4. script.js
let employees = [];

function addStudent() {
    let name = document.getElementById("name").value;
    let id = document.getElementById("roll").value;
    let dept = document.getElementById("course").value;

    employees.push({name, id, dept});

    document.getElementById("list").innerHTML +=
        "<li>" + name + " - " + id + " - " + dept + "</li>";
}

function searchStudent() {
    let id = document.getElementById("roll").value;
    let e = employees.find(x => x.id === id);

    alert(e ? e.name : "Employee Not Found");
}


5. Git commands
Create an empty GitHub repository named EmployeeManagementSystem.
git init
git add .
git commit -m "Initial employee project"

git branch -M main

git remote add origin https://github.com/USERNAME/EmployeeManagementSystem.git

git push -u origin main


Output:
Initialized empty Git repository
[main] Initial employee project
Writing objects: 100%
Everything pushed to GitHub



Q8. Banking Application – Stage, Unstage and Commit
Aim: Create a Banking Application and demonstrate staging, unstaging and committing source files.
1. Project structure
BankingApplication/
│
├── index.html
├── style.css
├── script.js
└── README.md


2. index.html
<html>
<head>
<title>Banking Application</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<h2>Banking Application</h2>

<input id="amount" placeholder="Enter Amount">

<button onclick="deposit()">Deposit</button>

<p id="result"></p>

<script src="script.js"></script>
</body>
</html>


3. style.css
body {
    text-align: center;
    font-family: Arial;
}

input, button {
    padding: 10px;
    margin: 5px;
}


4. script.js
let balance = 0;

function deposit() {
    let amount = Number(document.getElementById("amount").value);

    balance += amount;

    document.getElementById("result").innerHTML =
        "Balance: " + balance;
}


5. README.md
Banking Application

Features:
1. Deposit
2. Balance Display

Technologies:
HTML, CSS, JavaScript


6. Git commands
Step 1: Initialize repository
git init


Step 2: Stage files
git add index.html
git add style.css
git status


Step 3: Unstage file
git restore --staged style.css
git status


Step 4: Stage all files
git add .


Step 5: Commit
git commit -m "Added banking application"


Output:
Changes to be committed:
    new file: index.html
    new file: style.css

[main] Added banking application



Q9. Library Management System – Branching and Merging
Aim: Develop Library Management System, create feature branches for book registration and book search, merge branches and maintain version history.

Use the same code and project structure from Q6.
Step 1: Initialize repository
git init
git add .
git commit -m "Initial library project"


Step 2: Create book registration branch
git checkout -b book-registration


Modify script.js to add book registration:
function addBook() {
    let name = document.getElementById("name").value;
    let id = document.getElementById("roll").value;

    document.getElementById("list").innerHTML +=
        "<li>" + name + " - " + id + "</li>";
}


git add .
git commit -m "Added book registration"


Step 3: Create book search branch
git checkout main
git checkout -b book-search


Add search feature:
function searchBook() {
    let id = document.getElementById("roll").value;
    alert("Searching Book ID: " + id);
}


git add .
git commit -m "Added book search"


Step 4: Merge branches
git checkout main
git merge book-registration
git merge book-search


Step 5: Maintain version history
git log --oneline


Step 6: Push to GitHub
Create an empty GitHub repository named LibraryManagementSystem.
git remote add origin https://github.com/USERNAME/LibraryManagementSystem.git

git push -u origin main
git push origin book-registration
git push origin book-search


Output:
[main] Initial library project
[book-registration] Added book registration
[book-search] Added book search

Merge successful
Everything pushed to GitHub



Q10. Online Examination System – Git Branching and GitHub
Aim: Develop an Online Examination System with student login, question display and result calculation. Use Git branching, meaningful commits, merging and GitHub push.
1. Project structure
OnlineExaminationSystem/
│
├── index.html
├── style.css
├── script.js
└── README.md


2. index.html

<html>
<head>
<title>Online Examination</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<h2>Online Examination System</h2>

<input id="name" placeholder="Student Name">
<button onclick="login()">Login</button>

<p id="question"></p>

<button onclick="check(1)">HTML</button>
<button onclick="check(2)">Java</button>
<button onclick="check(3)">Python</button>

<p id="result"></p>

<script src="script.js"></script>
</body>
</html>



3. style.css
body {
    text-align: center;
    font-family: Arial;
}

input, button {
    padding: 10px;
    margin: 5px;
}


4. script.js
let marks = 0;

function login() {
    alert("Login Successful");

    document.getElementById("question").innerHTML =
        "Which is a programming language?";
}

function check(n) {
    if(n == 2)
        marks++;

    document.getElementById("result").innerHTML =
        "Your Result: " + marks + "/1";
}


5. README.md
Online Examination System

Features:
1. Student Login
2. Question Display
3. Result Calculation

Technologies:
HTML, CSS, JavaScript


6. Git commands
Step 1: Initialize repository
git init
git add .
git commit -m "Initial examination project"


Step 2: Student login branch
git checkout -b student-login
git add .
git commit -m "Added student login"


Step 3: Question display branch
git checkout main
git checkout -b question-display
git add .
git commit -m "Added question display"


Step 4: Result calculation branch
git checkout main
git checkout -b result-calculation
git add .
git commit -m "Added result calculation"


Step 5: Merge branches
git checkout main
git merge student-login
git merge question-display
git merge result-calculation


Step 6: Push to GitHub

Create an empty GitHub repository named OnlineExaminationSystem.
git branch -M main

git remote add origin https://github.com/USERNAME/OnlineExaminationSystem.git

git push -u origin main
git push origin student-login
git push origin question-display
git push origin result-calculation


Output:
[main] Initial examination project
Added student login
Added question display
Added result calculation

Merge successful
Everything pushed to GitHub



Final Revision – Important Git Commands
Learn this table before your lab examination. These commands are repeated in almost every question.
Operation	Git command
Initialize	git init
Check status	git status
Stage all	git add .
Stage selected	git add index.html
Unstage	git restore --staged filename
Commit	git commit -m "message"
View history	git log --oneline
Create branch	git branch name
Switch branch	git checkout main
Create + switch	git checkout -b name
Merge	git merge name
View branches	git branch
Add remote	git remote add origin URL
View remote	git remote -v
Push	git push -u origin main

Which code should you prepare?
Question	Project	Code preparation
Q3	Student Management	Full code
Q4	Student Branching	Q3 code
Q5	Merge Conflict	Q3 README
Q6	Library Management	Change student to book
Q7	Employee Management	Change student to employee
Q8	Banking Application	Simple deposit code
Q9	Library Branching	Q6 code
Q10	Online Examination	Separate simple code

My recommendation for your lab exam

First practise Q3 completely. Then practise Q4 and Q5 because they use the same project.

Next learn Q6 and Q9 together. Finally prepare Q7, Q8 and Q10.

Important: For Q4 and Q9, actually make independent commits on each branch. For Q5, actually modify the same README line in both branches. Otherwise, Git may not produce the required merge conflict.

You can use these eight programs as your main Git practical preparation.

















For third and fourth question, README.md file is not required, right?













Yes, correct. README.md is not compulsory for Questions 3 and 4 because it is not specifically mentioned in those questions.
- Q3: index.html, style.css, script.js are sufficient to track and push the source files.
- Q4: Use the same three files and create registration and search branches.
But Q5 requires README.md because the question specifically asks you to create a merge conflict in that file.

For simplicity, you can use:
Question	README.md
Q3	Not required
Q4	Not required
Q5	Required
Q6	Optional
Q7	Optional
Q8	Optional
Q9	Not required
Q10	Optional

Follow the exact requirements given in your lab question.

















So in fourth question you said that add search code in script.js. So we should add search code in third question script.js?













Yes! In Q3, keep both registration and search functions in script.js.

For Q4, you should demonstrate them independently using separate branches.
1. Create student-registration branch and modify/add the registration function. Commit it.
2. Return to main.
3. Create student-search branch and modify/add the search function. Commit it.
4. Merge both branches into main.
Important: Both branches start from Q3's main branch. To demonstrate independent development properly, make a separate change in each branch before committing.

So, you can reuse Q3's code, but make actual changes in Q4 to demonstrate branching and merging.

















Please can you give the updated code for the fourth question?













Sure! For Q4 – Student Registration and Student Search using Git Branching and Merging, use the following updated code.

We will use Q3's project as the base and make separate changes in two branches.
1. Project structure
StudentManagementSystem/
│
├── index.html
├── style.css
└── script.js


2. Initial code (Q3 – main branch)
Keep this code in Q3 before creating branches.

index.html
<html>
<head>
<title>Student Management</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<h2>Student Management System</h2>

<input id="name" placeholder="Student Name">
<input id="roll" placeholder="Roll Number">

<button onclick="addStudent()">Register</button>
<button onclick="searchStudent()">Search</button>

<ul id="list"></ul>

<script src="script.js"></script>
</body>
</html>


style.css
body {
    text-align: center;
    font-family: Arial;
}

input, button {
    padding: 10px;
    margin: 5px;
}


script.js
let students = [];

function addStudent() {
    alert("Registration Feature");
}

function searchStudent() {
    alert("Search Feature");
}


3. Q4 – Create registration branch
git checkout -b student-registration


Replace script.js with:

script.js – Registration branch
let students = [];

function addStudent() {
    let name = document.getElementById("name").value;
    let roll = document.getElementById("roll").value;

    students.push({name, roll});

    document.getElementById("list").innerHTML +=
        "<li>" + name + " - " + roll + "</li>";

    alert("Student Registered");
}


Commit:
git add script.js
git commit -m "Added student registration"


4. Create student search branch
Return to main:
git checkout main


Create search branch:
git checkout -b student-search


Replace script.js with:

script.js – Search branch
let students = [];

function searchStudent() {
    let roll = document.getElementById("roll").value;

    let s = students.find(x => x.roll === roll);

    alert(s ? s.name : "Student Not Found");
}


Commit:
git add script.js
git commit -m "Added student search"


5. Merge both branches
git checkout main
git merge student-registration
git merge student-search


Both features merged
Final script.js after merging
let students = [];

function addStudent() {
    let name = document.getElementById("name").value;
    let roll = document.getElementById("roll").value;

    students.push({name, roll});

    document.getElementById("list").innerHTML +=
        "<li>" + name + " - " + roll + "</li>";

    alert("Student Registered");
}

function searchStudent() {
    let roll = document.getElementById("roll").value;

    let s = students.find(x => x.roll === roll);

    alert(s ? s.name : "Student Not Found");
}


6. Push to GitHub
git push origin main
git push origin student-registration
git push origin student-search


7. Expected output
Switched to branch 'main'

Merge made by the 'ort' strategy.
Added student registration

Merge made by the 'ort' strategy.
Added student search

Everything pushed to GitHub