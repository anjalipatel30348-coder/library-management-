# library-management-
<!DOCTYPE html>
<html>
<head>
    <title>Library Management System</title>

    <style>
        body {
            font-family: Arial;
            background: #f4f4f4;
            margin: 0;
        }

        header {
            background: #2c3e50;
            color: white;
            padding: 15px;
            text-align: center;
        }

        .container {
            padding: 20px;
        }

        .box {
            background: white;
            padding: 15px;
            margin-bottom: 20px;
            border-radius: 8px;
        }

        input, button {
            padding: 10px;
            margin: 5px;
        }

        button {
            background: #3498db;
            color: white;
            border: none;
        }

        table {
            width: 100%;
            margin-top: 10px;
            border-collapse: collapse;
        }

        table, th, td {
            border: 1px solid black;
        }

        th, td {
            padding: 10px;
            text-align: center;
        }
    </style>
</head>

<body>

<header>
    <h1>📚 Library Management System</h1>
</header>

<div class="container">

    <!-- Add Book -->
    <div class="box">
        <h2>Add Book</h2>
        <input type="text" id="bookName" placeholder="Book Name">
        <input type="text" id="author" placeholder="Author">
        <button onclick="addBook()">Add</button>
    </div>

    <!-- Issue Book -->
    <div class="box">
        <h2>Issue Book</h2>
        <input type="text" id="studentName" placeholder="Student Name">
        <input type="text" id="issueBookName" placeholder="Book Name">
        <button onclick="issueBook()">Issue</button>
    </div>

    <!-- Book List -->
    <div class="box">
        <h2>Book List</h2>
        <table id="bookTable">
            <tr>
                <th>Book Name</th>
                <th>Author</th>
            </tr>
        </table>
    </div>

</div>

<script>
    function addBook() {
        let name = document.getElementById("bookName").value;
        let author = document.getElementById("author").value;

        if(name === "" || author === ""){
            alert("Fill all fields");
            return;
        }

        let table = document.getElementById("bookTable");

        let row = table.insertRow();
        row.insertCell(0).innerHTML = name;
        row.insertCell(1).innerHTML = author;

        document.getElementById("bookName").value = "";
        document.getElementById("author").value = "";
    }

    function issueBook() {
        let student = document.getElementById("studentName").value;
        let book = document.getElementById("issueBookName").value;

        if(student === "" || book === ""){
            alert("Fill all fields");
            return;
        }

        alert("Book Issued to " + student);

        document.getElementById("studentName").value = "";
        document.getElementById("issueBookName").value = "";
    }
</script>

</body>
</html>


----css---
/* Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Body */
body {
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(to right, #74ebd5, #ACB6E5);
    min-height: 100vh;
}

/* Header */
header {
    background: #2c3e50;
    color: white;
    padding: 15px;
    text-align: center;
    font-size: 24px;
    letter-spacing: 1px;
}

/* Container */
.container {
    width: 90%;
    margin: 20px auto;
}

/* Box (Card Style) */
.box {
    background: white;
    padding: 20px;
    margin-bottom: 20px;
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}

/* Headings */
h2 {
    margin-bottom: 10px;
    color: #333;
}

/* Inputs */
input {
    width: 30%;
    padding: 10px;
    margin: 8px 5px;
    border-radius: 6px;
    border: 1px solid #ccc;
    transition: 0.3s;
}

/* Input Focus */
input:focus {
    border-color: #3498db;
    outline: none;
}

/* Buttons */
button {
    padding: 10px 20px;
    border: none;
    background: #3498db;
    color: white;
    border-radius: 6px;
    cursor: pointer;
    transition: 0.3s;
}

/* Button Hover */
button:hover {
    background: #2980b9;
}

/* Table */
table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 10px;
}

/* Table Header */
th {
    background: #3498db;
    color: white;
    padding: 10px;
}

/* Table Data */
td {
    padding: 10px;
    text-align: center;
    border-bottom: 1px solid #ddd;
}

/* Zebra effect */
tr:nth-child(even) {
    background: #f2f2f2;
}

/* Responsive */
@media (max-width: 768px) {
    input {
        width: 100%;
    }
}

