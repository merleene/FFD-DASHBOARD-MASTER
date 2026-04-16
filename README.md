
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Segoe UI',Arial,sans-serif;font-size:13px;color:#1a2a3a;background:transparent}

.hdr{background:linear-gradient(135deg,#0a6e7a 0%,#0d8fa0 60%,#12b0c5 100%);padding:0;border-radius:10px 10px 0 0;overflow:hidden;position:relative}
.hdr-inner{display:flex;align-items:center;justify-content:space-between;padding:12px 20px;flex-wrap:wrap;gap:8px}
.hdr-left{display:flex;align-items:center;gap:14px}
.logo-box{width:48px;height:48px;background:#fff;border-radius:8px;display:flex;align-items:center;justify-content:center;flex-shrink:0;padding:4px}
.logo-svg{width:40px;height:40px}
.logo-text{display:flex;flex-direction:column;line-height:1.1}
.logo-text .t1{font-size:13px;font-weight:700;color:#fff;letter-spacing:.06em}
.logo-text .t2{font-size:11px;font-weight:400;color:rgba(255,255,255,.85);letter-spacing:.04em}
.hdr-right{text-align:right}
.hdr-title{font-size:16px;font-weight:600;color:#fff;letter-spacing:.02em}
.hdr-meta{font-size:11px;color:rgba(255,255,255,.75);margin-top:2px}
.hdr-strip{height:3px;background:linear-gradient(90deg,#fff2,#fff6,#fff2)}

.kpi-bar{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;padding:12px 16px;background:#f0f8f9;border-bottom:1px solid #c8e8ec}
.kpi{background:#fff;border:1px solid #c8e8ec;border-radius:8px;padding:10px 14px;text-align:center;position:relative;overflow:hidden}
.kpi::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,#0a6e7a,#12b0c5)}
.kpi .val{font-size:22px;font-weight:700;color:#0a6e7a}
.kpi .lbl{font-size:11px;color:#6b8a90;margin-top:3px;font-weight:500;letter-spacing:.03em;text-transform:uppercase}

.layout{display:flex;gap:0;min-height:520px}

.sidebar{width:228px;flex-shrink:0;background:#f7fcfd;border-right:1px solid #c8e8ec;padding:12px;display:flex;flex-direction:column;gap:10px}
.sidebar-section{display:flex;flex-direction:column;gap:5px}
.section-title{font-size:10px;font-weight:700;color:#0a6e7a;text-transform:uppercase;letter-spacing:.07em;padding:0 0 2px;border-bottom:1.5px solid #c8e8ec}
.upload-zone{border:1.5px dashed #9fcfd6;border-radius:8px;padding:9px 8px;text-align:center;cursor:pointer;font-size:11px;color:#5a8a90;background:#edf8f9;transition:all .15s}
.upload-zone:hover{background:#d8f2f5;border-color:#0a6e7a;color:#0a6e7a}
.upload-zone input{display:none}
.upload-icon{font-size:16px;margin-bottom:2px}
.upload-label{font-weight:600;font-size:11px}
.upload-sub{font-size:10px;color:#8aadb2;margin-top:1px}
.upload-status{font-size:10px;color:#0a6e7a;min-height:13px;font-weight:500}

.filter-divider{height:1px;background:#c8e8ec;margin:2px 0}
.filter-label{font-size:10px;font-weight:700;color:#4a7a80;text-transform:uppercase;letter-spacing:.06em}
.filter-select,.filter-input{width:100%;padding:5px 8px;font-size:12px;border:1px solid #c8e8ec;border-radius:6px;background:#fff;color:#1a2a3a;outline:none}
.filter-select:focus,.filter-input:focus{border-color:#0a6e7a;box-shadow:0 0 0 2px #0a6e7a22}
.date-row{display:flex;gap:4px}
.date-row .filter-input{flex:1;min-width:0}
.date-row .date-sep{font-size:10px;color:#8aadb2;display:flex;align-items:center;flex-shrink:0}

.apply-btn{width:100%;padding:7px;font-size:12px;font-weight:600;cursor:pointer;border:none;border-radius:6px;background:linear-gradient(135deg,#0a6e7a,#12b0c5);color:#fff;letter-spacing:.03em}
.apply-btn:hover{background:linear-gradient(135deg,#085e68,#0d8fa0)}
.reset-btn{width:100%;padding:5px;font-size:11px;cursor:pointer;border:1px solid #c8e8ec;border-radius:6px;background:#fff;color:#6b8a90}
.reset-btn:hover{background:#edf8f9;color:#0a6e7a;border-color:#9fcfd6}

.main{flex:1;min-width:0;display:flex;flex-direction:column}
.tabs{display:flex;background:#f0f8f9;border-bottom:1px solid #c8e8ec;overflow-x:auto}
.tab{padding:9px 14px;font-size:11.5px;font-weight:500;cursor:pointer;white-space:nowrap;border-bottom:2.5px solid transparent;color:#6b8a90;flex-shrink:0;letter-spacing:.02em;transition:all .15s}
.tab:hover{background:#e2f4f6;color:#0a6e7a}
.tab.active{border-bottom-color:#0a6e7a;color:#0a6e7a;font-weight:700;background:#fff}

.panel{display:none;padding:12px 14px;flex:1;overflow:auto}
.panel.active{display:block}
.toolbar{display:flex;align-items:center;gap:8px;margin-bottom:10px;flex-wrap:wrap}
.btn{padding:4px 10px;font-size:11px;font-weight:500;cursor:pointer;border:1px solid #c8e8ec;border-radius:6px;background:#fff;color:#0a6e7a}
.btn:hover{background:#edf8f9;border-color:#9fcfd6}
.search{padding:5px 10px;font-size:11px;border:1px solid #c8e8ec;border-radius:6px;background:#fff;color:#1a2a3a;width:160px;outline:none}
.search:focus{border-color:#0a6e7a;box-shadow:0 0 0 2px #0a6e7a18}

.ptable{border-collapse:collapse;font-size:12px;width:100%}
.ptable th{background:#0a6e7a;color:#fff;padding:7px 10px;text-align:center;font-weight:600;white-space:nowrap;border:1px solid #085e68;font-size:11px;position:sticky;top:0;z-index:1;letter-spacing:.03em;text-transform:uppercase}
.ptable th:first-child{text-align:left}
.ptable td{padding:5px 10px;border:0.5px solid #d8eef1;white-space:nowrap}
.ptable td:not(:first-child){text-align:center}
.ptable tbody tr:not(.tl-row):not(.grand):nth-child(even) td{background:#f7fcfd}
.tl-row td{background:#d6f0f3;color:#064a52;font-weight:600;cursor:pointer;user-select:none;border-top:1px solid #9fcfd6}
.tl-row:hover td{background:#c2e8ed}
.grand td{background:#0a6e7a;color:#fff;font-weight:700;border-top:1.5px solid #085e68}
.agent-row:hover td{background:#edf8f9}
.agent-row.hidden{display:none}
.tl-badge{font-size:10px;font-weight:400;color:#0a6e7a;margin-left:6px;background:#c2e8ed;padding:1px 5px;border-radius:8px}
.bar-wrap{display:flex;align-items:center;gap:6px}
.bar{height:7px;border-radius:3px;min-width:2px}
.bar-val{font-size:11px;color:#4a7a80;min-width:42px;font-weight:500}
.pct-pill{display:inline-block;padding:2px 7px;border-radius:10px;font-size:11px;font-weight:600}
.pct-hi{background:#fde8e8;color:#b03030}
.pct-mid{background:#fef3e0;color:#8a5a00}
.pct-lo{background:#e0f5ec;color:#0a6e7a}
.no-data{padding:48px;text-align:center;color:#8aadb2;font-size:13px}
.no-data-icon{font-size:32px;margin-bottom:8px}
</style>

<div class="hdr">
  <div class="hdr-inner">
    <div class="hdr-left">
      <div class="logo-box">
        <svg class="logo-svg" viewBox="0 0 100 110" xmlns="http://www.w3.org/2000/svg">
          <line x1="50" y1="5" x2="50" y2="75" stroke="#0a6e7a" stroke-width="8" stroke-linecap="round"/>
          <line x1="30" y1="5" x2="70" y2="5" stroke="#0a6e7a" stroke-width="8" stroke-linecap="round"/>
          <line x1="30" y1="38" x2="55" y2="38" stroke="#0a6e7a" stroke-width="7" stroke-linecap="round"/>
          <path d="M50 42 Q90 42 90 65 Q90 90 50 95" stroke="#0a6e7a" stroke-width="8" fill="none" stroke-linecap="round"/>
        </svg>
      </div>
      <div class="logo-text">
        <span class="t1">FOREFRONT</span>
        <span class="t2">DERMATOLOGY</span>
      </div>
    </div>
    <div class="hdr-right">
      <div class="hdr-title">AHT &amp; Transfers — Pivots</div>
      <div class="hdr-meta" id="hdr-meta">Upload data to begin</div>
    </div>
  </div>
  <div class="hdr-strip"></div>
</div>

<div class="kpi-bar">
  <div class="kpi"><div class="val" id="kpi-handled">—</div><div class="lbl">Handled Calls</div></div>
  <div class="kpi"><div class="val" id="kpi-transferred">—</div><div class="lbl">Transferred</div></div>
  <div class="kpi"><div class="val" id="kpi-xfer-pct">—</div><div class="lbl">Transfer Rate</div></div>
  <div class="kpi"><div class="val" id="kpi-aht">—</div><div class="lbl">Overall AHT</div></div>
</div>

<div class="layout">
  <div class="sidebar">

    <div class="sidebar-section">
      <div class="section-title">Data Sources</div>
      <div class="upload-zone" onclick="document.getElementById('up-raw').click()">
        <input type="file" id="up-raw" accept=".xlsx,.xls,.csv">
        <div class="upload-icon">📊</div>
        <div class="upload-label">Raw Data</div>
        <div class="upload-sub">.xlsx / .csv</div>
      </div>
      <div class="upload-status" id="status-raw"></div>
      <div class="upload-zone" onclick="document.getElementById('up-lkp').click()">
        <input type="file" id="up-lkp" accept=".xlsx,.xls,.csv">
        <div class="upload-icon">🔗</div>
        <div class="upload-label">Lookup / Master</div>
        <div class="upload-sub">.xlsx / .csv</div>
      </div>
      <div class="upload-status" id="status-lkp"></div>
    </div>

    <div class="filter-divider"></div>

    <div class="sidebar-section">
      <div class="section-title">Filters</div>

      <div class="filter-label">Week</div>
      <select class="filter-select" id="f-week"><option value="">All</option></select>

      <div class="filter-label" style="margin-top:6px">Day</div>
      <select class="filter-select" id="f-day">
        <option value="">All</option>
        <option>Monday</option><option>Tuesday</option><option>Wednesday</option>
        <option>Thursday</option><option>Friday</option><option>Saturday</option><option>Sunday</option>
      </select>

      <div class="filter-label" style="margin-top:6px">Contact Start Date</div>
      <div class="date-row">
        <input type="date" class="filter-input" id="f-date-from" title="From">
        <span class="date-sep">→</span>
        <input type="date" class="filter-input" id="f-date-to" title="To">
      </div>

      <div class="filter-label" style="margin-top:6px">Skill Name</div>
      <select class="filter-select" id="f-skill"><option value="">All</option></select>

      <div class="filter-label" style="margin-top:6px">Disposition</div>
      <select class="filter-select" id="f-dispo"><option value="">All</option></select>
    </div>

    <button class="apply-btn" onclick="applyFilters()">Apply Filters</button>
    <button class="reset-btn" onclick="resetFilters()">↺ Reset filters</button>
  </div>

  <div class="main">
    <div class="tabs" id="tabs"></div>
    <div id="panels" style="flex:1;overflow:auto"></div>
  </div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
<script>
let RAW=[],LOOKUP={};
let expandState={};
const DAYS=['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday'];

function parseTimeSecs(t){
  if(!t||t==='') return null;
  try{const p=String(t).trim().split(':');if(p.length===3)return +p[0]*3600+(+p[1])*60+(+p[2]);}catch(e){}
  return null;
}
function fmtHMS(s){
  if(s==null||isNaN(s)||s<0) return '00:00:00';
  s=Math.round(s);
  return `${String(Math.floor(s/3600)).padStart(2,'0')}:${String(Math.floor(s%3600/60)).padStart(2,'0')}:${String(s%60).padStart(2,'0')}`;
}
function cleanSkill(s){
  if(!s) return '(blank)';
  s=String(s).trim();const p=s.split(' ');
  if(p.length>=2&&/^\d+$/.test(p[p.length-1])) return p.slice(0,-1).join(' ');
  return s;
}

function processRaw(ws){
  const data=XLSX.utils.sheet_to_json(ws,{defval:null});
  RAW=data.map(r=>{
    const dt=r['Contact Start Date Time']||r['Contact Start Date']||null;
    let dateStr=null,dayName=null;
    if(dt){const d=new Date(dt);if(!isNaN(d)){dateStr=d.toISOString().slice(0,10);dayName=DAYS[d.getDay()];}}
    const skillRaw=r['Skill Name']||r['skill_name']||'';
    const tlInfo=LOOKUP[parseInt(r['Agent ID']||0)]||{};
    return{
      week:r['Week']||null,
      agent:r['Agent Name']||r['agent_name']||'',
      agentId:r['Agent ID']||null,
      dispo:r['Disposition Name']||r['Disposition']||'(blank)',
      skill:cleanSkill(skillRaw),
      date:dateStr,day:dayName,
      handleSecs:parseTimeSecs(r['Handle Time']||null),
      handled:+(r['Handled']||0)||0,
      transferred:+(r['Transferred']||0)||0,
      tl:tlInfo.tl||null,wave:tlInfo.wave||null,team:tlInfo.team||null,
    };
  }).filter(r=>r.agent);
}

function processLookup(ws){
  const data=XLSX.utils.sheet_to_json(ws,{defval:null});
  LOOKUP={};
  data.forEach(r=>{
    const id=parseInt(r['Agent RC ID']||r['AgentRCID']||0);
    if(id) LOOKUP[id]={tl:r['Team Leader']||null,wave:r['Wave']||null,team:r['Team']||null};
  });
}

document.getElementById('up-raw').addEventListener('change',e=>{
  const f=e.target.files[0];if(!f) return;
  const st=document.getElementById('status-raw');
  st.textContent='Reading…';st.style.color='#6b8a90';
  const rd=new FileReader();
  rd.onload=ev=>{
    try{
      const wb=XLSX.read(ev.target.result,{type:'array'});
      processRaw(wb.Sheets[wb.SheetNames[0]]);
      populateFilters();applyFilters();
      st.textContent=`✓ ${RAW.length.toLocaleString()} rows loaded`;st.style.color='#0a6e7a';
    }catch(err){st.textContent='Error: '+err.message;st.style.color='#b03030';}
  };
  rd.readAsArrayBuffer(f);
});

document.getElementById('up-lkp').addEventListener('change',e=>{
  const f=e.target.files[0];if(!f) return;
  const st=document.getElementById('status-lkp');
  st.textContent='Reading…';st.style.color='#6b8a90';
  const rd=new FileReader();
  rd.onload=ev=>{
    try{
      const wb=XLSX.read(ev.target.result,{type:'array'});
      const ws=wb.Sheets['LOOKUP']||wb.Sheets[wb.SheetNames[0]];
      processLookup(ws);
      if(RAW.length){
        RAW.forEach(r=>{const info=LOOKUP[parseInt(r.agentId||0)]||{};r.tl=info.tl||null;r.wave=info.wave||null;r.team=info.team||null;});
        applyFilters();
      }
      st.textContent=`✓ ${Object.keys(LOOKUP).length} agents mapped`;st.style.color='#0a6e7a';
    }catch(err){st.textContent='Error: '+err.message;st.style.color='#b03030';}
  };
  rd.readAsArrayBuffer(f);
});

function populateFilters(){
  const weeks=[...new Set(RAW.map(r=>r.week).filter(Boolean))].sort();
  const skills=[...new Set(RAW.map(r=>r.skill).filter(Boolean))].sort();
  const dispos=[...new Set(RAW.map(r=>r.dispo||'(blank)'))].sort();
  const dates=[...new Set(RAW.map(r=>r.date).filter(Boolean))].sort();
  document.getElementById('f-week').innerHTML='<option value="">All</option>'+weeks.map(w=>`<option>${w}</option>`).join('');
  document.getElementById('f-skill').innerHTML='<option value="">All</option>'+skills.map(s=>`<option>${s}</option>`).join('');
  document.getElementById('f-dispo').innerHTML='<option value="">All</option>'+dispos.map(d=>`<option>${d}</option>`).join('');
  if(dates.length){document.getElementById('f-date-from').value=dates[0];document.getElementById('f-date-to').value=dates[dates.length-1];}
}

function resetFilters(){
  ['f-week','f-day','f-skill','f-dispo'].forEach(id=>document.getElementById(id).value='');
  document.getElementById('f-date-from').value='';document.getElementById('f-date-to').value='';
  applyFilters();
}

let FILTERED=[];
function applyFilters(){
  if(!RAW.length) return;
  const week=document.getElementById('f-week').value;
  const day=document.getElementById('f-day').value;
  const df=document.getElementById('f-date-from').value;
  const dt=document.getElementById('f-date-to').value;
  const skill=document.getElementById('f-skill').value;
  const dispo=document.getElementById('f-dispo').value;
  FILTERED=RAW.filter(r=>{
    if(week&&r.week!==week) return false;
    if(day&&r.day!==day) return false;
    if(df&&r.date&&r.date<df) return false;
    if(dt&&r.date&&r.date>dt) return false;
    if(skill&&r.skill!==skill) return false;
    if(dispo&&(r.dispo||'(blank)')!==dispo) return false;
    return true;
  });
  updateKPIs();updateMeta();expandState={};rebuildAll();
}

function updateKPIs(){
  const h=FILTERED.reduce((a,r)=>a+r.handled,0);
  const t=FILTERED.reduce((a,r)=>a+r.transferred,0);
  const hR=FILTERED.filter(r=>r.handleSecs!=null&&r.handled===1);
  const aht=hR.length?hR.reduce((a,r)=>a+r.handleSecs,0)/hR.length:0;
  document.getElementById('kpi-handled').textContent=h.toLocaleString();
  document.getElementById('kpi-transferred').textContent=t.toLocaleString();
  document.getElementById('kpi-xfer-pct').textContent=h?(t/h*100).toFixed(1)+'%':'—';
  document.getElementById('kpi-aht').textContent=fmtHMS(aht);
}

function updateMeta(){
  const weeks=[...new Set(FILTERED.map(r=>r.week).filter(Boolean))];
  const dates=[...new Set(FILTERED.map(r=>r.date).filter(Boolean))].sort();
  const wStr=weeks.length?weeks.join(', '):'—';
  const dStr=dates.length?(dates[0]===dates[dates.length-1]?dates[0]:`${dates[0]} → ${dates[dates.length-1]}`):'—';
  document.getElementById('hdr-meta').textContent=`${wStr}  ·  ${dStr}  ·  ${FILTERED.length.toLocaleString()} records`;
}

const TABS=[
  {id:'overview',label:'AHT Overview',tl:true},
  {id:'sched_est',label:'AHT — Sched Est',tl:true},
  {id:'sched_new',label:'AHT — Sched New',tl:true},
  {id:'wave',label:'AHT by Wave',tl:false},
  {id:'skill',label:'AHT by Skill',tl:false},
  {id:'dispo_aht',label:'AHT by Disposition',tl:false},
  {id:'transfers',label:'Transfers by TL',tl:false},
  {id:'dispo_trans',label:'Transfers by Dispo',tl:false},
];
const tabsEl=document.getElementById('tabs'),panelsEl=document.getElementById('panels');
TABS.forEach((t,i)=>{
  const tb=document.createElement('div');
  tb.className='tab'+(i===0?' active':'');tb.textContent=t.label;tb.dataset.id=t.id;
  tabsEl.appendChild(tb);
  const pn=document.createElement('div');
  pn.className='panel'+(i===0?' active':'');pn.id='panel-'+t.id;
  pn.innerHTML=`<div class="no-data"><div class="no-data-icon">📂</div>Upload raw data to populate this view.</div>`;
  panelsEl.appendChild(pn);
});
tabsEl.addEventListener('click',e=>{
  const t=e.target.closest('.tab');if(!t) return;
  document.querySelectorAll('.tab').forEach(x=>x.classList.remove('active'));
  document.querySelectorAll('.panel').forEach(x=>x.classList.remove('active'));
  t.classList.add('active');
  document.getElementById('panel-'+t.dataset.id).classList.add('active');
  buildPanel(t.dataset.id);
});

function rebuildAll(){
  TABS.forEach(t=>{document.getElementById('panel-'+t.id).dataset.built='';});
  const a=document.querySelector('.tab.active');if(a) buildPanel(a.dataset.id);
}

function toolbar(pid,hasTgl){
  let h=`<div class="toolbar">`;
  if(hasTgl) h+=`<button class="btn" onclick="expandAll('${pid}')">▼ Expand all</button><button class="btn" onclick="collapseAll('${pid}')">▶ Collapse all</button>`;
  h+=`<input class="search" placeholder="🔍 Search…" oninput="filterTable('${pid}',this.value)"></div>`;
  return h;
}

function toggleGroup(gid){
  const open=expandState[gid]!==false;expandState[gid]=!open;
  document.querySelectorAll('.agent-of-'+gid).forEach(r=>open?r.classList.add('hidden'):r.classList.remove('hidden'));
  const ico=document.getElementById('ico-'+gid);if(ico) ico.textContent=open?'▶':'▼';
}
function expandAll(pid){
  document.querySelectorAll(`#panel-${pid} .tl-row`).forEach(r=>{
    const g=r.dataset.gid;expandState[g]=true;
    document.querySelectorAll('.agent-of-'+g).forEach(a=>a.classList.remove('hidden'));
    const ico=document.getElementById('ico-'+g);if(ico)ico.textContent='▼';
  });
}
function collapseAll(pid){
  document.querySelectorAll(`#panel-${pid} .tl-row`).forEach(r=>{
    const g=r.dataset.gid;expandState[g]=false;
    document.querySelectorAll('.agent-of-'+g).forEach(a=>a.classList.add('hidden'));
    const ico=document.getElementById('ico-'+g);if(ico)ico.textContent='▶';
  });
}
function filterTable(pid,q){
  q=q.toLowerCase();
  document.querySelectorAll(`#panel-${pid} tbody tr`).forEach(r=>{
    if(r.classList.contains('grand')) return;
    const match=r.textContent.toLowerCase().includes(q)||!q;
    r.style.display=match?'':'none';
    if(match&&q&&!r.classList.contains('tl-row')){
      r.classList.remove('hidden');
      const cls=[...r.classList].find(c=>c.startsWith('agent-of-'));
      if(cls){const g=cls.replace('agent-of-','');expandState[g]=true;const ico=document.getElementById('ico-'+g);if(ico)ico.textContent='▼';}
    }
  });
}

function groupByTL(rows){
  const map={};
  rows.forEach(r=>{
    const tl=r.tl||'(Unknown)';
    if(!map[tl]) map[tl]={tl,agents:{},h:0,s:0};
    if(r.handleSecs!=null&&r.handled===1){map[tl].h++;map[tl].s+=r.handleSecs;}
    const ag=r.agent;
    if(!map[tl].agents[ag]) map[tl].agents[ag]={n:ag,h:0,s:0};
    if(r.handleSecs!=null&&r.handled===1){map[tl].agents[ag].h++;map[tl].agents[ag].s+=r.handleSecs;}
  });
  return Object.values(map).sort((a,b)=>a.tl.localeCompare(b.tl)).map(g=>({
    tl:g.tl,h:g.h,as:g.h?Math.round(g.s/g.h):0,a:fmtHMS(g.h?g.s/g.h:0),
    agents:Object.values(g.agents).sort((a,b)=>a.n.localeCompare(b.n)).map(a=>({n:a.n,h:a.h,as:a.h?Math.round(a.s/a.h):0,a:fmtHMS(a.h?a.s/a.h:0)}))
  }));
}

function tlTable(data,pid,col){
  if(!data.length) return `<div class="no-data"><div class="no-data-icon">🔍</div>No data matching current filters.</div>`;
  const max=Math.max(...data.map(r=>r.as),1);
  const th=data.reduce((a,r)=>a+r.h,0),ts=data.reduce((a,r)=>a+r.h*r.as,0);
  let tbody='';
  data.forEach((r,gi)=>{
    const gid=pid+'-g'+gi,open=expandState[gid]!==false;
    tbody+=`<tr class="tl-row" data-gid="${gid}" onclick="toggleGroup('${gid}')">
      <td><span id="ico-${gid}" style="font-size:10px;margin-right:6px">${open?'▼':'▶'}</span>${r.tl}<span class="tl-badge">${r.agents.length}</span></td>
      <td>${r.h.toLocaleString()}</td>
      <td><div class="bar-wrap"><div class="bar" style="width:${Math.round(r.as/max*90)}px;background:${col}"></div><span class="bar-val">${r.a}</span></div></td>
    </tr>`;
    r.agents.forEach(a=>{
      tbody+=`<tr class="agent-row agent-of-${gid}${open?'':' hidden'}">
        <td style="padding-left:24px;color:#4a7a80">${a.n}</td>
        <td>${a.h.toLocaleString()}</td>
        <td><div class="bar-wrap"><div class="bar" style="width:${Math.round(a.as/max*90)}px;background:${col};opacity:.55"></div><span class="bar-val">${a.a}</span></div></td>
      </tr>`;
    });
  });
  tbody+=`<tr class="grand"><td>Grand Total</td><td>${th.toLocaleString()}</td><td>${fmtHMS(th?ts/th:0)}</td></tr>`;
  return `<table class="ptable"><thead><tr><th style="min-width:230px">Team Leader › Agent</th><th>Handled</th><th style="min-width:180px">AHT</th></tr></thead><tbody>${tbody}</tbody></table>`;
}

function simpleAHT(rows,labelFn,col){
  if(!rows.length) return `<div class="no-data"><div class="no-data-icon">🔍</div>No data.</div>`;
  const max=Math.max(...rows.map(r=>r.as),1);
  const th=rows.reduce((a,r)=>a+r.h,0),ts=rows.reduce((a,r)=>a+r.h*r.as,0);
  let tbody=rows.map(r=>`<tr class="agent-row"><td>${labelFn(r)}</td><td>${r.h.toLocaleString()}</td><td><div class="bar-wrap"><div class="bar" style="width:${Math.round(r.as/max*90)}px;background:${col}"></div><span class="bar-val">${r.a}</span></div></td></tr>`).join('');
  tbody+=`<tr class="grand"><td>Grand Total</td><td>${th.toLocaleString()}</td><td>${fmtHMS(th?ts/th:0)}</td></tr>`;
  return `<table class="ptable"><thead><tr><th style="min-width:200px">Group</th><th>Handled</th><th style="min-width:180px">AHT</th></tr></thead><tbody>${tbody}</tbody></table>`;
}

function buildPanel(id){
  const el=document.getElementById('panel-'+id);
  if(el.dataset.built==='1') return;
  el.dataset.built='1';
  if(!FILTERED.length){el.innerHTML=`<div class="no-data"><div class="no-data-icon">📂</div>Upload raw data to populate this view.</div>`;return;}
  const hRows=FILTERED.filter(r=>r.handleSecs!=null&&r.handled===1);

  if(id==='overview'){
    el.innerHTML=toolbar(id,true)+tlTable(groupByTL(hRows),id,'#0a6e7a');
  } else if(id==='sched_est'){
    el.innerHTML=toolbar(id,true)+tlTable(groupByTL(hRows.filter(r=>r.dispo==='Sched Est')),id,'#0d8fa0');
  } else if(id==='sched_new'){
    el.innerHTML=toolbar(id,true)+tlTable(groupByTL(hRows.filter(r=>r.dispo==='Sched New')),id,'#534AB7');
  } else if(id==='wave'){
    const map={};
    hRows.forEach(r=>{const w=r.wave?'Wave '+r.wave:'(Unknown)';if(!map[w])map[w]={h:0,s:0};map[w].h++;map[w].s+=r.handleSecs;});
    const rows=Object.entries(map).sort((a,b)=>a[0].localeCompare(b[0],undefined,{numeric:true})).map(([w,v])=>({w,h:v.h,as:v.h?Math.round(v.s/v.h):0,a:fmtHMS(v.h?v.s/v.h:0)}));
    el.innerHTML=toolbar(id,false)+simpleAHT(rows,r=>r.w,'#BA7517');
  } else if(id==='skill'){
    const map={};
    hRows.forEach(r=>{const sk=r.skill||'(blank)';if(!map[sk])map[sk]={h:0,s:0};map[sk].h++;map[sk].s+=r.handleSecs;});
    const rows=Object.entries(map).sort((a,b)=>a[0].localeCompare(b[0])).map(([sk,v])=>({sk,h:v.h,as:v.h?Math.round(v.s/v.h):0,a:fmtHMS(v.h?v.s/v.h:0)}));
    el.innerHTML=toolbar(id,false)+simpleAHT(rows,r=>r.sk,'#993C1D');
  } else if(id==='dispo_aht'){
    const map={};
    hRows.forEach(r=>{const d=r.dispo||'(blank)';if(!map[d])map[d]={h:0,s:0};map[d].h++;map[d].s+=r.handleSecs;});
    const rows=Object.entries(map).map(([d,v])=>({d,h:v.h,as:v.h?Math.round(v.s/v.h):0,a:fmtHMS(v.h?v.s/v.h:0)})).sort((a,b)=>b.as-a.as);
    el.innerHTML=toolbar(id,false)+simpleAHT(rows,r=>r.d,'#534AB7');
  } else if(id==='transfers'){
    const map={};
    FILTERED.forEach(r=>{const tl=r.tl||'(Unknown)';if(!map[tl])map[tl]={h:0,t:0};map[tl].h+=r.handled;map[tl].t+=r.transferred;});
    const rows=Object.entries(map).map(([tl,v])=>({tl,h:v.h,t:v.t,p:v.h?v.t/v.h*100:0})).sort((a,b)=>b.t-a.t);
    const maxT=Math.max(...rows.map(r=>r.t),1);
    const th=rows.reduce((a,r)=>a+r.h,0),tt=rows.reduce((a,r)=>a+r.t,0);
    let tbody=rows.map(r=>{
      const cls=r.p>=30?'pct-hi':r.p>=25?'pct-mid':'pct-lo';
      return `<tr class="agent-row"><td>${r.tl}</td><td>${r.h.toLocaleString()}</td><td><div class="bar-wrap"><div class="bar" style="width:${Math.round(r.t/maxT*90)}px;background:#D85A30"></div><span class="bar-val">${r.t.toLocaleString()}</span></div></td><td><span class="pct-pill ${cls}">${r.p.toFixed(1)}%</span></td></tr>`;
    }).join('');
    const gp=th?tt/th*100:0,gcls=gp>=30?'pct-hi':gp>=25?'pct-mid':'pct-lo';
    tbody+=`<tr class="grand"><td>Grand Total</td><td>${th.toLocaleString()}</td><td>${tt.toLocaleString()}</td><td><span class="pct-pill ${gcls}">${gp.toFixed(1)}%</span></td></tr>`;
    el.innerHTML=toolbar(id,false)+`<table class="ptable"><thead><tr><th style="min-width:210px">Team Leader</th><th>Handled</th><th style="min-width:160px">Transferred</th><th>Transfer %</th></tr></thead><tbody>${tbody}</tbody></table>`;
  } else if(id==='dispo_trans'){
    const map={};
    FILTERED.forEach(r=>{const d=r.dispo||'(blank)';if(!map[d])map[d]=0;map[d]+=r.handled;});
    const rows=Object.entries(map).map(([d,h])=>({d,h})).sort((a,b)=>b.h-a.h);
    const maxH=Math.max(...rows.map(r=>r.h),1),total=rows.reduce((a,r)=>a+r.h,0);
    let tbody=rows.map(r=>`<tr class="agent-row"><td>${r.d}</td><td><div class="bar-wrap"><div class="bar" style="width:${Math.round(r.h/maxH*90)}px;background:#1D9E75"></div><span class="bar-val">${r.h.toLocaleString()}</span></div></td></tr>`).join('');
    tbody+=`<tr class="grand"><td>Grand Total</td><td>${total.toLocaleString()}</td></tr>`;
    el.innerHTML=toolbar(id,false)+`<table class="ptable"><thead><tr><th style="min-width:250px">Disposition</th><th style="min-width:170px">Handled Calls</th></tr></thead><tbody>${tbody}</tbody></table>`;
  }
}
</script>
