# traffic
<!DOCTYPE html>
<html>
<head>
    <title>Traffic Light</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: #f0f0f0;
        }

        .traffic-light {
            background: #222;
            padding: 15px;
            border-radius: 10px;
        }

        .light {
            width: 80px;
            height: 80px;
            margin: 10px;
            border-radius: 50%;
            background: #555;
            opacity: 0.3;
        }

        .red.active {
            background: red;
            opacity: 1;
        }

        .yellow.active {
            background: yellow;
            opacity: 1;
        }

        .green.active {
            background: limegreen;
            opacity: 1;
        }
    </style>
</head>
<body>

<div class="traffic-light">
    <div class="light red" id="red"></div>
    <div class="light yellow" id="yellow"></div>
    <div class="light green" id="green"></div>
</div>

<script>
    const lights = [
        document.getElementById("red"),
        document.getElementById("yellow"),
        document.getElementById("green")
    ];

    let current = 0;

    function changeLight() {
        lights.forEach(light => light.classList.remove("active"));
        lights[current].classList.add("active");
        current = (current + 1) % lights.length;
    }

    changeLight();
    setInterval(changeLight, 2000);
</script>

</body>
</html>
