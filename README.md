<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>🔥 RACIK BUMBU NUSANTARA</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      background: linear-gradient(135deg, #1a0f0a 0%, #2d1a10 50%, #1f120c 100%);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Segoe UI', Tahoma, sans-serif;
      padding: 20px;
    }
    .game-container {
      background: #f5e6d3;
      background-image: radial-gradient(circle at 20% 30%, #fdf3e7, #e8d4be);
      border-radius: 48px 48px 30px 30px;
      box-shadow: 0 30px 50px rgba(0,0,0,0.8), 0 0 0 3px #b8956e inset;
      max-width: 820px;
      width: 100%;
      padding: 20px 24px 28px;
    }
    .header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #3f281d;
      padding: 12px 24px;
      border-radius: 60px;
      margin-bottom: 20px;
      color: #faead1;
      box-shadow: 0 6px 0 #1f120c;
    }
    .header h1 {
      font-size: 1.8rem;
      letter-spacing: 1px;
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .stats {
      display: flex;
      gap: 20px;
      font-weight: 700;
      font-size: 1.2rem;
    }
    .stats span {
      background: #1f120c;
      padding: 6px 18px;
      border-radius: 30px;
      color: #f7dba7;
    }
    .resep-hari-ini {
      background: #dcc2a8;
      border-radius: 30px;
      padding: 10px 20px;
      margin-bottom: 18px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border: 3px solid #b5906a;
      box-shadow: inset 0 2px 6px rgba(0,0,0,0.15);
    }
    .resep-hari-ini .label {
      font-weight: 600;
      color: #3d281a;
      font-size: 1.2rem;
    }
    .resep-hari-ini .target-resep {
      font-size: 1.8rem;
      font-weight: 700;
      color: #2c180a;
      background: #fef3e2;
      padding: 4px 24px;
      border-radius: 40px;
      box-shadow: 0 4px 0 #8f6d4a;
    }
    .resep-hari-ini .bahan-target {
      display: flex;
      gap: 6px;
      flex-wrap: wrap;
    }
    .bahan-target .bahan-chip {
      background: #4a3522;
      color: #f6e3cd;
      padding: 4px 14px;
      border-radius: 30px;
      font-size: 0.9rem;
      font-weight: 600;
    }
    .pantry-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      background: #b3906e;
      padding: 16px 14px;
      border-radius: 40px;
      margin-bottom: 18px;
      min-height: 80px;
      border: 4px solid #7a5a3d;
      box-shadow: inset 0 4px 10px rgba(0,0,0,0.3);
    }
    .bahan-item {
      background: #fcf0dd;
      padding: 8px 16px;
      border-radius: 40px;
      font-size: 1.2rem;
      font-weight: 600;
      box-shadow: 0 5px 0 #8f6d4a, 0 6px 12px rgba(0,0,0,0.2);
      cursor: pointer;
      transition: 0.08s linear;
      border: 2px solid #ead3b8;
      display: flex;
      align-items: center;
      gap: 6px;
      user-select: none;
    }
    .bahan-item:active {
      transform: scale(0.92);
      box-shadow: 0 2px 0 #6f5136;
    }
    .bahan-item.disabled {
      opacity: 0.4;
      pointer-events: none;
      transform: translateY(3px);
      box-shadow: 0 2px 0 #6f5136;
    }
    .wajan-utama {
      background: #2d241e;
      border-radius: 200px 200px 50px 50px;
      padding: 20px 16px 25px;
      border-bottom: 12px solid #0f0a08;
      box-shadow: inset 0 -8px 20px #00000077, 0 12px 28px rgba(0,0,0,0.7);
      margin: 8px 0 16px;
    }
    .wajan-inner {
      background: #4a4036;
      background: radial-gradient(circle at 30% 35%, #64584a, #322a22);
      min-height: 130px;
      border-radius: 160px 160px 50px 50px;
      padding: 18px 12px;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
      gap: 12px 20px;
      border: 4px solid #7a6852;
      box-shadow: inset 0 0 0 4px #1a1511;
    }
    .wajan-inner .bahan-item {
      background: #f2e2cc;
      box-shadow: 0 4px 0 #8f6d4a;
      font-size: 1rem;
      padding: 6px 14px;
      cursor: default;
      animation: jatuh 0.2s ease-out;
    }
    @keyframes jatuh {
      0% { transform: translateY(-40px) scale(0.5); opacity: 0; }
      100% { transform: translateY(0) scale(1); opacity: 1; }
    }
    .action-row {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      justify-content: center;
      margin: 18px 0 12px;
    }
    .btn {
      background: #fae6cf;
      border: none;
      border-radius: 50px;
      padding: 12px 28px;
      font-weight: 700;
      font-size: 1.1rem;
      box-shadow: 0 6px 0 #8f6d4a, 0 4px 12px rgba(0,0,0,0.25);
      cursor: pointer;
      transition: 0.06s linear;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      border: 2px solid #fef3e2;
      color: #2d1a0c;
    }
    .btn:active {
      transform: translateY(5px);
      box-shadow: 0 1px 0 #6f5136;
    }
    .btn:disabled {
      opacity: 0.5;
      transform: translateY(4px);
      box-shadow: 0 2px 0 #6f5136;
      pointer-events: none;
    }
    .btn-masak { background: #f5b56b; box-shadow: 0 6px 0 #b87d3a; }
    .btn-buang { background: #dd8066; box-shadow: 0 6px 0 #a55338; }
    .btn-acak { background: #8fc7a5; box-shadow: 0 6px 0 #4a7d5e; color: #1e3426; }
    .btn-reset { background: #c9b39b; box-shadow: 0 6px 0 #826b52; }
    .info-panel {
      background: #fcf3e6;
      border-radius: 40px;
      padding: 14px 20px;
      margin-top: 18px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border: 3px solid #d3b691;
      flex-wrap: wrap;
    }
    .info-panel .combo-box {
      font-size: 1.4rem;
      font-weight: 700;
      color: #2d1a0c;
    }
    .info-panel .msg-box {
      font-size: 1.2rem;
      font-weight: 600;
      color: #3d2618;
      background: #e6d4be;
      padding: 6px 24px;
      border-radius: 50px;
    }
    .timer-box {
      background: #2f1f14;
      padding: 6px 24px;
      border-radius: 40px;
      color: #f7dba7;
      font-weight: 700;
      font-size: 1.4rem;
    }
    @media (max-width: 600px) {
      .header { flex-direction: column; gap: 10px; }
      .stats { width: 100%; justify-content: center; }
      .resep-hari-ini { flex-direction: column; gap: 6px; }
    }
  </style>
</head>
<body>
<div class="game-container">
  <div class="header">
    <h1>🍲 RACIK BUMBU</h1>
    <div class="stats">
      <span>🏆 <span id="scoreDisplay">0</span></span>
      <span>⏱️ <span id="timerDisplay">30</span>s</span>
    </div>
  </div>

  <div class="resep-hari-ini">
    <span class="label">📋 Resep Hari Ini</span>
    <div class="target-resep" id="resepTarget">—</div>
    <div class="bahan-target" id="bahanTargetContainer"></div>
  </div>

  <div class="pantry-grid" id="pantryContainer"></div>

  <div class="wajan-utama">
    <div class="wajan-inner" id="wajanContainer"></div>
  </div>

  <div class="action-row">
    <button class="btn btn-masak" id="cookBtn">🔥 MASAK!</button>
    <button class="btn btn-buang" id="clearWajanBtn">🗑️ BUANG</button>
    <button class="btn btn-acak" id="randomBahanBtn">🎲 TAMBAH BAHAN</button>
  </div>

  <div class="info-panel">
    <div class="combo-box">🔥 COMBO: <span id="comboDisplay">0</span>x</div>
    <div class="msg-box" id="statusMsg">✨ Masukkan bahan ke wajan!</div>
    <div class="timer-box" id="timerBonusDisplay">⏳ +0</div>
  </div>

  <div style="display:flex; justify-content:center; margin-top:14px;">
    <button class="btn btn-reset" id="resetGameBtn">🔄 RESET GAME</button>
  </div>
</div>

<script>
  (function() {
    // ---- RESEP MASAKAN INDONESIA (versi urutan bahan) ----
    const RESEP = [
      { nama: 'Nasi Goreng', emoji: '🍛', bahan: ['nasi', 'bawang', 'cabe', 'kecap'] },
      { nama: 'Soto Ayam', emoji: '🍜', bahan: ['ayam', 'bawang', 'kunyit', 'daun salam'] },
      { nama: 'Gado-Gado', emoji: '🥗', bahan: ['kentang', 'telur', 'tahu', 'sayuran'] },
      { nama: 'Rendang', emoji: '🥘', bahan: ['daging', 'santan', 'cabe', 'kunyit'] },
      { nama: 'Pecel Lele', emoji: '🐟', bahan: ['lele', 'bawang', 'cabe', 'terasi'] },
      { nama: 'Bakso', emoji: '🍢', bahan: ['daging', 'bawang', 'telur', 'tapioka'] },
      { nama: 'Sate Ayam', emoji: '🍖', bahan: ['ayam', 'bawang', 'kecap', 'cabe'] },
    ];

    const semuaBahan = ['nasi', 'bawang', 'cabe', 'kecap', 'ayam', 'kunyit', 'daun salam', 'kentang', 'telur', 'tahu', 'sayuran', 'daging', 'santan', 'lele', 'terasi', 'tapioka'];
    const emojiBahan = {
      nasi: '🍚', bawang: '🧅', cabe: '🌶️', kecap: '🫘', ayam: '🍗', kunyit: '🟡',
      'daun salam': '🌿', kentang: '🥔', telur: '🥚', tahu: '🧈', sayuran: '🥬',
      daging: '🥩', santan: '🥥', lele: '🐟', terasi: '🦐', tapioka: '🧋'
    };

    // ---- STATE ----
    let pantryItems = [];
    let wajanItems = [];
    let score = 0;
    let combo = 0;
    let currentResep = null;        // resep yang sedang ditargetkan
    let timer = 30;                // detik
    let timerInterval = null;
    let gameActive = true;

    // DOM refs
    const pantryEl = document.getElementById('pantryContainer');
    const wajanEl = document.getElementById('wajanContainer');
    const scoreDisplay = document.getElementById('scoreDisplay');
    const timerDisplay = document.getElementById('timerDisplay');
    const timerBonusDisplay = document.getElementById('timerBonusDisplay');
    const comboDisplay = document.getElementById('comboDisplay');
    const statusMsg = document.getElementById('statusMsg');
    const resepTarget = document.getElementById('resepTarget');
    const bahanTargetContainer = document.getElementById('bahanTargetContainer');
    const cookBtn = document.getElementById('cookBtn');
    const clearWajanBtn = document.getElementById('clearWajanBtn');
    const randomBahanBtn = document.getElementById('randomBahanBtn');
    const resetGameBtn = document.getElementById('resetGameBtn');

    // ---- HELPER ----
    function shuffleArray(arr) {
      for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
      }
      return arr;
    }

    // pilih resep acak
    function pilihResep() {
      const random = RESEP[Math.floor(Math.random() * RESEP.length)];
      currentResep = { ...random };
      // update tampilan resep
      resepTarget.textContent = `${random.emoji} ${random.nama}`;
      bahanTargetContainer.innerHTML = '';
      random.bahan.forEach(b => {
        const chip = document.createElement('span');
        chip.className = 'bahan-chip';
        chip.textContent = `${emojiBahan[b] || '🍽️'} ${b}`;
        bahanTargetContainer.appendChild(chip);
      });
    }

    // inisialisasi pantry
    function initPantry() {
      const shuffled = shuffleArray([...semuaBahan]);
      const count = Math.min(10, Math.max(7, shuffled.length));
      pantryItems = shuffled.slice(0, count);
    }

    // render pantry
    function renderPantry() {
      pantryEl.innerHTML = '';
      pantryItems.forEach((bahan, idx) => {
        const div = document.createElement('div');
        div.className = 'bahan-item';
        div.dataset.bahan = bahan;
        div.dataset.index = idx;
        div.innerHTML = `${emojiBahan[bahan] || '🍽️'} ${bahan}`;
        div.addEventListener('click', () => pindahkanBahanKeWajan(bahan));
        pantryEl.appendChild(div);
      });
    }

    // render wajan
    function renderWajan() {
      wajanEl.innerHTML = '';
      wajanItems.forEach((bahan) => {
        const div = document.createElement('div');
        div.className = 'bahan-item';
        div.dataset.bahan = bahan;
        div.innerHTML = `${emojiBahan[bahan] || '🍽️'} ${bahan}`;
        wajanEl.appendChild(div);
      });
    }

    // update UI score, combo, timer, message
    function updateUI() {
      scoreDisplay.textContent = score;
      comboDisplay.textContent = combo;
      timerDisplay.textContent = timer;
      const bonus = Math.floor(timer / 5) * 2;
      timerBonusDisplay.textContent = `⏳ +${bonus}`;
    }

    // pindahkan bahan dari pantry ke wajan (dengan klik)
    function pindahkanBahanKeWajan(bahan) {
      if (!gameActive) {
        statusMsg.textContent = '⏰ Game selesai! Reset untuk bermain lagi.';
        return;
      }
      const index = pantryItems.indexOf(bahan);
      if (index === -1) return;
      pantryItems.splice(index, 1);
      wajanItems.push(bahan);
      renderPantry();
      renderWajan();
      updateUI();
      statusMsg.textContent = `➕ ${bahan} masuk wajan!`;
    }

    // ---- MASAK! (cek urutan bahan) ----
    function masak() {
      if (!gameActive) {
        statusMsg.textContent = '⏰ Game selesai! Reset dulu yuk.';
        return;
      }
      if (wajanItems.length === 0) {
        statusMsg.textContent = '⚠️ Wajan kosong! Masukkan bahan.';
        return;
      }
      if (!currentResep) {
        statusMsg.textContent = '❌ Tidak ada resep target!';
        return;
      }

      // cek apakah bahan di wajan SAMA PERSIS dengan resep (urutan harus sama)
      const resepBahan = currentResep.bahan;
      const isMatch = (wajanItems.length === resepBahan.length) &&
                      wajanItems.every((val, idx) => val === resepBahan[idx]);

      if (isMatch) {
        // BERHASIL!
        const bonusTimer = Math.floor(timer / 5) * 2;
        const totalScore = 10 + (combo * 2) + bonusTimer;
        score += totalScore;
        combo += 1;
        statusMsg.textContent = `🎉 ${currentResep.emoji} ${currentResep.nama} berhasil! +${totalScore} poin!`;
        // kosongkan wajan
        wajanItems = [];
        // tambah bahan baru ke pantry (1-2)
        const available = semuaBahan.filter(b => !pantryItems.includes(b));
        if (available.length > 0) {
          const bonus = shuffleArray(available).slice(0, Math.min(2, available.length));
          pantryItems.push(...bonus);
        }
        if (pantryItems.length > 14) pantryItems = pantryItems.slice(0, 14);
        // pilih resep baru
        pilihResep();
        // reset timer (tambah 10 detik)
        timer = Math.min(timer + 10, 60);
        renderPantry();
        renderWajan();
        updateUI();
      } else {
        // GAGAL (urutan salah)
        combo = 0;
        score = Math.max(0, score - 5);
        statusMsg.textContent = '😵 Urutan bahan salah! Combo reset, -5 poin.';
        // wajan tetap isinya (bisa dibuang atau diubah)
        updateUI();
      }
    }

    // ---- BUANG WAJAN ----
    function clearWajan() {
      if (!gameActive) return;
      if (wajanItems.length === 0) {
        statusMsg.textContent = '🧹 Wajan sudah kosong!';
        return;
      }
      wajanItems = [];
      combo = 0;
      renderWajan();
      updateUI();
      statusMsg.textContent = '🗑️ Bahan dibuang, combo reset.';
    }

    // ---- TAMBAH BAHAN ACAK ----
    function addRandomBahan() {
      if (!gameActive) return;
      const available = semuaBahan.filter(b => !pantryItems.includes(b));
      if (available.length === 0) {
        statusMsg.textContent = '📦 Semua bahan sudah ada!';
        return;
      }
      const count = Math.min(3, available.length);
      const randomBahan = shuffleArray(available).slice(0, count);
      pantryItems.push(...randomBahan);
      if (pantryItems.length > 14) pantryItems = pantryItems.slice(0, 14);
      renderPantry();
      updateUI();
      statusMsg.textContent = `🎲 +${count} bahan baru!`;
    }

    // ---- TIMER ----
    function startTimer() {
      if (timerInterval) clearInterval(timerInterval);
      timerInterval = setInterval(() => {
        if (!gameActive) return;
        timer -= 1;
        timerDisplay.textContent = timer;
        timerBonusDisplay.textContent = `⏳ +${Math.floor(timer / 5) * 2}`;
        if (timer <= 0) {
          timer = 0;
          gameActive = false;
          clearInterval(timerInterval);
          timerInterval = null;
          statusMsg.textContent = '⏰ WAKTU HABIS! Reset untuk bermain lagi.';
          cookBtn.disabled = true;
          clearWajanBtn.disabled = true;
          randomBahanBtn.disabled = true;
          updateUI();
        }
      }, 1000);
    }

    // ---- RESET GAME ----
    function resetGame() {
      if (timerInterval) {
        clearInterval(timerInterval);
        timerInterval = null;
      }
      initPantry();
      wajanItems = [];
      score = 0;
      combo = 0;
      timer = 30;
      gameActive = true;
      cookBtn.disabled = false;
      clearWajanBtn.disabled = false;
      randomBahanBtn.disabled = false;
      pilihResep();
      renderPantry();
      renderWajan();
      updateUI();
      statusMsg.textContent = '🔄 Game di-reset! Masak lagi!';
      startTimer();
    }

    // ---- EVENT LISTENERS ----
    cookBtn.addEventListener('click', masak);
    clearWajanBtn.addEventListener('click', clearWajan);
    randomBahanBtn.addEventListener('click', addRandomBahan);
    resetGameBtn.addEventListener('click', resetGame);

    // ---- INIT ----
    initPantry();
    pilihResep();
    renderPantry();
    renderWajan();
    updateUI();
    statusMsg.textContent = '🍳 Klik bahan untuk memasukkannya ke wajan!';
    startTimer();
  })();
</script>
</body>
</html>
