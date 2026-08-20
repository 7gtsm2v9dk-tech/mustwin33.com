# mustwin33.com
let points = Number(localStorage.getItem("mustwin33_points") || 1000);
const pointsEl = document.getElementById("points");
const toast = document.getElementById("toast");
function render(){pointsEl.textContent=points.toLocaleString();}
function show(msg){toast.textContent=msg;toast.classList.add("show");setTimeout(()=>toast.classList.remove("show"),2200)}
document.getElementById("dailyBtn").onclick=()=>{points+=100;localStorage.setItem("mustwin33_points",points);render();show("+100 demo points added")};
document.querySelectorAll(".game").forEach(btn=>btn.onclick=()=>show(btn.dataset.game+" demo selected"));
document.getElementById("installHelp").onclick=()=>show("Safari: Share → Add to Home Screen → Add");
render();
if("serviceWorker" in navigator){window.addEventListener("load",()=>navigator.serviceWorker.register("sw.js"))}
33MustWin33
◎
WELCOME BACK

Play. Compete.
Win points.

A mobile-first demo gaming experience using points with no cash value.

DEMO POINTS 1,000  Claim daily points
Games

Demo only
⚡Quick PlayFast demo round  33Pick 33Choose your numbers 🏆LeaderboardCompare demo scores
INSTALL ON IPHONE

Put MustWin33 on your Home Screen

In Safari, tap Share → Add to Home Screen.

How to install
Recent activity

Quick Play+120 pts
Daily bonus+100 pts
Pick 33+80 pts
⌂Home  ◈Games  ◎Profile
{
  "name": "MustWin33",
  "short_name": "MustWin33",
  "start_url": "./",
  "display": "standalone",
  "background_color": "#0b0b0d",
  "theme_color": "#111111",
  "description": "MustWin33 demo gaming experience using points with no cash value.",
  "icons": [{"src":"icon.svg","sizes":"any","type":"image/svg+xml","purpose":"any maskable"}]
}