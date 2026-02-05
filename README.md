# Omanaeee-
A special surprise 
<!DOCTYPE html>
<html>
<head>
    <title>For Someone Special 💖</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            text-align: center;
            overflow: hidden;
            background: linear-gradient(to right, #ff9a9e, #fad0c4);
        }

        .page {
            display: none;
            height: 100vh;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }

        .active {
            display: flex;
        }

        button {
            padding: 12px 25px;
            margin: 10px;
            font-size: 18px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            transition: 0.3s;
        }

        #openBtn {
            background-color: #ff4d6d;
            color: white;
        }

        #closeBtn {
            background-color: #333;
            color: white;
            position: absolute;
        }

        h1 {
            font-size: 32px;
            color: #fff;
        }

        .message {
            width: 80%;
            font-size: 20px;
            color: white;
            line-height: 1.6;
        }

        /* Floating hearts & flowers */
        .floating {
            position: absolute;
            bottom: -50px;
            font-size: 24px;
            animation: floatUp 6s linear infinite;
        }

        @keyframes floatUp {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-100vh); opacity: 0; }
        }

        /* Popup style */
        .popup {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0);
            background: white;
            color: #ff4d6d;
            padding: 30px 50px;
            border-radius: 20px;
            font-size: 28px;
            font-weight: bold;
            box-shadow: 0 0 20px rgba(0,0,0,0.3);
            transition: 0.5s ease;
            z-index: 10;
        }

        .popup.show {
            transform: translate(-50%, -50%) scale(1);
        }
    </style>
</head>
<body>

<!-- First Page -->
<div class="page active" id="page1">
    <h1>Oru sadhanam veno enna open njekkruthh 😌</h1>
    <button id="openBtn" onclick="openPage()">Open 💖</button>
    <button id="closeBtn">Close 😝</button>
</div>

<!-- Second Page -->
<div class="page" id="page2">
    <h1>Chundariiii 💕</h1>
    <div class="message">
        You are not just someone I care about… you are the calm in my chaos, 
        the smile I wait for, and the thought that stays in my heart all day. <br><br>
        Among everyone in my life, you hold a place that no one else can ever replace. <br><br>
        It’s not just about love — it’s about the way you make everything feel lighter, safer, and more beautiful. <br><br>
        No matter what happens, my heart will always choose you, again and again. 💫
    </div>
</div>

<!-- Final Popup -->
<div class="popup" id="lovePopup">
    I Love You 💞
</div>

<script>
    const closeBtn = document.getElementById("closeBtn");

    // Close button runs away
    closeBtn.addEventListener("mouseover", function() {
        const x = Math.random() * (window.innerWidth - 100);
        const y = Math.random() * (window.innerHeight - 50);
        closeBtn.style.left = x + "px";
        closeBtn.style.top = y + "px";
    });

    function openPage() {
        document.getElementById("page1").classList.remove("active");
        document.getElementById("page2").classList.add("active");
        startFloating();

        // Show I Love You popup after 4 seconds
        setTimeout(() => {
            document.getElementById("lovePopup").classList.add("show");
        }, 4000);
    }

    function startFloating() {
        setInterval(() => {
            const element = document.createElement("div");
            element.classList.add("floating");
            element.innerHTML = Math.random() > 0.5 ? "💖" : "🌸";
            element.style.left = Math.random() * 100 + "vw";
            element.style.animationDuration = (Math.random() * 3 + 3) + "s";
            document.body.appendChild(element);

            setTimeout(() => {
                element.remove();
            }, 6000);
        }, 300);
    }
</script>

</body>
</html>
