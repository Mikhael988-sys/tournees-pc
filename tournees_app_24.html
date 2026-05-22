<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<meta http-equiv="Content-Security-Policy" content="default-src * 'unsafe-inline' 'unsafe-eval' data: blob:;">
<title>Gestion de Tournées</title>
<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css"/>
<link rel="stylesheet" href="https://unpkg.com/leaflet-draw/dist/leaflet.draw.css"/>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Syne:wght@600;700;800&display=swap" rel="stylesheet"/>
<script src="https://unpkg.com/qrcodejs@1.0.0/qrcode.min.js"></script>
<style>
:root{--bg:#0d1117;--surf:#161b22;--surf2:#1c2330;--border:rgba(255,255,255,0.08);--fg:#e6edf3;--muted:#8b949e;--accent:#f0b429;--accent2:#58a6ff;--ok:#3fb950;--err:#f85149;--warn:#f0b429;--panel-w:380px;--hh:52px}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html,body{height:100%;font-family:'Syne',sans-serif;background:var(--bg);color:var(--fg);overflow:hidden}
#app-tabs{position:fixed;top:0;left:0;right:0;height:var(--hh);background:var(--surf);border-bottom:1px solid var(--border);display:flex;align-items:stretch;z-index:1000}
.tab-btn{flex:1;border:none;background:transparent;color:var(--muted);font-family:'Syne',sans-serif;font-size:14px;font-weight:700;cursor:pointer;transition:all .2s;border-bottom:3px solid transparent;padding:0 12px;display:flex;align-items:center;justify-content:center;gap:8px}
.tab-btn:hover{color:var(--fg);background:rgba(255,255,255,.04)}
.tab-btn.active{color:var(--accent);border-bottom-color:var(--accent);background:rgba(240,180,41,.06)}
.badge-count{display:inline-flex;align-items:center;justify-content:center;min-width:20px;height:20px;padding:0 5px;border-radius:10px;background:var(--err);color:#fff;font-size:11px;font-weight:700}
.badge-count.hidden{display:none}
.page{position:fixed;top:var(--hh);left:0;right:0;bottom:0;display:none}
.page.active{display:flex}
#page-carte{flex-direction:row}
#map{flex:1}
#panel{width:var(--panel-w);background:var(--surf);border-left:1px solid var(--border);display:flex;flex-direction:column;overflow:hidden}
.ps{padding:14px 16px;border-bottom:1px solid var(--border)}
.ps label{display:block;font-size:11px;letter-spacing:.08em;color:var(--muted);text-transform:uppercase;margin-bottom:8px;font-weight:600}
.stats-row{display:flex;gap:8px;flex-wrap:wrap}
.stat-chip{flex:1;min-width:70px;background:var(--surf2);border:1px solid var(--border);border-radius:10px;padding:8px 10px;text-align:center}
.stat-chip .val{font-size:20px;font-weight:800;color:var(--fg);font-family:'DM Mono',monospace}
.stat-chip .lbl{font-size:10px;color:var(--muted);text-transform:uppercase;margin-top:2px}
.stat-chip.warn .val{color:var(--warn)}
.stat-chip.ok .val{color:var(--ok)}
.inp{width:100%;padding:8px 10px;background:var(--surf2);border:1px solid var(--border);border-radius:8px;color:var(--fg);font-family:'DM Mono',monospace;font-size:14px;outline:none;transition:border .2s}
.inp:focus{border-color:var(--accent2)}
.btn{display:inline-flex;align-items:center;gap:6px;padding:8px 14px;border-radius:8px;border:1px solid var(--border);background:var(--surf2);color:var(--fg);font-family:'Syne',sans-serif;font-size:13px;font-weight:700;cursor:pointer;transition:all .18s;white-space:nowrap}
.btn:hover{background:var(--surf);border-color:rgba(255,255,255,.18)}
.btn.primary{background:var(--accent);border-color:var(--accent);color:#0d1117}
.btn.primary:hover{background:#f5c33a}
.btn.danger{background:rgba(248,81,73,.12);border-color:var(--err);color:var(--err)}
.btn.danger:hover{background:rgba(248,81,73,.25)}
.btn.sm{padding:5px 10px;font-size:12px}
.row{display:flex;gap:8px;align-items:center;flex-wrap:wrap}
.drop-zone{border:2px dashed var(--border);border-radius:12px;padding:16px;text-align:center;cursor:pointer;transition:all .2s;color:var(--muted);font-size:13px}
.drop-zone:hover,.drop-zone.drag-over{border-color:var(--accent2);color:var(--accent2);background:rgba(88,166,255,.04)}
.drop-zone input{display:none}
#tourList{flex:1;overflow-y:auto;padding:10px 12px}
#tourList::-webkit-scrollbar{width:5px}
#tourList::-webkit-scrollbar-thumb{background:var(--border);border-radius:3px}
.tour-card{background:var(--surf2);border:1px solid var(--border);border-radius:12px;margin-bottom:10px;overflow:hidden}
.tour-card-header{display:flex;align-items:center;gap:8px;padding:10px 12px;cursor:pointer}
.tour-dot{width:12px;height:12px;border-radius:50%;flex-shrink:0}
.tour-title{flex:1;font-weight:700;font-size:14px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.tour-meta{font-size:12px;color:var(--muted);font-family:'DM Mono',monospace;flex-shrink:0}
.tour-actions{display:flex;gap:4px;flex-shrink:0}
.tour-body{padding:0 12px 12px 12px;border-top:1px solid var(--border)}
.tour-body.hidden{display:none}
.point-list{max-height:180px;overflow-y:auto;margin:8px 0}
.point-item{display:flex;align-items:center;gap:6px;padding:4px 6px;border-radius:6px;font-size:12px;font-family:'DM Mono',monospace;cursor:grab}
.point-item:hover{background:rgba(255,255,255,.05)}
.point-item .pos{color:var(--muted);width:24px;text-align:right;flex-shrink:0}
.point-item .bc{flex:1;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.point-item .rm{cursor:pointer;color:var(--err);opacity:0;font-size:14px}
.point-item:hover .rm{opacity:1}
.point-item.dragging{opacity:.4}
.point-item.drag-over-top{border-top:2px solid var(--accent2)}
.point-item.drag-over-bottom{border-bottom:2px solid var(--accent2)}
/* SCANNER */
#page-scanner{background:var(--bg);flex-direction:column;align-items:center;justify-content:flex-start;padding:24px 16px;overflow-y:auto;gap:20px}
.scanner-card{width:min(700px,100%);background:var(--surf);border:1px solid var(--border);border-radius:20px;padding:24px;display:flex;flex-direction:column;gap:18px}
.scanner-display{min-height:200px;border-radius:16px;border:2px solid var(--border);background:#060a10;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px;transition:border-color .3s;padding:20px}
.scanner-display.state-ok{border-color:var(--ok);background:rgba(63,185,80,.04)}
.scanner-display.state-err{border-color:var(--err);background:rgba(248,81,73,.04)}
.display-main{font-size:clamp(48px,10vw,120px);font-weight:800;letter-spacing:2px;text-align:center;line-height:1;color:var(--muted);font-family:'DM Mono',monospace}
.display-main.ok{color:var(--ok)}
.display-main.err{color:var(--err)}
.display-sub{font-size:18px;color:var(--muted);font-family:'DM Mono',monospace;text-align:center}
.display-sub.ok{color:var(--ok)}
.display-sub.err{color:var(--err)}
.scan-input-row{display:flex;gap:10px}
.scan-input{flex:1;font-size:18px;padding:14px 16px;border-radius:12px;border:1px solid var(--border);background:var(--surf2);color:var(--fg);font-family:'DM Mono',monospace;outline:none}
.scan-input:focus{border-color:var(--accent2)}
.scan-input:disabled{opacity:.4}
.history-table{width:100%;border-collapse:collapse;font-family:'DM Mono',monospace;font-size:13px}
.history-table th{color:var(--muted);text-align:left;padding:6px 8px;font-weight:600;font-size:11px;text-transform:uppercase;border-bottom:1px solid var(--border)}
.history-table td{padding:6px 8px;border-bottom:1px solid rgba(255,255,255,.04)}
.history-table .ok{color:var(--ok)}
.history-table .err{color:var(--err)}
.history-wrap{max-height:260px;overflow-y:auto;border-radius:10px;border:1px solid var(--border)}
.scanner-stats{display:flex;gap:10px;flex-wrap:wrap}
.scanner-stat{flex:1;min-width:100px;background:var(--surf2);border:1px solid var(--border);border-radius:12px;padding:14px;text-align:center}
.scanner-stat .v{font-size:28px;font-weight:800;font-family:'DM Mono',monospace}
.scanner-stat .l{font-size:11px;color:var(--muted);text-transform:uppercase;margin-top:4px}
/* MODAL */
.modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,.75);z-index:2000;display:flex;align-items:center;justify-content:center;padding:20px}
.modal-overlay.hidden{display:none}
.modal{background:var(--surf);border:1px solid var(--border);border-radius:16px;padding:24px;width:min(480px,100%);max-height:85vh;overflow-y:auto;display:flex;flex-direction:column;gap:16px}
.modal h2{font-size:18px;font-weight:800}
.modal-actions{display:flex;gap:10px;justify-content:flex-end}
/* LEAFLET */
.tour-label-tt{background:rgba(13,17,23,0.85)!important;border:none!important;border-radius:8px!important;color:#fff!important;font-weight:800!important;font-size:13px!important;padding:4px 10px!important;white-space:nowrap!important}
.tour-label-tt::before{display:none!important}
.cp-tooltip{background:rgba(13,17,23,0.72)!important;border:none!important;border-radius:6px!important;color:#e6edf3!important;font-size:11px!important;font-weight:700!important;padding:2px 7px!important;white-space:nowrap!important;pointer-events:none!important}
.cp-tooltip::before{display:none!important}
.leaflet-control-zoom a,.leaflet-draw-toolbar a{background:#2a3441!important;color:#fff!important;border-color:#4a5568!important;width:33px!important;height:33px!important;line-height:33px!important;font-size:16px!important}
.leaflet-control-zoom a:hover,.leaflet-draw-toolbar a:hover{background:#3a4a5c!important;color:#f0b429!important;border-color:#f0b429!important}
.leaflet-draw-toolbar a{background-size:300px 33px!important}
.empty-state{color:var(--muted);font-size:13px;text-align:center;padding:20px}
#toast{position:fixed;bottom:20px;left:50%;transform:translateX(-50%);background:#222;color:#fff;padding:10px 20px;border-radius:20px;font-size:14px;font-weight:700;z-index:9999;opacity:0;transition:opacity .3s;pointer-events:none;white-space:nowrap}
</style>
</head>
<body>
<div id="app-tabs">
  <button class="tab-btn active" onclick="switchTab('carte')"><span style="font-size:18px">🗺️</span> Carte & Tournées</button>
  <button class="tab-btn" onclick="switchTab('scanner')"><span style="font-size:18px">📦</span> Scanner<span class="badge-count hidden" id="history-badge">0</span></button>
</div>

<!-- PAGE CARTE -->
<div id="page-carte" class="page active">
  <div id="map"></div>
  <div id="panel">
    <div class="ps">
      <label>Fichier Excel</label>
      <div class="drop-zone" id="dropZone" onclick="document.getElementById('fileInput').click()">
        <input type="file" id="fileInput" accept=".xlsx,.xls,.csv"/>
        <div id="dropLabel">📂 Cliquez ou glissez votre Excel ici</div>
      </div>
    </div>
    <div class="ps">
      <div class="stats-row">
        <div class="stat-chip"><div class="val" id="stat-total">0</div><div class="lbl">Total</div></div>
        <div class="stat-chip warn"><div class="val" id="stat-unassigned">0</div><div class="lbl">Non assignés</div></div>
        <div class="stat-chip ok"><div class="val" id="stat-assigned">0</div><div class="lbl">Assignés</div></div>
        <div class="stat-chip"><div class="val" id="stat-sel">0</div><div class="lbl">Sélection</div></div>
      </div>
    </div>
    <div class="ps">
      <label>Point de départ global 🏠</label>
      <div class="row" style="margin-bottom:6px">
        <input class="inp" type="number" id="depotLat" placeholder="Latitude" step="any" style="flex:1"/>
        <input class="inp" type="number" id="depotLon" placeholder="Longitude" step="any" style="flex:1"/>
      </div>
      <div class="row">
        <button class="btn sm" id="btnSetDepot">📍 Définir</button>
        <button class="btn sm" id="btnPickDepot">🖱️ Carte</button>
        <button class="btn sm danger" id="btnClearDepot" style="display:none">✕ Dépôt</button>
      </div>
      <div id="depotInfo" style="display:none;margin-top:6px">
        <span style="display:inline-flex;align-items:center;gap:6px;padding:4px 10px;border-radius:20px;background:rgba(88,166,255,.15);border:1px solid var(--accent2);color:var(--accent2);font-size:12px;font-weight:700">🏠 <span id="depotCoords"></span></span>
      </div>
    </div>
    <div class="ps">
      <label>Nom de la tournée</label>
      <input class="inp" type="text" id="tourName" placeholder="ex: A1, Zone-Nord…" style="margin-bottom:10px"/>
      <div class="row">
        <button class="btn primary" id="btnAssign">✅ Enregistrer</button>
        <button class="btn" id="btnClearSel">🗑️ Vider sél.</button>
      </div>
      <div style="font-size:12px;color:var(--muted);margin-top:6px">Dessinez un rectangle/polygone puis cliquez "Enregistrer".</div>
    </div>
    <div class="ps">
      <div class="row">
        <button class="btn" id="btnOptimize">⚡ Optimiser tout</button>
        <label style="display:flex;align-items:center;gap:6px;font-size:12px;color:var(--muted);cursor:pointer;white-space:nowrap">
          <input type="checkbox" id="chkRetour" style="accent-color:var(--accent)"/> Retour dépôt
        </label>
        <button class="btn primary" id="btnExport">⬇️ JSON</button>
      </div>
      <div class="row" style="margin-top:8px">
        <button class="btn" id="btnToggleCP">🗂️ CP couleurs : ON</button>
      </div>
    </div>
    <div id="tourList"><div class="empty-state">Chargez votre Excel.<br/>Colonnes A (codes-barres) et Z (GPS).</div></div>
  </div>
</div>

<!-- PAGE SCANNER -->
<div id="page-scanner" class="page">
  <div class="scanner-card">
    <div style="font-size:20px;font-weight:800">Scanner de tournée</div>
    <div>
      <label style="display:block;font-size:11px;text-transform:uppercase;color:var(--muted);margin-bottom:8px">Fichier JSON exporté</label>
      <div class="drop-zone" id="scanDropZone" onclick="document.getElementById('scanFileInput').click()">
        <input type="file" id="scanFileInput" accept=".json"/>
        <div id="scanDropLabel">📂 Glissez ou cliquez pour charger le JSON</div>
      </div>
    </div>
    <div class="scanner-stats">
      <div class="scanner-stat"><div class="v" id="sc-total">0</div><div class="l">Codes</div></div>
      <div class="scanner-stat"><div class="v" id="sc-tours">0</div><div class="l">Tournées</div></div>
      <div class="scanner-stat"><div class="v ok" id="sc-found">0</div><div class="l">Trouvés</div></div>
      <div class="scanner-stat"><div class="v err" id="sc-unknown">0</div><div class="l">Inconnus</div></div>
    </div>
    <div class="scanner-display" id="scanDisplay">
      <div class="display-main" id="scanMain">EN ATTENTE</div>
      <div class="display-sub" id="scanSub"></div>
    </div>
    <div class="scan-input-row">
      <input class="scan-input" id="scanInput" type="text" placeholder="Place le curseur ici et scanne…" disabled/>
      <button class="btn" id="scanClear" disabled>Effacer</button>
      <button class="btn danger" id="scanResetHist">🗑️ Hist.</button>
    </div>
    <div>
      <div style="font-size:12px;color:var(--muted);margin-bottom:8px">Historique</div>
      <div class="history-wrap">
        <table class="history-table">
          <thead><tr><th>#</th><th>Code</th><th>Tournée</th><th>Position</th></tr></thead>
          <tbody id="historyBody"></tbody>
        </table>
      </div>
    </div>
  </div>
</div>

<!-- MODAL EDIT TOUR -->
<div class="modal-overlay hidden" id="editModal">
  <div class="modal">
    <h2>✏️ Modifier la tournée</h2>
    <div>
      <label style="font-size:12px;color:var(--muted)">Nom</label>
      <input class="inp" type="text" id="editTourName" style="margin-top:6px"/>
    </div>
    <div class="modal-actions">
      <button class="btn" onclick="closeEditModal()">Annuler</button>
      <button class="btn primary" onclick="saveEditModal()">Enregistrer</button>
    </div>
  </div>
</div>

<!-- MODAL DEPOT TOURNEE -->
<div class="modal-overlay hidden" id="depotTourModal">
  <div class="modal">
    <h2>🏠 Départ — <span id="depotTourTitle"></span></h2>
    <p style="font-size:13px;color:var(--muted)">Laissez vide pour utiliser le départ global.</p>
    <div class="row">
      <input class="inp" type="number" id="depotTourLat" placeholder="Latitude" step="any" style="flex:1"/>
      <input class="inp" type="number" id="depotTourLon" placeholder="Longitude" step="any" style="flex:1"/>
    </div>
    <div class="modal-actions">
      <button class="btn danger" id="btnDepotTourClear">Supprimer</button>
      <button class="btn" onclick="closeDepotTourModal()">Annuler</button>
      <button class="btn primary" onclick="saveDepotTourModal()">Enregistrer</button>
    </div>
  </div>
</div>

<!-- MODAL QR -->
<div class="modal-overlay hidden" id="qrModal">
  <div class="modal" style="align-items:center;text-align:center">
    <h2 id="qrTitle">QR Code</h2>
    <p style="font-size:13px;color:var(--muted)">Le livreur scanne ce QR code avec l'application mobile.</p>
    <div id="qrCanvas" style="margin:12px 0;background:#fff;padding:12px;border-radius:8px"></div>
    <p id="qrSizeInfo" style="font-size:12px;color:var(--muted)"></p>
    <div class="modal-actions">
      <button class="btn" onclick="document.getElementById('qrModal').classList.add('hidden')">Fermer</button>
    </div>
  </div>
</div>

<div id="toast"></div>

<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
<script src="https://unpkg.com/leaflet-draw/dist/leaflet.draw.js"></script>
<script src="https://unpkg.com/xlsx/dist/xlsx.full.min.js"></script>
<script>
// ══════════════════════════════════════════════════════
//  ÉTAT GLOBAL
// ══════════════════════════════════════════════════════
var points=[], tours=[], selection=new Set(), editingTourId=null;
var depot=null, pickingDepot=false, editingDepotTourId=null;
var scanMap={}, foundCount=0, unknownCount=0, historyRows=[];
var tourIdCounter=0;

// ══════════════════════════════════════════════════════
//  TOAST
// ══════════════════════════════════════════════════════
function toast(msg,dur){
  dur=dur||2500;
  var el=document.getElementById('toast');
  el.textContent=msg; el.style.opacity='1';
  setTimeout(function(){el.style.opacity='0';},dur);
}

// ══════════════════════════════════════════════════════
//  TABS
// ══════════════════════════════════════════════════════
function switchTab(tab){
  document.querySelectorAll('.tab-btn').forEach(function(b,i){b.classList.toggle('active',['carte','scanner'][i]===tab);});
  document.getElementById('page-carte').classList.toggle('active',tab==='carte');
  document.getElementById('page-scanner').classList.toggle('active',tab==='scanner');
  if(tab==='carte') map.invalidateSize();
}

// ══════════════════════════════════════════════════════
//  CARTE
// ══════════════════════════════════════════════════════
var map=L.map('map').setView([44.010244,4.888484],11);
L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png',{
  attribution:'&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a>',maxZoom:19,crossOrigin:true
}).addTo(map);

var drawnItems=new L.FeatureGroup().addTo(map);
var tourDrawnLayers={};
map.addControl(new L.Control.Draw({
  draw:{marker:false,circle:false,circlemarker:false,polyline:false,rectangle:true,polygon:true},
  edit:{featureGroup:drawnItems}
}));
var markersLayer=L.layerGroup().addTo(map);

function makeIcon(color){
  return L.divIcon({className:'',
    html:'<div style="width:11px;height:11px;border-radius:50%;background:'+color+';border:2px solid rgba(255,255,255,.8);box-shadow:0 1px 4px rgba(0,0,0,.6)"></div>',
    iconSize:[11,11],iconAnchor:[5,5]});
}

function getAssignedBarcodes(){var s=new Set();tours.forEach(function(t){t.barcodes.forEach(function(b){s.add(b);});});return s;}

function getTourColor(barcode){
  for(var i=0;i<tours.length;i++) if(tours[i].barcodes.indexOf(barcode)>=0) return tours[i].color;
  return null;
}

function drawAllPoints(){
  markersLayer.clearLayers();
  var assigned=getAssignedBarcodes();
  var unassigned=0;
  points.forEach(function(p){
    var color;
    if(assigned.has(p.barcode)){
      color=getTourColor(p.barcode);
    } else {
      unassigned++;
      color=getCPColor(p);
    }
    L.marker([p.lat,p.lon],{icon:makeIcon(color)})
      .bindTooltip(p.barcode+(p.cp?' — '+p.cp:'')+(p.ville?' '+p.ville:''),{direction:'top'})
      .addTo(markersLayer);
  });
  updateStats(unassigned);
}

function updateStats(unassigned){
  var u=unassigned!==undefined?unassigned:countUnassigned();
  document.getElementById('stat-total').textContent=points.length;
  document.getElementById('stat-unassigned').textContent=u;
  document.getElementById('stat-assigned').textContent=points.length-u;
  document.getElementById('stat-sel').textContent=selection.size;
}
function countUnassigned(){var a=getAssignedBarcodes();return points.filter(function(p){return !a.has(p.barcode);}).length;}

// ══════════════════════════════════════════════════════
//  CODES POSTAUX — coloration par distance GPS
// ══════════════════════════════════════════════════════
var cpVisible=true;
var CP_PALETTE=['#e63946','#2196f3','#ff9800','#2e7d32','#7b1fa2','#00838f','#6d4c41','#c62828','#1565c0','#ef6c00','#558b2f','#ad1457'];
var cpColorIdx={};

function assignCPColors(){
  var cpPts={};
  points.forEach(function(p){
    if(!p.cp||!p.lat||!p.lon) return;
    if(!cpPts[p.cp]) cpPts[p.cp]={lats:[],lons:[]};
    cpPts[p.cp].lats.push(p.lat); cpPts[p.cp].lons.push(p.lon);
  });
  var cps=Object.keys(cpPts);
  var centroids={};
  cps.forEach(function(cp){
    var d=cpPts[cp];
    centroids[cp]={
      lat:d.lats.reduce(function(a,b){return a+b;},0)/d.lats.length,
      lon:d.lons.reduce(function(a,b){return a+b;},0)/d.lons.length
    };
  });
  var SEUIL=12;
  var adj={};
  cps.forEach(function(cp){adj[cp]=new Set();});
  for(var i=0;i<cps.length;i++){
    for(var j=i+1;j<cps.length;j++){
      var a=centroids[cps[i]],b=centroids[cps[j]];
      var dlat=(b.lat-a.lat)*Math.PI/180;
      var dlon=(b.lon-a.lon)*Math.PI/180;
      var la=(a.lat+b.lat)/2*Math.PI/180;
      var dist=Math.sqrt(dlat*dlat+(dlon*Math.cos(la))*(dlon*Math.cos(la)))*6371;
      if(dist<SEUIL){adj[cps[i]].add(cps[j]);adj[cps[j]].add(cps[i]);}
    }
  }
  var sorted=cps.slice().sort(function(a,b){return adj[b].size-adj[a].size;});
  sorted.forEach(function(cp){delete cpColorIdx[cp];});
  sorted.forEach(function(cp){
    var used=new Set();
    adj[cp].forEach(function(n){if(cpColorIdx[n]!==undefined) used.add(cpColorIdx[n]);});
    var idx=0; while(used.has(idx)) idx++;
    cpColorIdx[cp]=idx%CP_PALETTE.length;
  });
}
function getCPColor(p){
  if(!cpVisible||!p.cp) return '#ff2222';
  if(cpColorIdx[p.cp]===undefined) return '#ff2222';
  return CP_PALETTE[cpColorIdx[p.cp]];
}
document.getElementById('btnToggleCP').addEventListener('click',function(){
  cpVisible=!cpVisible;
  document.getElementById('btnToggleCP').textContent='🗂️ CP couleurs : '+(cpVisible?'ON':'OFF');
  drawAllPoints();
});

// ══════════════════════════════════════════════════════
//  EXCEL
// ══════════════════════════════════════════════════════
function cellVal(sheet,r,c){var cell=sheet[XLSX.utils.encode_cell({r:r,c:c})];return(cell&&cell.v!=null)?String(cell.v).trim():'';}
function parseLatLon(s){
  if(!s) return null;
  var t=String(s).trim().replace(/[;|]/g,',').replace(/[()[\]]/g,'');
  var parts=t.split(/[, ]+/).filter(Boolean);
  if(parts.length>=2){
    var a=parseFloat(parts[0].replace(',','.')), b=parseFloat(parts[1].replace(',','.'));
    if(isFinite(a)&&isFinite(b)){
      if(Math.abs(a)<=90&&Math.abs(b)<=180) return{lat:a,lon:b};
      if(Math.abs(b)<=90&&Math.abs(a)<=180) return{lat:b,lon:a};
    }
  }
  return null;
}
function loadSheet(sheet){
  var range=XLSX.utils.decode_range(sheet['!ref']);
  var tmp=[];
  for(var r=range.s.r+1;r<=range.e.r;r++){
    var barcode=cellVal(sheet,r,0), gps=cellVal(sheet,r,25);
    if(!barcode||!gps) continue;
    var ll=parseLatLon(gps); if(!ll) continue;
    tmp.push({barcode:barcode,lat:ll.lat,lon:ll.lon,
      telephone:cellVal(sheet,r,12),ville:cellVal(sheet,r,17),
      cp:cellVal(sheet,r,6),adresse:cellVal(sheet,r,19)});
  }
  var seen=new Set();
  points=tmp.filter(function(p){return !seen.has(p.barcode)&&seen.add(p.barcode);});
  Object.keys(cpColorIdx).forEach(function(k){delete cpColorIdx[k];});
  assignCPColors();
  drawAllPoints();
  if(points.length) map.fitBounds(L.latLngBounds(points.map(function(p){return[p.lat,p.lon];})).pad(.1));
  document.getElementById('dropLabel').textContent='✅ '+points.length+' points chargés';
  refreshTourList();
}
async function handleExcelFile(file){
  var buf=await file.arrayBuffer();
  var wb=XLSX.read(buf,{type:'array'});
  var sn=wb.SheetNames.indexOf('Feuil1')>=0?'Feuil1':wb.SheetNames[0];
  loadSheet(wb.Sheets[sn]);
}
document.getElementById('fileInput').addEventListener('change',function(e){if(e.target.files[0]) handleExcelFile(e.target.files[0]);});
var dz=document.getElementById('dropZone');
dz.addEventListener('dragover',function(e){e.preventDefault();dz.classList.add('drag-over');});
dz.addEventListener('dragleave',function(){dz.classList.remove('drag-over');});
dz.addEventListener('drop',function(e){e.preventDefault();dz.classList.remove('drag-over');if(e.dataTransfer.files[0]) handleExcelFile(e.dataTransfer.files[0]);});

// ══════════════════════════════════════════════════════
//  SÉLECTION DESSIN
// ══════════════════════════════════════════════════════
function ptInRect(ll,rect){return rect.getBounds().contains(ll);}
function ptInPoly(ll,poly){
  var x=ll.lat,y=ll.lng,arr=poly.getLatLngs()[0];
  var inside=false;
  for(var i=0,j=arr.length-1;i<arr.length;j=i++){
    var xi=arr[i].lat,yi=arr[i].lng,xj=arr[j].lat,yj=arr[j].lng;
    if(((yi>y)!=(yj>y))&&(x<(xj-xi)*(y-yi)/(yj-yi+1e-12)+xi)) inside=!inside;
  }
  return inside;
}
function recount(){
  selection.clear();
  var layers=drawnItems.getLayers();
  var pending=layers.filter(function(l){return Object.values(tourDrawnLayers).indexOf(l)<0;});
  if(!pending.length){updateStats();return;}
  var last=pending[pending.length-1];
  points.forEach(function(p){
    var ll=L.latLng(p.lat,p.lon);
    if(last instanceof L.Rectangle?ptInRect(ll,last):ptInPoly(ll,last)) selection.add(p.barcode);
  });
  updateStats();
}
map.on(L.Draw.Event.CREATED,function(e){drawnItems.addLayer(e.layer);recount();});
map.on(L.Draw.Event.EDITED,recount);
map.on(L.Draw.Event.DELETED,recount);

// ══════════════════════════════════════════════════════
//  OPTIMISATION
// ══════════════════════════════════════════════════════
function nnOrder(pts,startLat,startLon){
  var visited=new Array(pts.length).fill(false);
  var result=[];
  var curLat=startLat,curLon=startLon;
  while(result.length<pts.length){
    var bestIdx=-1,bestD=Infinity;
    for(var i=0;i<pts.length;i++){
      if(visited[i]) continue;
      var d=Math.hypot(curLat-pts[i].lat,curLon-pts[i].lon);
      if(d<bestD){bestD=d;bestIdx=i;}
    }
    if(bestIdx<0) break;
    visited[bestIdx]=true; result.push(bestIdx);
    curLat=pts[bestIdx].lat; curLon=pts[bestIdx].lon;
  }
  return result;
}

// Nearest-neighbor synchrone (création immédiate de tournée)
function optimizeOrder(barcodes,tourDepot,returnToDepot){
  var pts=barcodes.map(function(b){return points.find(function(p){return p.barcode===b;});}).filter(Boolean);
  if(!pts.length) return barcodes.slice();
  if(pts.length===1) return [pts[0].barcode];
  var start=tourDepot||depot||null;
  var sLat,sLon;
  var result=[];
  if(start){sLat=start.lat;sLon=start.lon;}
  else{
    var best=0,bestScore=-Infinity;
    pts.forEach(function(p,i){var s=p.lat-p.lon;if(s>bestScore){bestScore=s;best=i;}});
    result.push(pts[best].barcode);
    sLat=pts[best].lat;sLon=pts[best].lon;
    pts=pts.filter(function(p,i){return i!==best;});
  }
  var idxs=nnOrder(pts,sLat,sLon);
  idxs.forEach(function(i){result.push(pts[i].barcode);});
  return result;
}

// OSRM asynchrone
async function optimizeOrderOSRM(barcodes,tourDepot,returnToDepot){
  var pts=barcodes.map(function(b){return points.find(function(p){return p.barcode===b;});}).filter(Boolean);
  if(!pts.length) return barcodes.slice();
  if(pts.length===1) return [pts[0].barcode];
  var start=tourDepot||depot||null;
  var osrmPts=pts.slice(0,100);
  var restPts=pts.slice(100);
  var orderedPts=[];
  try{
    var coordsList=(start?[[start.lon,start.lat]]:[]).concat(osrmPts.map(function(p){return[p.lon,p.lat];}));
    var coordsStr=coordsList.map(function(c){return c[0]+','+c[1];}).join(';');
    var params='roundtrip='+(returnToDepot&&start?'true':'false');
    if(start) params+='&source=first';
    if(returnToDepot&&start) params+='&destination=last';
    var url='https://router.project-osrm.org/trip/v1/driving/'+coordsStr+'?'+params+'&overview=false';
    var resp=await fetch(url,{signal:AbortSignal.timeout(8000)});
    var data=await resp.json();
    if(data.code==='Ok'&&data.waypoints){
      var offset=start?1:0;
      var wps=data.waypoints
        .map(function(w,i){return{wi:w.waypoint_index,orig:i-offset};})
        .filter(function(w){return w.orig>=0&&w.orig<osrmPts.length;})
        .sort(function(a,b){return a.wi-b.wi;});
      if(wps.length===osrmPts.length) orderedPts=wps.map(function(w){return osrmPts[w.orig];});
    }
  }catch(e){console.warn('OSRM indisponible:',e.message);}
  if(!orderedPts.length){
    var sLat2=start?start.lat:null,sLon2=start?start.lon:null;
    if(!sLat2){var b2=0,bs=-Infinity;osrmPts.forEach(function(p,i){var s=p.lat-p.lon;if(s>bs){bs=s;b2=i;}});sLat2=osrmPts[b2].lat;sLon2=osrmPts[b2].lon;}
    nnOrder(osrmPts,sLat2,sLon2).forEach(function(i){orderedPts.push(osrmPts[i]);});
  }
  if(restPts.length){
    var last=orderedPts[orderedPts.length-1];
    nnOrder(restPts,last.lat,last.lon).forEach(function(i){orderedPts.push(restPts[i]);});
  }
  return orderedPts.map(function(p){return p.barcode;});
}

// ══════════════════════════════════════════════════════
//  TOURNÉES
// ══════════════════════════════════════════════════════
function rndColor(){return 'hsl('+Math.floor(Math.random()*360)+',80%,55%)';}

document.getElementById('btnAssign').addEventListener('click',function(){
  if(!selection.size){alert('Dessinez une zone pour sélectionner des points.');return;}
  var name=(document.getElementById('tourName').value||'').trim();
  if(!name){alert('Donnez un nom à la tournée.');return;}
  var color=rndColor();
  var barcodes=Array.from(selection);
  var retour=document.getElementById('chkRetour').checked;
  var order=optimizeOrder(barcodes,null,retour);
  var id=++tourIdCounter;
  var allLayers=drawnItems.getLayers();
  var pending=allLayers.filter(function(l){return Object.values(tourDrawnLayers).indexOf(l)<0;});
  var last=pending.length?pending[pending.length-1]:null;
  if(last&&last.setStyle){
    last.setStyle({color:color,fillColor:color,fillOpacity:.15,weight:2});
    last.bindTooltip(name,{permanent:true,direction:'center',className:'tour-label-tt'});
    tourDrawnLayers[id]=last;
  }
  tours.push({id:id,name:name,color:color,barcodes:barcodes,order:order,depot:null});
  document.getElementById('tourName').value='';
  selection.clear();
  drawAllPoints(); refreshTourList(); rebuildScanMap();
  // Lancer OSRM en arrière-plan
  var retour2=document.getElementById('chkRetour').checked;
  optimizeOrderOSRM(barcodes,null,retour2).then(function(ord){
    var t=tours.find(function(t){return t.id===id;});
    if(t){t.order=ord;refreshTourList();rebuildScanMap();toast('✅ Tournée '+name+' optimisée (OSRM)',2000);}
  });
});

document.getElementById('btnClearSel').addEventListener('click',function(){
  var allLayers=drawnItems.getLayers();
  var pending=allLayers.filter(function(l){return Object.values(tourDrawnLayers).indexOf(l)<0;});
  pending.forEach(function(l){drawnItems.removeLayer(l);});
  selection.clear(); updateStats();
});

document.getElementById('btnOptimize').addEventListener('click',async function(){
  var btn=this;
  btn.textContent='⏳ OSRM…'; btn.disabled=true;
  var retour=document.getElementById('chkRetour').checked;
  try{
    await Promise.all(tours.map(async function(t){
      t.order=await optimizeOrderOSRM(t.barcodes,t.depot||null,retour);
    }));
    refreshTourList(); rebuildScanMap();
    toast('✅ Itinéraires optimisés via OSRM'+(depot?' (départ défini)':''),3000);
  }catch(e){toast('⚠️ Erreur : '+e.message,4000);}
  finally{btn.textContent='⚡ Optimiser tout'; btn.disabled=false;}
});

function deleteTour(tourId){
  if(!confirm('Supprimer cette tournée ?')) return;
  if(tourDrawnLayers[tourId]){drawnItems.removeLayer(tourDrawnLayers[tourId]);delete tourDrawnLayers[tourId];}
  tours=tours.filter(function(t){return t.id!==tourId;});
  drawAllPoints(); refreshTourList(); rebuildScanMap();
}
function removePointFromTour(tourId,barcode){
  var t=tours.find(function(t){return t.id===tourId;}); if(!t) return;
  t.barcodes=t.barcodes.filter(function(b){return b!==barcode;});
  t.order=t.order.filter(function(b){return b!==barcode;});
  drawAllPoints(); refreshTourList(); rebuildScanMap();
}
function openEditModal(tourId){
  var t=tours.find(function(t){return t.id===tourId;}); if(!t) return;
  editingTourId=tourId;
  document.getElementById('editTourName').value=t.name;
  document.getElementById('editModal').classList.remove('hidden');
}
function closeEditModal(){document.getElementById('editModal').classList.add('hidden');editingTourId=null;}
function saveEditModal(){
  var t=tours.find(function(t){return t.id===editingTourId;});
  var name=(document.getElementById('editTourName').value||'').trim();
  if(t&&name){
    t.name=name;
    var layer=tourDrawnLayers[t.id];
    if(layer&&layer.setTooltipContent) layer.setTooltipContent(name);
    refreshTourList(); rebuildScanMap();
  }
  closeEditModal();
}

// Drag & drop reorder
var dragSrc=null;
function onDragStart(e,tourId,idx){dragSrc={tourId:tourId,orderIdx:idx};e.currentTarget.classList.add('dragging');e.dataTransfer.effectAllowed='move';}
function onDragEnd(e){e.currentTarget.classList.remove('dragging');}
function onDragOver(e,el,idx){
  e.preventDefault();
  document.querySelectorAll('.point-item').forEach(function(i){i.classList.remove('drag-over-top','drag-over-bottom');});
  if(!dragSrc) return;
  idx>dragSrc.orderIdx?el.classList.add('drag-over-bottom'):el.classList.add('drag-over-top');
}
function onDrop(e,tourId,toIdx){
  e.preventDefault();
  document.querySelectorAll('.point-item').forEach(function(i){i.classList.remove('drag-over-top','drag-over-bottom');});
  if(!dragSrc||dragSrc.tourId!==tourId) return;
  var t=tours.find(function(t){return t.id===tourId;}); if(!t) return;
  var item=t.order.splice(dragSrc.orderIdx,1)[0];
  t.order.splice(toIdx>dragSrc.orderIdx?toIdx-1:toIdx,0,item);
  dragSrc=null; refreshTourList(); rebuildScanMap();
}
function toggleTourBody(id){var el=document.getElementById('tour-body-'+id);if(el) el.classList.toggle('hidden');}

function reoptimizeTour(id){
  var t=tours.find(function(t){return t.id===id;}); if(!t) return;
  var retour=document.getElementById('chkRetour').checked;
  toast('⏳ Optimisation OSRM…',10000);
  optimizeOrderOSRM(t.barcodes,t.depot||null,retour).then(function(ord){
    t.order=ord; refreshTourList(); rebuildScanMap();
    toast('✅ Tournée '+t.name+' optimisée !',2500);
  });
}

function refreshTourList(){
  var el=document.getElementById('tourList');
  if(!tours.length){el.innerHTML='<div class="empty-state">Aucune tournée créée.</div>';return;}
  el.innerHTML=tours.map(function(t){
    var order=t.order.length?t.order:t.barcodes;
    var items=order.map(function(bc,idx){
      var safe=bc.replace(/'/g,"\\'");
      return '<div class="point-item" draggable="true"'+
        ' ondragstart="onDragStart(event,'+t.id+','+idx+')"'+
        ' ondragend="onDragEnd(event)"'+
        ' ondragover="onDragOver(event,this,'+idx+')"'+
        ' ondrop="onDrop(event,'+t.id+','+idx+')">'
        +'<span class="pos">'+(idx+1)+'</span>'
        +'<span class="bc">'+bc+'</span>'
        +'<span class="rm" onclick="removePointFromTour('+t.id+',\''+safe+'\')">✕</span>'
        +'</div>';
    }).join('');
    var depotStyle=t.depot?'border-color:var(--accent2);color:var(--accent2)':'';
    return '<div class="tour-card">'
      +'<div class="tour-card-header" onclick="toggleTourBody('+t.id+')">'
      +'<div class="tour-dot" style="background:'+t.color+'"></div>'
      +'<div class="tour-title" title="'+t.name+'">'+t.name+'</div>'
      +'<div class="tour-meta">'+t.barcodes.length+'pts</div>'
      +'<div class="tour-actions" onclick="event.stopPropagation()">'
      +'<button class="btn sm" title="Carte" onclick="openTourMap('+t.id+')">🗺️</button>'
      +'<button class="btn sm" title="Départ" onclick="openDepotTourModal('+t.id+')" style="'+depotStyle+'">🏠</button>'
      +'<button class="btn sm" title="QR" onclick="showQR('+t.id+')">📱</button>'
      +'<button class="btn sm" title="CSV" onclick="exportTourCSV('+t.id+')">⬇️</button>'
      +'<button class="btn sm" title="Modifier" onclick="openEditModal('+t.id+')">✏️</button>'
      +'<button class="btn sm danger" title="Supprimer" onclick="deleteTour('+t.id+')">🗑️</button>'
      +'</div></div>'
      +'<div class="tour-body hidden" id="tour-body-'+t.id+'">'
      +'<div style="font-size:11px;color:var(--muted);margin:8px 0 4px">Glissez pour réordonner :</div>'
      +'<div class="point-list">'+items+'</div>'
      +'<button class="btn sm" style="margin-top:8px" onclick="reoptimizeTour('+t.id+')">⚡ Ré-optimiser (OSRM)</button>'
      +'</div></div>';
  }).join('');
}

// ══════════════════════════════════════════════════════
//  CARTE TOURNÉE (nouvel onglet)
// ══════════════════════════════════════════════════════
function openTourMap(tourId){
  var t=tours.find(function(t){return t.id===tourId;}); if(!t) return;
  var order=t.order.length?t.order:t.barcodes;
  var pointMap={};
  points.forEach(function(p){pointMap[p.barcode]=p;});
  var pts=order.map(function(bc,i){var p=pointMap[bc];return p?Object.assign({},p,{pos:i+1}):null;}).filter(Boolean);
  if(!pts.length){alert('Aucun point GPS disponible.');return;}
  var startPt=t.depot||depot||null;
  var retour=document.getElementById('chkRetour').checked;
  var color=t.color;
  var tourName=t.name;
  var tourId2=t.id;

  var w=window.open('','_blank');
  if(!w) return;
  var d=w.document;
  d.open();
  d.write('<!DOCTYPE html><html><head>');
  d.write('<meta charset="utf-8"><title>Tournee '+tourName+'</title>');
  d.write('<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css">');
  d.write('<style>');
  d.write('*{box-sizing:border-box;margin:0;padding:0}');
  d.write('body{height:100vh;display:flex;flex-direction:column;font-family:-apple-system,BlinkMacSystemFont,sans-serif;background:#0d1117;color:#e6edf3}');
  d.write('#topbar{display:flex;align-items:center;gap:12px;padding:10px 14px;background:#161b22;border-bottom:1px solid rgba(255,255,255,.08);flex-shrink:0}');
  d.write('#topbar h1{font-size:15px;font-weight:700;flex:1}');
  d.write('#dist{font-size:13px;color:#8b949e;white-space:nowrap}');
  d.write('.save-btn{padding:7px 14px;background:#f0b429;border:none;border-radius:8px;font-weight:700;font-size:13px;cursor:pointer;color:#0d1117}');
  d.write('#main{display:flex;flex:1;min-height:0}');
  d.write('#map{flex:1}');
  d.write('#sidebar{width:300px;background:#161b22;border-left:1px solid rgba(255,255,255,.08);display:flex;flex-direction:column;overflow:hidden}');
  d.write('#sidebar-header{padding:10px 12px;border-bottom:1px solid rgba(255,255,255,.08);font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.08em;color:#8b949e}');
  d.write('#colis-list{flex:1;overflow-y:auto}');
  d.write('#colis-list::-webkit-scrollbar{width:4px}');
  d.write('#colis-list::-webkit-scrollbar-thumb{background:rgba(255,255,255,.1);border-radius:2px}');
  d.write('.colis-row{display:flex;align-items:center;gap:8px;padding:8px 10px;border-bottom:1px solid rgba(255,255,255,.05);cursor:grab;transition:background .15s}');
  d.write('.colis-row:hover{background:rgba(255,255,255,.04)}');
  d.write('.colis-row.dragging{opacity:.4;background:rgba(255,255,255,.08)}');
  d.write('.colis-row.drag-over{border-top:2px solid #f0b429}');
  d.write('.colis-num{width:26px;height:26px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;color:#000;flex-shrink:0}');
  d.write('.colis-info{flex:1;min-width:0}');
  d.write('.colis-bc{font-size:12px;font-weight:700;font-family:monospace;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}');
  d.write('.colis-addr{font-size:11px;color:#8b949e;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}');
  d.write('.mv-btns{display:flex;flex-direction:column;gap:2px;flex-shrink:0}');
  d.write('.mv-btn{width:22px;height:22px;border-radius:4px;border:1px solid rgba(255,255,255,.1);background:rgba(255,255,255,.05);color:#e6edf3;font-size:12px;display:flex;align-items:center;justify-content:center;cursor:pointer}');
  d.write('.mv-btn:hover{background:rgba(240,180,41,.2);border-color:#f0b429;color:#f0b429}');
  d.write('#loading{position:fixed;bottom:16px;left:50%;transform:translateX(-50%);background:rgba(0,0,0,.85);color:#fff;padding:8px 16px;border-radius:20px;font-size:13px;z-index:999;transition:opacity .4s}');
  d.write('@media(max-width:600px){#sidebar{width:100%;height:40vh;border-left:none;border-top:1px solid rgba(255,255,255,.08)}#main{flex-direction:column}}');
  d.write('</style></head><body>');
  d.write('<div id="topbar">');
  d.write('<h1>Tournee '+tourName+' — '+pts.length+' arrets</h1>');
  d.write('<span id="dist" title="Distance totale par la route">—</span>');
  d.write('<button class="save-btn" id="saveBtn">💾 Sauvegarder l'ordre</button>');
  d.write('</div>');
  d.write('<div id="main"><div id="map"></div>');
  d.write('<div id="sidebar">');
  d.write('<div id="sidebar-header">Ordre de passage — glissez pour modifier</div>');
  d.write('<div id="colis-list"></div>');
  d.write('</div></div>');
  d.write('<div id="loading">🛣️ Calcul itinéraire…</div>');

  // JS principal via blob
  var js='';
  js+='var currentPts='+JSON.stringify(pts)+';';
  js+='var startPt='+JSON.stringify(startPt)+';';
  js+='var retour='+JSON.stringify(retour)+';';
  js+='var color='+JSON.stringify(color)+';';
  js+='var routeLayer=null;';
  js+='var markersList=[];';
  js+='var debounceTimer=null;';
  js+='var tourId='+JSON.stringify(tourId2)+';';

  // Init carte
  js+='var map=L.map("map");';
  js+='L.tileLayer("https://tile.openstreetmap.org/{z}/{x}/{y}.png",{attribution:"OpenStreetMap",maxZoom:19,crossOrigin:true}).addTo(map);';

  // Marqueur dépôt
  js+='if(startPt) L.marker([startPt.lat,startPt.lon],{icon:L.divIcon({className:"",html:"<div style='font-size:24px;filter:drop-shadow(0 2px 4px rgba(0,0,0,.6))'>🏠</div>",iconSize:[28,28],iconAnchor:[14,24]})}).bindTooltip("Depart",{permanent:true,direction:"top"}).addTo(map);';

  // Fonction pour (re)dessiner les marqueurs
  js+='function drawMarkers(){';
  js+='  markersList.forEach(function(m){m.remove();});';
  js+='  markersList=[];';
  js+='  currentPts.forEach(function(p,i){';
  js+='    var m=L.marker([p.lat,p.lon],{icon:L.divIcon({className:"",';
  js+='      html:"<div style='background:"+color+";color:#000;border-radius:50%;width:26px;height:26px;display:flex;align-items:center;justify-content:center;font-weight:700;font-size:11px;border:2px solid #fff;box-shadow:0 2px 6px rgba(0,0,0,.4)'>"+(i+1)+"</div>",';
  js+='      iconSize:[26,26],iconAnchor:[13,13]})})';
  js+='      .bindTooltip("<b>"+(i+1)+"</b> — "+p.barcode+(p.adresse?"<br>"+p.adresse:"")+(p.ville?"<br>"+p.cp+" "+p.ville:""))';
  js+='      .addTo(map);';
  js+='    markersList.push(m);';
  js+='  });';
  js+='  if(!retour&&currentPts.length){';
  js+='    var last=currentPts[currentPts.length-1];';
  js+='    var m2=L.marker([last.lat,last.lon],{icon:L.divIcon({className:"",html:"<div style='font-size:20px;filter:drop-shadow(0 2px 4px rgba(0,0,0,.5))'>🏁</div>",iconSize:[26,26],iconAnchor:[13,26]})}).bindTooltip("Arrivee",{permanent:true,direction:"top"}).addTo(map);';
  js+='    markersList.push(m2);';
  js+='  }';
  js+='}';

  // Fonction OSRM
  js+='function loadRoute(){';
  js+='  showLoading();';
  js+='  var coords=(startPt?[[startPt.lon,startPt.lat]]:[])';
  js+='    .concat(currentPts.map(function(p){return[p.lon,p.lat];}))';
  js+='    .concat(retour&&startPt?[[startPt.lon,startPt.lat]]:[]);';
  js+='  if(coords.length<2){hideLoading();return;}';
  js+='  var segs=[]; for(var i=0;i<coords.length-1;i+=24) segs.push(coords.slice(i,Math.min(i+25,coords.length)));';
  js+='  var results=[]; var done=0; var totalKm=0;';
  js+='  segs.forEach(function(seg,si){';
  js+='    var url="https://router.project-osrm.org/route/v1/driving/"+seg.map(function(c){return c[0]+","+c[1];}).join(";")+"?overview=full&geometries=geojson";';
  js+='    fetch(url,{signal:AbortSignal.timeout(10000)})';
  js+='      .then(function(r){return r.json();})';
  js+='      .then(function(data){';
  js+='        if(data.code==="Ok"&&data.routes&&data.routes[0]){';
  js+='          results[si]=data.routes[0].geometry.coordinates.map(function(c){return[c[1],c[0]];});';
  js+='          totalKm+=data.routes[0].distance/1000;';
  js+='        }';
  js+='        done++; if(done===segs.length) applyRoute(results,totalKm);';
  js+='      })';
  js+='      .catch(function(){done++; if(done===segs.length) applyRoute(results,totalKm);});';
  js+='  });';
  js+='}';

  js+='function applyRoute(results,totalKm){';
  js+='  var flat=[]; results.forEach(function(s){if(s) flat=flat.concat(s);});';
  js+='  if(routeLayer){routeLayer.remove();}';
  js+='  if(flat.length>1){';
  js+='    routeLayer=L.polyline(flat,{color:color,weight:4,opacity:.85}).addTo(map);';
  js+='    document.getElementById("dist").textContent=totalKm.toFixed(1)+" km";';
  js+='  } else {';
  js+='    var fb=(startPt?[[startPt.lat,startPt.lon]]:[]).concat(currentPts.map(function(p){return[p.lat,p.lon];})).concat(retour&&startPt?[[startPt.lat,startPt.lon]]:[]);';
  js+='    routeLayer=L.polyline(fb,{color:color,weight:2.5,opacity:.5,dashArray:"6,6"}).addTo(map);';
  js+='    document.getElementById("dist").textContent="approx. (OSRM indisponible)";';
  js+='  }';
  js+='  hideLoading();';
  js+='}';

  js+='function showLoading(){var el=document.getElementById("loading");if(el) el.style.opacity="1";}';
  js+='function hideLoading(){var el=document.getElementById("loading");if(el){el.style.opacity="0";}}';

  // Debounce refresh (attend 600ms après la dernière modif avant de rappeler OSRM)
  js+='function refreshAll(){';
  js+='  drawMarkers();';
  js+='  clearTimeout(debounceTimer);';
  js+='  debounceTimer=setTimeout(loadRoute,600);';
  js+='}';

  // Liste colis drag & drop
  js+='var dragIdx=null;';
  js+='function renderList(){';
  js+='  var el=document.getElementById("colis-list");';
  js+='  el.innerHTML=currentPts.map(function(p,i){';
  js+='    return "<div class='colis-row' draggable='true' data-idx='"+i+"'>"+';
  js+='      "<div class='colis-num' style='background:"+color+"'>"+( i+1)+"</div>"+';
  js+='      "<div class='colis-info'>"+';
  js+='        "<div class='colis-bc'>"+p.barcode+"</div>"+';
  js+='        "<div class='colis-addr'>"+(p.adresse||"")+(p.cp?" "+p.cp:"")+(p.ville?" "+p.ville:"")+"</div>"+';
  js+='      "</div>"+';
  js+='      "<div class='mv-btns'>"+';
  js+='        "<div class='mv-btn' data-mv='up' data-idx='"+i+"'>↑</div>"+';
  js+='        "<div class='mv-btn' data-mv='dn' data-idx='"+i+"'>↓</div>"+';
  js+='      "</div>"+';
  js+='    "</div>";';
  js+='  }).join("");';
  // Events drag
  js+='  el.querySelectorAll(".colis-row").forEach(function(row){';
  js+='    row.addEventListener("dragstart",function(){dragIdx=parseInt(this.dataset.idx);this.classList.add("dragging");});';
  js+='    row.addEventListener("dragend",function(){this.classList.remove("dragging");el.querySelectorAll(".colis-row").forEach(function(r){r.classList.remove("drag-over");});});';
  js+='    row.addEventListener("dragover",function(e){e.preventDefault();el.querySelectorAll(".colis-row").forEach(function(r){r.classList.remove("drag-over");});this.classList.add("drag-over");});';
  js+='    row.addEventListener("drop",function(e){e.preventDefault();var toIdx=parseInt(this.dataset.idx);if(dragIdx===null||dragIdx===toIdx) return;var item=currentPts.splice(dragIdx,1)[0];currentPts.splice(toIdx,0,item);dragIdx=null;renderList();refreshAll();});';
  js+='  });';
  // Events boutons ↑↓
  js+='  el.querySelectorAll(".mv-btn").forEach(function(btn){';
  js+='    btn.addEventListener("click",function(e){e.stopPropagation();';
  js+='      var i=parseInt(this.dataset.idx);var mv=this.dataset.mv;';
  js+='      if(mv==="up"&&i>0){var tmp=currentPts[i-1];currentPts[i-1]=currentPts[i];currentPts[i]=tmp;}';
  js+='      else if(mv==="dn"&&i<currentPts.length-1){var tmp=currentPts[i+1];currentPts[i+1]=currentPts[i];currentPts[i]=tmp;}';
  js+='      renderList();refreshAll();';
  js+='    });';
  js+='  });';
  js+='}';

  // Sauvegarder l'ordre dans la fenêtre parente
  js+='document.getElementById("saveBtn").addEventListener("click",function(){';
  js+='  var newOrder=currentPts.map(function(p){return p.barcode;});';
  js+='  if(window.opener&&!window.opener.closed){';
  js+='    window.opener.applyTourOrder(tourId,newOrder);';
  js+='    this.textContent="✅ Sauvegardé !";';
  js+='    setTimeout(function(){document.getElementById("saveBtn").textContent="💾 Sauvegarder l'ordre";},2000);';
  js+='  } else {alert("Fenêtre principale fermée. Copiez l'ordre manuellement.");}';
  js+='}); ';

  // Init
  js+='var allBounds=(startPt?[[startPt.lat,startPt.lon]]:[]).concat(currentPts.map(function(p){return[p.lat,p.lon];}));';
  js+='map.fitBounds(L.latLngBounds(allBounds).pad(.1));';
  js+='drawMarkers();';
  js+='renderList();';
  js+='loadRoute();';

  var blob=new Blob([js],{type:'text/javascript'});
  var blobUrl=URL.createObjectURL(blob);
  d.write('<sc'+'ript src="https://unpkg.com/leaflet/dist/leaflet.js" onload="var s=document.createElement(\'sc\'+('ript'));s.src=\''+blobUrl+'\';document.head.appendChild(s);"></sc'+'ript>');
  d.write('</body></html>');
  d.close();
}

// Reçoit l'ordre modifié depuis la fenêtre carte
function applyTourOrder(tourId, newOrder){
  var t=tours.find(function(t){return t.id===tourId;}); if(!t) return;
  t.order=newOrder;
  refreshTourList(); rebuildScanMap();
  toast('✅ Ordre de la tournée '+t.name+' mis à jour !', 3000);
}

// ══════════════════════════════════════════════════════
//  QR CODE
// ══════════════════════════════════════════════════════
function showQR(tourId){
  var t=tours.find(function(t){return t.id===tourId;}); if(!t) return;
  var order=t.order.length?t.order:t.barcodes;
  var pointMap={};
  points.forEach(function(p){pointMap[p.barcode]=p;});
  var payload={name:t.name,color:t.color,colis:order.map(function(bc,i){var p=pointMap[bc]||{};return{bc:bc,pos:i+1,lat:p.lat||0,lon:p.lon||0};})};
  var json=JSON.stringify(payload);
  var bytes=new TextEncoder().encode(json).length;
  var kb=(bytes/1024).toFixed(1);
  document.getElementById('qrTitle').textContent='QR Code — Tournée '+t.name;
  var canvas=document.getElementById('qrCanvas'); canvas.innerHTML='';
  document.getElementById('qrModal').classList.remove('hidden');
  if(bytes>2800){canvas.innerHTML='<p style="color:#f85149;max-width:300px">⚠️ Tournée trop volumineuse ('+kb+' Ko). Utilisez export JSON + mail.</p>';return;}
  try{new QRCode(canvas,{text:json,width:256,height:256,correctLevel:QRCode.CorrectLevel.L});document.getElementById('qrSizeInfo').textContent='Taille : '+kb+' Ko — '+order.length+' colis';}
  catch(e){canvas.innerHTML='<p style="color:#f85149">Erreur : '+e.message+'</p>';}
}

// ══════════════════════════════════════════════════════
//  EXPORT JSON + CSV
// ══════════════════════════════════════════════════════
document.getElementById('btnExport').addEventListener('click',function(){
  var result={};
  var pm={};
  points.forEach(function(p){pm[p.barcode]=p;});
  tours.forEach(function(t){
    var order=t.order.length?t.order:t.barcodes;
    order.forEach(function(bc,idx){
      var p=pm[bc]||{};
      result[bc]={tournee:t.name,position:idx+1,total:order.length,lat:p.lat||0,lon:p.lon||0,adresse:p.adresse||'',ville:p.ville||'',cp:p.cp||''};
    });
  });
  var blob=new Blob([JSON.stringify(result,null,2)],{type:'application/json'});
  var a=document.createElement('a');a.href=URL.createObjectURL(blob);a.download='tournees_export.json';a.click();
});

function exportTourCSV(tourId){
  var t=tours.find(function(t){return t.id===tourId;}); if(!t) return;
  var order=t.order.length?t.order:t.barcodes;
  var pm={};
  points.forEach(function(p){pm[p.barcode]=p;});
  var header=['Position','N Colis (A)','Tel (M)','Ville (R)','CP (G)','Adresse (T)'];
  var rows=order.map(function(bc,idx){var p=pm[bc]||{};return[idx+1,bc,p.telephone||'',p.ville||'',p.cp||'',p.adresse||''];});
  var csv=[header].concat(rows).map(function(r){return r.map(function(v){return '"'+String(v).replace(/"/g,'""')+'"';}).join(';');}).join('\n');
  var blob=new Blob(['\uFEFF'+csv],{type:'text/csv;charset=utf-8;'});
  var a=document.createElement('a');a.href=URL.createObjectURL(blob);a.download='tournee_'+t.name+'_colis.csv';a.click();
}

// ══════════════════════════════════════════════════════
//  DÉPÔT / POINT DE DÉPART
// ══════════════════════════════════════════════════════
var depotMarker=L.marker([0,0],{
  icon:L.divIcon({className:'',html:'<div style="font-size:26px;filter:drop-shadow(0 2px 4px rgba(0,0,0,.6))">🏠</div>',iconSize:[28,28],iconAnchor:[14,24]}),
  draggable:true
});
depotMarker.on('dragend',function(e){var ll=e.target.getLatLng();depot={lat:ll.lat,lon:ll.lng};updateDepotUI();});

function updateDepotUI(){
  var has=!!depot;
  document.getElementById('depotInfo').style.display=has?'block':'none';
  document.getElementById('btnClearDepot').style.display=has?'':'none';
  if(has){
    document.getElementById('depotCoords').textContent=depot.lat.toFixed(5)+', '+depot.lon.toFixed(5);
    document.getElementById('depotLat').value=depot.lat;
    document.getElementById('depotLon').value=depot.lon;
    depotMarker.setLatLng([depot.lat,depot.lon]);
    if(!map.hasLayer(depotMarker)) depotMarker.addTo(map);
  } else {if(map.hasLayer(depotMarker)) depotMarker.remove();}
}
document.getElementById('btnSetDepot').addEventListener('click',function(){
  var lat=parseFloat(document.getElementById('depotLat').value);
  var lon=parseFloat(document.getElementById('depotLon').value);
  if(!isFinite(lat)||!isFinite(lon)){alert('Coordonnées invalides.');return;}
  depot={lat:lat,lon:lon}; updateDepotUI(); map.setView([lat,lon],13);
});
document.getElementById('btnPickDepot').addEventListener('click',function(){
  pickingDepot=true;
  this.textContent='✅ Cliquez sur la carte…';
  map.getContainer().style.cursor='crosshair';
});
document.getElementById('btnClearDepot').addEventListener('click',function(){depot=null;updateDepotUI();});
map.on('click',function(e){
  if(!pickingDepot) return;
  depot={lat:e.latlng.lat,lon:e.latlng.lng}; updateDepotUI();
  pickingDepot=false;
  document.getElementById('btnPickDepot').textContent='🖱️ Carte';
  map.getContainer().style.cursor='';
});

function openDepotTourModal(tourId){
  var t=tours.find(function(t){return t.id===tourId;}); if(!t) return;
  editingDepotTourId=tourId;
  document.getElementById('depotTourTitle').textContent=t.name;
  document.getElementById('depotTourLat').value=t.depot?t.depot.lat:'';
  document.getElementById('depotTourLon').value=t.depot?t.depot.lon:'';
  document.getElementById('depotTourModal').classList.remove('hidden');
}
function closeDepotTourModal(){document.getElementById('depotTourModal').classList.add('hidden');editingDepotTourId=null;}
function saveDepotTourModal(){
  var t=tours.find(function(t){return t.id===editingDepotTourId;}); if(!t) return;
  var lat=parseFloat(document.getElementById('depotTourLat').value);
  var lon=parseFloat(document.getElementById('depotTourLon').value);
  t.depot=(isFinite(lat)&&isFinite(lon))?{lat:lat,lon:lon}:null;
  closeDepotTourModal(); refreshTourList();
}
document.getElementById('btnDepotTourClear').addEventListener('click',function(){
  var t=tours.find(function(t){return t.id===editingDepotTourId;}); if(t) t.depot=null;
  closeDepotTourModal(); refreshTourList();
});

// ══════════════════════════════════════════════════════
//  SCANNER
// ══════════════════════════════════════════════════════
function normCode(s){return(s||'').replace(/[\u200b\ufeff\xa0]/g,'').trim().replace(/\s+/g,'').toUpperCase();}

function rebuildScanMap(){
  scanMap={};
  tours.forEach(function(t){
    var order=t.order.length?t.order:t.barcodes;
    order.forEach(function(bc,idx){
      scanMap[normCode(bc)]={tourName:t.name,position:idx+1,total:order.length};
    });
  });
  var total=Object.keys(scanMap).length;
  var ts=new Set(Object.values(scanMap).map(function(v){return v.tourName;}));
  document.getElementById('sc-total').textContent=total;
  document.getElementById('sc-tours').textContent=ts.size;
  document.getElementById('sc-found').textContent=foundCount;
  document.getElementById('sc-unknown').textContent=unknownCount;
}

async function loadScanJSON(file){
  try{
    var txt=await file.text();
    var raw=JSON.parse(txt);
    scanMap={};
    for(var k in raw){
      var v=raw[k];
      var code=normCode(k);
      if(typeof v==='object'&&v.tournee!==undefined){
        scanMap[code]={tourName:String(v.tournee),position:v.position||0,total:v.total||0};
      } else {
        scanMap[code]={tourName:String(v),position:0,total:0};
      }
    }
    document.getElementById('scanDropLabel').textContent='✅ '+Object.keys(scanMap).length+' codes chargés';
    document.getElementById('scanInput').disabled=false;
    document.getElementById('scanClear').disabled=false;
    document.getElementById('scanMain').textContent='PRÊT';
    document.getElementById('scanMain').className='display-main';
    document.getElementById('scanSub').textContent='';
    document.getElementById('scanDisplay').className='scanner-display';
    document.getElementById('scanInput').focus();
    rebuildScanMap();
  }catch(err){alert('Fichier JSON invalide.');}
}
document.getElementById('scanFileInput').addEventListener('change',function(e){if(e.target.files[0]) loadScanJSON(e.target.files[0]);});
var sdz=document.getElementById('scanDropZone');
sdz.addEventListener('dragover',function(e){e.preventDefault();sdz.classList.add('drag-over');});
sdz.addEventListener('dragleave',function(){sdz.classList.remove('drag-over');});
sdz.addEventListener('drop',function(e){e.preventDefault();sdz.classList.remove('drag-over');if(e.dataTransfer.files[0]) loadScanJSON(e.dataTransfer.files[0]);});

function doScan(raw){
  var code=normCode(raw);
  var info=scanMap[code];
  var mainEl=document.getElementById('scanMain');
  var subEl=document.getElementById('scanSub');
  var dispEl=document.getElementById('scanDisplay');
  if(info===undefined){
    unknownCount++;
    mainEl.textContent='INCONNU';mainEl.className='display-main err';
    subEl.textContent=code||'—';subEl.className='display-sub err';
    dispEl.className='scanner-display state-err';
    addHistory(code,null,null);
  } else {
    foundCount++;
    mainEl.textContent='TOURNÉE '+info.tourName;mainEl.className='display-main ok';
    var posText=info.position?'Position '+info.position+(info.total?' / '+info.total:''):'';
    subEl.textContent=posText;subEl.className='display-sub ok';
    dispEl.className='scanner-display state-ok';
    addHistory(code,info.tourName,info.position&&info.total?info.position+'/'+info.total:'—');
  }
  document.getElementById('sc-found').textContent=foundCount;
  document.getElementById('sc-unknown').textContent=unknownCount;
  var badge=document.getElementById('history-badge');
  badge.textContent=historyRows.length;
  badge.classList.toggle('hidden',historyRows.length===0);
}
function addHistory(code,tour,pos){
  historyRows.unshift({code:code,tour:tour,pos:pos});
  if(historyRows.length>200) historyRows.pop();
  renderHistory();
}
function renderHistory(){
  document.getElementById('historyBody').innerHTML=historyRows.map(function(r,i){
    return '<tr><td class="ok" style="color:var(--muted)">'+(historyRows.length-i)+'</td>'
      +'<td>'+r.code+'</td>'
      +'<td class="'+(r.tour!==null?'ok':'err')+'">'+(r.tour!==null?r.tour:'INCONNU')+'</td>'
      +'<td style="color:var(--muted)">'+(r.pos||'—')+'</td></tr>';
  }).join('');
}
document.getElementById('scanInput').addEventListener('keydown',function(e){
  if(e.key==='Enter'){doScan(e.target.value);e.target.select();}
});
document.getElementById('scanClear').addEventListener('click',function(){
  document.getElementById('scanInput').value='';
  document.getElementById('scanInput').focus();
  document.getElementById('scanMain').textContent='PRÊT';
  document.getElementById('scanMain').className='display-main';
  document.getElementById('scanSub').textContent='';
  document.getElementById('scanDisplay').className='scanner-display';
});
document.getElementById('scanResetHist').addEventListener('click',function(){
  if(!confirm("Vider l'historique ?")) return;
  historyRows=[];foundCount=0;unknownCount=0;
  renderHistory();rebuildScanMap();
  document.getElementById('history-badge').classList.add('hidden');
});
</script>
</body>
</html>
