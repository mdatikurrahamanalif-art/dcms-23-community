
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DCMS 23 Community</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:#07111f;color:#fff}
header{padding:22px 16px;background:#101e32;text-align:center;border-bottom:1px solid #263952}
header h1{margin:0;color:#65e6c4;font-size:27px}
header p{color:#bdc9d9;margin-bottom:0}
main{max-width:850px;margin:auto;padding:25px 16px}
.hero{text-align:center;padding:35px 15px;background:linear-gradient(135deg,#153b50,#182746);border-radius:18px}
.hero h2{font-size:29px;margin:0 0 12px}
.hero p{color:#d1deea;line-height:1.6}
button{background:#65e6c4;color:#07111f;border:0;padding:12px 18px;border-radius:9px;font-weight:bold;cursor:pointer}
section{background:#101e32;margin-top:22px;padding:22px;border-radius:15px}
h3{margin-top:0;color:#65e6c4}
input,select{width:100%;padding:12px;margin:7px 0 13px;border:1px solid #34465d;border-radius:8px;background:#07111f;color:#fff}
label{font-size:14px;color:#d1deea}
#message{color:#65e6c4;overflow-wrap:anywhere}
footer{text-align:center;padding:25px;color:#a8b6c8}
</style>
</head>
<body>
<header>
<h1>DCMS 23 Community</h1>
<p>Dhanbari Collegiate Model School</p>
</header>

<main>
<div class="hero">
<h2>Welcome to DCMS 23 🎓</h2>
<p>একসাথে শিখি, একসাথে এগিয়ে যাই।<br>
Connect with your classmates and build our community.</p>
<button onclick="document.getElementById('profile').scrollIntoView({behavior:'smooth'})">Create Student Profile</button>
</div>

<section id="profile">
<h3>👨‍🎓 Student Profile</h3>
<p>তোমার শিক্ষার্থীর তথ্য এখানে লিখো।</p>
<form id="profileForm">
<label>Full Name</label>
<input id="name" type="text" placeholder="তোমার নাম" required>
<label>Roll Number</label>
<input id="roll" type="text" placeholder="তোমার রোল" required>
<label>Department</label>
<select id="department" required>
<option value="">বিভাগ নির্বাচন করো</option>
<option>Science</option>
<option>Business Studies</option>
<option>Humanities</option>
</select>
<label>Photo URL (ঐচ্ছিক)</label>
<input id="photo" type="url" placeholder="ছবির লিংক">
<label>Facebook Profile URL (ঐচ্ছিক)</label>
<input id="facebook" type="url" placeholder="https://www.facebook.com/...">
<button type="submit">Preview Profile</button>
</form>
<div id="message" aria-live="polite"></div>
</section>

<section id="directory">
<h3>🌐 Student Profile Preview</h3>
<div id="preview">তোমার তথ্য পূরণ করে Preview Profile চাপো।</div>
</section>

<section>
<h3>🤝 Join Our Community</h3>
<p>DCMS 23-এর সঙ্গে যুক্ত থাকো এবং বন্ধুদের সঙ্গে যোগাযোগ রাখো।</p>
<button onclick="document.getElementById('profile').scrollIntoView({behavior:'smooth'})">Join Now</button>
</section>
</main>

<footer>© 2026 DCMS 23 Community | Made for Students ❤️</footer>

<script>
document.getElementById('profileForm').addEventListener('submit',function(event){
event.preventDefault();
const name=document.getElementById('name').value.trim();
const roll=document.getElementById('roll').value.trim();
const department=document.getElementById('department').value;
const photo=document.getElementById('photo').value.trim();
const facebook=document.getElementById('facebook').value.trim();

const preview=document.getElementById('preview');
preview.replaceChildren();

if(photo){
try{
const url=new URL(photo);
if(url.protocol==='https:'){
const img=document.createElement('img');
img.src=url.href;
img.alt='Student photo';
img.style.cssText='width:100px;height:100px;object-fit:cover;border-radius:50%;display:block;margin-bottom:12px';
preview.appendChild(img);
}
}catch(e){}
}

const details=document.createElement('p');
details.textContent='Name: '+name+' | Roll: '+roll+' | Department: '+department;
preview.appendChild(details);

if(facebook){
try{
const url=new URL(facebook);
if(url.protocol==='https:' && (url.hostname==='facebook.com'||url.hostname.endsWith('.facebook.com'))){
const link=document.createElement('a');
link.href=url.href;
link.target='_blank';
link.rel='noopener noreferrer';
link.textContent='Facebook Profile';
link.style.color='#65e6c4';
preview.appendChild(link);
}
}catch(e){}
}

document.getElementById('message').textContent='Profile preview তৈরি হয়েছে! মনে রেখো: এই ভার্সনে তথ্য অনলাইনে সেভ হয় না।';
});
</script>
</body>
</html>
