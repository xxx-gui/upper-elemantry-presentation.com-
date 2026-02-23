<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mosque Explorer Mission</title>
    <style>
        :root {
            --blue-grad: linear-gradient(135deg, #0077b6 0%, #023e8a 100%);
            --light-grad: linear-gradient(135deg, #e1f5fe 0%, #ffffff 100%);
            --navy: #023e8a;
            --gold: #ffb700;
        }

        * { box-sizing: border-box; }

        body {
            margin: 0; padding: 0;
            font-family: 'Segoe UI', Tahoma, sans-serif;
            background: var(--blue-grad);
            height: 100vh; display: flex; justify-content: center; align-items: center; overflow: hidden;
        }

        .app-shell {
            width: 95%; max-width: 900px; height: 92vh;
            background: white; border-radius: 40px;
            border: 8px solid rgba(255,255,255,0.2); position: relative;
            box-shadow: 0 30px 60px rgba(0,0,0,0.4); overflow: hidden;
        }

        /* Slide & Text Animations */
        @keyframes slideIn {
            from { opacity: 0; transform: scale(0.9) translateY(30px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        .slide { display: none; width: 100%; height: 100%; padding: 40px; flex-direction: column; align-items: center; justify-content: space-between; }
        .slide.active { display: flex; animation: slideIn 0.5s cubic-bezier(0.25, 1, 0.5, 1); }

        h1 { 
            background: var(--blue-grad); -webkit-background-clip: text; -webkit-text-fill-color: transparent;
            font-size: 2rem; margin: 0; text-transform: uppercase; font-weight: 900; text-align: center;
        }

        /* Every Image is a Button */
        .img-btn {
            width: 100%; max-width: 550px; height: 320px;
            border-radius: 30px; border: 6px solid #b3e5fc;
            overflow: hidden; cursor: pointer; position: relative;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 15px 35px rgba(0,0,0,0.15);
        }

        .img-btn:hover {
            transform: scale(1.04) translateY(-5px);
            border-color: var(--gold);
            box-shadow: 0 20px 45px rgba(0,0,0,0.3);
        }

        .img-btn::after {
            content: "CLICK IMAGE TO CONTINUE ➔";
            position: absolute; bottom: 15px; left: 50%; transform: translateX(-50%);
            background: rgba(2, 62, 138, 0.8); color: white;
            padding: 8px 15px; border-radius: 50px; font-size: 0.8rem; font-weight: bold;
            opacity: 0; transition: opacity 0.3s;
        }

        .img-btn:hover::after { opacity: 1; }

        .img-btn img { width: 100%; height: 100%; object-fit: cover; }

        .story-box {
            width: 100%; background: var(--light-grad); border-radius: 25px;
            padding: 25px; min-height: 150px; margin: 15px 0;
            font-size: 1.25rem; line-height: 1.6; color: var(--navy);
            border-left: 10px solid var(--navy); text-align: center;
            display: flex; flex-direction: column; justify-content: center;
        }

        .tag {
            background: #ff5252; color: white; padding: 4px 12px;
            border-radius: 10px; font-size: 0.8rem; font-weight: bold;
            margin-bottom: 10px; width: fit-content; align-self: center;
        }

        /* Hunt List */
        .hunt-grid {
            display: grid; grid-template-columns: 1fr 1fr; gap: 15px; width: 100%; margin-top: 10px;
        }
        .hunt-card {
            background: white; padding: 12px; border-radius: 15px;
            border: 2px dashed var(--navy); color: var(--navy);
            font-weight: bold; font-size: 1rem; text-align: center;
        }

        .restart-btn {
            background: var(--gold); color: var(--navy); border: none;
            padding: 15px 40px; font-size: 1.2rem; font-weight: bold;
            border-radius: 50px; cursor: pointer; transition: 0.3s;
            box-shadow: 0 8px 15px rgba(0,0,0,0.1);
        }
        .restart-btn:hover { transform: scale(1.1); background: #fff; }
    </style>
</head>
<body>

<div class="app-shell">

    <div class="slide active" id="s1">
        <h1>Mosque Explorer Mission</h1>
        <div class="img-btn" onclick="go(2)"><img src="MOSQUE THING.JPG"></div>
        <div class="story-box" id="t1"></div>
    </div>

    <div class="slide" id="s2">
        <h1>The Community Heart</h1>
        <div class="img-btn" onclick="go(3)"><img src="MOSQUE EXTIRIOR.JPG"></div>
        <div class="story-box" id="t2"></div>
    </div>

    <div class="slide" id="s3">
        <h1>Ancient Roots</h1>
        <div class="img-btn" onclick="go(4)"><img src="ANCIENT.JPG"></div>
        <div class="story-box" id="t3"></div>
    </div>

    <div class="slide" id="s4">
        <h1>Built to Last</h1>
        <div class="img-btn" onclick="go(5)"><img src="mosque.jpg"></div>
        <div class="story-box" id="t4"></div>
    </div>

    <div class="slide" id="s5">
        <h1>The Art of Focus</h1>
        <div class="img-btn" onclick="go(6)"><img src="QURAN.JPG"></div>
        <div class="story-box" id="t5"></div>
    </div>

    <div class="slide" id="s6">
        <h1>Geometry Secrets</h1>
        <div class="img-btn" onclick="go(7)"><img src="COLOURFUL STARS.JPG"></div>
        <div class="story-box" id="t6"></div>
    </div>

    <div class="slide" id="s7">
        <h1>Science of Sound</h1>
        <div class="img-btn" onclick="go(8)"><img src="MOSQUE DOME.JPG"></div>
        <div class="story-box" id="t7"></div>
    </div>

    <div class="slide" id="s8">
        <h1>Natural Cooling</h1>
        <div class="img-btn" onclick="go(9)"><img src="ANCIENT STONE.JPG"></div>
        <div class="story-box" id="t8"></div>
    </div>

    <div class="slide" id="s9">
        <h1>Equality for All</h1>
        <div class="img-btn" onclick="go(10)"><img src="MOSQUE INTERORIO.JPG"></div>
        <div class="story-box" id="t9"></div>
    </div>

    <div class="slide" id="s10">
        <h1>Live Scavenger Hunt</h1>
        <div class="story-box">
            <p>Mission Success! You are now an expert. When we visit the Mosque, find these 4 secrets:</p>
            <div class="hunt-grid">
                <div class="hunt-card">🔍 The Prayer Arch</div>
                <div class="hunt-card">🔍 8-Pointed Stars</div>
                <div class="hunt-card">🔍 Washing Fountains</div>
                <div class="hunt-card">🔍 The Dome Echo</div>
            </div>
        </div>
        <button class="restart-btn" onclick="location.reload()">RESTART MISSION</button>
    </div>

</div>

<script>
    const scripts = {
        1: "Welcome! Today we discover how mosques use math, history, and science. Click the image to start your journey!",
        2: "Why are they special? Mosques are community hubs where people gather to help neighbors, learn, and find peace.",
        3: "Who built the first one? The Prophet Muhammad (pbuh) built the first mosque in Medina as a place for everyone to belong.",
        4: "When? 1,400 years ago! That first building was incredibly simple, made from palm trees and mud bricks.",
        5: "Why no sculptures? You won't see statues here. This helps everyone focus on their spiritual connection, not on human images.",
        6: "Instead of statues, they use 'Sacred Geometry.' Math creates infinite star patterns that show how everything is connected.",
        7: "SHOCK FACT: Domes are giant speakers! Their curved shape was designed to carry a person's voice across the whole room.",
        8: "SHOCK FACT: Ancient builders created 'Wind Towers' to catch cool air and push it inside—early air conditioning!",
        9: "Inside, there are no chairs. Sitting together on the floor shows that every person is equal, no matter who they are.",
        10: ""
    };

    function typeWriter(text, elementId) {
        let i = 0;
        const elem = document.getElementById(elementId);
        elem.innerHTML = "";
        
        if(text.includes("SHOCK FACT")) {
            elem.innerHTML = '<span class="tag">DID YOU KNOW?</span><br>';
        }

        function type() {
            if (i < text.length) {
                elem.innerHTML += text.charAt(i);
                i++;
                setTimeout(type, 15);
            }
        }
        type();
    }

    function go(num) {
        document.querySelectorAll('.slide').forEach(s => s.classList.remove('active'));
        document.getElementById('s' + num).classList.add('active');
        if(num < 10) typeWriter(scripts[num], 't' + num);
    }

    window.onload = () => typeWriter(scripts[1], 't1');
</script>

</body>
</html>
