# Camera
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camera Access</title>
</head>
<body>
    <h1>Camera Access Example</h1>
    <button onclick="startCamera()">Start Camera</button>
    <video id="cameraStream" autoplay></video>

    <script>
        function startCamera() {
            navigator.mediaDevices.getUserMedia({ video: true })
                .then(function (stream) {
                    const video = document.getElementById('cameraStream');
                    video.srcObject = stream;
                })
                .catch(function (error) {
                    console.error("Error accessing camera:", error);
                });
        }
    </script>
</body>
</html>
