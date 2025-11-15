<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Md. Julfiqar Islam</title>
<style>
:root {
    --primary: #4a90e2;
    --bg-light: #f4f4f9;
    --bg-dark: #121212;
    --text-light: #333;
    --text-dark: #f4f4f9;
}
body {
    font-family: Arial, sans-serif;
    margin:0; padding:0;
    background-color: var(--bg-light);
    color: var(--text-light);
    transition: background 0.3s, color 0.3s;
    scroll-behavior: smooth;
}
/* Navigation Menu */
nav {
    position: fixed;
    top:0; left:0; width:100%;
    background-color: rgba(74,144,226,0.95);
    display:flex;
    justify-content:center;
    z-index:1000;
    box-shadow: 0 2px 8px rgba(0,0,0,0.2);
}
nav a {
    color:white;
    text-decoration:none;
    padding:15px 20px;
    display:inline-block;
    font-weight:bold;
    transition: background 0.3s;
}
nav a:hover { background-color: rgba(255,255,255,0.2); border-radius:5px; }

header {
    background-color: var(--primary);
    color: white;
    text-align: center;
    padding: 100px 20px 40px 20px;
    position: relative;
}
header h1 { margin: 10px 0; font-size: 2.8em; }
header p { font-size: 1.2em; margin: 5px 0 20px 0; }

.upload-btn, .cv-btn, .social-btn {
    display: inline-block;
    padding: 10px 20px;
    background-color: #fff;
    color: var(--primary);
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-weight: bold;
    margin: 5px 5px 5px 0;
    transition: transform 0.2s;
}
.upload-btn:hover, .cv-btn:hover, .social-btn:hover { transform: scale(1.05); }

.profile-pic {
    width:150px; height:150px;
    background-color:#fff;
    border-radius:50%;
    margin:0 auto 15px auto;
    display:flex; align-items:center; justify-content:center;
    font-weight:bold; color:#aaa;
    font-size:0.9em;
    overflow:hidden;
    transition: transform 0.3s;
}
.profile-pic img { width:100%; height:100%; object-fit:cover; display:block;}
.profile-pic:hover { transform: scale(1.05); }

.container { width:90%; max-width:1000px; margin:40px auto; }

section {
    background-color:white;
    padding: 25px;
    margin-bottom: 25px;
    border-radius: 15px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    opacity:0; transform: translateY(30px);
    animation: fadeInUp 0.8s forwards;
}
section:nth-of-type(1){animation-delay:0.2s;}
section:nth-of-type(2){animation-delay:0.4s;}
section:nth-of-type(3){animation-delay:0.6s;}
section:nth-of-type(4){animation-delay:0.8s;}
section:nth-of-type(5){animation-delay:1s;}
section:nth-of-type(6){animation-delay:1.2s;}
section:nth-of-type(7){animation-delay:1.4s;}
section:nth-of-type(8){animation-delay:1.6s;}

@keyframes fadeInUp {
    to {opacity:1; transform:translateY(0);}
}
h2 {
    border-bottom: 2px solid var(--primary);
    padding-bottom: 5px;
    margin-bottom: 15px;
    color: var(--primary);
}
ul { list-style-type:none; padding:0; }
ul li { padding:5px 0; }
.skills, .hobbies {
    display:flex; flex-wrap:wrap;
}
.skills span, .hobbies span {
    background-color: var(--primary);
    color:white;
    padding:5px 12px;
    border-radius:25px;
    margin:5px;
    font-size:0.95em;
    transition: transform 0.2s;
    cursor: default;
}
.skills span:hover, .hobbies span:hover { transform: scale(1.1); }

/* Family Album */
.album-grid {
    display:grid;
    grid-template-columns: repeat(auto-fill,minmax(150px,1fr));
    gap:15px;
    margin-top:15px;
}
.album-grid img {
    width:100%;
    height:150px;
    object-fit:cover;
    border-radius:10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.2);
    transition: transform 0.3s;
}
.album-grid img:hover { transform: scale(1.05); }

