<!DOCTYPE html>
<html lang="no">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <title>Treningsapp – Lagvelger</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      -webkit-tap-highlight-color: transparent;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    }
    .no-scrollbar::-webkit-scrollbar {
      display: none;
    }
    .no-scrollbar {
      -ms-overflow-style: none;
      scrollbar-width: none;
    }
  </style>
</head>
<body class="bg-slate-950 text-slate-100 min-h-screen pb-28 select-none">

  <!-- Top Header -->
  <header class="sticky top-0 z-30 bg-slate-900/95 backdrop-blur border-b border-slate-800 px-4 py-3">
    <div class="max-w-3xl mx-auto flex items-center justify-between gap-2">
      <div>
        <h1 class="text-lg font-bold tracking-tight text-white flex items-center gap-2">
          <span>⚽</span> Treningsfeltet
        </h1>
        <p id="header-stats" class="text-xs text-emerald-400 font-medium">50 av 50 på trening</p>
      </div>
      <div class="flex items-center gap-2">
        <button id="toggle-levels-btn" onclick="toggleShowLevels()" class="px-2.5 py-1.5 rounded-lg text-xs font-medium bg-slate-800 text-slate-300 border border-slate-700 hover:bg-slate-700 transition">
          👁️ Nivå: På
        </button>
        <button id="edit-mode-btn" onclick="toggleEditMode()" class="px-2.5 py-1.5 rounded-lg text-xs font-medium bg-slate-800 text-slate-300 border border-slate-700 hover:bg-slate-700 transition">
          ✏️ Endre tropp
        </button>
      </div>
    </div>
  </header>

  <main class="max-w-3xl mx-auto px-4 pt-4">

    <!-- Tab Navigation -->
    <div class="grid grid-cols-2 gap-2 bg-slate-900 p-1 rounded-xl border border-slate-800 mb-4">
      <button id="tab-attendance" onclick="switchTab('attendance')" class="py-2.5 rounded-lg text-sm font-semibold bg-emerald-600 text-white shadow transition">
        1. Oppmøte (<span id="tab-present-count">50</span>)
      </button>
      <button id="tab-teams" onclick="switchTab('teams')" class="py-2.5 rounded-lg text-sm font-semibold text-slate-400 hover:text-white transition">
        2. Laginndeling
      </button>
    </div>

    <!-- VIEW 1: ATTENDANCE -->
    <section id="view-attendance">
      <!-- Add Player Form (Visible only in Edit Mode) -->
      <div id="add-player-panel" class="hidden bg-slate-900 border border-slate-800 rounded-xl p-3.5 mb-4">
        <div class="flex items-center justify-between mb-2">
          <h2 class="text-xs font-bold uppercase tracking-wider text-slate-400">Legg til ny spiller</h2>
          <button onclick="resetDefaultPlayers()" class="text-xs text-rose-400 hover:underline">Tilbakestill standardliste</button>
        </div>
        <form onsubmit="addPlayer(event)" class="flex flex-col sm:flex-row gap-2">
          <input id="new-player-name" type="text" placeholder="Fullt navn..." required
            class="flex-1 bg-slate-950 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white placeholder-slate-500 focus:outline-none focus:border-emerald-500">
          <div class="flex gap-2">
            <select id="new-player-level" class="bg-slate-950 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-emerald-500">
              <option value="1">Nivå 1</option>
              <option value="2" selected>Nivå 2</option>
              <option value="3">Nivå 3</option>
            </select>
            <button type="submit" class="bg-emerald-600 hover:bg-emerald-500 text-white font-semibold px-4 py-2 rounded-lg text-sm transition">
              + Legg til
            </button>
          </div>
        </form>
      </div>

      <!-- Search & Quick Actions -->
      <div class="flex flex-col sm:flex-row gap-2 mb-3">
        <div class="relative flex-1">
          <input id="search-input" type="text" oninput="renderPlayers()" placeholder="Søk etter spiller..."
            class="w-full bg-slate-900 border border-slate-800 rounded-xl pl-9 pr-8 py-2.5 text-sm text-white placeholder-slate-500 focus:outline-none focus:border-emerald-500">
          <span class="absolute left-3 top-2.5 text-slate-500 text-sm">🔍</span>
          <button id="clear-search" onclick="clearSearch()" class="hidden absolute right-2.5 top-2 text-slate-400 hover:text-white text-sm px-1">✕</button>
        </div>
        <div class="flex gap-2">
          <button onclick="setAllPresent(true)" class="flex-1 sm:flex-none px-3 py-2 bg-slate-900 hover:bg-slate-800 border border-slate-800 rounded-xl text-xs font-medium text-emerald-400 transition">
            Alle til stede
          </button>
          <button onclick="setAllPresent(false)" class="flex-1 sm:flex-none px-3 py-2 bg-slate-900 hover:bg-slate-800 border border-slate-800 rounded-xl text-xs font-medium text-rose-400 transition">
            Alle borte
          </button>
        </div>
      </div>

      <p class="text-xs text-slate-400 mb-3 px-1">
        Trykk på en spiller for å huke av som <span class="text-rose-400 font-semibold">borte fra trening</span>.
      </p>

      <!-- Player List -->
      <div id="player-list" class="grid grid-cols-1 sm:grid-cols-2 gap-2"></div>
    </section>

    <!-- VIEW 2: TEAMS -->
    <section id="view-teams" class="hidden">
      <!-- Controls Card -->
      <div class="bg-slate-900 border border-slate-800 rounded-2xl p-4 mb-4 space-y-4">
        <div>
          <label class="block text-xs font-semibold uppercase tracking-wider text-slate-400 mb-2">Antall lag</label>
          <div class="grid grid-cols-4 gap-2">
            <button onclick="setTeamCount(2)" data-team-btn="2" class="team-count-btn py-2.5 rounded-xl font-bold text-sm border transition">2 lag</button>
            <button onclick="setTeamCount(3)" data-team-btn="3" class="team-count-btn py-2.5 rounded-xl font-bold text-sm border transition">3 lag</button>
            <button onclick="setTeamCount(4)" data-team-btn="4" class="team-count-btn py-2.5 rounded-xl font-bold text-sm border transition">4 lag</button>
            <button onclick="setTeamCount(5)" data-team-btn="5" class="team-count-btn py-2.5 rounded-xl font-bold text-sm border transition">5 lag</button>
          </div>
        </div>

        <div>
          <label class="block text-xs font-semibold uppercase tracking-wider text-slate-400 mb-2">Fordelingsmetode</label>
          <div class="grid grid-cols-2 gap-2">
            <button id="mode-balanced" onclick="setBalanceMode('balanced')" class="py-2.5 px-3 rounded-xl text-xs sm:text-sm font-semibold border transition flex items-center justify-center gap-1.5">
              ⚖️ Jevne lag (Nivå)
            </button>
            <button id="mode-random" onclick="setBalanceMode('random')" class="py-2.5 px-3 rounded-xl text-xs sm:text-sm font-semibold border transition flex items-center justify-center gap-1.5">
              🎲 Helt tilfeldig
            </button>
          </div>
        </div>

        <div class="flex gap-2 pt-1">
          <button onclick="generateTeams()" class="flex-1 bg-emerald-600 hover:bg-emerald-500 active:scale-[0.99] text-white font-bold py-3 px-4 rounded-xl shadow-lg shadow-emerald-950/50 transition flex items-center justify-center gap-2">
            <span>🔄</span> Stokk og lag lag
          </button>
          <button onclick="copyTeamsToClipboard()" id="copy-btn" class="bg-slate-800 hover:bg-slate-700 text-slate-200 font-semibold py-3 px-4 rounded-xl border border-slate-700 transition flex items-center justify-center gap-1.5">
            <span>📋</span> <span id="copy-btn-text">Kopier</span>
          </button>
        </div>
      </div>

      <!-- Swap Helper Banner -->
      <div id="swap-banner" class="hidden bg-amber-500/15 border border-amber-500/40 text-amber-200 text-xs rounded-xl px-3.5 py-2.5 mb-3 flex items-center justify-between">
        <span id="swap-banner-text">Velg en spiller på et annet lag for å bytte plass.</span>
        <button onclick="cancelSwap()" class="text-amber-300 font-bold underline ml-2">Avbryt</button>
      </div>

      <!-- Generated Teams Container -->
      <div id="teams-container" class="grid grid-cols-1 md:grid-cols-2 gap-3"></div>
    </section>

  </main>

  <!-- Sticky Bottom Action Bar (Attendance View) -->
  <div id="bottom-bar" class="fixed bottom-0 inset-x-0 bg-slate-900/95 backdrop-blur border-t border-slate-800 p-3 z-20">
    <div class="max-w-3xl mx-auto flex items-center justify-between gap-3">
      <div class="text-xs">
        <span class="text-slate-400">Klar for trening:</span>
        <div class="text-sm font-bold text-white"><span id="bottom-present-count" class="text-emerald-400">50</span> spillere</div>
      </div>
      <button onclick="goToTeamsAndGenerate()" class="bg-emerald-600 hover:bg-emerald-500 active:scale-[0.99] text-white font-bold px-5 py-3 rounded-xl text-sm shadow-lg transition flex items-center gap-2">
        <span>Lag lag nå</span>
        <span>→</span>
      </button>
    </div>
  </div>

  <script>
    const DEFAULT_PLAYERS = [
      { id: 1, name: "Aksel Stefansen-Løland", level: 3, present: true },
      { id: 2, name: "Andreas Hassel Ajaxson", level: 2, present: true },
      { id: 3, name: "Aron Os Gangdal", level: 2, present: true },
      { id: 4, name: "Benjamin Dyrdal", level: 2, present: true },
      { id: 5, name: "Benjamin Nydal Helgeland", level: 1, present: true },
      { id: 6, name: "Benjamin Ødegård", level: 3, present: true },
      { id: 7, name: "Eduard Catalin Ignat", level: 3, present: true },
      { id: 8, name: "Eirik Tenfjord", level: 2, present: true },
      { id: 9, name: "Elias Hinna Dalen", level: 3, present: true },
      { id: 10, name: "Eliot Byrkjeland", level: 1, present: true },
      { id: 11, name: "Emil Sundgot Gjerstad", level: 3, present: true },
      { id: 12, name: "Fredrik Schwalenberg Larsen", level: 2, present: true },
      { id: 13, name: "Fredrik Tjemsland", level: 2, present: true },
      { id: 14, name: "Gustav Mæland", level: 3, present: true },
      { id: 15, name: "Håkon Simpson Hetlevik", level: 2, present: true },
      { id: 16, name: "Isak Johannesen", level: 3, present: true },
      { id: 17, name: "Jakob Sætre Otterskred", level: 2, present: true },
      { id: 18, name: "Jakob Tordal Skar", level: 3, present: true },
      { id: 19, name: "Jan Fredrik Ahmer", level: 2, present: true },
      { id: 20, name: "Johannes Lien Skeiseid", level: 3, present: true },
      { id: 21, name: "Konrad Amble", level: 1, present: true },
      { id: 22, name: "Lars Raude Angermann", level: 1, present: true },
      { id: 23, name: "Leander Hamre Østervold", level: 2, present: true },
      { id: 24, name: "Leandro Dangelo", level: 3, present: true },
      { id: 25, name: "Malvin Skulstad Mcintosh", level: 3, present: true },
      { id: 26, name: "Marius Brekke Strandå", level: 2, present: true },
      { id: 27, name: "Markus Laastad", level: 2, present: true },
      { id: 28, name: "Mats Anders Eikenes Gravdal", level: 1, present: true },
      { id: 29, name: "Nicholas Sylvester Davik", level: 1, present: true },
      { id: 30, name: "Niklas Bøtun Selland", level: 2, present: true },
      { id: 31, name: "Nikolai Skjoldal", level: 2, present: true },
      { id: 32, name: "Noah Tillerli Sirevåg", level: 2, present: true },
      { id: 33, name: "Olav Fjeldstad Nerbøvik", level: 2, present: true },
      { id: 34, name: "Olav Tønder Antun", level: 2, present: true },
      { id: 35, name: "Ole Stephansen", level: 3, present: true },
      { id: 36, name: "Oliver Henriksen Haga", level: 2, present: true },
      { id: 37, name: "Olliver Sulen Bjørkly", level: 2, present: true },
      { id: 38, name: "Oscar Twomey", level: 3, present: true },
      { id: 39, name: "Philip Steiner Røssevold", level: 3, present: true },
      { id: 40, name: "Sander Angeltvedt", level: 2, present: true },
      { id: 41, name: "Sander Johansen", level: 2, present: true },
      { id: 42, name: "Sander Skjelbred Lie", level: 1, present: true },
      { id: 43, name: "Sigurd Bruu Raa", level: 2, present: true },
      { id: 44, name: "Sigurd Tenfjord", level: 2, present: true },
      { id: 45, name: "Sondre Graue Lerøy", level: 2, present: true },
      { id: 46, name: "Sondre Mikal Døssland", level: 2, present: true },
      { id: 47, name: "Theodor Viken Næss", level: 2, present: true },
      { id: 48, name: "Tobias Glaser", level: 3, present: true },
      { id: 49, name: "Tobias Hansen Storli", level: 2, present: true },
      { id: 50, name: "Tobias Strand Knudsen", level: 1, present: true }
    ];

    const TEAM_STYLES = [
      { name: "Lag 1 (Grønn)", badge: "bg-emerald-500/20 text-emerald-300 border-emerald-500/40", dot: "bg-emerald-400" },
      { name: "Lag 2 (Blå)", badge: "bg-sky-500/20 text-sky-300 border-sky-500/40", dot: "bg-sky-400" },
      { name: "Lag 3 (Rød)", badge: "bg-rose-500/20 text-rose-300 border-rose-500/40", dot: "bg-rose-400" },
      { name: "Lag 4 (Gul)", badge: "bg-amber-500/20 text-amber-300 border-amber-500/40", dot: "bg-amber-400" },
      { name: "Lag 5 (Lilla)", badge: "bg-purple-500/20 text-purple-300 border-purple-500/40", dot: "bg-purple-400" }
    ];

    let players = loadPlayers();
    let teamCount = 3;
    let balanceMode = 'balanced'; // 'balanced' | 'random'
    let showLevels = true;
    let editMode = false;
    let currentTeams = [];
    let selectedForSwap = null; // { teamIndex, playerIndex }

    function loadPlayers() {
      try {
        const saved = localStorage.getItem('fotball_tropp_v1');
        if (saved) {
          const parsed = JSON.parse(saved);
          if (Array.isArray(parsed) && parsed.length > 0) return parsed;
        }
      } catch (e) {}
      return JSON.parse(JSON.stringify(DEFAULT_PLAYERS));
    }

    function savePlayers() {
      try {
        localStorage.setItem('fotball_tropp_v1', JSON.stringify(players));
      } catch (e) {}
    }

    function sortPlayersList() {
      players.sort((a, b) => a.name.localeCompare(b.name, 'no'));
    }

    function updateCounts() {
      const presentCount = players.filter(p => p.present).length;
      const totalCount = players.length;
      document.getElementById('header-stats').textContent = `${presentCount} av ${totalCount} på trening`;
      document.getElementById('tab-present-count').textContent = presentCount;
      document.getElementById('bottom-present-count').textContent = presentCount;
    }

    function renderPlayers() {
      sortPlayersList();
      updateCounts();

      const query = document.getElementById('search-input').value.trim().toLowerCase();
      const clearBtn = document.getElementById('clear-search');
      clearBtn.classList.toggle('hidden', query.length === 0);

      const listEl = document.getElementById('player-list');
      listEl.innerHTML = '';

      const filtered = players.filter(p => p.name.toLowerCase().includes(query));

      if (filtered.length === 0) {
        listEl.innerHTML = `<div class="col-span-full text-center py-8 text-slate-500 text-sm">Ingen spillere funnet for «${query}»</div>`;
        return;
      }

      filtered.forEach(player => {
        const card = document.createElement('div');
        const isPresent = player.present;

        card.className = `flex items-center justify-between p-3 rounded-xl border transition cursor-pointer ${
          isPresent
            ? 'bg-slate-900 border-slate-800 hover:border-slate-700'
            : 'bg-rose-950/25 border-rose-900/50 opacity-75'
        }`;

        card.onclick = (e) => {
          if (e.target.closest('.edit-control')) return;
          toggleAttendance(player.id);
        };

        const leftSide = document.createElement('div');
        leftSide.className = 'flex items-center gap-3 min-w-0';

        const statusIcon = document.createElement('div');
        statusIcon.className = `w-6 h-6 rounded-full flex items-center justify-center text-xs font-bold shrink-0 transition ${
          isPresent
            ? 'bg-emerald-500/20 text-emerald-400 border border-emerald-500/40'
            : 'bg-rose-500/20 text-rose-400 border border-rose-500/40'
        }`;
        statusIcon.textContent = isPresent ? '✓' : '✕';

        const nameWrap = document.createElement('div');
        nameWrap.className = 'truncate';
        const nameEl = document.createElement('div');
        nameEl.className = `text-sm font-medium truncate ${isPresent ? 'text-slate-100' : 'line-through text-slate-400'}`;
        nameEl.textContent = player.name;

        const statusSub = document.createElement('div');
        statusSub.className = `text-[11px] ${isPresent ? 'text-emerald-500/80' : 'text-rose-400'}`;
        statusSub.textContent = isPresent ? 'På trening' : 'Borte';

        nameWrap.appendChild(nameEl);
        nameWrap.appendChild(statusSub);
        leftSide.appendChild(statusIcon);
        leftSide.appendChild(nameWrap);

        const rightSide = document.createElement('div');
        rightSide.className = 'flex items-center gap-1.5 shrink-0 ml-2';

        if (editMode) {
          const levelSelect = document.createElement('select');
          levelSelect.className = 'edit-control bg-slate-950 border border-slate-700 rounded-lg px-2 py-1 text-xs text-slate-200';
          [1, 2, 3].forEach(lvl => {
            const opt = document.createElement('option');
            opt.value = lvl;
            opt.textContent = `Nivå ${lvl}`;
            if (player.level === lvl) opt.selected = true;
            levelSelect.appendChild(opt);
          });
          levelSelect.onchange = (e) => {
            updatePlayerLevel(player.id, parseInt(e.target.value, 10));
          };

          const delBtn = document.createElement('button');
          delBtn.className = 'edit-control p-1.5 rounded-lg bg-rose-500/10 text-rose-400 hover:bg-rose-500/20 text-xs';
          delBtn.textContent = '🗑️';
          delBtn.title = 'Slett spiller';
          delBtn.onclick = () => deletePlayer(player.id);

          rightSide.appendChild(levelSelect);
          rightSide.appendChild(delBtn);
        } else if (showLevels) {
          const badge = document.createElement('span');
          const levelColors = {
            1: 'bg-slate-800 text-slate-300 border-slate-700',
            2: 'bg-blue-950/60 text-blue-300 border-blue-800/60',
            3: 'bg-amber-950/60 text-amber-300 border-amber-800/60'
          };
          badge.className = `px-2 py-0.5 rounded-md text-[11px] font-semibold border ${levelColors[player.level] || levelColors[2]}`;
          badge.textContent = `Nivå ${player.level}`;
          rightSide.appendChild(badge);
        }

        card.appendChild(leftSide);
        card.appendChild(rightSide);
        listEl.appendChild(card);
      });
    }

    function toggleAttendance(id) {
      const p = players.find(item => item.id === id);
      if (p) {
        p.present = !p.present;
        savePlayers();
        renderPlayers();
      }
    }

    function setAllPresent(state) {
      players.forEach(p => p.present = state);
      savePlayers();
      renderPlayers();
    }

    function clearSearch() {
      document.getElementById('search-input').value = '';
      renderPlayers();
    }

    function toggleShowLevels() {
      showLevels = !showLevels;
      const btn = document.getElementById('toggle-levels-btn');
      btn.textContent = showLevels ? '👁️ Nivå: På' : '🙈 Nivå: Skjult';
      renderPlayers();
      if (currentTeams.length > 0) renderTeams();
    }

    function toggleEditMode() {
      editMode = !editMode;
      const btn = document.getElementById('edit-mode-btn');
      const panel = document.getElementById('add-player-panel');
      if (editMode) {
        btn.classList.add('bg-emerald-600', 'text-white', 'border-emerald-500');
        btn.classList.remove('bg-slate-800', 'text-slate-300', 'border-slate-700');
        btn.textContent = '✓ Ferdig';
        panel.classList.remove('hidden');
      } else {
        btn.classList.remove('bg-emerald-600', 'text-white', 'border-emerald-500');
        btn.classList.add('bg-slate-800', 'text-slate-300', 'border-slate-700');
        btn.textContent = '✏️ Endre tropp';
        panel.classList.add('hidden');
      }
      renderPlayers();
    }

    function addPlayer(e) {
      e.preventDefault();
      const nameInput = document.getElementById('new-player-name');
      const levelSelect = document.getElementById('new-player-level');
      const name = nameInput.value.trim();
      if (!name) return;

      const maxId = players.reduce((max, p) => Math.max(max, p.id), 0);
      players.push({
        id: maxId + 1,
        name: name,
        level: parseInt(levelSelect.value, 10),
        present: true
      });

      nameInput.value = '';
      savePlayers();
      renderPlayers();
    }

    function updatePlayerLevel(id, level) {
      const p = players.find(item => item.id === id);
      if (p) {
        p.level = level;
        savePlayers();
      }
    }

    function deletePlayer(id) {
      const p = players.find(item => item.id === id);
      if (!p) return;
      if (confirm(`Slette ${p.name} fra troppen?`)) {
        players = players.filter(item => item.id !== id);
        savePlayers();
        renderPlayers();
      }
    }

    function resetDefaultPlayers() {
      if (confirm('Tilbakestille spillerlisten til de opprinnelige 50 spillerne?')) {
        players = JSON.parse(JSON.stringify(DEFAULT_PLAYERS));
        savePlayers();
        renderPlayers();
      }
    }

    function switchTab(tab) {
      const attView = document.getElementById('view-attendance');
      const teamView = document.getElementById('view-teams');
      const attTab = document.getElementById('tab-attendance');
      const teamTab = document.getElementById('tab-teams');
      const bottomBar = document.getElementById('bottom-bar');

      if (tab === 'attendance') {
        attView.classList.remove('hidden');
        teamView.classList.add('hidden');
        bottomBar.classList.remove('hidden');

        attTab.classList.add('bg-emerald-600', 'text-white', 'shadow');
        attTab.classList.remove('text-slate-400');
        teamTab.classList.remove('bg-emerald-600', 'text-white', 'shadow');
        teamTab.classList.add('text-slate-400');
      } else {
        attView.classList.add('hidden');
        teamView.classList.remove('hidden');
        bottomBar.classList.add('hidden');

        teamTab.classList.add('bg-emerald-600', 'text-white', 'shadow');
        teamTab.classList.remove('text-slate-400');
        attTab.classList.remove('bg-emerald-600', 'text-white', 'shadow');
        attTab.classList.add('text-slate-400');

        if (currentTeams.length === 0) {
          generateTeams();
        }
      }
    }

    function goToTeamsAndGenerate() {
      switchTab('teams');
      generateTeams();
    }

    function setTeamCount(count) {
      teamCount = count;
      document.querySelectorAll('.team-count-btn').forEach(btn => {
        const val = parseInt(btn.getAttribute('data-team-btn'), 10);
        if (val === count) {
          btn.classList.add('bg-emerald-600', 'border-emerald-500', 'text-white');
          btn.classList.remove('bg-slate-950', 'border-slate-800', 'text-slate-300');
        } else {
          btn.classList.remove('bg-emerald-600', 'border-emerald-500', 'text-white');
          btn.classList.add('bg-slate-950', 'border-slate-800', 'text-slate-300');
        }
      });
      generateTeams();
    }

    function setBalanceMode(mode) {
      balanceMode = mode;
      const balBtn = document.getElementById('mode-balanced');
      const rndBtn = document.getElementById('mode-random');

      if (mode === 'balanced') {
        balBtn.classList.add('bg-emerald-600/20', 'border-emerald-500', 'text-emerald-300');
        balBtn.classList.remove('bg-slate-950', 'border-slate-800', 'text-slate-400');
        rndBtn.classList.remove('bg-emerald-600/20', 'border-emerald-500', 'text-emerald-300');
        rndBtn.classList.add('bg-slate-950', 'border-slate-800', 'text-slate-400');
      } else {
        rndBtn.classList.add('bg-emerald-600/20', 'border-emerald-500', 'text-emerald-300');
        rndBtn.classList.remove('bg-slate-950', 'border-slate-800', 'text-slate-400');
        balBtn.classList.remove('bg-emerald-600/20', 'border-emerald-500', 'text-emerald-300');
        balBtn.classList.add('bg-slate-950', 'border-slate-800', 'text-slate-400');
      }
      generateTeams();
    }

    function shuffleArray(array) {
      const arr = [...array];
      for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
      }
      return arr;
    }

    function generateTeams() {
      cancelSwap();
      const available = players.filter(p => p.present);
      const container = document.getElementById('teams-container');

      if (available.length < teamCount) {
        currentTeams = [];
        container.innerHTML = `
          <div class="col-span-full bg-slate-900 border border-slate-800 rounded-2xl p-6 text-center">
            <p class="text-slate-300 font-medium mb-1">For få spillere til ${teamCount} lag</p>
            <p class="text-xs text-slate-400">Det er kun ${available.length} spillere markert som til stede.</p>
          </div>
        `;
        return;
      }

      const teams = Array.from({ length: teamCount }, () => []);

      if (balanceMode === 'random') {
        const shuffled = shuffleArray(available);
        shuffled.forEach((player, idx) => {
          teams[idx % teamCount].push(player);
        });
      } else {
        // Group by level (3, 2, 1), shuffle inside each level for fresh combinations, then snake-draft
        const byLevel = {
          3: shuffleArray(available.filter(p => p.level === 3)),
          2: shuffleArray(available.filter(p => p.level === 2)),
          1: shuffleArray(available.filter(p => p.level === 1))
        };
        const ordered = [...byLevel[3], ...byLevel[2], ...byLevel[1]];

        ordered.forEach((player, idx) => {
          const round = Math.floor(idx / teamCount);
          const pos = idx % teamCount;
          const teamIdx = round % 2 === 0 ? pos : (teamCount - 1 - pos);
          teams[teamIdx].push(player);
        });
      }

      // Sort players alphabetically inside each team for easy reading
      teams.forEach(t => t.sort((a, b) => a.name.localeCompare(b.name, 'no')));
      currentTeams = teams;
      renderTeams();
    }

    function renderTeams() {
      const container = document.getElementById('teams-container');
      container.innerHTML = '';

      currentTeams.forEach((team, teamIdx) => {
        const style = TEAM_STYLES[teamIdx % TEAM_STYLES.length];
        const totalSkill = team.reduce((sum, p) => sum + p.level, 0);
        const avgSkill = team.length ? (totalSkill / team.length).toFixed(2) : '0.00';

        const card = document.createElement('div');
        card.className = 'bg-slate-900 border border-slate-800 rounded-2xl overflow-hidden flex flex-col';

        const header = document.createElement('div');
        header.className = 'px-4 py-3 border-b border-slate-800 flex items-center justify-between bg-slate-900/70';

        const titleWrap = document.createElement('div');
        titleWrap.className = 'flex items-center gap-2';
        titleWrap.innerHTML = `
          <span class="w-2.5 h-2.5 rounded-full ${style.dot}"></span>
          <h3 class="font-bold text-sm text-white">${style.name}</h3>
        `;

        const metaWrap = document.createElement('div');
        metaWrap.className = 'flex items-center gap-2 text-xs';
        metaWrap.innerHTML = `
          <span class="px-2 py-0.5 rounded-md border font-semibold ${style.badge}">${team.length} spillere</span>
          ${showLevels ? `<span class="text-slate-400 font-medium">Snitt: ${avgSkill}</span>` : ''}
        `;

        header.appendChild(titleWrap);
        header.appendChild(metaWrap);
        card.appendChild(header);

        const list = document.createElement('div');
        list.className = 'divide-y divide-slate-800/70';

        team.forEach((player, playerIdx) => {
          const isSelected = selectedForSwap && selectedForSwap.teamIndex === teamIdx && selectedForSwap.playerIndex === playerIdx;
          const row = document.createElement('div');
          row.className = `px-4 py-2.5 flex items-center justify-between text-sm cursor-pointer transition ${
            isSelected
              ? 'bg-amber-500/20 text-amber-200'
              : 'hover:bg-slate-800/50 text-slate-200'
          }`;
          row.onclick = () => handlePlayerSwapClick(teamIdx, playerIdx);

          const nameSpan = document.createElement('span');
          nameSpan.className = 'truncate pr-2';
          nameSpan.textContent = `${playerIdx + 1}. ${player.name}`;

          const rightSpan = document.createElement('div');
          rightSpan.className = 'flex items-center gap-2 shrink-0';

          if (showLevels) {
            const lvl = document.createElement('span');
            lvl.className = 'text-[11px] text-slate-400 bg-slate-950 px-1.5 py-0.5 rounded border border-slate-800';
            lvl.textContent = `Nivå ${player.level}`;
            rightSpan.appendChild(lvl);
          }

          const swapIcon = document.createElement('span');
          swapIcon.className = 'text-xs text-slate-500';
          swapIcon.textContent = isSelected ? '⇄ Valgt' : '⇄';
          rightSpan.appendChild(swapIcon);

          row.appendChild(nameSpan);
          row.appendChild(rightSpan);
          list.appendChild(row);
        });

        card.appendChild(list);
        container.appendChild(card);
      });
    }

    function handlePlayerSwapClick(teamIndex, playerIndex) {
      if (!selectedForSwap) {
        selectedForSwap = { teamIndex, playerIndex };
        const pName = currentTeams[teamIndex][playerIndex].name;
        document.getElementById('swap-banner-text').textContent = `Valgt: ${pName}. Trykk på en spiller på et annet lag for å bytte.`;
        document.getElementById('swap-banner').classList.remove('hidden');
        renderTeams();
        return;
      }

      if (selectedForSwap.teamIndex === teamIndex && selectedForSwap.playerIndex === playerIndex) {
        cancelSwap();
        return;
      }

      // Swap players between teams
      const temp = currentTeams[selectedForSwap.teamIndex][selectedForSwap.playerIndex];
      currentTeams[selectedForSwap.teamIndex][selectedForSwap.playerIndex] = currentTeams[teamIndex][playerIndex];
      currentTeams[teamIndex][playerIndex] = temp;

      // Keep alphabetical order
      currentTeams[selectedForSwap.teamIndex].sort((a, b) => a.name.localeCompare(b.name, 'no'));
      currentTeams[teamIndex].sort((a, b) => a.name.localeCompare(b.name, 'no'));

      cancelSwap();
    }

    function cancelSwap() {
      selectedForSwap = null;
      document.getElementById('swap-banner').classList.add('hidden');
      if (currentTeams.length > 0) renderTeams();
    }

    function copyTeamsToClipboard() {
      if (!currentTeams.length) return;
      const lines = currentTeams.map((team, idx) => {
        const style = TEAM_STYLES[idx % TEAM_STYLES.length];
        const playerLines = team.map(p => `- ${p.name}`).join('\n');
        return `${style.name} (${team.length}):\n${playerLines}`;
      });

      const text = lines.join('\n\n');
      navigator.clipboard.writeText(text).then(() => {
        const btnText = document.getElementById('copy-btn-text');
        btnText.textContent = 'Kopiert!';
        setTimeout(() => {
          btnText.textContent = 'Kopier';
        }, 2000);
      });
    }

    // Init
    setTeamCount(3);
    setBalanceMode('balanced');
    renderPlayers();
  </script>
</body>
</html>
