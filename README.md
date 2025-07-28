
<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8" />
  <title>Jogos Concluídos pelos Jogadores</title>
  <style>
    body {
      background-color: #000;
      color: #ff5555;
      font-family: Arial, sans-serif;
      padding: 20px;
      max-width: 700px;
      margin: auto;
    }
    h1, h2 {
      text-align: center;
    }
    form {
      margin-bottom: 20px;
      background: #220000;
      padding: 15px;
      border-radius: 8px;
    }
    label {
      display: block;
      margin-bottom: 5px;
    }
    input[type="text"] {
      width: 100%;
      padding: 8px;
      margin-bottom: 10px;
      border: none;
      border-radius: 4px;
      font-size: 1em;
      box-sizing: border-box;
    }
    button {
      background-color: #ff4444;
      color: white;
      border: none;
      padding: 10px 20px;
      font-size: 1em;
      border-radius: 6px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    button:hover,
    button:focus {
      background-color: #ff2222;
      outline: none;
    }
    ul {
      list-style-type: none;
      padding-left: 0;
    }
    li {
      background-color: #330000;
      margin-bottom: 10px;
      padding: 10px;
      border-radius: 6px;
      font-size: 1.1em;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    li button.remove-btn {
      background-color: #aa2222;
      border: none;
      color: white;
      padding: 5px 10px;
      border-radius: 5px;
      cursor: pointer;
      font-size: 0.9em;
      transition: background-color 0.3s ease;
    }
    li button.remove-btn:hover,
    li button.remove-btn:focus {
      background-color: #cc3333;
      outline: none;
    }
    #emptyMessageMegadeath,
    #emptyMessageNaruto {
      text-align: center;
      font-style: italic;
      color: #aa4444;
      margin-top: 10px;
    }
    p.description {
      text-align: center;
      font-style: italic;
      color: #ff7777;
      margin-bottom: 20px;
    }
  </style>
</head>
<body>

  <h1>Jogos Concluídos pelos Jogadores</h1>
  <p class="description">
    Todos os jogos listados foram completamente concluídos pelos respectivos jogadores ✅
  </p>

  <form id="gameForm" aria-label="Formulário para adicionar jogos concluídos">
    <label for="playerName">Nome do Jogador:</label>
    <input type="text" id="playerName" placeholder="Ex: João" required autocomplete="off" />

    <label for="gameName">Nome do Jogo Concluído:</label>
    <input type="text" id="gameName" placeholder="Ex: The Legend of Zelda" required autocomplete="off" />

    <button type="submit">Adicionar</button>
  </form>

  <h2>Jogos concluídos por Megadeath</h2>
  <ul id="megadeathList" aria-live="polite" aria-relevant="additions removals"></ul>
  <p id="emptyMessageMegadeath">Nenhum jogo concluído por Megadeath.</p>

  <h2>Jogos concluídos por naruto123</h2>
  <ul id="narutoList" aria-live="polite" aria-relevant="additions removals"></ul>
  <p id="emptyMessageNaruto">Nenhum jogo concluído por naruto123.</p>

<script>
  const form = document.getElementById('gameForm');
  const megadeathList = document.getElementById('megadeathList');
  const narutoList = document.getElementById('narutoList');
  const emptyMessageMegadeath = document.getElementById('emptyMessageMegadeath');
  const emptyMessageNaruto = document.getElementById('emptyMessageNaruto');

  let completedGames = JSON.parse(localStorage.getItem('completedGames')) || [
    // Megadeath - PS2
    { player: 'Megadeath', game: 'God of War (PS2)' },
    { player: 'Megadeath', game: 'Shadow of the Colossus (PS2)' },
    { player: 'Megadeath', game: 'Final Fantasy X (PS2)' },
    { player: 'Megadeath', game: 'Grand Theft Auto: San Andreas (PS2)' },
    { player: 'Megadeath', game: 'Metal Gear Solid 3: Snake Eater (PS2)' },
    { player: 'Megadeath', game: 'Devil May Cry 3 (PS2)' },
    { player: 'Megadeath', game: 'Kingdom Hearts (PS2)' },
    { player: 'Megadeath', game: 'Okami (PS2)' },
    { player: 'Megadeath', game: 'Resident Evil 4 (PS2)' },
    { player: 'Megadeath', game: 'Persona 4 (PS2)' },
    // Megadeath - PS3
    { player: 'Megadeath', game: 'The Last of Us (PS3)' },
    { player: 'Megadeath', game: 'Uncharted 2: Among Thieves (PS3)' },
    { player: 'Megadeath', game: 'Red Dead Redemption (PS3)' },
    { player: 'Megadeath', game: 'Demon’s Souls (PS3)' },
    { player: 'Megadeath', game: 'Bioshock Infinite (PS3)' },
    { player: 'Megadeath', game: 'God of War III (PS3)' },
    { player: 'Megadeath', game: 'Heavy Rain (PS3)' },
    { player: 'Megadeath', game: 'Batman: Arkham City (PS3)' },
    { player: 'Megadeath', game: 'Journey (PS3)' },
    { player: 'Megadeath', game: 'Ni no Kuni: Wrath of the White Witch (PS3)' },
    // naruto123 - PS4
    { player: 'naruto123', game: 'God of War (PS4)' },const img = document.createElement('img');
img.src = 'https://upload.wikimedia.org/wikipedia/en/a/a7/God_of_War_4_cover.jpg';
img.alt = game.game;
img.width = 80;
img.style.borderRadius = '6px';
img.style.marginRight = '10px';

const gameText = document.createElement('span');
gameText.textContent = game.game;

li.appendChild(img);
li.appendChild(gameText);


    { player: 'naruto123', game: 'Spider-Man (PS4)' },
    { player: 'naruto123', game: 'Horizon Zero Dawn (PS4)' },
    { player: 'naruto123', game: 'Bloodborne (PS4)' },
    { player: 'naruto123', game: 'Uncharted 4: A Thief’s End (PS4)' },
    { player: 'naruto123', game: 'Persona 5 (PS4)' },
    { player: 'naruto123', game: 'The Last Guardian (PS4)' },
    { player: 'naruto123', game: 'Detroit: Become Human (PS4)' },
    { player: 'naruto123', game: 'Sekiro: Shadows Die Twice (PS4)' },
    { player: 'naruto123', game: 'Nier: Automata (PS4)' }
  ];

  function saveToStorage() {
    localStorage.setItem('completedGames', JSON.stringify(completedGames));
  }

  function updateList() {
    megadeathList.innerHTML = '';
    narutoList.innerHTML = '';

    const gamesMegadeath = completedGames.filter(entry => entry.player.toLowerCase() === 'megadeath');
    if (gamesMegadeath.length === 0) {
      emptyMessageMegadeath.style.display = 'block';
    } else {
      emptyMessageMegadeath.style.display = 'none';
      games

const form = document.getElementById('gameForm');
const megadeathList = document.getElementById('megadeathList');
const narutoList = document.getElementById('narutoList');
const emptyMessageMegadeath = document.getElementById('emptyMessageMegadeath');
const emptyMessageNaruto = document.getElementById('emptyMessageNaruto');

let completedGames = JSON.parse(localStorage.getItem('completedGames')) || [
  // seus dados iniciais aqui...
];

// Salva no localStorage
function saveToStorage() {
  localStorage.setItem('completedGames', JSON.stringify(completedGames));
}

// Atualiza as listas na tela
function updateList() {
  megadeathList.innerHTML = '';
  narutoList.innerHTML = '';

  const gamesMegadeath = completedGames.filter(entry => entry.player.toLowerCase() === 'megadeath');
  if (gamesMegadeath.length === 0) {
    emptyMessageMegadeath.style.display = 'block';
  } else {
    emptyMessageMegadeath.style.display = 'none';
    gamesMegadeath.forEach(game => {
      const li = document.createElement('li');
      li.textContent = game.game;
      megadeathList.appendChild(li);
    });
  }

  const gamesNaruto = completedGames.filter(entry => entry.player.toLowerCase() === 'naruto123');
  if (gamesNaruto.length === 0) {
    emptyMessageNaruto.style.display = 'block';
  } else {
    emptyMessageNaruto.style.display = 'none';
    gamesNaruto.forEach(game => {
      const li = document.createElement('li');
      li.textContent = game.game;
      narutoList.appendChild(li);
    });
  }
}

// Função para mostrar erro se jogador não tem jogos
function checkPlayerGames(playerName) {
  const playerGames = completedGames.filter(entry => entry.player.toLowerCase() === playerName.toLowerCase());
  if (playerGames.length === 0) {
    alert(`Erro: O jogador "${playerName}" não tem jogos cadastrados.`);
    return false;
  }
  return true;
}

form.addEventListener('submit', function (e) {
  e.preventDefault();

  const player = document.getElementById('playerName').value.trim();
  const game = document.getElementById('gameName').value.trim();

  if (!player || !game) return;

  // Antes de adicionar, verificar se jogador existe na lista
  // Se não existir, adiciona normalmente (porque pode ser jogador novo)
  // Se quiser obrigar só a adicionar para jogadores existentes, descomente este if:
  /*
  if (!checkPlayerGames(player)) {
    return; // para não adicionar jogo para jogador sem jogos
  }
  */

  // Adiciona o novo jogo
  completedGames.push({ player, game });
  saveToStorage();
  updateList();

  form.reset();
});

// Inicializa
updateList();

<script>
  const form = document.getElementById('gameForm');
  const megadeathList = document.getElementById('megadeathList');
  const narutoList = document.getElementById('narutoList');
  const emptyMessageMegadeath = document.getElementById('emptyMessageMegadeath');
  const emptyMessageNaruto = document.getElementById('emptyMessageNaruto');

  const gameImages = {
    'Final Fantasy VII (PS1)': 'https://upload.wikimedia.org/wikipedia/en/2/20/Final_Fantasy_VII_Box_Art.jpg',
    'Metal Gear Solid (PS1)': 'https://upload.wikimedia.org/wikipedia/en/4/4b/Metal_Gear_Solid_cover_art.png',
    'God of War (PS2)': 'https://upload.wikimedia.org/wikipedia/en/a/ac/God_of_War_1_cover.jpg',
    'God of War (PS4)': 'https://upload.wikimedia.org/wikipedia/en/a/a7/God_of_War_4_cover.jpg',
    'Spider-Man (PS4)': 'https://upload.wikimedia.org/wikipedia/en/0/00/Spider-Man_PS4_cover.jpg',
    'Bloodborne (PS4)': 'https://upload.wikimedia.org/wikipedia/en/6/68/Bloodborne_Cover_Wallpaper.jpg'
  };

  const gameTrailers = {
    'Final Fantasy VII (PS1)': 'https://www.youtube.com/watch?v=2IwKCBtVvPA',
    'Metal Gear Solid (PS1)': 'https://www.youtube.com/watch?v=DU6TgoGkNyM',
    'God of War (PS2)': 'https://www.youtube.com/watch?v=3nSRtd5_d6o',
    'God of War (PS4)': 'https://www.youtube.com/watch?v=K0u_kAWLJOA',
    'Spider-Man (PS4)': 'https://www.youtube.com/watch?v=3R2uvJqWeVg',
    'Bloodborne (PS4)': 'https://www.youtube.com/watch?v=G203e1HhixY'
  };

  let completedGames = JSON.parse(localStorage.getItem('completedGames')) || [];

  function saveToStorage() {
    localStorage.setItem('completedGames', JSON.stringify(completedGames));
  }

  function createGameItem(game) {
    const li = document.createElement('li');
    li.style.display = 'flex';
    li.style.alignItems = 'center';
    li.style.flexDirection = 'column';
    li.style.textAlign = 'center';

    const img = document.createElement('img');
    img.src = gameImages[game.game] || 'https://via.placeholder.com/100x100?text=?';
    img.alt = game.game;
    img.style.width = '100px';
    img.style.height = '100px';
    img.style.borderRadius = '6px';
    img.style.marginBottom = '10px';

    const name = document.createElement('strong');
    name.textContent = game.game;

    li.appendChild(img);
    li.appendChild(name);

    const trailerUrl = gameTrailers[game.game];
    if (trailerUrl) {
      const link = document.createElement('a');
      link.href = trailerUrl;
      link.textContent = '▶ Ver Trailer';
      link.target = '_blank';
      link.style.marginTop = '5px';
      link.style.display = 'inline-block';
      link.style.background = '#ff2222';
      link.style.color = '#fff';
      link.style.padding = '5px 10px';
      link.style.borderRadius = '5px';
      link.style.textDecoration = 'none';
      link.style.fontSize = '0.9em';

      li.appendChild(link);
    }

    return li;
  }

  function updateList() {
    megadeathList.innerHTML = '';
    narutoList.innerHTML = '';

    const gamesMegadeath = completedGames.filter(entry => entry.player.toLowerCase() === 'megadeath');
    if (gamesMegadeath.length === 0) {
      emptyMessageMegadeath.style.display = 'block';
    } else {
      emptyMessageMegadeath.style.display = 'none';
      gamesMegadeath.forEach(game => {
        megadeathList.appendChild(createGameItem(game));
      });
    }

    const gamesNaruto = completedGames.filter(entry => entry.player.toLowerCase() === 'naruto123');
    if (gamesNaruto.length === 0) {
      emptyMessageNaruto.style.display = 'block';
    } else {
      emptyMessageNaruto.style.display = 'none';
      gamesNaruto.forEach(game => {
        narutoList.appendChild(createGameItem(game));
      });
    }
  }

  form.addEventListener('submit', function (e) {
    e.preventDefault();

    const player = document.getElementById('playerName').value.trim();
    const game = document.getElementById('gameName').value.trim();

    if (!player || !game) return;

    completedGames.push({ player, game });
    saveToStorage();
    updateList();
    form.reset();
  });

  updateList();

 const gameImages = {
  'God of War (PS4)': 'https://upload.wikimedia.org/wikipedia/en/a/a7/God_of_War_4_cover.jpg',
  'God of War (PS2)': 'https://upload.wikimedia.org/wikipedia/en/a/ac/God_of_War_1_cover.jpg'
</script>





