# Valentine-proposal
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Valentine Proposal</title>
    <style>
        html, body {
            margin: 0;
            height: 100%;
            overflow: hidden;
        }
        .bg_heart {
            position: relative;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #ff6b9d, #c44569, #ff6b9d);
            background-size: 400% 400%;
            animation: gradientShift 10s ease infinite;
            z-index: -1;
        }
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .container {
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            width: 100%;
            text-align: center;
            color: white;
            font-family: 'Arial', cursive;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        h1 {
            font-size: 2.5em;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }
        #text1 {
            font-size: 1.2em;
            line-height: 1.6;
            max-width: 80%;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
        }
        .heart {
            position: absolute;
            transform: rotate(-45deg);
        }
        .heart:before,
        .heart:after {
            position: absolute;
            top: -50%;
            left: 0;
            display: block;
            content: "";
            width: 100%;
            height: 100%;
            background: inherit;
            border-radius: 50%;
        }
        .heart:after {
            left: 50%;
        }
        @keyframes love {
            0% { top: 110%; opacity: 1; }
            100% { top: -10%; opacity: 0; }
        }
        .yes-btn {
            background: #ff4757;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.5em;
            border-radius: 50px;
            cursor: pointer;
            margin-top: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            transition: all 0.3s ease;
        }
        .yes-btn:hover {
            transform: scale(1.1);
            background: #ff3742;
        }
    </style>
</head>
<body>
    <div class="bg_heart"></div>
    <div class="container">
        <h1>Happy Valentine's Day! 💖</h1>
        <div id="text1"></div>
        <button class="yes-btn" onclick="acceptProposal()">Yes, I will! ❤️</button>
    </div>

    <script>
        // Falling hearts animation
        setInterval(function() {
            var r_num = Math.floor(Math.random() * 40) + 1;
            var r_size = Math.floor(Math.random() * 65) + 10;
            var r_left = Math.floor(Math.random() * 100) + 1;
            var r_bg_r = Math.floor(Math.random() * 55) + 200;
            var r_bg_g = Math.floor(Math.random() * 55) + 100;
            var r_bg_b = Math.floor(Math.random() * 155) + 100;
            var r_time = Math.floor(Math.random() * 5) + 5;

            document.querySelector('.bg_heart').innerHTML += 
                `<div class='heart' style='width:${r_size}px;height:${r_size}px;left:${r_left}%;background:rgba(${r_bg_r},${r_bg_g},${r_bg_b},0.8);animation:love ${r_time}s linear infinite'></div>`;
        }, 300);

        // Typewriter effect message
        var i = 0;
        var txt1 = "My dearest love, on this Valentine's Day, I want to tell you how special you are to me. From the moment we met, you've filled my world with joy. Will you make me the happiest by being my Valentine forever? 💕";
        var speed = 60;

        function typeWriter() {
            if (i < txt1.length) {
                document.getElementById("text1").innerHTML += txt1.charAt(i);
                i++;
                setTimeout(typeWriter, speed);
            }
        }
        typeWriter();

        // Accept proposal
        function acceptProposal() {
            document.getElementById("text1").innerHTML = "Yay! I knew it! Let's celebrate our love forever. 😍❤️";
            document.querySelector('.yes-btn').style.display = 'none';
        }
    </script>
</body>
</html>
