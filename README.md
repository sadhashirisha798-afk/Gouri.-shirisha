
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SYNAPSE AI | Student OS</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#080817;color:#f4f4ff;font-family:Arial,sans-serif}
header{height:65px;background:#11112a;border-bottom:1px solid #4545a5;display:flex;align-items:center;justify-content:space-between;padding:0 18px;position:sticky;top:0;z-index:10}
.logo{font-size:21px;font-weight:bold;color:#8d83ff}
.logo span{color:#35d9ff}
button{background:linear-gradient(100deg,#6655ff,#168bff);border:0;color:white;padding:11px 15px;border-radius:9px;cursor:pointer;margin:4px}
button:hover{filter:brightness(1.2)}
nav{display:none;position:absolute;right:12px;top:58px;background:#171735;border:1px solid #655bff;border-radius:12px;padding:10px;width:210px;max-height:75vh;overflow:auto}
nav button{display:block;width:100%;text-align:left;background:#25234c}
main{max-width:1050px;margin:auto;padding:16px}
.hero{padding:28px 20px;border-radius:20px;background:linear-gradient(120deg,#29205e,#102b53,#10102a);border:1px solid #6157dc}
.hero h1{font-size:32px;color:#7be7ff;margin:8px 0}
.tag{color:#b9b3ff;letter-spacing:2px;font-size:12px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(145px,1fr));gap:13px;margin:16px 0}
.card,.panel{background:#14142c;border:1px solid #34346b;border-radius:15px;padding:16px}
.card{cursor:pointer;min-height:120px;transition:.2s}
.card:hover{transform:translateY(-4px);border-color:#58dfff}
.card h3{color:#8fddff}
h2{color:#9c91ff}
h3{margin-top:8px}
.page{display:none}
.page.active{display:block}
input,textarea,select{width:100%;padding:12px;margin:7px 0;background:#09091c;color:white;border:1px solid #494980;border-radius:9px}
textarea{min-height:95px}
.muted{color:#aaaac8;font-size:13px}
.output{background:#09091c;border-left:3px solid #36dfff;padding:13px;margin-top:10px;border-radius:7px;white-space:pre-wrap}
.task{padding:10px;border-bottom:1px solid #39395f}
.stat{font-size:25px;color:#50dfff;font-weight:bold}
footer{text-align:center;padding:25px;color:#77779d}
</style>
</head>
<body>
<header>
 <div class="logo">SYNAPSE <span>AI ✦</span></div>
 <button onclick="menu()">☰ MENU</button>
 <nav id="nav">
  <button onclick="show('home')">🏠 Dashboard</button>
  <button onclick="show('profile')">👤 Profile</button>
  <button onclick="show('study')">📚 Study Hub</button>
  <button onclick="show('planner')">📝 Study Planner</button>
  <button onclick="show('paper')">📄 Paper Analyser</button>
  <button onclick="show('assistant')">🤖 AI Assistant</button>
  <button onclick="show('quiz')">🧠 Quiz Arena</button>
  <button onclick="show('attendance')">📊 Attendance</button>
  <button onclick="show('focus')">⏱️ Focus Room</button>
  <button onclick="show('career')">🚀 Career Lab</button>
 </nav>
</header>

<main>
<section id="home" class="page active">
 <div class="hero">
  <div class="tag">NEXT GENERATION STUDENT PLATFORM</div>
  <h1>Think. Learn. Achieve.</h1>
  <p>Welcome to your intelligent academic command center.</p>
  <p class="muted">Plan your semester, practise questions and build your future.</p>
  <button onclick="show('study')">Explore Study Hub →</button>
 </div>
 <h2>YOUR WORKSPACE</h2>
 <div class="grid">
  <div class="card" onclick="show('study')">📚<h3>Study Hub</h3><p class="muted">Subjects and exam questions</p></div>
  <div class="card" onclick="show('planner')">📝<h3>Smart Planner</h3><p class="muted">Organise daily study goals</p></div>
  <div class="card" onclick="show('paper')">📄<h3>Paper Analysis</h3><p class="muted">Find repeated keywords</p></div>
  <div class="card" onclick="show('assistant')">🤖<h3>AI Assistant</h3><p class="muted">Ask study questions</p></div>
  <div class="card" onclick="show('quiz')">🧠<h3>Quiz Arena</h3><p class="muted">Test your knowledge</p></div>
  <div class="card" onclick="show('attendance')">📊<h3>Attendance</h3><p class="muted">Calculate percentage</p></div>
  <div class="card" onclick="show('focus')">⏱️<h3>Focus Room</h3><p class="muted">Pomodoro timer</p></div>
  <div class="card" onclick="show('career')">🚀<h3>Career Lab</h3><p class="muted">Explore your future</p></div>
 </div>
 <div class="panel">
  <h3>✨ Today's Motivation</h3>
  <p id="quote">Small progress every day creates big results.</p>
  <button onclick="newQuote()">New Motivation</button>
 </div>
</section>

<section id="profile" class="page">
 <h2>👤 Student Profile</h2>
 <div class="panel">
  <label>Student Name</label><input id="pname" placeholder="Enter your name">
  <label>Branch</label><input id="branch" placeholder="Example: AI & DS">
  <label>College</label><input id="college" placeholder="Enter college name">
  <label>Roll Number</label><input id="roll" placeholder="Enter roll number">
  <button onclick="saveProfile()">Save Profile</button>
  <div id="profileOut" class="output">Your profile will appear here.</div>
 </div>
</section>

<section id="study" class="page">
 <h2>📚 Study Hub</h2>
 <div class="panel">
  <h3>Choose Subject</h3>
  <select id="subject">
   <option>Data Structures</option><option>Design and Analysis of Algorithms</option>
   <option>Database Management Systems</option><option>Operating Systems</option>
   <option>Computer Networks</option><option>Artificial Intelligence</option>
   <option>Web Programming</option>
  </select>
  <h3>Choose Marks</h3>
  <select id="marks">
   <option>2 Marks</option><option>5 Marks</option>
   <option>10 Marks</option><option>15 Marks</option>
  </select>
  <button onclick="questions()">Show Questions</button>
  <div id="questionOut" class="output">Select a subject and marks to view sample questions.</div>
  <p class="muted">Sample practice bank. Check your syllabus and previous papers for your university's exact questions.</p>
 </div>
</section>

<section id="planner" class="page">
 <h2>📝 Smart Study Planner</h2>
 <div class="panel">
  <input id="taskInput" placeholder="Enter your study task">
  <input id="taskDate" type="date">
  <button onclick="addTask()">+ Add Study Goal</button>
  <div id="tasks"></div>
 </div>
</section>

<section id="paper" class="page">
 <h2>📄 Previous Paper Analyser</h2>
 <div class="panel">
  <p class="muted">Paste the text copied from a question paper below.</p>
  <textarea id="paperText" placeholder="Paste your question paper text here..."></textarea>
  <button onclick="analyse()">Analyse Paper</button>
  <div id="analysisOut" class="output">Analysis results will appear here.</div>
 </div>
</section>

<section id="assistant" class="page">
 <h2>🤖 Study Assistant</h2>
 <div class="panel">
  <p class="muted">Ask a question about exams, study planning or programming.</p>
  <textarea id="ask" placeholder="Example: Explain stack in simple words"></textarea>
  <button onclick="askAI()">Ask Assistant</button>
  <div id="answer" class="output">Your study assistant is ready.</div>
  <p class="muted">This is an offline demo assistant using preset responses, not a live AI model.</p>
 </div>
</section>

<section id="quiz" class="page">
 <h2>🧠 Quiz Arena</h2>
 <div class="panel">
  <h3 id="quizQuestion">What does CPU stand for?</h3>
  <div id="options"></div>
  <div id="quizResult" class="output">Choose your answer.</div>
  <button onclick="nextQuiz()">Next Question →</button>
 </div>
</section>

<section id="attendance" class="page">
 <h2>📊 Attendance Calculator</h2>
 <div class="panel">
  <label>Total Classes</label><input type="number" id="total" placeholder="Example: 100">
  <label>Classes Attended</label><input type="number" id="attended" placeholder="Example: 85">
  <button onclick="calculate()">Calculate Attendance</button>
  <div id="attendanceOut" class="output"></div>
 </div>
</section>

<section id="focus" class="page">
 <h2>⏱️ Focus Room</h2>
 <div class="panel" style="text-align:center">
  <p class="muted">POMODORO STUDY SESSION</p>
  <div class="stat" id="clock" style="font-size:55px">25:00</div>
  <button onclick="startTimer()">Start</button>
  <button onclick="pauseTimer()">Pause</button>
  <button onclick="resetTimer()">Reset</button>
  <p class="muted">Study for 25 minutes, then take a short break.</p>
 </div>
</section>

<section id="career" class="page">
 <h2>🚀 Career Lab</h2>
 <div class="panel">
  <h3>AI & Data Science Roadmap</h3>
  <div class="task">01 — Python programming fundamentals</div>
  <div class="task">02 — Mathematics and statistics</div>
  <div class="task">03 — SQL and database concepts</div>
  <div class="task">04 — Data analysis with Pandas and NumPy</div>
  <div class="task">05 — Machine learning fundamentals</div>
  <div class="task">06 — Build real-world projects</div>
  <div class="task">07 — GitHub, resume and interview preparation</div>
  <h3>Career Paths</h3>
  <p>Data Analyst · AI Engineer · Machine Learning Engineer · Python Developer · Data Scientist</p>
 </div>
</section>
</main>
<footer>SYNAPSE AI GENESIS · Student Innovation Platform</footer>

<script>
function menu(){
 const n=document.getElementById("nav");
 n.style.display=n.style.display==="block"?"none":"block";
}
function show(id){
 document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));
 document.getElementById(id).classList.add("active");
 document.getElementById("nav").style.display="none";
 window.scrollTo(0,0);
}
function saveProfile(){
 let data={
 name:document.getElementById("pname").value,
 branch:document.getElementById("branch").value,
 college:document.getElementById("college").value,
 roll:document.getElementById("roll").value
 };
 localStorage.setItem("synapseProfile",JSON.stringify(data));
 document.getElementById("profileOut").textContent=
 "Name: "+data.name+"\nBranch: "+data.branch+"\nCollege: "+data.college+"\nRoll Number: "+data.roll;
}
function loadProfile(){
 let d=JSON.parse(localStorage.getItem("synapseProfile")||"null");
 if(!d)return;
 pname.value=d.name;branch.value=d.branch;college.value=d.college;roll.value=d.roll;
 profileOut.textContent="Name: "+d.name+"\nBranch: "+d.branch+"\nCollege: "+d.college+"\nRoll Number: "+d.roll;
}
const bank={
 "Data Structures":{
 "2 Marks":["Define data structure.","What is a stack?","Define queue.","What is a linked list?"],
 "5 Marks":["Explain stack operations with an example.","Explain types of linked lists.","Differentiate stack and queue."],
 "10 Marks":["Explain stack implementation using arrays.","Explain queue operations and applications."],
 "15 Marks":["Explain linked lists, their types and operations with diagrams."]
 },
 "Design and Analysis of Algorithms":{
 "2 Marks":["Define algorithm.","What is time complexity?","Define greedy method."],
 "5 Marks":["Explain asymptotic notations.","Explain binary search."],
 "10 Marks":["Explain merge sort with an example.","Explain quick sort and its complexity."],
 "15 Marks":["Explain the greedy method with a suitable example."]
 },
 "Database Management Systems":{
 "2 Marks":["Define DBMS.","What is a primary key?","Define normalization."],
 "5 Marks":["Explain DBMS advantages.","Explain different types of keys."],
 "10 Marks":["Explain database normalization.","Explain the ER model with an example."],
 "15 Marks":["Explain DBMS architecture and its components."]
 },
 "Operating Systems":{
 "2 Marks":["Define operating system.","What is a process?","Define deadlock."],
 "5 Marks":["Explain process states.","Differentiate process and thread."],
 "10 Marks":["Explain CPU scheduling algorithms.","Explain deadlock conditions."],
 "15 Marks":["Explain process management and CPU scheduling."]
 },
 "Computer Networks":{
 "2 Marks":["Define network protocol.","What is TCP?","What is an IP address?"],
 "5 Marks":["Differentiate TCP and UDP.","Explain the OSI model."],
 "10 Marks":["Explain HTTP protocol.","Explain TCP connection establishment."],
 "15 Marks":["Explain the OSI reference model with a neat diagram."]
 },
 "Artificial Intelligence":{
 "2 Marks":["Define artificial intelligence.","What is an intelligent agent?","Define heuristic."],
 "5 Marks":["Explain types of agents.","Explain knowledge representation."],
 "10 Marks":["Explain problem solving by search.","Explain Bayesian networks."],
 "15 Marks":["Explain intelligent agents and their architecture."]
 },
 "Web Programming":{
 "2 Marks":["Define HTML.","What is CSS?","Define servlet."],
 "5 Marks":["Explain HTML forms.","Explain servlet life cycle."],
 "10 Marks":["Explain JavaScript events.","Explain servlet architecture."],
 "15 Marks":["Explain the servlet life cycle with a neat diagram."]
 }
};
function questions(){
 let s=subject.value,m=marks.value;
 questionOut.textContent=(bank[s]&&bank[s][m]||["No sample questions available."]).map((q,i)=>(i+1)+". "+q).join("\n");
}
let tasks=JSON.parse(localStorage.getItem("synapseTasks")||"[]");
function renderTasks(){
 tasksDiv=document.getElementById("tasks");
 tasksDiv.innerHTML="";
 tasks.forEach((t,i)=>{
 let d=document.createElement("div");d.className="task";
 let b=document.createElement("button");b.textContent=t.done?"Completed":"Mark Done";
 b.onclick=()=>{tasks[i].done=!tasks[i].done;saveTasks()};
 d.append(document.createTextNode(t.text+" | "+t.date+" "),b);
 tasksDiv.appendChild(d);
 });
}
function saveTasks(){localStorage.setItem("synapseTasks",JSON.stringify(tasks));renderTasks()}
function addTask(){
 let v=taskInput.value.trim();if(!v){alert("Enter a task");return}
 tasks.push({text:v,date:taskDate.value||"No date",done:false});
 taskInput.value="";saveTasks();
}
function analyse(){
 let txt=paperText.value.toLowerCase();
 if(!txt.trim()){analysisOut.textContent="Please paste question paper text first.";return}
 let words=txt.match(/[a-z]{4,}/g)||[];
 let counts={};
 words.forEach(w=>counts[w]=(counts[w]||0)+1);
 let sorted=Object.entries(counts).sort((a,b)=>b[1]-a[1]).slice(0,12);
 analysisOut.textContent="Total words: "+words.length+"\n\nFrequently repeated words:\n"+
 sorted.map(x=>x[0]+" — "+x[1]+" times").join("\n")+
 "\n\nUse these keywords to guide revision. Repeated words are not guaranteed exam questions.";
}
function askAI(){
 let q=ask.value.toLowerCase(),a="Try breaking the topic into a definition, explanation, example and advantages. Revise it and practise writing the answer.";
 if(q.includes("stack"))a="A stack is a linear data structure that follows LIFO (Last In, First Out). Main operations are PUSH, POP and PEEK. Example: a stack of plates.";
 else if(q.includes("exam"))a="Exam strategy:\n1. Check your syllabus.\n2. Prepare important questions unit-wise.\n3. Practise previous papers.\n4. Revise definitions and diagrams.\n5. Write answers within the time limit.";
 else if(q.includes("python"))a="Start Python with variables, data types, conditions, loops, functions, lists, dictionaries and file handling. Practise small programs daily.";
 else if(q.includes("time table")||q.includes("timetable"))a="Create a daily timetable with study blocks, short breaks and revision time. Start with your most difficult subject.";
 else if(q.includes("algorithm"))a="An algorithm is a finite sequence of clear steps used to solve a problem. Its important properties include input, output, definiteness and finiteness.";
 answer.textContent=a;
}
const quizData=[
 {q:"What does CPU stand for?",o:["Central Processing Unit","Computer Personal Unit","Central Program Utility"],a:0},
 {q:"Which data structure follows LIFO?",o:["Queue","Stack","Tree"],a:1},
 {q:"Which language is popular for AI?",o:["Python","HTML","CSS"],a:0},
 {q:"Which protocol is connection-oriented?",o:["UDP","TCP","HTTP"],a:1}
];
let qi=0,score=0,answered=false;
function renderQuiz(){
 let q=quizData[qi];quizQuestion.textContent=(qi+1)+". "+q.q;
 options.innerHTML="";answered=false;quizResult.textContent="Choose your answer.";
 q.o.forEach((v,i)=>{
 let b=document.createElement("button");b.textContent=v;b.style.display="block";b.style.width="100%";
 b.onclick=()=>{if(answered)return;answered=true;if(i===q.a){score++;quizResult.textContent="Correct! 🎉";}else{quizResult.textContent="Not quite. Correct answer: "+q.o[q.a];}};
 options.appendChild(b);
 });
}
function nextQuiz(){qi++;if(qi>=quizData.length){quizQuestion.textContent="Quiz completed!";options.innerHTML="";quizResult.textContent="Your score: "+score+" / "+quizData.length+" — refresh to try again.";return}renderQuiz()}
function calculate(){
 let t=Number(total.value),a=Number(attended.value);
 if(t<=0||a<0||a>t){attendanceOut.textContent="Enter valid class numbers.";return}
 let p=a/t*100;
 attendanceOut.textContent="Attendance: "+p.toFixed(2)+"%\n"+(p>=75?"You have reached 75%.":"You are below 75%. Check your college attendance rules.");
}
let seconds=1500,timer=null;
function updateClock(){clock.textContent=String(Math.floor(seconds/60)).padStart(2,"0")+":"+String(seconds%60).padStart(2,"0")}
function startTimer(){if(timer)return;timer=setInterval(()=>{if(seconds>0){seconds--;updateClock()}else{pauseTimer();alert("Focus session completed! Take a short break.")}},1000)}
function pauseTimer(){clearInterval(timer);timer=null}
function resetTimer(){pauseTimer();seconds=1500;updateClock()}
function newQuote(){
 let q=["One chapter at a time. One step closer to success.","Consistency is more powerful than motivation.","Your future is built by what you study today.","Believe in your progress and keep learning."];
 quote.textContent=q[Math.floor(Math.random()*q.length)];
}
loadProfile();renderTasks();renderQuiz();updateClock();
</script>
</body>
</html>

