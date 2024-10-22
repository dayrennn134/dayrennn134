<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ dayren }}</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            const lines = [
                { text: "'Cause you could be the one that I love, love, love", delay: 100 },
                { text: "I could be the one that you dream of, of, of", delay: 100 },
                { text: "Message in a bottle is all I can do, do, do", delay: 100 },
                { text: "Standin' here, hopin' it gets to you", delay: 100 },
                { text: "You could be the one that I keep, and I, I, I", delay: 100 },
                { text: "Could be the reason you can't sleep at night, night, night", delay: 100 },
                { text: "Message in a bottle is all I can do, do, do", delay: 100 },
                { text: "Standin' here, hopin' it gets to you", delay: 100 },
            ];
            
            let currentLine = 0;
            let currentChar = 0;

            function typeCharacter() {
                if (currentLine < lines.length) {
                    const line = lines[currentLine];
                    if (currentChar < line.text.length) {
                        document.getElementById('lyrics').innerText += line.text[currentChar];
                        currentChar++;
                        setTimeout(typeCharacter, line.delay);
                    } else {
                        document.getElementById('lyrics').innerText += '\n';
                        currentChar = 0;
                        currentLine++;
                        setTimeout(typeCharacter, 50);
                    }
                }
            }

            document.getElementById('startButton').addEventListener('click', function() {
                // Sembunyikan tombol mulai
                this.style.display = 'none';
                // Tampilkan lirik
                document.getElementById('lyrics').style.display = 'block';
                // Bersihkan lirik sebelum mulai
                document.getElementById('lyrics').innerText = '';
                // Mulai mengetik lirik
                typeCharacter();
            });
        });
    </script>
</head>
<body>
    <div>
        <h1>{{ <333 }}</h1>
        <button id="startButton">Start</button>
        <pre id="dayrenn"></pre>
    </div>
</body>
</html>
