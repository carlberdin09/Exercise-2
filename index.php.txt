<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="style.css">
    <title>Group 6 Team</title>
</head>
<body>
    <?php
    $profiles = ["member 1.jpg", "member 2.jpg", "member 3.jpg", "member 4.jpg", "member 5.jpg"];
    $names = ["Carl Berdin", "Marco Haloc", "Marc Dionisio", "Ricky Pili", "Mary Feb Malinao"];
    $statuses = ["Aspiring IT Specialist", "Aspiring IT Specialist", "Aspiring IT Specialist", "Aspiring IT Specialist", "Aspiring IT Specialist"];
    ?>

    <h1 class="heading">Group 6 Team</h1>
    <div class="image-container">
        <?php
        for ($i = 0; $i < count($profiles); $i++) {
            echo '<div class="image" onclick="fetch_info(' . $i . ')"><img src="' . $profiles[$i] . '"></div>';
        }
        ?>
    </div>

    <div class="info-container">
        <img class="profile" id="profile" src="<?php echo $profiles[0]; ?>" />
        <div class="info">
            <h1 class="name" id="name"><?php echo $names[0]; ?></h1>
            <h3 class="status" id="status"><?php echo $statuses[0]; ?></h3>
            <p class="about" id="about">
                I am an IT student and I believe in myself that I can do everything to become a professional in IT.
            </p>
        </div>
    </div>

    <script>
        function fetch_info(i) {
            let profile = <?php echo json_encode($profiles); ?>;
            let name = <?php echo json_encode($names); ?>;
            let status = <?php echo json_encode($statuses); ?>;
            
            document.getElementById("profile").src = profile[i];
            document.getElementById("name").innerHTML = name[i];
            document.getElementById("status").innerHTML = status[i];
            document.getElementById("about").innerHTML = name[i] + 
            " I am an IT student and I believe in myself that I can do everything to become a professional in IT." + 
            " My hobby is to play basketball. I always make time to learn HTML to improve and gain knowledge about how websites work." + 
            " Being an IT student is challenging and exciting at the same time. I'll push myself to learn and gain knowledge in HTML." + 
            " I am a hardworking student and I will do everything to achieve my dreams. I will make my family proud." + 
            " I am a 4th-year student with irregular standing, a working student, and working hard to finish my studies. I aim to join a good company after I graduate.";
        }
    </script>
</body>
</html>
