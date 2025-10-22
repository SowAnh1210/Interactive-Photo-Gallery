<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Interactive Photo Gallery</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f0f0f0;
      margin: 0;
      padding: 20px;
    }

    h1 {
      color: #333;
    }

    #image {
      width: 500px;
      height: 300px;
      margin: 20px auto;
      border: 3px solid #444;
      border-radius: 12px;
      background-color: #ddd;
      background-size: cover;
      background-position: center;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      color: #222;
      font-weight: bold;
    }

    .preview {
      width: 150px;
      height: 100px;
      margin: 10px;
      border: 2px solid #ccc;
      border-radius: 8px;
      transition: 0.3s;
    }

    .preview:hover {
      border-color: #666;
      transform: scale(1.05);
      cursor: pointer;
    }

    .gallery {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
    }
  </style>
</head>
<body>
  <h1>🌄 Interactive Photo Gallery</h1>

  <div id="image">Hover over an image below to display here.</div>

  <div class="gallery">
    <img class="preview" src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?w=400" 
         alt="A peaceful mountain view" 
         onmouseover="upDate(this)" onmouseout="undo()">

    <img class="preview" src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=400" 
         alt="Golden beach at sunset" 
         onmouseover="upDate(this)" onmouseout="undo()">

    <img class="preview" src="https://images.unsplash.com/photo-1519125323398-675f0ddb6308?w=400" 
         alt="Starry night sky" 
         onmouseover="upDate(this)" onmouseout="undo()">

    <img class="preview" src="https://images.unsplash.com/photo-1491553895911-0055eca6402d?w=400" 
         alt="City skyline at dusk" 
         onmouseover="upDate(this)" onmouseout="undo()">

    <img class="preview" src="https://images.unsplash.com/photo-1469474968028-56623f02e42e?w=400" 
         alt="Forest in the morning fog" 
         onmouseover="upDate(this)" onmouseout="undo()">
  </div>

  <script>
    function upDate(previewPic) {
      console.log("Event triggered!");
      console.log("Image source: " + previewPic.src);
      console.log("Image description: " + previewPic.alt);

      let imageDiv = document.getElementById('image');
      imageDiv.style.backgroundImage = "url('" + previewPic.src + "')";
      imageDiv.innerHTML = previewPic.alt;
    }

    function undo() {
      let imageDiv = document.getElementById('image');
      imageDiv.style.backgroundImage = "url('')";
      imageDiv.innerHTML = "Hover over an image below to display here.";
    }
  </script>
</body>
</html>
