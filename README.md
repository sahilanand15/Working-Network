<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>SmartNet — Intelligent Work Network</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:Inter,Arial,sans-serif;
    background:#080b14;
    color:#f5f7ff;
}

/* =========================
   LAYOUT
========================= */

.app{
    min-height:100vh;
    display:flex;
}

/* =========================
   SIDEBAR
========================= */

.sidebar{
    width:250px;
    min-height:100vh;
    padding:25px 18px;
    background:#0d111c;
    border-right:1px solid #202637;
    display:flex;
    flex-direction:column;
}

.logo{
    display:flex;
    align-items:center;
    gap:12px;
    margin-bottom:45px;
}

.logo-icon{
    width:42px;
    height:42px;
    border-radius:13px;
    display:flex;
    align-items:center;
    justify-content:center;
    background:linear-gradient(135deg,#6c63ff,#00d4ff);
    font-weight:bold;
    font-size:20px;
}

.logo h2{
    font-size:20px;
}

.logo span{
    color:#6c63ff;
}

.menu{
    display:flex;
    flex-direction:column;
    gap:8px;
}

.menu button{
    width:100%;
    border:0;
    padding:14px 15px;
    border-radius:12px;
    background:transparent;
    color:#9299aa;
    text-align:left;
    cursor:pointer;
    font-size:15px;
    transition:.25s;
}

.menu button:hover,
.menu button.active{
    background:#171d2d;
    color:white;
}

.status{
    margin-top:auto;
    padding:17px;
    border-radius:16px;
    background:#111827;
    border:1px solid #222b40;
}

.status-title{
    display:flex;
    justify-content:space-between;
    margin-bottom:12px;
}

.online{
    color:#35e58a;
    font-size:13px;
}

.status-bar{
    height:6px;
    background:#252d3d;
    border-radius:10px;
    overflow:hidden;
}

.status-fill{
    width:92%;
    height:100%;
    background:#35e58a;
}

/* =========================
   MAIN
========================= */

.main{
    flex:1;
    padding:25px;
    overflow:hidden;
}

/* HEADER */

.header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:30px;
}

.header h1{
    font-size:28px;
}

.header p{
    color:#7e8799;
    margin-top:6px;
}

.header-right{
    display:flex;
    align-items:center;
    gap:15px;
}

.search{
    width:220px;
    padding:12px 15px;
    border-radius:12px;
    border:1px solid #252d40;
    background:#101521;
    color:white;
    outline:none;
}

.avatar{
    width:42px;
    height:42px;
    border-radius:50%;
    display:flex;
    align-items:center;
    justify-content:center;
    background:linear-gradient(135deg,#6c63ff,#00d4ff);
    font-weight:bold;
}

/* =========================
   CARDS
========================= */

.cards{
    display:flex;
    gap:18px;
    flex-wrap:wrap;
}

.card{
    flex:1;
    min-width:210px;
    padding:22px;
    background:#101521;
    border:1px solid #20283a;
    border-radius:18px;
    transition:.3s;
}

.card:hover{
    transform:translateY(-4px);
    border-color:#39445e;
}

.card-top{
    display:flex;
    justify-content:space-between;
    align-items:center;
}

.card-icon{
    width:43px;
    height:43px;
    display:flex;
    align-items:center;
    justify-content:center;
    border-radius:12px;
    background:#181f31;
}

.card small{
    color:#7e8799;
}

.card h2{
    margin-top:15px;
    font-size:29px;
}

.growth{
    margin-top:7px;
    color:#35e58a;
    font-size:13px;
}

/* =========================
   DASHBOARD
========================= */

.dashboard{
    margin-top:22px;
    display:flex;
    gap:20px;
}

.panel{
    background:#101521;
    border:1px solid #20283a;
    border-radius:18px;
    padding:22px;
}

.network-panel{
    flex:2;
}

.activity-panel{
    flex:1;
    min-width:280px;
}

.panel-header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:22px;
}

.panel-header h3{
    font-size:18px;
}

.panel-header span{
    color:#7e8799;
    font-size:13px;
}

/* NETWORK MAP */

