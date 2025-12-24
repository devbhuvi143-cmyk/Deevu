# Deevu
<!DOCTYPE html>
<html>
<head>
  <title>Family Location Share</title>
</head>
<body style="font-family: Arial; text-align:center; margin-top:50px;">
  <h2>📍 Family Location Share</h2>
  <p>Button dabane se aap apni location share karne ki ijazat dete hain.</p>

  <button onclick="getLocation()" style="padding:10px 20px; font-size:16px;">
    Share My Location
  </button>

  <p id="result"></p>

  <script>
    function getLocation() {
      if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(showPosition, showError);
      } else {
        document.getElementById("result").innerHTML = "Geolocation supported nahi hai.";
      }
    }

    function showPosition(position) {
      const lat = position.coords.latitude;
      const lon = position.coords.longitude;
      document.getElementById("result").innerHTML =
        "✅ Location received:<br>Latitude: " + lat + "<br>Longitude: " + lon;
    }

    function showError(error) {
      document.getElementById("result").innerHTML = "❌ Location permission denied.";
    }
  </script>
</body>
</html>
