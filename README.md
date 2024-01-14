# nebula-natter
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Nebula Natter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-image: url('https://images.unsplash.com/photo-1462331940025-496dfbfc7564?q=80&w=1822&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
      background-size: cover;
      background-position: center;
    }

    header {
      background-color: rgba(0, 0, 0, 0.8);
      color: #fff;
      text-align: center;
      padding: 1em;
    }

    main {
      max-width: 600px;
      margin: 20px auto;
      padding: 20px;
      background-color: rgba(255, 255, 255, 0.9);
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
    }

    textarea {
      width: 100%;
      margin-bottom: 10px;
      padding: 10px;
      box-sizing: border-box;
      resize: vertical;
    }

    button {
      background-color:#17a2b8;
      color: #f0e9e9;
      padding: 10px;
      border: none;
      cursor: pointer;
      border-radius: 26%;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #555;
    }

    ul {
      list-style-type: none;
      padding: 0;
    }

    li {
      margin-bottom: 10px;
      padding: 10px;
      background-color: #f9f9f9;
      box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
      border-radius: 5px;
    }

    #animatedPhoto {
      width: 100px;
      height: 100px;
      background-image: url('https://images.unsplash.com/photo-1577563908411-5077b6dc7624?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
      background-size: cover;
      background-position: center;
      border-radius: 50%;
      margin: 0 auto 20px;
      animation: bounce 0.67s infinite alternate;
    }

    @keyframes bounce {
      0% {
        transform: translateY(0);
      }
      100% {
        transform: translateY(-10px);
      }
    }
    .tabs {
      display: flex;
      justify-content: space-around;
      margin-bottom: 20px;
    }

    .tab {
      cursor: pointer;
      padding: 10px;
      background-color:#2c3e50;
      color:  #ffffff ;
      border:2px solid white;
      border-radius: 5px;
      transition: background-color 0.3s ease;
    }

    .tab:hover {
      background-color: #555;
    }

    .tab-content {
      display: none;
    }

    #viewTabContent,
    #postTabContent {
      display: block;
    }

    #audioTabContent {
      display: none;
      text-align: center;
    }

    #micIcon {
      font-size: 36px;
      color: #333;
      cursor: pointer;
      animation: bounce 0.34s infinite alternate;
    }
  </style>
</head>
<body>
  <header>
    <h1>Nebula Natter</h1>
  </header>

  <div class="tabs">
    <button class="tab" onclick="showTab('viewTabContent')">View & Comment</button>
    <button class="tab" onclick="showTab('postTabContent')">Post</button>
    <button class="tab" onclick="showTab('audioTabContent')">Audio Chat</button>
  </div>

  <main>
    <div id="viewTabContent" class="tab-content">
      <h2>Recent Posts</h2>
      <ul id="postsList"></ul>
    </div>

    <div id="postTabContent" class="tab-content">
      <div id="animatedPhoto"></div>
      <h2>Post Something</h2>
      <textarea id="postContent" rows="4" placeholder="Type your post here"></textarea>
      <button onclick="createPost()">Post</button>
    </div>

    <div id="audioTabContent" class="tab-content">
      <div id="micIcon">&#127908;</div>
      <p>Click the microphone icon to start an audio chat with a random stranger.</p>
    </div>
  </main>

  <script>

    function showTab(tabId) {
      const tabs = document.querySelectorAll('.tab-content');
      tabs.forEach(tab => {
        tab.style.display = 'none';
      });

      document.getElementById(tabId).style.display = 'block';
    }
  </script>
</body>
</html>
 
