Task 1
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/792eaacb-fde5-401c-818e-e99b5a0f770d" />

Task 2
Step 1: Sign Up for ChatGPT
Go to chat.openai.com.

Click Sign Up.

Choose one of the following:

Google account

Microsoft account

Email and password

Verify your email address.

Log in to access the ChatGPT interface.


Step 2: Upload the Original Picture
In the chat window, click the paperclip icon 📎.

Select the original image file (picture-template.jpeg).

Wait until the image preview appears in the chat.


Step 3: Add the Albatross
Type a clear prompt such as:
Add an albatross flying above the landscape in this picture.
ChatGPT will process the image and generate a new version with the Albatross added.

Review the result and download it if satisfied.

Step 4: Save the Final Image
Click the download icon ⬇️ next to the generated image.

Save it as final-albatross.jpeg.

Insert both the original and final images into your answer.md file.


📑 Step 5: Verify Image Requirements
Ensure the Albatross is clearly visible.

Maintain the original picture’s resolution and proportions.

Confirm the file format is .jpeg or .png.

Include both images in your submission.


Task 3

graph TD

IONA --> AXEL
IONA --> MIRA

AXEL --> IONA
AXEL --> LUNE
AXEL --> RAFE

MIRA --> IONA
MIRA --> SOL
MIRA --> LUNE

LUNE --> AXEL
LUNE --> MIRA
LUNE --> WHISP

RAFE --> AXEL
RAFE --> SOL

SOL --> MIRA
SOL --> RAFE
SOL --> WHISP

WHISP --> LUNE
WHISP --> SOL


Task 4

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>GPA Calculator – Pascal</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 40px;
        background: #f5f7fa;
    }
    h1 {
        text-align: center;
        margin-bottom: 10px;
    }
    table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 20px;
        background: white;
    }
    th, td {
        border: 1px solid #ccc;
        padding: 8px;
        text-align: center;
    }
    th {
        background: #e8eef5;
    }
    .tooltip {
        position: relative;
        display: inline-block;
        cursor: pointer;
        font-size: 20px;
        margin-left: 10px;
    }
    .tooltip .tooltiptext {
        visibility: hidden;
        width: 400px;
        background-color: #333;
        color: #fff;
        text-align: left;
        border-radius: 6px;
        padding: 10px;
        position: absolute;
        z-index: 1;
        top: 30px;
        left: 0;
    }
    .tooltip:hover .tooltiptext {
        visibility: visible;
    }
    button {
        margin-top: 20px;
        padding: 12px 20px;
        font-size: 16px;
        cursor: pointer;
        background: #2b6cb0;
        color: white;
        border: none;
        border-radius: 6px;
    }
    #result {
        margin-top: 20px;
        font-size: 20px;
        font-weight: bold;
    }
</style>
</head>

<body>

<h1>GPA Calculator</h1>

<h2>Your Program: Bachelor of Computer Science</h2>

<!-- GPA INFO TOOLTIP -->
<div>
    <strong>GPA Information</strong>
    <span class="tooltip">ℹ️
        <span class="tooltiptext">
            <strong>Translated GPA Document:</strong><br><br>
            GPA is calculated by multiplying each course grade by its credit,
            summing all results, and dividing by total attempted credits.
            Grades follow the Ilia State University scale where:
            A = 4.0, B = 3.0, C = 2.0, D = 1.0, F = 0.0.
            Only passed courses count toward earned credits.
        </span>
    </span>
</div>

<!-- COURSE TABLE -->
<table id="courseTable">
    <thead>
        <tr>
            <th>Course</th>
            <th>Credit</th>
            <th>Grade</th>
            <th>Passed</th>
        </tr>
    </thead>
    <tbody></tbody>
</table>

<!-- BUTTONS -->
<button onclick="calculateGPA()">Calculate GPA</button>
<button onclick="calculateAI()">Calculate with Introduction to AI</button>

<div id="result"></div>

<script>
    // Your real transcript courses (example placeholders)
    const courses = [
        {course: "Introduction to AI", credit: 6, grade: 70, passed: "No"},
        {course: "Programming I", credit: 6, grade: 95, passed: "Yes"},
        {course: "Programming II", credit: 6, grade: 88, passed: "Yes"},
        {course: "Calculus I", credit: 6, grade: 77, passed: "Yes"},
        {course: "Calculus II", credit: 6, grade: 65, passed: "Yes"},
        {course: "Physics", credit: 6, grade: 55, passed: "No"},
        {course: "Algorithms", credit: 6, grade: 90, passed: "Yes"},
    ];

    // Add 5 extra program courses
    const extraCourses = [
        {course: "Data Structures", credit: 6, grade: 100, passed: "Yes"},
        {course: "Computer Architecture", credit: 6, grade: 100, passed: "Yes"},
        {course: "Operating Systems", credit: 6, grade: 100, passed: "Yes"},
        {course: "Databases", credit: 6, grade: 100, passed: "Yes"},
        {course: "Computer Networks", credit: 6, grade: 100, passed: "Yes"},
    ];

    const allCourses = [...courses, ...extraCourses];

    function loadTable() {
        const tbody = document.querySelector("#courseTable tbody");
        allCourses.forEach(c => {
            const row = document.createElement("tr");
            row.innerHTML = `
                <td>${c.course}</td>
                <td>${c.credit}</td>
                <td>${c.grade}</td>
                <td>${c.passed}</td>
            `;
            tbody.appendChild(row);
        });
    }

    function gradeToGPA(grade) {
        if (grade >= 90) return 4.0;
        if (grade >= 80) return 3.0;
        if (grade >= 70) return 2.0;
        if (grade >= 60) return 1.0;
        return 0.0;
    }

    function calculateGPA() {
        let totalPoints = 0;
        let totalCredits = 0;

        allCourses.forEach(c => {
            const gpa = gradeToGPA(c.grade);
            totalPoints += gpa * c.credit;
            totalCredits += c.credit;
        });

        const gpa = (totalPoints / totalCredits).toFixed(2);
        document.getElementById("result").innerText = "GPA: " + gpa;
    }

    function calculateAI() {
        let totalPoints = 0;
        let totalCredits = 0;

        allCourses.forEach(c => {
            let grade = c.grade;
            if (c.course === "Introduction to AI") {
                grade = c.grade + 30; // special rule
            }
            const gpa = gradeToGPA(grade);
            totalPoints += gpa * c.credit;
            totalCredits += c.credit;
        });

        const gpa = (totalPoints / totalCredits).toFixed(2);
        document.getElementById("result").innerText =
            "GPA with Introduction to AI: " + gpa;
    }

    loadTable();
</script>

</body>
</html>
