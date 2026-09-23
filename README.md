<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>RK University Student Portal</title>

<style>

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    font-family:Arial,Helvetica,sans-serif;
    background:#f4f6fb;
    color:#222;
    transition:.3s;
}

body.dark{
    background:#101522;
    color:white;
}

button{
    cursor:pointer;
    border:none;
}

.header{
    background:linear-gradient(135deg,#760000,#c62828);
    color:white;
    padding:25px 15px;
    text-align:center;
}

.logo{
    width:70px;
    height:70px;
    line-height:70px;
    margin:auto;
    border-radius:50%;
    background:white;
    color:#9b0000;
    font-size:32px;
    font-weight:bold;
}

.header h1{
    margin-top:10px;
    font-size:30px;
}

.header p{
    margin-top:6px;
}

.nav{
    background:#8e0000;
    padding:10px;
    display:flex;
    justify-content:center;
    gap:8px;
    flex-wrap:wrap;
}

.nav button{
    background:white;
    color:#8e0000;
    padding:10px 14px;
    border-radius:8px;
    font-weight:bold;
}

.container{
    width:95%;
    max-width:1100px;
    margin:auto;
    padding:25px 0;
}

.clock{
    text-align:center;
    font-weight:bold;
    margin-bottom:20px;
}

.welcome,
.card{
    background:white;
    padding:20px;
    border-radius:18px;
    margin-bottom:18px;
    box-shadow:0 5px 20px rgba(0,0,0,.08);
}

.dark .welcome,
.dark .card{
    background:#1c2535;
}

.welcome h2,
.card h3{
    color:#a50000;
    margin-bottom:12px;
}

.dark .welcome h2,
.dark .card h3{
    color:#ff6b6b;
}

.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
    gap:18px;
}

input,
select{
    width:100%;
    padding:12px;
    margin:6px 0;
    border:1px solid #ccc;
    border-radius:8px;
}

.btn{
    background:#a50000;
    color:white;
    padding:10px 15px;
    border-radius:8px;
    font-weight:bold;
    margin:4px;
}

.btn:hover{
    background:#700000;
}

.big{
    font-size:40px;
    text-align:center;
    margin:15px;
}

.progress{
    height:15px;
    background:#ddd;
    border-radius:20px;
    overflow:hidden;
}

.progress-bar{
    height:100%;
    width:0%;
    background:#c62828;
}

.timer{
    text-align:center;
}

.timer-display{
    font-size:45px;
    font-weight:bold;
    margin:15px;
}

.task-list li{
    list-style:none;
    background:#eee;
    color:#222;
    padding:10px;
    margin:7px 0;
    border-radius:8px;
    display:flex;
    justify-content:space-between;
}

.dark .task-list li{
    background:#293449;
    color:white;
}

.delete,
.remove{
    background:#e53935;
    color:white;
    padding:6px 9px;
    border-radius:6px;
}

