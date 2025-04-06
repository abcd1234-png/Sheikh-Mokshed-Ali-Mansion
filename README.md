<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>শেখ মোকসেদ আলী ম্যানশন</title>
  <style>
    .edit-btn {
      position: fixed;
      top: 10px;
      right: 10px;
      z-index: 1000;
      padding: 10px 15px;
      margin-bottom: 10px;
      background-color: #3498db;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
    }
    .edit-btn:hover {
      background-color: #2980b9;
    }
    [contenteditable="true"] {
      border: 1px dashed #999;
      background-color: #fef9e7;
    }
    body {
      font-family: Arial, sans-serif;
      padding: 60px 20px 20px;
      max-width: 800px;
      margin: auto;
      line-height: 1.6;
    }
    h1 {
      color: #2c3e50;
    }
  </style>
</head>
<body>
  <button class="edit-btn" onclick="toggleEdit()">Toggle Edit Mode</button>
  <button class="edit-btn" style="top: 60px;" onclick="saveContent()">Save</button>

  <h1 id="title" contenteditable="false">শেখ মোকসেদ আলী ম্যানশন</h1>
  <p id="address" contenteditable="false">
    বাসা/ হোল্ডিং :৭, ছত্রভোগ জামে মসজিদ সংলগ্ন, গ্রাম: ছত্রভোগ, ডাক: বাঘড়া-১৫৫৭, উপজেলা/থানা: শ্রীনগর, জেলা: মুন্সিগঞ্জ, ঢাকা।
  </p>

  <script>
    let isEditMode = false;

    function toggleEdit() {
      isEditMode = !isEditMode;
      document.querySelectorAll('[contenteditable]').forEach(el => {
        el.contentEditable = isEditMode;
      });
    }

    function saveContent() {
      const title = document.getElementById('title').innerText;
      const address = document.getElementById('address').innerText;

      localStorage.setItem('title', title);
      localStorage.setItem('address', address);

      alert("Content Saved!");
    }

    window.onload = () => {
      const savedTitle = localStorage.getItem('title');
      const savedAddress = localStorage.getItem('address');
      if (savedTitle) document.getElementById('title').innerText = savedTitle;
      if (savedAddress) document.getElementById('address').innerText = savedAddress;
    };
  </script>
</body>
</html>