.network-map{
    min-height:310px;
    position:relative;
    border-radius:15px;
    overflow:hidden;
    background:
        linear-gradient(#151c2b 1px,transparent 1px),
        linear-gradient(90deg,#151c2b 1px,transparent 1px);
    background-size:35px 35px;
}

/* Lines */

.connection{
    position:absolute;
    height:2px;
    background:linear-gradient(
        90deg,
        transparent,
        #5d6cff,
        #00d9ff,
        transparent
    );
    transform-origin:left center;
    animation:dataFlow 2s linear infinite;
}

.line1{
    width:180px;
    left:30%;
    top:50%;
    transform:rotate(-25deg);
}

.line2{
    width:180px;
    left:45%;
    top:50%;
    transform:rotate(28deg);
}

.line3{
    width:150px;
    left:43%;
    top:51%;
    transform:rotate(90deg);
}

@keyframes dataFlow{
    0%{
        opacity:.25;
    }
    50%{
        opacity:1;
    }
    100%{
        opacity:.25;
    }
}

/* Network Nodes */

.node{
    position:absolute;
    width:60px;
    height:60px;
    border-radius:18px;
    display:flex;
    align-items:center;
    justify-content:center;
    background:#171f31;
    border:1px solid #35415b;
    box-shadow:0 0 25px rgba(82,97,255,.15);
    z-index:2;
}

.node::after{
    content:"";
    position:absolute;
    width:9px;
    height:9px;
    border-radius:50%;
    right:3px;
    top:3px;
    background:#35e58a;
    box-shadow:0 0 12px #35e58a;
}

.router{
    left:42%;
    top:40%;
    width:75px;
    height:75px;
    border-radius:22px;
    background:linear-gradient(135deg,#252d69,#171d39);
    border-color:#5967ff;
}

.node1{
    left:12%;
    top:25%;
}

.node2{
    left:70%;
    top:25%;
}

.node3{
    left:72%;
    top:65%;
}

.node4{
    left:12%;
    top:68%;
}

/* =========================
   ACTIVITY
========================= */

.activity{
    display:flex;
    flex-direction:column;
    gap:17px;
}

.activity-item{
    display:flex;
    gap:12px;
    align-items:center;
    padding-bottom:15px;
    border-bottom:1px solid #20283a;
}

.activity-icon{
    width:38px;
    height:38px;
    flex-shrink:0;
    display:flex;
    align-items:center;
    justify-content:center;
    border-radius:11px;
    background:#181f31;
}

.activity-text{
    flex:1;
}

.activity-text strong{
    display:block;
    font-size:14px;
}

.activity-text small{
    color:#70798b;
}

/* =========================
   DEVICES
========================= */

.devices{
    margin-top:22px;
    display:flex;
    gap:20px;
}

.device-panel{
    flex:1;
    background:#101521;
    border:1px solid #20283a;
    border-radius:18px;
    padding:22px;
}

.device{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:15px 0;
    border-bottom:1px solid #20283a;
}

.device:last-child{
    border-bottom:0;
}

.device-info{
    display:flex;
    align-items:center;
    gap:13px;
}

.device-icon{
    width:42px;
    height:42px;
    border-radius:12px;
    background:#181f31;
    display:flex;
    align-items:center;
    justify-content:center;
}

.device-info strong{
    display:block;
}

.device-info small{
    color:#737d90;
}

.badge{
    padding:6px 10px;
    border-radius:20px;
    font-size:11px;
}

.badge.online{
    background:rgba(53,229,138,.1);
}

.badge.warning{
    background:rgba(255,185,70,.1);
    color:#ffb946;
}

/* =========================
   RESPONSIVE
========================= */

@media(max-width:950px){

    .sidebar{
        width:80px;
        padding:20px 10px;
    }

    .logo h2,
    .menu button span,
    .status{
        display:none;
    }

    .logo{
        justify-content:center;
    }

    .menu button{
        text-align:center;
        font-size:20px;
    }

    .dashboard,
    .devices{
        flex-direction:column;
    }
}

@media(max-width:650px){

    .main{
        padding:15px;
    }

    .header{
        align-items:flex-start;
        gap:15px;
    }

    .header-right .search{
        display:none;
    }

    .cards{
        flex-direction:column;
    }

    .card{
        min-width:100%;
    }

    .network-map{
        min-height:260px;
    }
}
</style>
</head>

<body>

<div class="app">

<!-- SIDEBAR -->

<aside class="sidebar">

    <div class="logo">
        <div class="logo-icon">N</div>
        <h2>Smart<span>Net</span></h2>
    </div>

    <div class="menu">

        <button class="active">⌂ <span>Dashboard</span></button>

        <button>◉ <span>Network</span></button>

        <button>▣ <span>Devices</span></button>

        <button>◈ <span>Team</span></button>

        <button>⚙ <span>Settings</span></button>

    </div>

    <div class="status">

        <div class="status-title">
            <strong>Network</strong>
            <span class="online">Online</span>
        </div>

        <div class="status-bar">
            <div class="status-fill"></div>
        </div>

        <small style="color:#737d90;display:block;margin-top:8px;">
            92% performance
        </small>

    </div>

</aside>


<!-- MAIN -->

<main class="main">

    <!-- HEADER -->

    <header class="header">

        <div>
            <h1>Smart Workspace</h1>
            <p>Monitor your intelligent network in real time.</p>
        </div>

        <div class="header-right">

            <input
                class="search"
                type="search"
                placeholder="Search network..."
            >

            <div class="avatar">S</div>

        </div>

    </header>


    <!-- STATS -->

    <section class="cards">

        <div class="card">

            <div class="card-top">
                <small>Connected Devices</small>
                <div class="card-icon">▣</div>
            </div>

            <h2 id="devices">48</h2>

            <div class="growth">↑ 12% this week</div>

        </div>


        <div class="card">

            <div class="card-top">
                <small>Network Speed</small>
                <div class="card-icon">⚡</div>
            </div>

            <h2>942 Mbps</h2>

            <div class="growth">↑ 8.4% faster</div>

        </div>


        <div class="card">

            <div class="card-top">
                <small>Active Users</small>
                <div class="card-icon">●</div>
            </div>

            <h2>126</h2>

            <div class="growth">↑ 16 users online</div>

        </div>


        <div class="card">

            <div class="card-top">
                <small>Security</small>
                <div class="card-icon">🔒</div>
            </div>

            <h2>99.9%</h2>

            <div class="growth">Protected</div>

        </div>

    </section>


    <!-- NETWORK -->

    <section class="dashboard">

        <div class="panel network-panel">

            <div class="panel-header">

                <h3>Live Network</h3>

                <span>● Live monitoring</span>

            </div>


            <div class="network-map">

                <div class="connection line1"></div>
                <div class="connection line2"></div>
                <div class="connection line3"></div>

                <div class="node node1">💻</div>

                <div class="node node2">📱</div>

                <div class="node router">⚡</div>

                <div class="node node3">🖥️</div>

                <div class="node node4">☁️</div>

            </div>

        </div>


        <!-- ACTIVITY -->

        <div class="panel activity-panel">

            <div class="panel-header">
                <h3>Live Activity</h3>
                <span>Now</span>
            </div>


            <div class="activity">

                <div class="activity-item">

                    <div class="activity-icon">💻</div>

                    <div class="activity-text">
                        <strong>New device connected</strong>
                        <small>MacBook Pro · 2 min ago</small>
                    </div>

                </div>


                <div class="activity-item">

                    <div class="activity-icon">🔐</div>

                    <div class="activity-text">
                        <strong>Security scan completed</strong>
                        <small>No threats detected</small>
                    </div>

                </div>


                <div class="activity-item">

                    <div class="activity-icon">⚡</div>

                    <div class="activity-text">
                        <strong>Speed optimized</strong>
                        <small>Network performance improved</small>
                    </div>

                </div>


                <div class="activity-item">

                    <div class="activity-icon">☁️</div>

                    <div class="activity-text">
                        <strong>Cloud sync complete</strong>
                        <small>All files synchronized</small>
                    </div>

                </div>

            </div>

        </div>

    </section>


    <!-- DEVICES -->

    <section class="devices">

        <div class="device-panel">

            <div class="panel-header">
                <h3>Connected Devices</h3>
                <span>48 devices</span>
            </div>


            <div class="device">

                <div class="device-info">

                    <div class="device-icon">💻</div>

                    <div>
                        <strong>Developer Laptop</strong>
                        <small>192.168.1.24</small>
                    </div>

                </div>

                <span class="badge online">Online</span>

            </div>


            <div class="device">

                <div class="device-info">

                    <div class="device-icon">📱</div>

                    <div>
                        <strong>Mobile Device</strong>
                        <small>192.168.1.31</small>
                    </div>

                </div>

                <span class="badge online">Online</span>

            </div>


            <div class="device">

                <div class="device-info">

                    <div class="device-icon">🖨️</div>

                    <div>
                        <strong>Office Printer</strong>
                        <small>192.168.1.42</small>
                    </div>

                </div>

                <span class="badge warning">Idle</span>

            </div>

        </div>


        <div class="device-panel">

            <div class="panel-header">
                <h3>Smart Automation</h3>
                <span>4 active</span>
            </div>


            <div class="device">

                <div class="device-info">

                    <div class="device-icon">🤖</div>

                    <div>
                        <strong>Auto Optimization</strong>
                        <small>Traffic management</small>
                    </div>

                </div>

                <span class="badge online">Active</span>

            </div>


            <div class="device">

                <div class="device-info">

                    <div class="device-icon">🛡️</div>

                    <div>
                        <strong>Threat Protection</strong>
                        <small>Real-time security</small>
                    </div>

                </div>

                <span class="badge online">Active</span>

            </div>


            <div class="device">

                <div class="device-info">

                    <div class="device-icon">☁️</div>

                    <div>
                        <strong>Cloud Backup</strong>
                        <small>Automatic backup</small>
                    </div>

                </div>

                <span class="badge online">Active</span>

            </div>

        </div>

    </section>

</main>

</div>


<script>

/* =========================
   SMART DASHBOARD DEMO
========================= */

const deviceCounter =
    document.getElementById("devices");

let devices = 48;

setInterval(() => {

    const change =
        Math.random() > .5 ? 1 : -1;

    devices += change;

    if(devices < 40) devices = 40;
    if(devices > 60) devices = 60;

    deviceCounter.textContent = devices;

},3000);


/* MENU */

document.querySelectorAll(".menu button")
.forEach(button => {

    button.addEventListener("click", () => {

        document
        .querySelectorAll(".menu button")
        .forEach(btn =>
            btn.classList.remove("active")
        );

        button.classList.add("active");

    });

});


/* SEARCH */

document
.querySelector(".search")
.addEventListener("input", function(){

    console.log(
        "Searching network for:",
        this.value
    );

});

</script>

</body>
</html>