.friend{
    background:#eee;
    color:#222;
    padding:12px;
    margin:8px 0;
    border-radius:10px;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

.dark .friend{
    background:#293449;
    color:white;
}

table{
    width:100%;
    border-collapse:collapse;
}

th,
td{
    border:1px solid #ddd;
    padding:10px;
    text-align:center;
}

th{
    background:#a50000;
    color:white;
}

.notice{
    padding:12px;
    background:#fff3cd;
    color:#664d03;
    border-radius:8px;
    margin:8px 0;
}

.option{
    display:block;
    width:100%;
    padding:11px;
    margin:7px 0;
    border:1px solid #ccc;
    border-radius:8px;
    text-align:left;
}

footer{
    background:#760000;
    color:white;
    text-align:center;
    padding:25px 10px;
}

footer h3{
    margin:8px;
}

.account-box{
    max-width:500px;
    margin:40px auto;
}

.profile{
    padding:15px;
    background:#f1f1f1;
    color:#222;
    border-radius:10px;
    margin-top:10px;
}

.dark .profile{
    background:#293449;
    color:white;
}

.success{
    color:green;
    font-weight:bold;
}

.error{
    color:#e53935;
    font-weight:bold;
}

.setting{
    padding:15px;
    background:#eee;
    color:#222;
    margin:10px 0;
    border-radius:10px;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

.dark .setting{
    background:#293449;
    color:white;
}

@media(max-width:600px){

    .header h1{
        font-size:23px;
    }

    .nav button{
        font-size:12px;
        padding:8px 10px;
    }

    .container{
        width:92%;
    }

    .timer-display{
        font-size:38px;
    }

    th,
    td{
        font-size:12px;
        padding:7px;
    }

}



/* ================= ADMIN SYSTEM ================= */
.admin-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:18px}
.admin-stat{background:#f4f4f4;color:#222;padding:18px;border-radius:12px;text-align:center}
.dark .admin-stat{background:#293449;color:white}
.admin-stat b{font-size:30px;display:block;color:#a50000}
.dark .admin-stat b{color:#ff6b6b}
.admin-table{overflow-x:auto}
.admin-actions{display:flex;gap:5px;flex-wrap:wrap;justify-content:center}
.admin-banned{opacity:.65}
.admin-badge{display:inline-block;padding:4px 8px;border-radius:15px;background:#e53935;color:#fff;font-size:11px}
.admin-badge.ok{background:#4caf50}
.admin-danger{background:#b71c1c!important}
.admin-warning{background:#ef6c00!important}
.admin-success{background:#2e7d32!important}

</style>

</head>

<body>


<header class="header">

    <div class="logo" id="universityLogo"><img id="universityLogoImg" src="https://lookaside.fbsbx.com/lookaside/crawler/instagram/rkuniversity/profile_pic.jpg" alt="RK University Logo" onerror="this.style.display='none';this.parentElement.innerHTML='RK';"></div>

    <h1 id="universityName">RK UNIVERSITY</h1>

    <p>Student Digital Portal</p>

</header>


<nav class="nav" id="navigation">

    <button onclick="home()">🏠 Home</button>

    <button onclick="notice()">📢 Notices</button>

    <button onclick="friends()">👥 Friends</button>

    <button onclick="about()">🎓 About</button>

    <button onclick="settings()">⚙️ Settings</button>

    <button onclick="logout()">🚪 Logout</button>

    <button onclick="adminLoginPage()">🛡️ Admin</button>

</nav>


<main class="container" id="mainContent"></main>


<footer>

    <p>© 2026 RK University Student Portal</p>

    <p>Educational Demonstration Project</p>

    <h3>💻 MOHAMMAD ASFAK</h3>

    <p>Student Developer</p>

</footer>


<script>

/* =========================
   ACCOUNT SYSTEM
========================= */

var currentUser =
    localStorage.getItem("currentUser");


function getUsers(){

    return JSON.parse(
        localStorage.getItem("users") || "{}"
    );

}


function saveUsers(users){

    localStorage.setItem(
        "users",
        JSON.stringify(users)
    );

}


/* =========================
   SIGN UP PAGE
========================= */

function signup(){

    document.getElementById("mainContent").innerHTML = `

        <div class="card account-box">

            <h2>📝 Create Student Account</h2>

            <br>

            <input
                id="signupName"
                placeholder="Full Name"
            >

            <input
                id="signupID"
                placeholder="Student ID"
            >

            <input
                id="signupEmail"
                type="email"
                placeholder="Email Address"
            >

            <input
                id="signupPassword"
                type="password"
                placeholder="Create Password"
            >

            <button
                class="btn"
                onclick="createAccount()">
                🚀 Create Account
            </button>

            <button
                class="btn"
                onclick="loginPage()">
                🔑 Already have an account?
            </button>

            <p id="signupMessage"></p>

        </div>

    `;

}


/* CREATE ACCOUNT */

function createAccount(){

    var name =
        document.getElementById("signupName").value.trim();

    var studentID =
        document.getElementById("signupID").value.trim();

    var email =
        document.getElementById("signupEmail").value.trim();

    var password =
        document.getElementById("signupPassword").value;


    if(
        name === "" ||
        studentID === "" ||
        email === "" ||
        password === ""
    ){

        document.getElementById(
            "signupMessage"
        ).innerHTML =
            "<p class='error'>Please fill all fields.</p>";

        return;

    }


    var users = getUsers();


    if(users[email]){

        document.getElementById(
            "signupMessage"
        ).innerHTML =
            "<p class='error'>Account already exists.</p>";

        return;

    }


    users[email] = {

        name:name,

        studentID:studentID,

        email:email,

        password:password,

        friends:[],

        tasks:[]

    };


    saveUsers(users);


    alert(
        "✅ Account created successfully!"
    );


    loginPage();

}


/* =========================
   LOGIN PAGE
========================= */

function loginPage(){

    document.getElementById("mainContent").innerHTML = `

        <div class="card account-box">

            <h2>🔐 Student Login</h2>

            <br>

            <input
                id="loginEmail"
                type="email"
                placeholder="Email Address"
            >

            <input
                id="loginPassword"
                type="password"
                placeholder="Password"
            >

            <button
                class="btn"
                onclick="login()">
                🔓 Login
            </button>

            <button
                class="btn"
                onclick="signup()">
                📝 Create Account
            </button>

            <p id="loginMessage"></p>

        </div>

    `;

}


/* LOGIN */

function login(){

    var email =
        document.getElementById("loginEmail").value.trim();

    var password =
        document.getElementById("loginPassword").value;


    var users = getUsers();


    if(
        !users[email] ||
        users[email].password !== password
    ){

        document.getElementById(
            "loginMessage"
        ).innerHTML =
            "<p class='error'>❌ Invalid email or password.</p>";

        return;

    }


    localStorage.setItem(
        "currentUser",
        email
    );


    currentUser = email;


    alert("✅ Login successful!");


    home();

}


/* LOGOUT */

function logout(){

    localStorage.removeItem("currentUser");

    currentUser = null;

    loginPage();

}


/* =========================
   CHECK LOGIN
========================= */

function requireLogin(){

    if(!currentUser){

        loginPage();

        return false;

    }

    return true;

}


/* =========================
   CURRENT USER
========================= */

function userData(){

    var users = getUsers();

    return users[currentUser];

}


/* =========================
   SAVE USER
========================= */

function saveUserData(data){

    var users = getUsers();

    users[currentUser] = data;

    saveUsers(users);

}


/* =========================
   HOME
========================= */

function home(){

    if(!requireLogin()) return;


    var user = userData();


    document.getElementById("mainContent").innerHTML = `

        <div class="clock" id="clock"></div>


        <div class="welcome">

            <h2>
                Welcome, ${user.name} 👋
            </h2>

            <p>
                Welcome to your RK University
                Student Digital Portal.
            </p>

        </div>


        <div class="cards">


            <div class="card">

                <h3>👤 My Profile</h3>

                <div class="profile">

                    <p>
                        <b>Name:</b>
                        ${user.name}
                    </p>

                    <p>
                        <b>Student ID:</b>
                        ${user.studentID}
                    </p>

                    <p>
                        <b>Email:</b>
                        ${user.email}
                    </p>

                </div>

            </div>


            <div class="card">

                <h3>📊 Attendance</h3>

                <input
                    type="number"
                    id="totalClasses"
                    placeholder="Total Classes"
                >

                <input
                    type="number"
                    id="presentClasses"
                    placeholder="Classes Attended"
                >

                <button
                    class="btn"
                    onclick="calculateAttendance()">
                    Calculate
                </button>

                <div
                    class="big"
                    id="attendance">
                    0%
                </div>

                <div class="progress">

                    <div
                        class="progress-bar"
                        id="attendanceBar">
                    </div>

                </div>

                <br>

                <p id="attendanceMessage"></p>

            </div>


            <div class="card timer">

                <h3>⏱️ Study Timer</h3>

                <div
                    class="timer-display"
                    id="timer">
                    25:00
                </div>

                <button
                    class="btn"
                    onclick="startTimer()">
                    ▶ Start
                </button>

                <button
                    class="btn"
                    onclick="pauseTimer()">
                    ⏸ Pause
                </button>

                <button
                    class="btn"
                    onclick="resetTimer()">
                    🔄 Reset
                </button>

                <p id="timerStatus">
                    Ready to study
                </p>

            </div>


            <div class="card">

                <h3>📝 My Tasks</h3>

                <input
                    id="taskInput"
                    placeholder="Enter assignment or task"
                >

                <button
                    class="btn"
                    onclick="addTask()">
                    ➕ Add Task
                </button>

                <ul
                    class="task-list"
                    id="taskList">
                </ul>

            </div>


            <div class="card">

                <h3>👥 Friends</h3>

                <p>
                    You have
                    <b>
                        ${user.friends.length}
                    </b>
                    friend(s).
                </p>

                <button
                    class="btn"
                    onclick="friends()">
                    👥 Manage Friends
                </button>

            </div>


        </div>


        <div class="card">

            <h3>📅 Weekly Timetable</h3>

            <table>

                <tr>
                    <th>Day</th>
                    <th>9 AM</th>
                    <th>11 AM</th>
                    <th>2 PM</th>
                </tr>

                <tr>
                    <td>Monday</td>
                    <td>Web Development</td>
                    <td>Mathematics</td>
                    <td>Programming</td>
                </tr>

                <tr>
                    <td>Tuesday</td>
                    <td>Database</td>
                    <td>Networking</td>
                    <td>English</td>
                </tr>

                <tr>
                    <td>Wednesday</td>
                    <td>Programming</td>
                    <td>Mathematics</td>
                    <td>Web Development</td>
                </tr>

                <tr>
                    <td>Thursday</td>
                    <td>Database</td>
                    <td>Programming</td>
                    <td>Networking</td>
                </tr>

                <tr>
                    <td>Friday</td>
                    <td>English</td>
                    <td>Web Development</td>
                    <td>Project Work</td>
                </tr>

            </table>

        </div>


        <div class="card">

            <h3>🧠 Computer Quiz</h3>

            <p id="question"></p>

            <div id="options"></div>

            <p id="quizResult"></p>

            <button
                class="btn"
                onclick="nextQuestion()">
                Next Question →
            </button>

        </div>

    `;


    displayTimer();

    loadTasks();

    loadQuestion();

    startClock();

}


/* =========================
   TASKS
========================= */

function addTask(){

    var text =
        document.getElementById("taskInput")
        .value.trim();


    if(text === ""){

        alert("Enter a task first.");

        return;

    }


    var user = userData();


    user.tasks.push(text);


    saveUserData(user);


    document.getElementById(
        "taskInput"
    ).value = "";


    loadTasks();

}


function loadTasks(){

    var list =
        document.getElementById("taskList");


    if(!list) return;


    var user = userData();


    list.innerHTML = "";


    user.tasks.forEach(
        function(task,index){

            list.innerHTML += `

                <li>

                    ${task}

                    <button
                        class="delete"
                        onclick="deleteTask(${index})">
                        ❌
                    </button>

                </li>

            `;

        }
    );

}


function deleteTask(index){

    var user = userData();


    user.tasks.splice(index,1);


    saveUserData(user);


    loadTasks();

}


/* =========================
   ATTENDANCE
========================= */

function calculateAttendance(){

    var total =
        Number(
            document.getElementById("totalClasses").value
        );

    var present =
        Number(
            document.getElementById("presentClasses").value
        );


    if(
        total <= 0 ||
        present < 0 ||
        present > total
    ){

        alert("Enter valid attendance.");

        return;

    }


    var percentage =
        ((present / total) * 100)
        .toFixed(1);


    document.getElementById(
        "attendance"
    ).innerHTML =
        percentage + "%";


    document.getElementById(
        "attendanceBar"
    ).style.width =
        percentage + "%";


    document.getElementById(
        "attendanceMessage"
    ).innerHTML =
        Number(percentage) >= 75
        ? "✅ Attendance requirement met."
        : "⚠️ Attendance is below 75%.";

}


/* =========================
   TIMER
========================= */

var seconds = 1500;

var timerInterval = null;


function displayTimer(){

    var element =
        document.getElementById("timer");


    if(!element) return;


    var minutes =
        Math.floor(seconds / 60);

    var sec =
        seconds % 60;


    element.innerHTML =
        String(minutes).padStart(2,"0")
        + ":" +
        String(sec).padStart(2,"0");

}


function startTimer(){

    if(timerInterval !== null)
        return;


    var status =
        document.getElementById("timerStatus");


    if(status)
        status.innerHTML =
            "🔥 Study session running";


    timerInterval =
        setInterval(function(){

            if(seconds > 0){

                seconds--;

                displayTimer();

            }
            else{

                clearInterval(timerInterval);

                timerInterval = null;

                alert(
                    "🎉 Study session completed!"
                );

            }

        },1000);

}


function pauseTimer(){

    clearInterval(timerInterval);

    timerInterval = null;


    var status =
        document.getElementById("timerStatus");


    if(status)
        status.innerHTML =
            "⏸ Timer paused";

}


function resetTimer(){

    clearInterval(timerInterval);

    timerInterval = null;

    seconds = 1500;

    displayTimer();

}


/* =========================
   FRIENDS
========================= */

function friends(){

    if(!requireLogin()) return;


    var user = userData();


    document.getElementById(
        "mainContent"
    ).innerHTML = `

        <div class="card">

            <h2>👥 My Friends</h2>

            <br>

            <input
                id="friendName"
                placeholder="Friend Name"
            >

            <input
                id="friendID"
                placeholder="Friend Student ID"
            >

            <button
                class="btn"
                onclick="addFriend()">
                ➕ Add Friend
            </button>

            <button
                class="btn"
                onclick="copyInvite()">
                📋 Copy Invitation
            </button>

            <div id="friendList"></div>

            <br>

            <button
                class="btn"
                onclick="home()">
                ← Back Home
            </button>

        </div>

    `;


    showFriends();

}


function addFriend(){

    var name =
        document.getElementById("friendName")
        .value.trim();


    var id =
        document.getElementById("friendID")
        .value.trim();


    if(name === "" || id === ""){

        alert(
            "Enter friend name and Student ID."
        );

        return;

    }


    var user = userData();


    var exists =
        user.friends.some(
            function(friend){

                return friend.id === id;

            }
        );


    if(exists){

        alert(
            "This friend is already added."
        );

        return;

    }


    user.friends.push({

        name:name,

        id:id

    });


    saveUserData(user);


    document.getElementById(
        "friendName"
    ).value = "";


    document.getElementById(
        "friendID"
    ).value = "";


    showFriends();

}


function showFriends(){

    var list =
        document.getElementById("friendList");


    if(!list) return;


    var user = userData();


    if(user.friends.length === 0){

        list.innerHTML =
            "<p>👤 No friends added yet.</p>";

        return;

    }


    list.innerHTML =
        "<h3 style='margin-top:20px'>👨‍👩‍👧‍👦 Friend List</h3>";


    user.friends.forEach(
        function(friend,index){

            list.innerHTML += `

                <div class="friend">

                    <div>

                        <b>👤 ${friend.name}</b>

                        <br>

                        <small>
                            Student ID: ${friend.id}
                        </small>

                    </div>

                    <button
                        class="remove"
                        onclick="removeFriend(${index})">
                        ❌
                    </button>

                </div>

            `;

        }
    );

}


function removeFriend(index){

    var user = userData();


    user.friends.splice(index,1);


    saveUserData(user);


    showFriends();

}


function copyInvite(){

    var message =
        "👋 Hey! Join me on the RK University Student Digital Portal. Let's stay connected with our student activities!";


    if(navigator.clipboard){

        navigator.clipboard.writeText(message)

        .then(function(){

            alert(
                "✅ Invitation message copied!"
            );

        });

    }
    else{

        alert(message);

    }

}


/* =========================
   SETTINGS
========================= */

function settings(){

    if(!requireLogin()) return;


    document.getElementById(
        "mainContent"
    ).innerHTML = `

        <div class="card">

            <h2>⚙️ Account Settings</h2>


            <div class="setting">

                <span>🌙 Dark Mode</span>

                <button
                    class="btn"
                    onclick="toggleDark()">
                    ON / OFF
                </button>

            </div>


            <div class="setting">

                <span>👤 My Profile</span>

                <button
                    class="btn"
                    onclick="profile()">
                    Open
                </button>

            </div>


            <div class="setting">

                <span>👥 Manage Friends</span>

                <button
                    class="btn"
                    onclick="friends()">
                    Open
                </button>

            </div>


            <div class="setting">

                <span>🚪 Logout</span>

                <button
                    class="btn"
                    onclick="logout()">
                    Logout
                </button>

            </div>


            <br>

            <button
                class="btn"
                onclick="home()">
                ← Back Home
            </button>

        </div>

    `;

}


/* DARK MODE */

function toggleDark(){

    document.body.classList.toggle("dark");

    localStorage.setItem(
        "darkMode",
        document.body.classList.contains("dark")
        ? "on"
        : "off"
    );

}


if(
    localStorage.getItem("darkMode")
    === "on"
){

    document.body.classList.add("dark");

}


/* =========================
   PROFILE
========================= */

function profile(){

    if(!requireLogin()) return;


    var user = userData();


    document.getElementById(
        "mainContent"
    ).innerHTML = `

        <div class="card">

            <h2>👤 My Profile</h2>

            <div class="profile">

                <p>
                    <b>Name:</b>
                    ${user.name}
                </p>

                <br>

                <p>
                    <b>Student ID:</b>
                    ${user.studentID}
                </p>

                <br>

                <p>
                    <b>Email:</b>
                    ${user.email}
                </p>

                <br>

                <p>
                    <b>University:</b>
                    RK University
                </p>

                <br>

                <p>
                    <b>Developer:</b>
                    MOHAMMAD ASFAK
                </p>

            </div>

            <br>

            <button
                class="btn"
                onclick="home()">
                ← Back Home
            </button>

        </div>

    `;

}


/* =========================
   NOTICES
========================= */

function notice(){

    if(!requireLogin()) return;


    document.getElementById(
        "mainContent"
    ).innerHTML = `

        <div class="card">

            <h2>📢 Notice Board</h2>

            <div class="notice">
                📌 Welcome to the Student Portal.
            </div>

            <div class="notice">
                📌 Check your academic schedule regularly.
            </div>

            <div class="notice">
                📌 Complete assignments before deadlines.
            </div>

            <div class="notice">
                📌 Keep your attendance updated.
            </div>

            <br>

            <button
                class="btn"
                onclick="home()">
                ← Back Home
            </button>

        </div>

    `;

}


/* =========================
   ABOUT
========================= */

function about(){

    document.getElementById(
        "mainContent"
    ).innerHTML = `

        <div class="card">

            <h2>🎓 About This Project</h2>

            <br>

            <p>
                This is a student-made educational
                demonstration of a digital university
                student portal.
            </p>

            <br>

            <p>
                Features include account creation,
                login, profile, friends, tasks,
                attendance, timer, quiz and settings.
            </p>

            <br>

            <p>
                <b>Developer:</b>
                MOHAMMAD ASFAK
            </p>

            <br>

            <button
                class="btn"
                onclick="home()">
                ← Back Home
            </button>

        </div>

    `;

}


/* =========================
   QUIZ
========================= */

var quiz = [

    {
        question:"What does HTML stand for?",

        options:[
            "Hyper Text Markup Language",
            "High Tech Modern Language",
            "Home Tool Markup Language"
        ],

        answer:0
    },

    {
        question:"Which language styles a webpage?",

        options:[
            "Python",
            "CSS",
            "Java"
        ],

        answer:1
    },

    {
        question:"Which language makes webpages interactive?",

        options:[
            "HTML",
            "CSS",
            "JavaScript"
        ],

        answer:2
    },

    {
        question:"Largest HTML heading tag?",

        options:[
            "<h1>",
            "<h6>",
            "<heading>"
        ],

        answer:0
    }

];


var currentQuestion = 0;


function loadQuestion(){

    var question =
        document.getElementById("question");


    if(!question) return;


    var q =
        quiz[currentQuestion];


    question.innerHTML =
        q.question;


    var options =
        document.getElementById("options");


    options.innerHTML = "";


    q.options.forEach(
        function(option,index){

            var button =
                document.createElement("button");


            button.className =
                "option";


            button.innerHTML =
                option;


            button.onclick =
                function(){

                    var result =
                        document.getElementById(
                            "quizResult"
                        );


                    if(index === q.answer){

                        result.innerHTML =
                            "✅ Correct Answer!";

                        button.style.background =
                            "#4caf50";

                        button.style.color =
                            "white";

                    }
                    else{

                        result.innerHTML =
                            "❌ Incorrect Answer.";

                        button.style.background =
                            "#e53935";

                        button.style.color =
                            "white";

                    }

                };


            options.appendChild(button);

        }
    );

}


function nextQuestion(){

    currentQuestion++;


    if(
        currentQuestion >= quiz.length
    ){

        currentQuestion = 0;

    }


    loadQuestion();

}


/* =========================
   CLOCK
========================= */

function startClock(){

    function update(){

        var clock =
            document.getElementById("clock");


        if(clock){

            clock.innerHTML =
                "📅 " +
                new Date().toLocaleDateString()
                +
                " | ⏰ " +
                new Date().toLocaleTimeString();

        }

    }


    update();

    setInterval(update,1000);

}



/* =====================================================
   ADMIN CONTROL CENTER
   HTML/localStorage DEMO VERSION
===================================================== */

var ADMIN_MASTER_KEY = "ASFAK-ROOT-2026";
var INITIAL_ADMIN_ID = "ASFAK-ADMIN";
var INITIAL_ADMIN_PASSWORD = "RK@Admin2026";

function getAdminData(){
    return JSON.parse(localStorage.getItem("portal_admins") || "{}");
}
function saveAdminData(data){
    localStorage.setItem("portal_admins", JSON.stringify(data));
}
function getPortalSettings(){
    return JSON.parse(localStorage.getItem("portal_settings") || JSON.stringify({
        universityName:"RK UNIVERSITY",
        logo:"https://lookaside.fbsbx.com/lookaside/crawler/instagram/rkuniversity/profile_pic.jpg"
    }));
}
function savePortalSettings(data){
    localStorage.setItem("portal_settings", JSON.stringify(data));
}
function getBanned(){ return JSON.parse(localStorage.getItem("portal_banned") || "[]"); }
function saveBanned(x){ localStorage.setItem("portal_banned",JSON.stringify(x)); }
function getKicked(){ return JSON.parse(localStorage.getItem("portal_kicked") || "[]"); }
function saveKicked(x){ localStorage.setItem("portal_kicked",JSON.stringify(x)); }
function getAdminSession(){ return localStorage.getItem("portal_admin_session"); }
function isAdmin(){ return !!getAdminSession() && !!getAdminData()[getAdminSession()]; }

(function seedAdmin(){
    var admins=getAdminData();
    if(!admins[INITIAL_ADMIN_ID]){
        admins[INITIAL_ADMIN_ID]={id:INITIAL_ADMIN_ID,password:INITIAL_ADMIN_PASSWORD,name:"MOHAMMAD ASFAK",owner:true};
        saveAdminData(admins);
    }
})();

function adminLoginPage(){
    document.getElementById("mainContent").innerHTML=`
        <div class="card account-box">
            <h2>🛡️ University Admin Login</h2><br>
            <p>Only authorized administrators can access the control center.</p><br>
            <input id="adminID" placeholder="Admin ID">
            <input id="adminPassword" type="password" placeholder="Admin Password">
            <button class="btn" onclick="adminLogin()">🔐 Admin Login</button>
            <button class="btn" onclick="home()">← Student Portal</button>
            <p style="margin-top:10px;font-size:13px">Owner Master Key is required only when creating another Admin ID.</p>
            <p id="adminLoginMessage"></p>
        </div>`;
}

function adminLogin(){
    var id=document.getElementById("adminID").value.trim();
    var pass=document.getElementById("adminPassword").value;
    var admins=getAdminData();

    /* Always make sure the original owner credentials work in this demo. */
    if(id===INITIAL_ADMIN_ID && pass===INITIAL_ADMIN_PASSWORD){
        if(!admins[id]){
            admins[id]={id:INITIAL_ADMIN_ID,password:INITIAL_ADMIN_PASSWORD,name:"MOHAMMAD ASFAK",owner:true};
            saveAdminData(admins);
        }
        localStorage.setItem("portal_admin_session",id);
        adminDashboard();
        return;
    }

    if(!admins[id] || admins[id].password!==pass){
        document.getElementById("adminLoginMessage").innerHTML="<p class='error'>❌ Invalid Admin ID or Password.</p>"; return;
    }

    localStorage.setItem("portal_admin_session",id);
    adminDashboard();
}

function adminLogout(){
    localStorage.removeItem("portal_admin_session");
    adminLoginPage();
}

function adminDashboard(){
    if(!isAdmin()){adminLoginPage();return;}
    var users=getUsers();
    var banned=getBanned();
    var kicked=getKicked();
    var admins=getAdminData();
    var settings=getPortalSettings();
    var active=Object.keys(users).filter(e=>!banned.includes(e)&&!kicked.includes(e)).length;
    document.getElementById("mainContent").innerHTML=`
        <div class="welcome">
            <h2>🛡️ Admin Control Center</h2>
            <p>Logged in as <b>${escapeHTML(getAdminSession())}</b></p>
            <button class="btn" onclick="adminLogout()">🚪 Admin Logout</button>
        </div>

        <div class="admin-grid">
            <div class="admin-stat"><b>${Object.keys(users).length}</b>Total Students</div>
            <div class="admin-stat"><b>${active}</b>Active Students</div>
            <div class="admin-stat"><b>${banned.length}</b>Banned</div>
            <div class="admin-stat"><b>${kicked.length}</b>Kicked</div>
            <div class="admin-stat"><b>${Object.keys(admins).length}</b>Admins</div>
        </div>

        <div class="card">
            <h3>🏫 University Settings</h3>
            <input id="adminUniName" value="${escapeAttribute(settings.universityName)}" placeholder="University Name">
            <input id="adminLogoURL" value="${escapeAttribute(settings.logo)}" placeholder="Logo Image URL">
            <button class="btn admin-success" onclick="saveUniversitySettings()">💾 Save University Settings</button>
        </div>

        <div class="card">
            <h3>📢 Manage Notices</h3>
            <input id="adminNotice" placeholder="Write a university notice">
            <button class="btn" onclick="addAdminNotice()">➕ Add Notice</button>
            <div id="adminNoticeList"></div>
        </div>

        <div class="card">
            <h3>👥 Student Management</h3>
            <div class="admin-table"><table>
                <tr><th>Name</th><th>Student ID</th><th>Email</th><th>Status</th><th>Action</th></tr>
                ${Object.keys(users).map(email=>{
                    var u=users[email], ban=banned.includes(email), kick=kicked.includes(email);
                    var status=ban?"BANNED":kick?"KICKED":"ACTIVE";
                    return `<tr class="${ban||kick?'admin-banned':''}">
                        <td>${escapeHTML(u.name)}</td><td>${escapeHTML(u.studentID)}</td><td>${escapeHTML(email)}</td>
                        <td><span class="admin-badge ${status==='ACTIVE'?'ok':''}">${status}</span></td>
                        <td><div class="admin-actions">
                            <button class="btn admin-warning" onclick="toggleBanStudent('${escapeAttribute(email)}')">${ban?'♻️ Unban':'🚫 Ban'}</button>
                            <button class="btn admin-danger" onclick="toggleKickStudent('${escapeAttribute(email)}')">${kick?'♻️ Restore':'👢 Kick'}</button>
                            <button class="btn" onclick="deleteStudent('${escapeAttribute(email)}')">🗑️ Delete</button>
                        </div></td>
                    </tr>`;
                }).join('')}
            </table></div>
        </div>

        <div class="card">
            <h3>🛡️ Create Admin ID</h3>
            <p>Only a logged-in admin can create another admin account. The owner admin is the only account allowed to use the master key.</p>
            <input id="newAdminID" placeholder="New Admin ID">
            <input id="newAdminName" placeholder="Admin Name">
            <input id="newAdminPassword" type="password" placeholder="New Admin Password">
            <input id="newAdminMaster" type="password" placeholder="Owner Master Key">
            <button class="btn" onclick="createAdminAccount()">➕ Create Admin</button>
            <div id="adminList"></div>
        </div>

        <div class="card">
            <h3>⚠️ Admin Controls</h3>
            <p>Ban blocks login. Kick temporarily blocks access until restored. Delete permanently removes the student from this browser's demo database.</p>
            <button class="btn" onclick="home()">🏠 Student Home</button>
        </div>`;
    renderAdminNotices();
    renderAdminList();
}

function saveUniversitySettings(){
    var name=document.getElementById("adminUniName").value.trim();
    var logo=document.getElementById("adminLogoURL").value.trim();
    if(!name){alert("University name is required.");return;}
    var s={universityName:name,logo:logo||getPortalSettings().logo};
    savePortalSettings(s); applyUniversitySettings(); alert("✅ University settings saved."); adminDashboard();
}

function applyUniversitySettings(){
    var s=getPortalSettings();
    var n=document.getElementById("universityName");
    var img=document.getElementById("universityLogoImg");
    if(n)n.textContent=s.universityName;
    if(img){img.src=s.logo;img.style.display="block";}
    document.title=s.universityName+" Student Portal";
}

function toggleBanStudent(email){
    var a=getBanned();
    if(a.includes(email)) a=a.filter(x=>x!==email); else a.push(email);
    saveBanned(a); adminDashboard();
}
function toggleKickStudent(email){
    var a=getKicked();
    if(a.includes(email)) a=a.filter(x=>x!==email); else a.push(email);
    saveKicked(a); adminDashboard();
}
function deleteStudent(email){
    if(email===getAdminSession()) return;
    if(!confirm("Delete this student account permanently from this demo?"))return;
    var users=getUsers(); delete users[email]; saveUsers(users);
    saveBanned(getBanned().filter(x=>x!==email));
    saveKicked(getKicked().filter(x=>x!==email));
    if(currentUser===email){localStorage.removeItem("currentUser");currentUser=null;}
    adminDashboard();
}

function createAdminAccount(){
    if(!isAdmin()){adminLoginPage();return;}
    var me=getAdminData()[getAdminSession()];
    if(!me.owner){alert("Only the owner admin can create admin IDs.");return;}
    var key=document.getElementById("newAdminMaster").value;
    if(key!==ADMIN_MASTER_KEY){alert("❌ Owner master key is incorrect.");return;}
    var id=document.getElementById("newAdminID").value.trim();
    var name=document.getElementById("newAdminName").value.trim();
    var pass=document.getElementById("newAdminPassword").value;
    var admins=getAdminData();
    if(!id||!name||!pass){alert("Fill all admin fields.");return;}
    if(admins[id]){alert("Admin ID already exists.");return;}
    admins[id]={id:id,name:name,password:pass,owner:false};
    saveAdminData(admins); alert("✅ Admin ID created."); adminDashboard();
}

function renderAdminList(){
    var box=document.getElementById("adminList"); if(!box)return;
    var admins=getAdminData();
    box.innerHTML="<h3 style='margin-top:18px'>Existing Admins</h3>"+Object.keys(admins).map(id=>`<p>🛡️ <b>${escapeHTML(id)}</b> — ${escapeHTML(admins[id].name)} ${admins[id].owner?'(Owner)':''}</p>`).join('');
}

function getPortalNotices(){return JSON.parse(localStorage.getItem("portal_notices")||"[]");}
function savePortalNotices(x){localStorage.setItem("portal_notices",JSON.stringify(x));}
function addAdminNotice(){
    var t=document.getElementById("adminNotice").value.trim(); if(!t)return;
    var a=getPortalNotices(); a.push(t); savePortalNotices(a); adminDashboard();
}
function deleteAdminNotice(i){var a=getPortalNotices();a.splice(i,1);savePortalNotices(a);adminDashboard();}
function renderAdminNotices(){
    var box=document.getElementById("adminNoticeList");if(!box)return;
    var a=getPortalNotices();
    box.innerHTML=a.length?a.map((x,i)=>`<div class="notice">📢 ${escapeHTML(x)} <button class="delete" onclick="deleteAdminNotice(${i})">❌</button></div>`).join(''):'<p>No custom notices yet.</p>';
}

/* Replace/augment normal notice page with admin notices */
var originalNotice = typeof notice === "function" ? notice : null;
function notice(){
    if(typeof requireLogin==='function' && !requireLogin())return;
    var a=getPortalNotices();
    document.getElementById("mainContent").innerHTML=`<div class="card"><h2>📢 Notice Board</h2>
        <div class="notice">📌 Welcome to the Student Portal.</div>
        <div class="notice">📌 Check your academic schedule regularly.</div>
        <div class="notice">📌 Complete assignments before deadlines.</div>
        <div class="notice">📌 Keep your attendance updated.</div>
        ${a.map(x=>`<div class="notice">📢 ${escapeHTML(x)}</div>`).join('')}
        <br><button class="btn" onclick="home()">← Back Home</button></div>`;
}

/* Student login protection */
var originalLogin = login;
login = function(){
    var email=document.getElementById("loginEmail").value.trim().toLowerCase();
    var banned=getBanned(), kicked=getKicked();
    if(banned.includes(email)){
        document.getElementById("loginMessage").innerHTML="<p class='error'>🚫 This student account has been banned by the university admin.</p>";return;
    }
    if(kicked.includes(email)){
        document.getElementById("loginMessage").innerHTML="<p class='error'>👢 This student account is currently kicked. Contact the university administration.</p>";return;
    }
    originalLogin();
};

applyUniversitySettings();

/* =========================
   START APP
========================= */

if(currentUser){

    home();

}
else{

    loginPage();

}

</script>

</body>
</html>
