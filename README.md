<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Solar System with A-frame</title>
  <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
   <script src="https://cdn.jsdelivr.net/npm/mindarjs"></script>
  <script src="https://cdn.rawgit.com/jeromeetienne/AR.js/2.3.1/aframe/build/aframe-ar.js"></script>

  <link rel="stylesheet" href="styles.css">

<body>
  <a-scene id="scene" embedded arjs>
</head>
<body>
  <a-scene>
 
    <a-sphere position="-5 1.5 -5" radius="1.5" color="gray" src="https://github.com/aframevr/sample-assets/blob/master/assets/images/noise/disturb.jpg?raw=true"></a-sphere>
    <a-sphere position="-3 0 -3" radius="0.5" color="orange" src="https://github.com/aframevr/sample-assets/blob/master/assets/images/noise/waternormals.jpg?raw=true"></a-sphere>
    <a-sphere position="-2 0 -2" radius="0.7" color="brown" src="https://github.com/aframevr/sample-assets/blob/master/assets/images/noise/perlin-512.png?raw=true"></a-sphere>
    <a-sphere position="0 0 0" radius="1" color="blue" src="https://github.com/aframevr/sample-assets/blob/master/assets/images/space/earth_atmos_4096.jpg?raw=true"></a-sphere>
    </a-scene>

   <a-scene embedded arjs="sourceType: webcam; detectionMode: mono_and_matrix; matrixCodeType: 3x3;">
    <a-marker preset="custom" type="pattern" url="../SonyaIT/Apple_Store_logo.svg">
      <a-entity position="0 1.5 0" text="value: MindAR"></a-entity>
    </a-marker>

    
    <a-entity camera position="0 3 10"></a-entity>
  </a-scene>
   <script>
    document.addEventListener("DOMContentLoaded", function () {
     
      MindAR.initialize();

     
      MindAR.trackMarker({
        markerImageUrl: "../Apple_Store_logo.svg",
        onMarkerFound: function () {
          
          console.log("MindAR Marker Found");
        },
        onMarkerLost: function () {
         
          console.log("MindAR Marker Lost");
        }
      });
    });
  </script>
</body>
</html>
