.<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body { display: flex; justify-content: center; align-items: center; height: 100vh; background: #fdf2f2; font-family: sans-serif; text-align: center; overflow: hidden; margin: 0; }
        .card { background: white; padding: 30px; border-radius: 30px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); width: 85%; max-width: 350px; border: 2px solid #ffccd5; }
        img { width: 160px; border-radius: 20px; margin-bottom: 20px; transition: 0.3s; }
        h1 { color: #d63384; font-size: 18px; line-height: 1.4; height: 60px; }
        .btn-container { height: 100px; position: relative; width: 100%; margin-top: 20px; }
        button { padding: 12px 25px; border: none; border-radius: 50px; cursor: pointer; font-weight: bold; position: absolute; transition: 0.1s; }
        #yesBtn { background-color: #ff4d6d; color: white; left: 10%; }
        #noBtn { background-color: #f0f0f0; color: #555; right: 10%; }
    </style>
</head>
<body>
    <div class="card">
        <img id="catGif" src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueXp4bmZ4bmZ4bmZ4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZweW5sJnB0PTEmY3Q9cw/cLS1zl2KqjaOdx4m9Z/giphy.gif">
        <h1 id="msg">I'm so sorry, this time I have totally messed up. Will you forgive me? 🥺</h1>
        <div class="btn-container">
            <button id="yesBtn" onclick="alert('Thank you... I promise, I won\'t make a mistake like this ever again! ❤️ Check the next link now.')">Yes</button>
            <button id="noBtn">No</button>
        </div>
    </div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const msg = document.getElementById('msg');
        const catGif = document.getElementById('catGif');
        
        // These are the messages that flash up when she tries to click "No"
        const lines = [
            "No? Please... 🥺",
            "I'm so sorry, I won't make a mistake anymore!",
            "I really messed up, please forgive me...",
            "I promise to be better! 😭",
            "Don't say no... please!",
            "I'll do anything to make it up to you! ❤️"
        ];
        
        let i = 0;

        noBtn.addEventListener('mouseover', () => {
            // Make the button jump off the screen
            noBtn.style.position = 'fixed';
            noBtn.style.left = Math.random() * (window.innerWidth - 100) + 'px';
            noBtn.style.top = Math.random() * (window.innerHeight - 50) + 'px';
            
            // Change the text and flash the GIF
            if(i < lines.length) {
                msg.innerText = lines[i];
                i++;
            } else {
                msg.innerText = "I'm so sorry, I won't make a mistake again. I promise! ❤️";
            }
            
            // Subtle "flash" effect for the GIF
            catGif.style.transform = "scale(1.1)";
            setTimeout(() => { catGif.style.transform = "scale(1)"; }, 100);
        });
    </script>
</body>
</html>

