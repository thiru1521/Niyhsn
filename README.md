<!DOCTYPE html>
<html>
<head>
    <title>MGR University - Student Grade Sheet</title>
    <style>
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: #eef2f3; text-align: center; color: #333; }
        .container { margin-top: 50px; background: white; padding: 40px; width: 600px; margin-left: auto; margin-right: auto; box-shadow: 0px 10px 25px rgba(0,0,0,0.1); border-radius: 12px; border-top: 8px solid #003366; }
        h2 { color: #003366; margin-bottom: 5px; letter-spacing: 1px; }
        h4 { color: #666; margin-top: 0; margin-bottom: 25px; font-weight: 400; border-bottom: 1px solid #eee; padding-bottom: 15px; }
        input { padding: 12px; width: 60%; margin: 10px; border: 1px solid #ddd; border-radius: 5px; outline: none; }
        button { padding: 12px 30px; background: #003366; color: white; border: none; border-radius: 5px; cursor: pointer; font-weight: bold; transition: 0.3s; }
        button:hover { background: #00509e; }
        table { margin: 25px auto; border-collapse: collapse; width: 100%; background: #fff; }
        table, th, td { border: 1px solid #eee; padding: 12px; text-align: left; }
        th { background-color: #f4f6f8; color: #003366; text-transform: uppercase; font-size: 13px; }
        .fail { color: #e74c3c; font-weight: bold; }
        .absent { color: #95a5a6; font-style: italic; }
        .practical-row { background-color: #fafafa; }
        .student-header { text-align: left; margin-top: 20px; padding: 10px; background: #f9f9f9; border-left: 5px solid #003366; }
        .student-name { color: #2c3e50; font-weight: bold; margin: 0; font-size: 18px; }
    </style>
</head>
<body>

<div class="container">
    <h2>MGR UNIVERSITY</h2>
    <h4>Student Grade Sheet - Nov/Dec 2025</h4>

    <input type="text" id="regno" placeholder="Enter 12-Digit Register Number">
    <br>
    <button onclick="getResult()">VIEW GRADE SHEET</button>

    <div id="result"></div>
</div>

<script>
function getResult() {
    var reg = document.getElementById("regno").value.trim();
    var resultDiv = document.getElementById("result");
    
    var header = `<table><tr><th>Type</th><th>Subject</th><th>Grade</th></tr>`;
    
    var practicals = `
        <tr class="practical-row"><td>Practical</td><td>Data Structure Lab</td><td>D</td></tr>
        <tr class="practical-row"><td>Practical</td><td>Database Lab</td><td>C</td></tr>
        <tr class="practical-row"><td>Practical</td><td>C++ Lab</td><td>D</td></tr>`;

    let content = "";

    // 1. Dinesh .R - All Theory Fail
    if(reg == "254012101074"){
        content = `<div class="student-header"><p class="student-name">DINESH R</p>Reg No: 254012101074</div>` + header + `
        <tr><td>Theory</td><td>C++</td><td class="fail">RA</td></tr>
        <tr><td>Theory</td><td>Web</td><td class="fail">RA</td></tr>
        <tr><td>Theory</td><td>Research</td><td class="fail">RA</td></tr>
        <tr><td>Theory</td><td>DSA</td><td class="fail">RA</td></tr>
        <tr><td>Theory</td><td>DBMS</td><td class="fail">RA</td></tr>` + practicals + `</table>`;
    }

    // 2. Basker .S - Web Absent, 1 Sub Fail
    else if(reg == "254012101070"){
        content = `<div class="student-header"><p class="student-name">BASKER S</p>Reg No: 254012101070</div>` + header + `
        <tr><td>Theory</td><td>C++</td><td>B</td></tr>
        <tr><td>Theory</td><td>Web</td><td class="absent">ABS</td></tr>
        <tr><td>Theory</td><td>Research</td><td>C</td></tr>
        <tr><td>Theory</td><td>DSA</td><td class="fail">RA</td></tr>
        <tr><td>Theory</td><td>DBMS</td><td>D</td></tr>` + practicals + `</table>`;
    }

    // 3. Harikrishnan .R - 3 Fail
    else if(reg == "25401210191"){
        content = `<div class="student-header"><p class="student-name">HARIKRISHNAN R</p>Reg No: 25401210191</div>` + header + `
        <tr><td>Theory</td><td>C++</td><td class="fail">RA</td></tr>
        <tr><td>Theory</td><td>Web</td><td class="fail">RA</td></tr>
        <tr><td>Theory</td><td>Research</td><td class="fail">RA</td></tr>
        <tr><td>Theory</td><td>DSA</td><td>C</td></tr>
        <tr><td>Theory</td><td>DBMS</td><td>D</td></tr>` + practicals + `</table>`;
    }

    // 4. Ashik Rahuman .B - All Pass (Minimum)
    else if(reg == "254012101064"){
        content = `<div class="student-header"><p class="student-name">ASHIK RAHUMAN B</p>Reg No: 254012101064</div>` + header + `
        <tr><td>Theory</td><td>C++</td><td>D</td></tr>
        <tr><td>Theory</td><td>Web</td><td>C</td></tr>
        <tr><td>Theory</td><td>Research</td><td>D</td></tr>
        <tr><td>Theory</td><td>DSA</td><td>C</td></tr>
        <tr><td>Theory</td><td>DBMS</td><td>D</td></tr>` + practicals + `</table>`;
    }

    // 5. Girini Vasan .I - 2 Fail
    else if(reg == "254012101087"){
        content = `<div class="student-header"><p class="student-name">GIRINI VASAN I</p>Reg No: 254012101087</div>` + header + `
        <tr><td>Theory</td><td>C++</td><td>B</td></tr>
        <tr><td>Theory</td><td>Web</td><td>C</td></tr>
        <tr><td>Theory</td><td>Research</td><td>B</td></tr>
        <tr><td>Theory</td><td>DSA</td><td class="fail">RA</td></tr>
        <tr><td>Theory</td><td>DBMS</td><td class="fail">RA</td></tr>` + practicals + `</table>`;
    }

    else {
        content = "<p style='color:#e74c3c; margin-top:20px; font-weight:bold;'>Registration Number Not Found</p>";
    }

    resultDiv.innerHTML = content;
}
</script>

</body>
</html>

