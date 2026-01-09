<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>🎬 Video Tracker</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <!-- Firebase -->
  <script src="https://www.gstatic.com/firebasejs/9.22.0/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/9.22.0/firebase-firestore-compat.js"></script>

  <style>
    body {
      background: #121212;
      color: white;
      font-family: 'Segoe UI', sans-serif;
      padding: 20px;
    }

    h2 {
      text-align: center;
      color: #ff4d4d;
    }

    input {
      width: 95%;
      padding: 10px;
      margin-bottom: 10px;
      font-size: 15px;
      border-radius: 8px;
      border: none;
      outline: none;
      background: #fff;
      color: #000;
    }

    input::placeholder {
      color: #888;
    }

      input:focus {
  border: 2px solid #ff4d4d;  /* Red border when focused */
  box-shadow: 0 0 5px rgba(255,77,77,0.5); /* Soft red glow */
  background: #fff; /* Keep white background */
  color: #000;
}

    button {
      padding: 10px 16px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      background: #ff2d55;
      color: white;
      font-weight: bold;
      font-size: 15px;
    }

    button:hover {
      background: #cc0033;
    }

    .video-block {
      background: rgba(255,255,255,0.06);
      border-left: 4px solid #ff4d4d;
      padding: 12px;
      border-radius: 12px;
      margin-bottom: 15px;
      position: relative;
    }

    .video-block.success {
      border-left: 4px solid #2ecc71;
      box-shadow: 0 0 0 2px #2ecc71;
    }

    .video-block.error {
      border-left: 4px solid #e74c3c;
      box-shadow: 0 0 0 2px #e74c3c;
    }

    .delete-btn {
      position: absolute;
      bottom: 8px;
      right: 12px;
      font-size: 20px;
      color: #ff4d4d;
      cursor: pointer;
      background: transparent;
      border: none;
    }

    .video-top {
      display: flex;
      align-items: center;
    }

    .thumb {
      width: 90px;
      height: 90px;
      border-radius: 8px;
      object-fit: cover;
      margin-right: 12px;
    }

    .video-title {
      font-size: 14px;
      font-weight: 500;
    }

    .video-serial {
      color: #f1c40f;
      font-weight: bold;
      margin-right: 6px;
    }

    .not-found {
      color: #ff6b6b;
      font-weight: bold;
    }

    #frameContainer {
      border: 2px solid #444;
      border-radius: 12px;
      padding: 15px;
      margin-top: 20px;
      background: #1e1e1e;
      max-height: 500px;
      overflow-y: auto;
    }

    #loader {
      text-align: center;
      margin-top: 10px;
      color: #ccc;
    }

    #customPopup {
      position: fixed;
      bottom: 40px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 9999;
    }

    #popupContent {
      background: #2ecc71;
      color: #fff;
      padding: 12px 20px;
      border-radius: 10px;
      font-weight: bold;
      border: 2px solid #2ecc71;
    }

    #confirmModal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: rgba(0, 0, 0, 0.6);
      z-index: 99999;
      align-items: center;
      justify-content: center;
    }

    #confirmModalContent {
      background: #222;
      padding: 20px;
      border-radius: 12px;
      max-width: 300px;
      width: 90%;
      text-align: center;
      border: 2px solid #ff4d4d;
    }

    #videoModal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: rgba(0,0,0,0.8);
      z-index: 100000;
      align-items: center;
      justify-content: center;
    }

    #videoModalContent {
      background: #000;
      border-radius: 12px;
      padding: 10px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    #modalIframe {
      width: 70%;
      height: 70px;
      border-radius: 8px;
    }

    .clickable-title {
      cursor: pointer;
      text-decoration: underline;
    }

    
   .likes-btn {
      background: linear-gradient(90deg, #ff004d, #ff9900);
      color: white;
      padding: 5px 12px;
      border-radius: 10px;
      font-size: 14px;
      cursor: pointer;
      display: inline-block;
      margin-top: 6px;
      box-shadow: 0 0 6px rgba(255, 0, 77, 0.4);
      transition: all 0.2s ease;
    }
    .likes-btn:hover {
      transform: scale(1.05);
      box-shadow: 0 0 12px rgba(255, 153, 0, 0.7);
    }

  </style>
</head>
<body>

<!-- Not Found Button -->
<button id="notFoundBtn" onclick="showNotFound()" 
  style="background:#1e1e1e; padding:10px 16px; border:2px solid #ff9900; border-radius:8px; color:white;">
  AVAILABLE BOT (0)
</button>

<!-- Not Found Modal -->
<div id="notFoundModal" style="display:none; position:fixed; top:0; left:0; right:0; bottom:0; background:rgba(0,0,0,0.6); z-index:150000; align-items:center; justify-content:center;">
  <div id="notFoundModalContent" style="background:#222; padding:20px; border-radius:12px; max-height:70%; width:80%; max-width:400px; overflow-y:auto; border:2px solid #ff9900; color:white;">
    <h3 style="text-align:center; margin-top:0;">Available Bot</h3>
    <div id="notFoundList" style="text-align:center; font-size:14px; line-height:1.6;"></div>
  </div>
</div>


<!-- All Links Bottom Button -->
<div id="bottomLinksBtn" style="position:fixed; bottom:10px; left:50%; transform:translateX(-50%); z-index:200000;">
  <button onclick="showAllLinks()" 
    style="
      background:#1e1e1e; 
      padding:10px 16px; 
      border:2px solid #ff4d4d; 
      border-radius:8px; 
      color:white; 
      font-weight:bold; 
      cursor:pointer;
      box-shadow:0 0 10px rgba(255,77,77,0.3);
      transition: all 0.2s ease;
    "
    onmouseover="this.style.background='#ff4d4d'; this.style.color='#fff';"
    onmouseout="this.style.background='#1e1e1e'; this.style.color='white';"
  >
    📋 All Links
  </button>
</div>

  

<!-- All Links Modal -->

<div id="allLinksModal" style="display:none; position:fixed; top:0; left:0; right:0; bottom:0; background:rgba(0,0,0,0.6); z-index:150000; align-items:center; justify-content:center;">
  <div id="allLinksModalContent" style="background:#222; padding:20px; border-radius:12px; max-height:70%; width:80%; max-width:400px; overflow-y:auto; border:2px solid #ff4d4d; color:white; box-shadow:0 0 15px rgba(0,0,0,0.5);">
    
    <h3 style="text-align:center; margin-top:0;">📋 Saved Videos</h3>
    <textarea id="allLinksContent" readonly 
      style="width:100%; height:250px; background:#111; color:#fff; border:none; border-radius:6px; padding:10px; font-size:13px; line-height:1.4; resize:none;">
    </textarea>
    
    <div style="text-align:center; margin-top:10px; display:flex; justify-content:center; gap:10px; flex-wrap:wrap;">
      
      <!-- Copy All Button -->
      <button onclick="copyAllLinks()" 
        style="
          background:#1e1e1e; 
          padding:8px 14px; 
          border:2px solid #2e8bff; 
          border-radius:8px; 
          color:white; 
          font-weight:bold; 
          cursor:pointer;
          box-shadow:0 0 10px rgba(46,139,255,0.3);
          transition: all 0.2s ease;
        "
        onmouseover="this.style.background='#2e8bff'; this.style.color='#fff';"
        onmouseout="this.style.background='#1e1e1e'; this.style.color='white';"
      >
        📄 Copy All
      </button>
      
      <!-- Reset All Button -->
      <button onclick="resetAll()" 
        style="
          background:#1e1e1e; 
          padding:8px 14px; 
          border:2px solid #ff4d4d; 
          border-radius:8px; 
          color:white; 
          font-weight:bold; 
          cursor:pointer;
          box-shadow:0 0 10px rgba(255,77,77,0.3);
          transition: all 0.2s ease;
        "
        onmouseover="this.style.background='#ff4d4d'; this.style.color='#fff';"
        onmouseout="this.style.background='#1e1e1e'; this.style.color='white';"
      >
        ♻️ Reset All
      </button>
      
    </div>
    
  </div>
</div>

<!-- Confirmation Popup -->
<div id="resetConfirm" style="display:none; position:fixed; top:0; left:0; right:0; bottom:0; background:rgba(0,0,0,0.7); z-index:300000; align-items:center; justify-content:center;">
  <div style="background:#222; padding:20px; border-radius:12px; width:90%; max-width:300px; text-align:center; border:2px solid #ff4d4d; color:white; box-shadow:0 0 15px rgba(0,0,0,0.5);">
    <p style="margin-bottom:15px; font-size:14px;">⚠ Are you sure you want to delete all saved videos?</p>
    <div style="display:flex; justify-content:center; gap:10px;">
      <button onclick="doReset()" style="background:#ff4d4d; padding:8px 14px; border:none; border-radius:6px; color:white; cursor:pointer;">
        Yes
      </button>
      <button onclick="closeResetConfirm()" style="background:#666; padding:8px 14px; border:none; border-radius:6px; color:white; cursor:pointer;">
        No
      </button>
    </div>
  </div>
</div>

<input type="text" id="searchBox" placeholder="Search YouTube (Last Hour)" oninput="handleSearchInput()" />

<div style="display:flex;gap:10px;margin-top:15px;">
  <input type="tel" id="serialInput" placeholder="Bot" style="flex:1;" oninput="handleSerialInput()" />
<input type="text" id="linkInput" placeholder="YouTube Link" style="flex:3;" oninput="handleLinkInput()" />
</div>

<div id="loader" style="display:none;">⏳ Tracking... please wait</div>

<div id="frameContainer">
  <div id="results" class="result"></div>
</div>

<!-- Popup -->
<div id="customPopup" style="display: none;">
  <div id="popupContent"></div>
</div>

<!-- Confirm Modal -->
<div id="confirmModal">
  <div id="confirmModalContent">
    <p id="confirmText">Are you sure?</p>
    <div style="margin-top: 15px;">
      <button id="confirmYes" style="background:#ff2d55;">Yes</button>
      <button id="confirmNo" style="background:#666;">Cancel</button>
    </div>
  </div>
</div>

<!-- Video Modal -->
<div id="videoModal">
  <div id="videoModalContent">
    <iframe id="modalIframe" src="" frameborder="0" allowfullscreen></iframe>
  </div>
</div>

<script>
  const firebaseConfig = {
    apiKey: "AIzaSyDOSmFSpbsfXveaDpozsjDwTbc3yjmcAhg",
    authDomain: "amittg-tool.firebaseapp.com",
    projectId: "amittg-tool",
    storageBucket: "amittg-tool.appspot.com",
    messagingSenderId: "873427375036",
    appId: "1:873427375036:web:315252c835a9dcf6f111b9"
  };

  firebase.initializeApp(firebaseConfig);
  const db = firebase.firestore();
  const ytCollection = db.collection("youtube_links");
  const YT_API_KEY = "AIzaSyDFvv93DEI4LG-uCwR8EGWm1lQ_i6Ob1n8";
  const YT_LIKE_KEY = "AIzaSyDXbiFdiB7IzuuPqKrbSfdTg5CUurFknpo";

  ytCollection.orderBy("timestamp", "asc").onSnapshot(snapshot => {
    const docs = snapshot.docs.map(doc => ({
      id: doc.id,
      serial: parseInt(doc.data().serial),
      link: doc.data().link
    }));

    docs.sort((a, b) => a.serial - b.serial);
    window.allYTDocs = docs;
    checkVideos();
  });

  function extractVideoID(url) {
    const regExp = /(?:youtube\.com\/(?:[^\/\n\s]+\/\S+\/|(?:v|embed)\/|.*[?&]v=)|youtu\.be\/)([a-zA-Z0-9_-]{11})/;
    const match = url.match(regExp);
    return match ? match[1] : null;
  }

  
  async function checkVideos() {
  const docs = window.allYTDocs || [];
  const resultsDiv = document.getElementById("results");
  const loader = document.getElementById("loader");
  resultsDiv.innerHTML = "";
  loader.style.display = "block";

  const videoIdMap = {};
  const serialStatus = {}; // Track status of each serial
  const allBlocksTemp = []; // Store {serial, block}

  const tasks = docs.map((doc) => {
    const { serial, link } = doc;
    const videoId = extractVideoID(link);
    if (videoId) videoIdMap[videoId] = (videoIdMap[videoId] || 0) + 1;

    if (!serialStatus[serial]) {
      serialStatus[serial] = { available: false, notFound: false };
    }

    const block = document.createElement("div");
    block.className = "video-block";

    if (!videoId) {
      block.classList.add("error");
      serialStatus[serial].notFound = true;
      block.innerHTML = `<div class="video-title"><span class="video-serial">${serial}</span><span class="not-found">❌ Invalid</span><br><a href="${link}" target="_blank">${link}</a></div>`;
      allBlocksTemp.push({ serial, block });
      return block;
    }

    return fetch(`https://www.youtube.com/oembed?url=https://www.youtube.com/watch?v=${videoId}&format=json`)
      .then(res => res.json())
      .then(data => {
        block.classList.add("success");
        serialStatus[serial].available = true;
        block.innerHTML = `<div class="video-top"><img src="https://img.youtube.com/vi/${videoId}/hqdefault.jpg" class="thumb"><div class="video-info"><div class="video-title"><span class="video-serial">${serial}</span><span class="clickable-title" onclick="openVideoModal('${videoId}')">${data.title}</span></div><span class="likes-btn" onclick="showLikes(this, '${videoId}')">👍 Likes</span></div></div>`;
        if (videoIdMap[videoId] > 1) addDeleteButton(block, doc);
        allBlocksTemp.push({ serial, block });
        return block;
      })
      .catch(async () => {
        const apiURL = `https://www.googleapis.com/youtube/v3/videos?part=status&id=${videoId}&key=${YT_API_KEY}`;
        try {
          const res = await fetch(apiURL);
          const json = await res.json();
          const status = json.items?.[0]?.status?.uploadStatus || 'deleted';
          const isAvailable = status.toLowerCase() !== "deleted";
          if (isAvailable) serialStatus[serial].available = true;
          else serialStatus[serial].notFound = true;

          block.classList.add(isAvailable ? "success" : "error");
          block.innerHTML = `<div class="video-top">${isAvailable ? `<img src="https://img.youtube.com/vi/${videoId}/hqdefault.jpg" class="thumb">` : ""}<div class="video-info" style="margin-left:12px;"><div class="video-title"><span class="video-serial">${serial}</span><span class="clickable-title ${isAvailable ? '' : 'not-found'}" onclick="openVideoModal('${videoId}')">${isAvailable ? "✅ Available" : "❌ Not Found"}</span></div>${isAvailable ? `<span class="likes-btn" onclick="showLikes(this, '${videoId}')">👍 Likes</span>` : ""}</div></div>`;
          if (videoIdMap[videoId] > 1) addDeleteButton(block, doc);
          allBlocksTemp.push({ serial, block });
          return block;
        } catch {
          serialStatus[serial].notFound = true;
          block.classList.add("error");
          block.innerHTML = `<div class="video-title"><span class="video-serial">${serial}</span><span class="not-found">❌ Not Found</span><br><a href="${link}" target="_blank">${link}</a></div>`;
          allBlocksTemp.push({ serial, block });
          return block;
        }
      });
  });

  const allBlocks = await Promise.all(tasks);
  allBlocks.forEach(block => block && resultsDiv.appendChild(block));

  // Build Not Found list ONLY for those serials where NO video is available
  window.notFoundSerials = Object.keys(serialStatus)
    .filter(s => serialStatus[s].notFound && !serialStatus[s].available);

  // Update button count
  const nfBtn = document.getElementById("notFoundBtn");
  if (nfBtn) nfBtn.innerText = `Available Bot (${window.notFoundSerials.length})`;

  loader.style.display = "none";
}



async function showLikes(elem, videoId) {
  elem.textContent = "⏳ ...";
  if (!videoId) {
    elem.textContent = "❌ No ID";
    return;
  }
  try {
    const likeAPI = `https://www.googleapis.com/youtube/v3/videos?part=statistics&id=${videoId}&key=${YT_LIKE_KEY}`;
    const res = await fetch(likeAPI);
    const data = await res.json();
    const likes = data.items?.[0]?.statistics?.likeCount || "0";
    elem.textContent = `${likes}`;
  } catch {
    elem.textContent = "⚠️ Error";
  }
}

  function addDeleteButton(block, doc) {
    const deleteBtn = document.createElement("span");
    deleteBtn.className = "delete-btn";
    deleteBtn.textContent = "❌";
    deleteBtn.title = "Delete from Firestore";
    deleteBtn.onclick = () => {
      showConfirm("Delete this video from Firestore?", async () => {
        await ytCollection.doc(doc.id).delete();
        showPopup(`🗑️ Deleted Serial #${doc.serial}`);
      });
    };
    block.appendChild(deleteBtn);
  }

  async function saveEntry() {
  const serial = document.getElementById("serialInput").value.trim();
  const link = document.getElementById("linkInput").value.trim();
  const videoId = extractVideoID(link);

  if (!serial || !link || !videoId) {
    showPopup("❌ Invalid input or link", false);
    return;
  }

  try {
    await ytCollection.add({
      serial,
      link,
      timestamp: firebase.firestore.FieldValue.serverTimestamp()
    });
    document.getElementById("serialInput").value = "";
    document.getElementById("linkInput").value = "";
    showPopup(`✅ Saved Serial #${serial}`);
  } catch (err) {
    console.error("Save error:", err);
    showPopup("❌ Failed to save", false);
  }
}

function resetAll() {
  document.getElementById("resetConfirm").style.display = "flex";
}

async function doReset() {
  const snapshot = await ytCollection.get();
  const batch = db.batch();
  snapshot.docs.forEach(doc => batch.delete(doc.ref));
  await batch.commit();
  document.getElementById("results").innerHTML = "";
  showPopup("♻️ All entries reset");
  closeResetConfirm();
}

function closeResetConfirm() {
  document.getElementById("resetConfirm").style.display = "none";
}

// Click outside popup to close
document.getElementById("resetConfirm").addEventListener("click", function(e) {
  const modalContent = this.querySelector("div");
  if (!modalContent.contains(e.target)) {
    closeResetConfirm();
  }
});

  function searchYouTube() {
    const input = document.getElementById('searchBox');
    const query = input.value.trim();
    if (!query) return alert("Please enter a search term.");
    const encoded = encodeURIComponent(query);
    const url = `https://www.youtube.com/results?search_query=${encoded}&sp=EgIIAQ%253D%253D`;
    window.open(url, "_blank");
    input.value = "";
  }

  function showPopup(message, success = true) {
    const popup = document.getElementById("customPopup");
    const content = document.getElementById("popupContent");
    content.style.borderColor = success ? "#2ecc71" : "#e74c3c";
    content.style.background = success ? "#2ecc71" : "#e74c3c";
    content.innerHTML = message;
    popup.style.display = "block";
    setTimeout(() => popup.style.display = "none", 3000);
  }

  function showConfirm(message, onConfirm) {
    const modal = document.getElementById("confirmModal");
    const text = document.getElementById("confirmText");
    const yesBtn = document.getElementById("confirmYes");
    const noBtn = document.getElementById("confirmNo");

    text.textContent = message;
    modal.style.display = "flex";

    const cleanup = () => {
      modal.style.display = "none";
      yesBtn.onclick = null;
      noBtn.onclick = null;
    };

    yesBtn.onclick = () => {
      cleanup();
      onConfirm();
    };
    noBtn.onclick = cleanup;
  }

  function openVideoModal(videoId) {
    const modal = document.getElementById("videoModal");
    const iframe = document.getElementById("modalIframe");
    iframe.src = `https://www.youtube.com/embed/${videoId}`;
    modal.style.display = "flex";
  }

  // Click outside to close modal
  document.getElementById("videoModal").addEventListener("click", function (e) {
    const content = document.getElementById("videoModalContent");
    if (!content.contains(e.target)) {
      this.style.display = "none";
      document.getElementById("modalIframe").src = "";
    }
  });
document.getElementById("serialInput").addEventListener("input", function () {
  const val = this.value.trim();
  if (val.length === 2) {
    document.getElementById("linkInput").focus();
  }
});

function handleSerialInput() {
  const serial = document.getElementById("serialInput").value.trim();
  if (serial.length === 2) {
    // Move focus to the link input
    document.getElementById("linkInput").focus();
  }
}

function handleLinkInput() {
  const serial = document.getElementById("serialInput").value.trim();
  const link = document.getElementById("linkInput").value.trim();

  const videoId = extractVideoID(link);
  if (!videoId) return;

  if (serial && videoId.length === 11) {
    saveEntry(); // auto-save
  }
}

function handleSearchInput() {
  const input = document.getElementById('searchBox');
  const query = input.value.trim();
  if (query.length > 2) {
    const encoded = encodeURIComponent(query);
    const url = `https://www.youtube.com/results?search_query=${encoded}&sp=EgIIAQ%253D%253D`; // Last hour filter
    window.open(url, "_blank");
    input.value = ""; // optional: clear input after redirect
  }
}

function showAllLinks() {
  const textarea = document.getElementById("allLinksContent");
  const docs = window.allYTDocs || [];

  if (docs.length === 0) {
    textarea.value = "No links saved yet.";
  } else {
    textarea.value = docs.map(doc => `${doc.serial} — ${doc.link}`).join("\n");
  }

  document.getElementById("allLinksModal").style.display = "flex";
}


function closeAllLinks() {
  document.getElementById("allLinksModal").style.display = "none";
}

// Close popup when clicking outside the box
document.getElementById("allLinksModal").addEventListener("click", function(e) {
  const content = document.getElementById("allLinksModalContent");
  if (!content.contains(e.target)) {
    closeAllLinks();
  }
});


function copyAllLinks() {
  const textarea = document.getElementById("allLinksContent");
  if (!textarea.value.trim()) {
    showPopup("❌ No links to copy!", false);
    return;
  }
  textarea.select();
  document.execCommand("copy");
  showPopup("✅ All links copied to clipboard!", true); // Toast show
}

function showNotFound() {
  const listDiv = document.getElementById("notFoundList");
  if (!window.notFoundSerials || window.notFoundSerials.length === 0) {
    listDiv.innerHTML = "<p style='color:#ccc;'>✅ No Not Found videos currently.</p>";
  } else {
    listDiv.innerHTML = window.notFoundSerials
      .map(num => `<span style="cursor:pointer; color:#ff9900; text-decoration:underline;" onclick="focusSerial('${num}')">${num}</span>`)
      .join(" &nbsp; &nbsp; ");
  }
  document.getElementById("notFoundModal").style.display = "flex";
}

function closeNotFound() {
  document.getElementById("notFoundModal").style.display = "none";
}

document.getElementById("notFoundModal").addEventListener("click", function(e) {
  const content = document.getElementById("notFoundModalContent");
  if (!content.contains(e.target)) {
    closeNotFound();
  }
});

function focusSerial(serial) {
  closeNotFound();
  const container = document.getElementById("frameContainer");
  const block = Array.from(container.querySelectorAll(".video-block"))
    .find(div => div.querySelector(".video-serial")?.textContent.trim() == serial);

  if (block) {
    block.scrollIntoView({ behavior: "smooth", block: "center" });
    block.style.boxShadow = "0 0 10px 3px yellow";
    setTimeout(() => block.style.boxShadow = "", 2000);
  }
}
  

</script>
</body>
</html>
