<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Registration Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #20232a;
            color: #f5f5f5;
            padding: 40px;
        }
        h2 {
            color: #61dafb;
        }
        form {
            background-color: #282c34;
            padding: 20px;
            border-radius: 10px;
            width: 380px;
        }
        label {
            display: block;
            margin-top: 10px;
        }
        input, textarea, select {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
            border-radius: 5px;
            border: none;
        }
        input[type="submit"] {
            background-color: #61dafb;
            color: #000;
            font-weight: bold;
            margin-top: 15px;
            cursor: pointer;
        }
        .output {
            margin-top: 20px;
            background-color: #333;
            padding: 15px;
            border-radius: 8px;
        }
    </style>
</head>
<body>

<h2>Simple Registration Form</h2>

<!-- Form using POST method -->
<form method="POST" action="">
    <label for="firstname">First Name:</label>
    <input type="text" name="firstname" id="firstname">

    <label for="age">Age:</label>
    <input type="number" name="age" id="age" min="1">

    <label for="gender">Gender:</label>
    <select name="gender" id="gender">
        <option value="">-- Select Gender --</option>
        <option value="Male">Male</option>
        <option value="Female">Female</option>
        <option value="Prefer not to say">Prefer not to say</option>
    </select>

    <label for="quote">Quote in Life:</label>
    <textarea name="quote" id="quote" rows="3"></textarea>

    <input type="submit" name="submit" value="Submit">
</form>

<?php
// Check if form is submitted
if (isset($_POST['submit'])) {

    // Collect form inputs
    $firstname = trim($_POST['firstname']);
    $age = trim($_POST['age']);
    $gender = trim($_POST['gender']);
    $quote = trim($_POST['quote']);

    // Validation: Ensure no field is empty
    if (empty($firstname) || empty($age) || empty($gender) || empty($quote)) {
        echo "<div class='output'>⚠️ All fields are required. Please complete the form.</div>";
    } else {
        // Display formatted confirmation message
        echo "<div class='output'>";
        echo "You are <strong>$firstname</strong>, a <strong>$age</strong>-year-old <strong>$gender</strong>.<br>";
        echo "Your motto in life is: <em>\"$quote\"</em>.";
        echo "</div>";
    }
}
?>

</body>
</html>
