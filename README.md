<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camera Access</title>
</head>
<body>
    <h1>Camera Access</h1>
    <video id="video" width="640" height="480" autoplay></video>
    <script src="script.js"></script>
</body>
</html>
<!Doctype script.js>
const video = document.getElementById('video');

async function startCamera() {
    try {
        const stream = await navigator.mediaDevices.getUserMedia({ video: true });
        video.srcObject = stream;
    } catch (error) {
        console.error('Error accessing the camera', error);
    }
}

startCamera();
