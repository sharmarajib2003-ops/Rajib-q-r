<!DOCTYPE html>
<html lang="ne">
<head>
  <meta charset="UTF-8">
  <title>Microphone Access (With Permission)</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>

<body style="font-family: sans-serif; padding:20px;">

  <h2>🎤 माइक्रोफोन लाइभ एक्सेस</h2>

  <p>
    यो पेजले तपाईंको माइक्रोफोन प्रयोग गर्न
    <b>पहिले अनुमति (Permission)</b> माग्छ।  
    अनुमति दिएपछि मात्र आवाज लाइभ सुन्न सकिन्छ।
  </p>

  <button onclick="startMic()" style="padding:10px 20px; font-size:16px;">
    ▶️ Start Microphone
  </button>

  <br><br>

  <audio id="audio" controls autoplay></audio>

  <script>
    async function startMic() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
        const audio = document.getElementById("audio");
        audio.srcObject = stream;
        alert("✅ Microphone permission granted. Live audio started.");
      } catch (error) {
        alert("❌ Microphone permission denied or error occurred.");
        console.error(error);
      }
    }
  </script>

</body>
</html>
