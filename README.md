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
