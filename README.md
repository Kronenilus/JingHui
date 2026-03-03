# JingHui<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Quick Question...</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: #fdf2f4;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            overflow: hidden;
        }

        .card {
            text-align: center;
            background: white;
            padding: 40px;
            border-radius: 24px;
            box-shadow: 0 15px 35px rgba(255, 75, 43, 0.1);
            max-width: 400px;
            position: relative;
            z-index: 1;
        }

        h1 { color: #ff4b2b; margin-bottom: 10px; }
        p { font-size: 1.1rem; color: #555; line-height: 1.5; }
        
        .btn-container {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 20px;
            height: 50px; /* Keeps layout stable when button moves */
        }

        .btn {
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: bold;
            text-decoration: none;
            font-size: 1rem;
            transition: all 0.2s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }

        .yes-btn {
            background: #24A1DE; /* Telegram Blue */
            color: white;
            border: none;
            min-width: 100px;
        }

        .no-btn {
            background: #eee;
            color: #777;
            border: none;
            position: absolute; /* Needed for the movement script */
            cursor: pointer;
        }

        .emoji { font-size: 45px; margin-bottom: 10px; }
    </style>
</head>
<body>

    <div class="card">
        <div class="emoji">💌</div>
        <h1>Hey pickle rat/mello/Jing Hui,</h1>
        <p>I’ve been thinking about this for a while...</p>
        <p><strong>I really like you.</strong></p>
        <p>Would you like to go out sometime?</p>
        
        <div class="btn-container">
            <a href="https://t.me/Cchengxun" class="yes-btn btn">Yes!</a>
            <button class="no-btn btn" id="noBtn">No</button>
        </div>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');

        // Function to move the button to a random spot
        const moveButton = () => {
            // Calculate random positions within the visible screen
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;
        };

        // Triggers when the mouse/finger hovers or touches the button
        noBtn.addEventListener('mouseenter', moveButton);
        noBtn.addEventListener('touchstart', (e) => {
            e.preventDefault(); // Prevents clicking on mobile
            moveButton();
        });
    </script>

</body>
</html>
