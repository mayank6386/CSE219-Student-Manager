<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Management System</title>
    <style>
        table {
            width: 50%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: center;
        }
        th {
            background-color: #f2f2f2;
        }
        button {
            padding: 5px 10px;
            background-color: red;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: darkred;
        }
    </style>
</head>
<body>

    <h2>Student Management System</h2>
    <table>
        <thead>
            <tr>
                <th>ID</th>
                <th>Name</th>
                <th>Age</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody id="students-table"></tbody>
    </table>

    <script>
        let students = [
            { id: 1, name: 'Alice', age: 20 },
            { id: 2, name: 'Bob', age: 21 },
            { id: 3, name: 'Charlie', age: 22 }
        ];

        function displayStudents() {
            let table = document.getElementById('students-table');
            table.innerHTML = ''; // Clear existing table content

            students.forEach(student => {
                let row = `<tr>
                               <td>${student.id}</td>
                               <td>${student.name}</td>
                               <td>${student.age}</td>
                               <td><button onclick="removeStudent(${student.id})">Remove</button></td>
                           </tr>`;
                table.innerHTML += row;
            });
        }

        function removeStudent(id) {
            students = students.filter(student => student.id !== id);
            displayStudents();
        }

        displayStudents();
    </script>

</body>
</html>
