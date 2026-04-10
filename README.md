
<style>
  @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600&family=Barlow:wght@300;400;500&display=swap');

  :root {
    --bg: #0d1117;
    --surface: #161d27;
    --surface2: #1e2736;
    --border: #2a3a50;
    --gold: #c9a84c;
    --gold-dim: #8a6e2f;
    --text: #d4cfc8;
    --text-dim: #7a8899;
    --text-bright: #eae6df;
    --accent: #4a90c4;
    --yes: #4a7c59;
    --yes-text: #8fcca0;
    --no: #6b2f2f;
    --no-text: #cc8888;
    --highlight-col: rgba(201,168,76,0.08);
    --highlight-border: rgba(201,168,76,0.35);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body, .app {
    background: var(--bg);
    color: var(--text);
    font-family: 'Barlow', sans-serif;
    font-size: 14px;
    min-height: 100vh;
  }

  .app { padding: 0 0 3rem; }

  .header {
    background: var(--surface);
    border-bottom: 1px solid var(--border);
    padding: 1.25rem 1.5rem 1rem;
    position: relative;
  }

  .header-top {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 1rem;
  }

  .crystal {
    width: 28px; height: 28px;
    flex-shrink: 0;
  }

  .header h1 {
    font-family: 'Cinzel', serif;
    font-size: 18px;
    font-weight: 600;
    color: var(--gold);
    letter-spacing: 0.05em;
    line-height: 1.2;
  }

  .header h1 span {
    display: block;
    font-size: 11px;
    font-weight: 400;
    color: var(--text-dim);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-top: 2px;
    font-family: 'Barlow', sans-serif;
  }

  .url-bar {
    display: flex;
    gap: 8px;
    align-items: center;
    margin-bottom: 1rem;
  }

  .url-bar input {
    flex: 1;
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 4px;
    color: var(--text);
    font-family: 'Barlow', sans-serif;
    font-size: 12px;
    padding: 6px 10px;
    outline: none;
  }

  .url-bar input:focus { border-color: var(--gold-dim); }

  .url-bar input::placeholder { color: var(--text-dim); }

  .btn-load {
    background: var(--gold);
    border: none;
    border-radius: 4px;
    color: #1a1200;
    cursor: pointer;
    font-family: 'Cinzel', serif;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.08em;
    padding: 6px 14px;
    white-space: nowrap;
  }

  .btn-load:hover { background: #dbb95c; }
  .btn-load:disabled { background: var(--gold-dim); cursor: not-allowed; opacity: 0.6; }

  .filters {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    align-items: center;
  }

  .filter-group {
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .filter-group label {
    font-size: 11px;
    color: var(--text-dim);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    white-space: nowrap;
  }

  select, .search-input {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 4px;
    color: var(--text);
    font-family: 'Barlow', sans-serif;
    font-size: 13px;
    padding: 5px 8px;
    outline: none;
    cursor: pointer;
  }

  select:focus, .search-input:focus { border-color: var(--gold-dim); }

  .search-input {
    width: 220px;
    cursor: text;
  }

  .search-input::placeholder { color: var(--text-dim); }

  .divider {
    width: 1px;
    height: 20px;
    background: var(--border);
  }

  .stats {
    margin-left: auto;
    font-size: 12px;
    color: var(--text-dim);
    white-space: nowrap;
  }

  .stats b { color: var(--gold); font-weight: 500; }

  .table-wrap {
    overflow-x: auto;
    margin: 0;
  }

  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
  }

  thead {
    background: var(--surface);
    position: sticky;
    top: 0;
    z-index: 10;
  }

  th {
    font-family: 'Cinzel', serif;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.1em;
    color: var(--text-dim);
    text-align: left;
    padding: 10px 10px;
    border-bottom: 1px solid var(--border);
    white-space: nowrap;
    text-transform: uppercase;
  }

  th.race-col { text-align: center; min-width: 52px; }
  th.highlighted { color: var(--gold); background: var(--highlight-col); border-bottom-color: var(--highlight-border); }

  td {
    padding: 7px 10px;
    border-bottom: 1px solid rgba(42,58,80,0.5);
    vertical-align: middle;
    color: var(--text);
  }

  td.race-col { text-align: center; }
  td.highlighted { background: var(--highlight-col); }

  tr:hover td { background: rgba(255,255,255,0.025); }
  tr:hover td.highlighted { background: rgba(201,168,76,0.13); }

  .id-cell {
    font-family: 'Barlow', monospace;
    font-size: 12px;
    color: var(--gold-dim);
    white-space: nowrap;
  }

  .cat-badge {
    display: inline-block;
    font-size: 10px;
    padding: 2px 7px;
    border-radius: 3px;
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--text-dim);
    letter-spacing: 0.04em;
    white-space: nowrap;
  }

  .desc-cell { max-width: 280px; color: var(--text-bright); }

  .yes-pill, .no-pill, .empty-pill {
    display: inline-block;
    width: 20px; height: 20px;
    border-radius: 50%;
    line-height: 20px;
    font-size: 10px;
    font-weight: 500;
    text-align: center;
  }

  .yes-pill { background: var(--yes); color: var(--yes-text); }
  .no-pill  { background: var(--no);  color: var(--no-text);  }
  .empty-pill { background: transparent; color: var(--text-dim); }

  .notes-cell {
    font-size: 11px;
    color: var(--text-dim);
    font-style: italic;
    max-width: 200px;
  }

  .state-msg {
    text-align: center;
    padding: 4rem 2rem;
    color: var(--text-dim);
  }

  .state-msg .icon { font-size: 32px; margin-bottom: 1rem; display: block; }
  .state-msg p { font-size: 14px; line-height: 1.6; }
  .state-msg .hint { font-size: 12px; margin-top: 0.5rem; color: #4a5a6a; }

  .error-msg {
    background: rgba(107,47,47,0.3);
    border: 1px solid var(--no);
    border-radius: 4px;
    color: var(--no-text);
    font-size: 12px;
    margin: 1rem 1.5rem 0;
    padding: 8px 12px;
  }

  .ornament {
    color: var(--gold-dim);
    font-family: 'Cinzel', serif;
    font-size: 10px;
    letter-spacing: 0.2em;
    text-align: center;
    margin: 0.5rem 0;
    opacity: 0.5;
  }
</style>

<div class="app">
  <div class="header">
    <div class="header-top">
      <svg class="crystal" viewBox="0 0 28 28" fill="none">
        <polygon points="14,2 22,9 22,19 14,26 6,19 6,9" fill="#1e2736" stroke="#c9a84c" stroke-width="1"/>
        <polygon points="14,2 22,9 14,14" fill="#c9a84c" opacity="0.5"/>
        <polygon points="14,14 22,19 14,26" fill="#8a6e2f" opacity="0.6"/>
        <polygon points="14,2 6,9 14,14"  fill="#c9a84c" opacity="0.25"/>
        <polygon points="14,14 6,19 14,26" fill="#8a6e2f" opacity="0.3"/>
      </svg>
      <h1>
        FFXIV Animation Database
        <span>Community modding reference</span>
      </h1>
    </div>

    <div class="url-bar">
      <input type="text" id="sheetUrl" placeholder="Paste your Google Sheets CSV export URL here…" />
      <button class="btn-load" id="loadBtn" onclick="loadData()">Load Sheet</button>
    </div>

    <div class="filters">
      <div class="filter-group">
        <label>Search</label>
        <input class="search-input" type="text" id="searchInput" placeholder="ID or description…" oninput="applyFilters()" />
      </div>
      <div class="divider"></div>
      <div class="filter-group">
        <label>Category</label>
        <select id="catFilter" onchange="applyFilters()">
          <option value="">All</option>
        </select>
      </div>
      <div class="divider"></div>
      <div class="filter-group">
        <label>Race</label>
        <select id="raceFilter" onchange="applyFilters()">
          <option value="">All races</option>
        </select>
      </div>
      <div class="filter-group">
        <label>Gender</label>
        <select id="genderFilter" onchange="applyFilters()">
          <option value="">All</option>
          <option value="M">Masculine</option>
          <option value="F">Feminine</option>
        </select>
      </div>
      <div class="stats" id="stats"></div>
    </div>
  </div>

  <div id="errorMsg" class="error-msg" style="display:none"></div>

  <div class="table-wrap">
    <div class="state-msg" id="stateMsg">
      <span class="icon">
        <svg width="40" height="40" viewBox="0 0 28 28" fill="none">
          <polygon points="14,2 22,9 22,19 14,26 6,19 6,9" fill="#1e2736" stroke="#c9a84c" stroke-width="1"/>
          <polygon points="14,2 22,9 14,14" fill="#c9a84c" opacity="0.4"/>
          <polygon points="14,14 22,19 14,26" fill="#8a6e2f" opacity="0.5"/>
        </svg>
      </span>
      <p>Paste your Google Sheets CSV URL above and click <b style="color:var(--gold)">Load Sheet</b> to begin.</p>
      <p class="hint">In Google Sheets: File → Share → Publish to web → CSV → Copy link</p>
    </div>
    <table id="dataTable" style="display:none">
      <thead id="tableHead"></thead>
      <tbody id="tableBody"></tbody>
    </table>
  </div>
</div>

<script>
  const RACES = ['Midlander','Highlander','Elezen','Lalafell',"Miqo'te",'Roegadyn','Au Ra','Hrothgar','Viera'];
  const GENDERS = ['M','F'];
  const RACE_COLS = RACES.flatMap(r => [`${r} M`, `${r} F`]);

  let allRows = [];
  let headers = [];

  function getHighlightedCol() {
    const r = document.getElementById('raceFilter').value;
    const g = document.getElementById('genderFilter').value;
    if (r && g) return `${r} ${g}`;
    if (r) return r;
    return null;
  }

  async function loadData() {
    const raw = document.getElementById('sheetUrl').value.trim();
    if (!raw) return;
    const btn = document.getElementById('loadBtn');
    const errEl = document.getElementById('errorMsg');
    errEl.style.display = 'none';
    btn.disabled = true;
    btn.textContent = 'Loading…';

    let url = raw;
    const sheetMatch = raw.match(/\/spreadsheets\/d\/([^/]+)/);
    if (sheetMatch) {
      const id = sheetMatch[1];
      const gidMatch = raw.match(/[?&]gid=(\d+)/);
      const gid = gidMatch ? gidMatch[1] : '0';
      url = `https://docs.google.com/spreadsheets/d/${id}/export?format=csv&gid=${gid}`;
    }

    try {
      const res = await fetch(url);
      if (!res.ok) throw new Error(`HTTP ${res.status}`);
      const text = await res.text();
      parseCSV(text);
      btn.textContent = 'Reload';
    } catch(e) {
      errEl.textContent = `Could not load sheet: ${e.message}. Make sure the sheet is published publicly (File → Share → Publish to web).`;
      errEl.style.display = 'block';
      btn.textContent = 'Load Sheet';
    }
    btn.disabled = false;
  }

  function parseCSV(text) {
    const lines = text.trim().split(/\r?\n/);
    headers = parseCSVLine(lines[0]);
    allRows = lines.slice(1).map(l => {
      const vals = parseCSVLine(l);
      const obj = {};
      headers.forEach((h,i) => obj[h] = (vals[i] || '').trim());
      return obj;
    }).filter(r => r['ID'] && r['ID'].trim());

    populateFilters();
    buildTableHead();
    applyFilters();
    document.getElementById('stateMsg').style.display = 'none';
    document.getElementById('dataTable').style.display = 'table';
  }

  function parseCSVLine(line) {
    const res = []; let cur = ''; let inQ = false;
    for (let i = 0; i < line.length; i++) {
      const c = line[i];
      if (c === '"') { inQ = !inQ; continue; }
      if (c === ',' && !inQ) { res.push(cur); cur = ''; continue; }
      cur += c;
    }
    res.push(cur);
    return res;
  }

  function populateFilters() {
    const cats = [...new Set(allRows.map(r => r['Category']).filter(Boolean))].sort();
    const catSel = document.getElementById('catFilter');
    catSel.innerHTML = '<option value="">All categories</option>';
    cats.forEach(c => { const o = document.createElement('option'); o.value = c; o.textContent = c; catSel.appendChild(o); });

    const raceSel = document.getElementById('raceFilter');
    raceSel.innerHTML = '<option value="">All races</option>';
    RACES.forEach(r => { const o = document.createElement('option'); o.value = r; o.textContent = r; raceSel.appendChild(o); });
  }

  function buildTableHead() {
    const hl = getHighlightedCol();
    const thead = document.getElementById('tableHead');
    const tr = document.createElement('tr');
    const fixedCols = ['ID','Category','Description'];
    [...fixedCols, ...RACE_COLS, 'Notes'].forEach(col => {
      const th = document.createElement('th');
      const isRace = RACE_COLS.includes(col);
      if (isRace) {
        th.className = 'race-col' + (isHighlighted(col, hl) ? ' highlighted' : '');
        const [race, gen] = col.split(/ (?=[MF]$)/);
        th.innerHTML = `<span style="display:block;font-size:9px">${race}</span><span>${gen === 'M' ? 'M' : 'F'}</span>`;
      } else {
        th.textContent = col;
        if (col === 'Notes') th.style.minWidth = '140px';
      }
      tr.appendChild(th);
    });
    thead.innerHTML = '';
    thead.appendChild(tr);
  }

  function isHighlighted(col, hl) {
    if (!hl) return false;
    if (hl.includes(' ')) return col === hl;
    return col.startsWith(hl + ' ');
  }

  function applyFilters() {
    const search = document.getElementById('searchInput').value.toLowerCase();
    const cat = document.getElementById('catFilter').value;
    const race = document.getElementById('raceFilter').value;
    const gender = document.getElementById('genderFilter').value;
    const hl = getHighlightedCol();

    buildTableHead();

    let filtered = allRows.filter(row => {
      if (search && !row['ID'].toLowerCase().includes(search) && !(row['Description']||'').toLowerCase().includes(search)) return false;
      if (cat && row['Category'] !== cat) return false;
      if (race && gender) {
        const col = `${race} ${gender}`;
        if ((row[col]||'').toLowerCase() !== 'yes') return false;
      } else if (race) {
        const hasAny = GENDERS.some(g => (row[`${race} ${g}`]||'').toLowerCase() === 'yes');
        if (!hasAny) return false;
      }
      return true;
    });

    const tbody = document.getElementById('tableBody');
    tbody.innerHTML = '';

    filtered.forEach(row => {
      const tr = document.createElement('tr');
      const fixedCols = ['ID','Category','Description'];

      fixedCols.forEach(col => {
        const td = document.createElement('td');
        if (col === 'ID') { td.className = 'id-cell'; td.textContent = row[col]; }
        else if (col === 'Category') { td.innerHTML = `<span class="cat-badge">${row[col]||''}</span>`; }
        else if (col === 'Description') { td.className = 'desc-cell'; td.textContent = row[col]||''; }
        tr.appendChild(td);
      });

      RACE_COLS.forEach(col => {
        const td = document.createElement('td');
        td.className = 'race-col' + (isHighlighted(col, hl) ? ' highlighted' : '');
        const val = (row[col]||'').trim();
        if (val.toLowerCase() === 'yes') td.innerHTML = '<span class="yes-pill">Y</span>';
        else if (val.toLowerCase() === 'no') td.innerHTML = '<span class="no-pill">N</span>';
        else td.innerHTML = '<span class="empty-pill">·</span>';
        tr.appendChild(td);
      });

      const noteTd = document.createElement('td');
      noteTd.className = 'notes-cell';
      noteTd.textContent = row['Notes']||'';
      tr.appendChild(noteTd);

      tbody.appendChild(tr);
    });

    document.getElementById('stats').innerHTML =
      `Showing <b>${filtered.length}</b> of <b>${allRows.length}</b> animations`;

    const msg = document.getElementById('stateMsg');
    const tbl = document.getElementById('dataTable');
    if (allRows.length === 0) { msg.style.display='block'; tbl.style.display='none'; }
    else if (filtered.length === 0) {
      msg.style.display='block';
      msg.innerHTML = `<span class="icon">·</span><p>No animations match your current filters.</p>`;
      tbl.style.display='none';
    } else {
      msg.style.display='none';
      tbl.style.display='table';
    }
  }

  document.getElementById('sheetUrl').addEventListener('keydown', e => {
    if (e.key === 'Enter') loadData();
  });
</script>