/* Dark Mode */
.dark-mode {
    background-color: var(--bg-dark);
    color: var(--text-dark);
}
.dark-mode section { background-color:#1e1e1e; box-shadow:0 4px 15px rgba(255,255,255,0.05);}
.dark-mode h2 { color: var(--primary); }
.dark-mode .skills span, .dark-mode .hobbies span { background-color: var(--primary); }

.toggle-btn {
    position: fixed;
    top:20px; right:20px;
    background-color: var(--primary);
    color:white;
    border:none;
    padding:10px 15px;
    border-radius:10px;
    cursor:pointer;
    font-weight:bold;
    z-index:1000;
}
@media(max-width:600px){
    header h1{font-size:2em;}
    header p{font-size:1em;}
    nav a{padding:10px 12px; font-size:0.9em;}
}
</style>
</head>
<body>

<nav>
    <a href="#home">Home</a>
    <a href="#personal">Personal</a>
    <a href="#education">Education</a>
    <a href="#skills">Skills</a>
    <a href="#hobbies">Hobbies</a>
    <a href="#languages">Languages</a>
    <a href="#contact">Contact</a>
    <a href="#family-album">Family Album</a>
</nav>

<button class="toggle-btn" onclick="toggleDarkMode()">Dark Mode</button>

<header id="home">
    <div>
        <div class="profile-pic" id="profilePic">Upload Photo</div>
        <h1>Md. Julfiqar Islam</h1>
        <p>“Dedicated to Growth | Passionate About Excellence | Lifelong Learner”</p>
        <input type="file" id="fileInput" accept="image/*" style="display:none;">
        <button class="upload-btn" onclick="document.getElementById('fileInput').click();">Upload Photo</button>
        <a href="YOUR_CV_FILE.pdf" download class="cv-btn">Download CV</a>
    </div>
</header>

<div class="container">
    <section id="personal">
        <h2>Personal Details</h2>
        <ul>
            <li><strong>জন্মতারিখ:</strong> ২০/০৯/২০০১</li>
            <li><strong>ঠিকানা:</strong> গ্রাম: শহরকসবা, ইউনিয়ন: ১৯ নং তেওয়ারিগঞ্জ, থানা: লক্ষীপুর, উপজেলা: সদর লক্ষীপুর, জেলা: লক্ষীপুর, বিভাগ: চট্টগ্রাম, বাংলাদেশ</li>
            <li><strong>মায়ের নাম:</strong> খালেদা আক্তার</li>
            <li><strong>বাবার নাম:</strong> জাকির হোসাইন</li>
            <li><strong>ছোট ভাই:</strong> সিফাত হোসেন</li>
            <li><strong>স্ত্রী:</strong> অনামিকা ইসলাম</li>
            <li><strong>সন্তান:</strong> ফারিস (১.৫ বছর)</li>
            <li><strong>বৈবাহিক অবস্থা:</strong> বিবাহিত</li>
        </ul>
        <div>
            <a href="https://wa.me/8801400719679" target="_blank" class="social-btn">WhatsApp Chat</a>
            <a href="mailto:krifat550@gmail.com" class="social-btn">Send Email</a>
            <a href="https://www.facebook.com/" target="_blank" class="social-btn">Facebook</a>
            <a href="https://www.linkedin.com/" target="_blank" class="social-btn">LinkedIn</a>
            <a href="https://www.instagram.com/" target="_blank" class="social-btn">Instagram</a>
        </div>
    </section>

    <section id="education">
        <h2>Education</h2>
        <ul>
            <li>প্রাথমিক: হোসেনপুর সরকারি প্রাথমিক বিদ্যালয়</li>
            <li>মাধ্যমিক: হোসেনপুর উচ্চ বিদ্যালয়</li>
            <li>কলেজ: লক্ষীপুর সরকারি কলেজ</li>
            <li>বিশ্ববিদ্যালয়: লক্ষীপুর সরকারি কলেজ এবং বিশ্ববিদ্যালয়</li>
        </ul>
    </section>

    <section id="skills">
        <h2>Skills</h2>
        <div class="skills">
            <span>কাস্টমার সার্ভিস</span>
            <span>কম্পিউটার চালনায় দক্ষ</span>
            <span>লিডারশিপ</span>
            <span>প্রফেশনাল টাইপিং স্পিড</span>
        </div>
    </section>

    <section id="hobbies">
        <h2>Hobbies</h2>
        <div class="hobbies">
            <span>Sports</span>
            <span>Music</span>
        </div>
    </section>

    <section id="languages">
        <h2>Languages</h2>
        <ul>
            <li>Bangla</li>
            <li>English</li>
            <li>Hindi</li>
        </ul>
    </section>

    <section id="contact">
        <h2>Contact</h2>
        <ul>
            <li>ফোন/WhatsApp: 01400719679</li>
            <li>ইমেইল: krifat550@gmail.com</li>
        </ul>
    </section>

    <section id="family-album">
        <h2>Family Album</h2>
        <div class="album-grid" id="albumGrid"></div>
        <input type="file" id="albumInput" accept="image/*" multiple style="display:none;">
        <button class="upload-btn" onclick="document.getElementById('albumInput').click();">Upload Family Photos</button>
    </section>
</div>

<script>
function toggleDarkMode(){ document.body.classList.toggle('dark-mode'); }

// Profile photo upload
const fileInput = document.getElementById('fileInput');
const profilePic = document.getElementById('profilePic');
fileInput.addEventListener('change', function(){
    const file = this.files[0];
    if(file){
        const reader = new FileReader();
        reader.onload = function(e){
            profilePic.innerHTML = '';
            const img = document.createElement('img');
            img.src = e.target.result;
            profilePic.appendChild(img);
        }
        reader.readAsDataURL(file);
    }
});

// Family Album Upload
const albumInput = document.getElementById('albumInput');
const albumGrid = document.getElementById('albumGrid');
albumInput.addEventListener('change', function(){
    const files = Array.from(this.files);
    files.forEach(file => {
        const reader = new FileReader();
        reader.onload = function(e){
            const img = document.createElement('img');
            img.src = e.target.result;
            albumGrid.appendChild(img);
        }
        reader.readAsDataURL(file);
    });
});
</script>

</body>
</html>
