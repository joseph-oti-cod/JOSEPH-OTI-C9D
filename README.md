<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CS Genius GitHub README Architect & Puzzle Playground</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        cyber: {
                            50: '#e6f9ff',
                            100: '#b3f2ff',
                            400: '#33f0ff',
                            500: '#00f2fe',
                            600: '#00c3cf',
                            900: '#050b14',
                            800: '#0b1629',
                            700: '#12233f'
                        }
                    },
                    fontFamily: {
                        mono: ['Fira Code', 'Courier New', 'monospace'],
                        sans: ['Inter', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* Custom scrollbar for dark modern feel */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0b1629;
        }
        ::-webkit-scrollbar-thumb {
            background: #1e3a8a;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #00f2fe;
        }
        .glow-cyan {
            box-shadow: 0 0 15px rgba(0, 242, 254, 0.25);
        }
        .glow-cyan-lg {
            box-shadow: 0 0 30px rgba(0, 242, 254, 0.4);
        }
        .tab-active {
            border-bottom: 2px solid #00f2fe;
            color: #00f2fe;
        }
        .matrix-bg {
            background: radial-gradient(circle at center, #0b1629 0%, #050b14 100%);
        }
    </style>
</head>
<body class="bg-cyber-900 text-slate-200 font-sans min-h-screen flex flex-col selection:bg-cyber-500 selection:text-black">

    <!-- Top Navigation Header -->
    <header class="border-b border-slate-800 bg-cyber-800/80 backdrop-blur-md sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            <div class="flex items-center space-x-3">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-tr from-cyan-500 to-blue-600 flex items-center justify-center text-black font-bold text-xl shadow-lg shadow-cyan-500/30">
                    <i class="fa-solid fa-terminal"></i>
                </div>
                <div>
                    <h1 class="font-bold text-lg text-white tracking-wide flex items-center gap-2">
                        CS README Architect <span class="text-xs bg-cyan-950 text-cyan-400 border border-cyan-800 px-2 py-0.5 rounded-full font-mono">v2.5 Hacker Edition</span>
                    </h1>
                    <p class="text-xs text-slate-400">Build high-impact GitHub profiles with puzzles & interactive widgets</p>
                </div>
            </div>

            <div class="flex items-center space-x-3">
                <button id="btn-copy-main" onclick="copyMarkdownCode()" class="flex items-center space-x-2 bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-400 hover:to-blue-500 text-slate-950 font-bold px-4 py-2 rounded-lg transition-all duration-200 transform hover:scale-105 shadow-md shadow-cyan-500/20 active:scale-95">
                    <i class="fa-regular fa-copy"></i>
                    <span>Copy README Code</span>
                </button>
            </div>
        </div>
    </header>

    <!-- Main Grid Content -->
    <main class="flex-1 max-w-7xl w-full mx-auto p-4 sm:p-6 grid grid-cols-1 lg:grid-cols-12 gap-6">

        <!-- Left Controls / Form Panel (5 cols) -->
        <section class="lg:col-span-5 flex flex-col gap-6">
            
            <!-- Builder Tabs -->
            <div class="bg-cyber-800 border border-slate-800 rounded-xl p-2 flex space-x-1 shadow-xl">
                <button onclick="switchTab('profile')" id="tab-btn-profile" class="flex-1 py-2 px-3 text-sm font-medium rounded-lg transition-all duration-200 text-cyan-400 bg-slate-800/80 border border-slate-700/50 flex items-center justify-center gap-2">
                    <i class="fa-solid fa-user-gear"></i> Profile & Stack
                </button>
                <button onclick="switchTab('puzzles')" id="tab-btn-puzzles" class="flex-1 py-2 px-3 text-sm font-medium rounded-lg transition-all duration-200 text-slate-400 hover:text-white flex items-center justify-center gap-2">
                    <i class="fa-solid fa-chess"></i> Puzzles & Cipher
                </button>
                <button onclick="switchTab('stats')" id="tab-btn-stats" class="flex-1 py-2 px-3 text-sm font-medium rounded-lg transition-all duration-200 text-slate-400 hover:text-white flex items-center justify-center gap-2">
                    <i class="fa-solid fa-chart-pie"></i> Stats & Theme
                </button>
            </div>

            <!-- TAB 1: Profile & Tech Stack Settings -->
            <div id="tab-content-profile" class="bg-cyber-800 border border-slate-800 rounded-xl p-5 shadow-xl flex flex-col gap-4">
                <h2 class="text-md font-semibold text-white border-b border-slate-700/60 pb-2 flex items-center gap-2">
                    <i class="fa-solid fa-id-card text-cyan-400"></i> Developer Profile Data
                </h2>

                <div>
                    <label class="block text-xs font-mono text-slate-300 mb-1">GitHub Username</label>
                    <input type="text" id="in-username" value="otieno-joseph" oninput="updatePreview()" class="w-full bg-slate-900 border border-slate-700 rounded-lg px-3 py-2 text-sm text-cyan-300 focus:outline-none focus:border-cyan-500 font-mono">
                </div>

                <div>
                    <label class="block text-xs font-mono text-slate-300 mb-1">Display Name</label>
                    <input type="text" id="in-name" value="otieno Joseph smith" oninput="updatePreview()" class="w-full bg-slate-900 border border-slate-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-cyan-500">
                </div>

                <div>
                    <label class="block text-xs font-mono text-slate-300 mb-1">Tagline / Tag Subtitle</label>
                    <input type="text" id="in-tagline" value="Still waiting for tech to catch up to my ideas 🚀" oninput="updatePreview()" class="w-full bg-slate-900 border border-slate-700 rounded-lg px-3 py-2 text-sm text-slate-200 focus:outline-none focus:border-cyan-500">
                </div>

                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-mono text-slate-300 mb-1">Instagram Handle</label>
                        <input type="text" id="in-instagram" value="otieno_js" oninput="updatePreview()" class="w-full bg-slate-900 border border-slate-700 rounded-lg px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-cyan-500">
                    </div>
                    <div>
                        <label class="block text-xs font-mono text-slate-300 mb-1">Email Address</label>
                        <input type="text" id="in-email" value="joseph.smith@csgenius.dev" oninput="updatePreview()" class="w-full bg-slate-900 border border-slate-700 rounded-lg px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-cyan-500">
                    </div>
                </div>

                <div>
                    <label class="block text-xs font-mono text-slate-300 mb-1">About Me Bio</label>
                    <textarea id="in-bio" rows="3" oninput="updatePreview()" class="w-full bg-slate-900 border border-slate-700 rounded-lg px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-cyan-500">Technology enthusiast, computer science student, currently debugging life with no stack trace available. Powered by curiosity, caffeine, a pretty bad sleeping schedule, and way too many browser tabs.</textarea>
                </div>

                <div>
                    <label class="block text-xs font-mono text-slate-300 mb-2">Selected Operating Systems & Badges</label>
                    <div class="grid grid-cols-3 gap-2">
                        <label class="flex items-center space-x-2 text-xs bg-slate-900 border border-slate-700 p-2 rounded cursor-pointer hover:border-cyan-500">
                            <input type="checkbox" id="chk-os-kali" checked onchange="updatePreview()" class="rounded text-cyan-500 focus:ring-0">
                            <span>Kali Linux</span>
                        </label>
                        <label class="flex items-center space-x-2 text-xs bg-slate-900 border border-slate-700 p-2 rounded cursor-pointer hover:border-cyan-500">
                            <input type="checkbox" id="chk-os-linux" checked onchange="updatePreview()" class="rounded text-cyan-500 focus:ring-0">
                            <span>GNU Linux</span>
                        </label>
                        <label class="flex items-center space-x-2 text-xs bg-slate-900 border border-slate-700 p-2 rounded cursor-pointer hover:border-cyan-500">
                            <input type="checkbox" id="chk-os-ubuntu" checked onchange="updatePreview()" class="rounded text-cyan-500 focus:ring-0">
                            <span>Ubuntu</span>
                        </label>
                    </div>
                </div>

                <div>
                    <label class="block text-xs font-mono text-slate-300 mb-2">Core Languages</label>
                    <div class="grid grid-cols-3 gap-2">
                        <label class="flex items-center space-x-2 text-xs bg-slate-900 border border-slate-700 p-2 rounded cursor-pointer hover:border-cyan-500">
                            <input type="checkbox" id="chk-lang-c" checked onchange="updatePreview()" class="rounded text-cyan-500 focus:ring-0">
                            <span>C</span>
                        </label>
                        <label class="flex items-center space-x-2 text-xs bg-slate-900 border border-slate-700 p-2 rounded cursor-pointer hover:border-cyan-500">
                            <input type="checkbox" id="chk-lang-cpp" checked onchange="updatePreview()" class="rounded text-cyan-500 focus:ring-0">
                            <span>C++</span>
                        </label>
                        <label class="flex items-center space-x-2 text-xs bg-slate-900 border border-slate-700 p-2 rounded cursor-pointer hover:border-cyan-500">
                            <input type="checkbox" id="chk-lang-py" checked onchange="updatePreview()" class="rounded text-cyan-500 focus:ring-0">
                            <span>Python</span>
                        </label>
                        <label class="flex items-center space-x-2 text-xs bg-slate-900 border border-slate-700 p-2 rounded cursor-pointer hover:border-cyan-500">
                            <input type="checkbox" id="chk-lang-bash" checked onchange="updatePreview()" class="rounded text-cyan-500 focus:ring-0">
                            <span>Bash / Shell</span>
                        </label>
                        <label class="flex items-center space-x-2 text-xs bg-slate-900 border border-slate-700 p-2 rounded cursor-pointer hover:border-cyan-500">
                            <input type="checkbox" id="chk-lang-asm" checked onchange="updatePreview()" class="rounded text-cyan-500 focus:ring-0">
                            <span>Assembly</span>
                        </label>
                    </div>
                </div>
            </div>

            <!-- TAB 2: Puzzles & Cryptography -->
            <div id="tab-content-puzzles" class="hidden bg-cyber-800 border border-slate-800 rounded-xl p-5 shadow-xl flex-col gap-4">
                <h2 class="text-md font-semibold text-white border-b border-slate-700/60 pb-2 flex items-center gap-2">
                    <i class="fa-solid fa-puzzle-piece text-cyan-400"></i> Interactive Genius Modules
                </h2>

                <!-- Imitation Game Chess Config -->
                <div class="bg-slate-900/90 border border-slate-700/60 rounded-lg p-3">
                    <div class="flex items-center justify-between mb-2">
                        <span class="text-xs font-bold text-white flex items-center gap-2">
                            <i class="fa-solid fa-chess-knight text-amber-400"></i> The Imitation Game Chess Puzzle
                        </span>
                        <input type="checkbox" id="chk-sec-chess" checked onchange="updatePreview()" class="rounded text-cyan-500">
                    </div>
                    <p class="text-[11px] text-slate-400 mb-2">Alan Turing inspired cryptographic puzzle board inserted into README.</p>
                    <label class="block text-[10px] font-mono text-slate-400 mb-1">Quote</label>
                    <input type="text" id="in-turing-quote" value="Sometimes it is the people no one imagines anything of who do the things that no one can imagine." oninput="updatePreview()" class="w-full bg-slate-950 border border-slate-700 rounded px-2 py-1 text-xs text-amber-300">
                </div>

                <!-- Sudoku Config -->
                <div class="bg-slate-900/90 border border-slate-700/60 rounded-lg p-3">
                    <div class="flex items-center justify-between mb-2">
                        <span class="text-xs font-bold text-white flex items-center gap-2">
                            <i class="fa-solid fa-border-all text-cyan-400"></i> Hacker's Sudoku Matrix
                        </span>
                        <input type="checkbox" id="chk-sec-sudoku" checked onchange="updatePreview()" class="rounded text-cyan-500">
                    </div>
                    <p class="text-[11px] text-slate-400 mb-2">Algorithmic Sudoku challenge matrix for visitors to solve.</p>
                    <button onclick="generateRandomSudoku()" class="w-full bg-slate-800 hover:bg-slate-700 border border-slate-600 text-cyan-300 text-xs py-1 rounded flex items-center justify-center gap-2 transition">
                        <i class="fa-solid fa-shuffle"></i> Regenerate Sudoku Seed
                    </button>
                </div>

                <!-- Hex Cipher Config -->
                <div class="bg-slate-900/90 border border-slate-700/60 rounded-lg p-3">
                    <div class="flex items-center justify-between mb-2">
                        <span class="text-xs font-bold text-white flex items-center gap-2">
                            <i class="fa-solid fa-key text-emerald-400"></i> Custom Hex String Payload
                        </span>
                        <input type="checkbox" id="chk-sec-cipher" checked onchange="updatePreview()" class="rounded text-cyan-500">
                    </div>
                    <input type="text" id="in-hex-text" value="Hack The Planet!" oninput="updateHexPayload()" class="w-full bg-slate-950 border border-slate-700 rounded px-2 py-1 text-xs text-emerald-400 font-mono">
                    <p class="text-[10px] font-mono text-slate-400 mt-1" id="lbl-hex-preview">Payload: 0x48 0x61 0x63 0x6b...</p>
                </div>
            </div>

            <!-- TAB 3: Stats & Visual Themes -->
            <div id="tab-content-stats" class="hidden bg-cyber-800 border border-slate-800 rounded-xl p-5 shadow-xl flex-col gap-4">
                <h2 class="text-md font-semibold text-white border-b border-slate-700/60 pb-2 flex items-center gap-2">
                    <i class="fa-solid fa-palette text-cyan-400"></i> Theme & Graph Options
                </h2>

                <div>
                    <label class="block text-xs font-mono text-slate-300 mb-1">Stats Theme Palette</label>
                    <select id="sel-stats-theme" onchange="updatePreview()" class="w-full bg-slate-900 border border-slate-700 rounded-lg px-3 py-2 text-xs text-cyan-300 focus:outline-none">
                        <option value="tokyonight" selected>Tokyo Night (Dark Blue/Cyan)</option>
                        <option value="cyberpunk">Cyberpunk (High Contrast Neon)</option>
                        <option value="dracula">Dracula (Vampire Dark)</option>
                        <option value="radical">Radical (Vibrant Red/Cyan)</option>
                        <option value="matrix">Matrix (Hacker Green)</option>
                    </select>
                </div>

                <div class="flex flex-col gap-2">
                    <label class="flex items-center justify-between bg-slate-900 p-2.5 rounded-lg border border-slate-700 cursor-pointer">
                        <span class="text-xs text-slate-200">Include Contribution Snake</span>
                        <input type="checkbox" id="chk-widget-snake" checked onchange="updatePreview()" class="rounded text-cyan-500">
                    </label>

                    <label class="flex items-center justify-between bg-slate-900 p-2.5 rounded-lg border border-slate-700 cursor-pointer">
                        <span class="text-xs text-slate-200">Include Activity Graph</span>
                        <input type="checkbox" id="chk-widget-graph" checked onchange="updatePreview()" class="rounded text-cyan-500">
                    </label>

                    <label class="flex items-center justify-between bg-slate-900 p-2.5 rounded-lg border border-slate-700 cursor-pointer">
                        <span class="text-xs text-slate-200">Include Arcade / Mini Game Link</span>
                        <input type="checkbox" id="chk-widget-arcade" checked onchange="updatePreview()" class="rounded text-cyan-500">
                    </label>
                </div>
            </div>

            <!-- Simulator Interactive Play Zone -->
            <div class="bg-slate-950 border border-cyan-900/50 rounded-xl p-4 shadow-xl">
                <h3 class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-2 flex items-center gap-2">
                    <i class="fa-solid fa-vial-virus"></i> Interactive Puzzle Sandbox
                </h3>
                <p class="text-[11px] text-slate-400 mb-3">Test solving your custom profile puzzles right in this playground:</p>
                
                <div class="flex space-x-2 border-b border-slate-800 pb-2 mb-3">
                    <button onclick="switchSandbox('sudoku')" id="sb-tab-sudoku" class="text-xs font-mono text-cyan-400 font-bold border-b-2 border-cyan-400 pb-1">Sudoku</button>
                    <button onclick="switchSandbox('chess')" id="sb-tab-chess" class="text-xs font-mono text-slate-400 hover:text-white pb-1">Chess Tactical</button>
                </div>

                <!-- Sandbox Sudoku -->
                <div id="sb-view-sudoku" class="flex flex-col items-center">
                    <div id="sudoku-grid-container" class="grid grid-cols-9 gap-[2px] bg-cyan-950 p-1.5 rounded border border-cyan-800 max-w-[240px]">
                        <!-- Sudoku cells rendered via JS -->
                    </div>
                    <div class="mt-2 flex gap-2">
                        <button onclick="solveSudokuStep()" class="text-[10px] bg-cyan-950 border border-cyan-700 text-cyan-300 px-2 py-1 rounded hover:bg-cyan-900">
                            <i class="fa-solid fa-wand-magic-sparkles"></i> Auto Solve Step
                        </button>
                        <button onclick="resetSudokuGrid()" class="text-[10px] bg-slate-900 border border-slate-700 text-slate-300 px-2 py-1 rounded hover:bg-slate-800">
                            Reset Grid
                        </button>
                    </div>
                </div>

                <!-- Sandbox Chess -->
                <div id="sb-view-chess" class="hidden flex-col items-center">
                    <div class="font-mono text-xs text-amber-300 bg-slate-900 border border-slate-800 p-3 rounded w-full text-center">
                        <div class="font-bold text-white mb-1">Turing's Cryptic Board (Tactical Mate)</div>
                        <pre id="chess-board-sim" class="text-[11px] leading-tight text-slate-300 mt-2">
8 [r][ ][b][q][k][b][ ][r]
7 [p][p][p][ ][ ][p][p][p]
6 [ ][ ][n][ ][p][n][ ][ ]
5 [ ][ ][ ][p][P][ ][ ][ ]
4 [ ][ ][P][P][ ][ ][ ][ ]
3 [ ][N][ ][ ][ ][N][ ][ ]
2 [P][P][ ][ ]|[P][P][P][P]
1 [R][N][B][Q][K][B][ ][R]
  A  B  C  D  E  F  G  H</pre>
                    </div>
                    <div class="mt-2 text-center">
                        <span id="chess-status" class="text-[11px] text-emerald-400 font-mono">Move: White Knight to D5 (Nxd5)</span>
                    </div>
                </div>
            </div>

        </section>

        <!-- Right Preview & Code Panel (7 cols) -->
        <section class="lg:col-span-7 flex flex-col gap-4">
            
            <!-- View Mode Switcher -->
            <div class="bg-cyber-800 border border-slate-800 rounded-xl p-2 flex items-center justify-between">
                <div class="flex space-x-1">
                    <button onclick="setViewMode('preview')" id="view-btn-preview" class="px-4 py-1.5 text-xs font-semibold rounded-lg bg-cyan-500 text-slate-950 shadow-md">
                        <i class="fa-solid fa-eye"></i> Visual Preview
                    </button>
                    <button onclick="setViewMode('code')" id="view-btn-code" class="px-4 py-1.5 text-xs font-semibold rounded-lg text-slate-400 hover:text-white">
                        <i class="fa-solid fa-code"></i> Markdown Code
                    </button>
                </div>
                <span class="text-xs font-mono text-slate-400 pr-2">Single File Output (.md)</span>
            </div>

            <!-- Container Visual Render Preview -->
            <div id="panel-preview" class="bg-slate-900 border border-slate-800 rounded-xl p-6 overflow-y-auto max-h-[750px] shadow-2xl space-y-6">
                <!-- Rendered Header -->
                <div class="text-center space-y-3">
                    <div class="flex justify-center space-x-2">
                        <span id="pv-badge-insta" class="bg-pink-600 text-white text-[10px] font-bold px-2 py-0.5 rounded shadow">INSTAGRAM</span>
                        <span id="pv-badge-email" class="bg-red-600 text-white text-[10px] font-bold px-2 py-0.5 rounded shadow">EMAIL</span>
                    </div>

                    <div class="w-full bg-gradient-to-r from-cyan-900 via-blue-900 to-indigo-950 p-6 rounded-xl border border-cyan-500/30 glow-cyan">
                        <h1 id="pv-name" class="text-2xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 to-blue-400 font-mono">
                            Hi, I'm otieno Joseph smith
                        </h1>
                    </div>

                    <p id="pv-tagline" class="text-sm italic text-amber-300 font-medium">
                        Still waiting for tech to catch up to my ideas 🚀
                    </p>
                </div>

                <hr class="border-slate-800">

                <!-- About Me Section -->
                <div>
                    <h3 class="text-base font-bold text-white mb-2 flex items-center gap-2">
                        🚀 About Me
                    </h3>
                    <p id="pv-bio" class="text-xs text-slate-300 leading-relaxed mb-3">
                        Technology enthusiast, computer science student...
                    </p>
                    <ul class="text-xs text-slate-300 space-y-1 font-mono">
                        <li>🔭 Always on the go with a new project</li>
                        <li>👯 Open to coding team-ups and tech brainstorming</li>
                        <li>⚡ Core Stack: C / C++, Kali Linux, and Low-Level Architecture</li>
                    </ul>
                </div>

                <hr class="border-slate-800">

                <!-- Operating Systems & Tools -->
                <div>
                    <h3 class="text-base font-bold text-white mb-3 flex items-center gap-2">
                        🛠️ Operating Systems & Core Stack
                    </h3>
                    <div class="flex flex-wrap gap-2" id="pv-badges-container">
                        <!-- Badges rendered live -->
                    </div>
                </div>

                <!-- Imitation Chess Section -->
                <div id="pv-sec-chess-box">
                    <hr class="border-slate-800 mb-6">
                    <h3 class="text-base font-bold text-white mb-2 flex items-center gap-2">
                        ♟️ The Imitation Game: Cryptographic Chess Puzzle
                    </h3>
                    <blockquote id="pv-turing-quote" class="border-l-2 border-amber-400 pl-3 italic text-xs text-amber-200/90 mb-3">
                        "Sometimes it is the people no one imagines anything of..."
                    </blockquote>
                    <pre id="pv-chess-grid" class="bg-slate-950 p-4 rounded-lg border border-slate-800 font-mono text-xs text-amber-300 overflow-x-auto leading-tight"></pre>
                </div>

                <!-- Sudoku Section -->
                <div id="pv-sec-sudoku-box">
                    <hr class="border-slate-800 mb-6">
                    <h3 class="text-base font-bold text-white mb-2 flex items-center gap-2">
                        🧩 Hacker's Sudoku Challenge
                    </h3>
                    <p class="text-xs text-slate-400 mb-2">Solve this grid using algorithmic deduction (no brute forcing):</p>
                    <pre id="pv-sudoku-grid" class="bg-slate-950 p-4 rounded-lg border border-slate-800 font-mono text-xs text-cyan-400 overflow-x-auto leading-tight"></pre>
                </div>

                <!-- Stats Placeholder Box -->
                <div>
                    <hr class="border-slate-800 mb-6">
                    <h3 class="text-base font-bold text-white mb-3 flex items-center gap-2">
                        📊 GitHub Analytics Card Preview
                    </h3>
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                        <div class="bg-slate-950 border border-slate-800 p-4 rounded-lg text-center font-mono">
                            <span class="text-xs text-slate-400">Stats Card Theme</span>
                            <div id="pv-stat-theme-name" class="text-sm font-bold text-cyan-400 mt-1">tokyonight</div>
                        </div>
                        <div class="bg-slate-950 border border-slate-800 p-4 rounded-lg text-center font-mono">
                            <span class="text-xs text-slate-400">Top Languages Widget</span>
                            <div class="text-sm font-bold text-emerald-400 mt-1">C 85.4% | C++ 14.6%</div>
                        </div>
                    </div>
                </div>

            </div>

            <!-- Raw Markdown Code View -->
            <div id="panel-code" class="hidden bg-slate-950 border border-slate-800 rounded-xl p-4 shadow-2xl relative">
                <div class="flex justify-between items-center mb-2 pb-2 border-b border-slate-800">
                    <span class="text-xs font-mono text-slate-400">Single Copy-Paste README Block</span>
                    <button onclick="copyMarkdownCode()" class="text-xs text-cyan-400 hover:text-cyan-300 flex items-center gap-1 font-mono">
                        <i class="fa-regular fa-copy"></i> Copy Code
                    </button>
                </div>
                <textarea id="markdown-output" readonly rows="24" class="w-full bg-transparent font-mono text-xs text-emerald-400 focus:outline-none resize-none leading-relaxed"></textarea>
            </div>

        </section>

    </main>

    <!-- Notification Toast -->
    <div id="toast" class="fixed bottom-5 right-5 bg-cyan-500 text-slate-950 font-bold text-xs px-4 py-3 rounded-lg shadow-2xl flex items-center gap-2 transform translate-y-20 opacity-0 transition-all duration-300 z-50">
        <i class="fa-solid fa-circle-check text-base"></i>
        <span id="toast-msg">README Code copied to clipboard!</span>
    </div>

    <!-- Application Script -->
    <script>
        // Default State
        const state = {
            username: "otieno-joseph",
            name: "otieno Joseph smith",
            tagline: "Still waiting for tech to catch up to my ideas 🚀",
            instagram: "otieno_js",
            email: "joseph.smith@csgenius.dev",
            bio: "Technology enthusiast, computer science student, currently debugging life with no stack trace available. Powered by curiosity, caffeine, a pretty bad sleeping schedule, and way too many browser tabs.",
            os: { kali: true, linux: true, ubuntu: true },
            languages: { c: true, cpp: true, py: true, bash: true, asm: true },
            turingQuote: "Sometimes it is the people no one imagines anything of who do the things that no one can imagine.",
            hexText: "Hack The Planet!",
            secChess: true,
            secSudoku: true,
            secCipher: true,
            theme: "tokyonight",
            widgetSnake: true,
            widgetGraph: true,
            widgetArcade: true,
            sudokuGrid: [
                [5, 3, 0, 0, 7, 0, 0, 0, 0],
                [6, 0, 0, 1, 9, 5, 0, 0, 0],
                [0, 9, 8, 0, 0, 0, 0, 6, 0],
                [8, 0, 0, 0, 6, 0, 0, 0, 3],
                [4, 0, 0, 8, 0, 3, 0, 0, 1],
                [7, 0, 0, 0, 2, 0, 0, 0, 6],
                [0, 6, 0, 0, 0, 0, 2, 8, 0],
                [0, 0, 0, 4, 1, 9, 0, 0, 5],
                [0, 0, 0, 0, 8, 0, 0, 7, 9]
            ]
        };

        const chessBoardAscii = 
`  8 [r][ ][b][q][k][b][ ][r]
  7 [p][p][p][ ][ ][p][p][p]
  6 [ ][ ][n][ ][p][n][ ][ ]
  5 [ ][ ][ ][p][P][ ][ ][ ]
  4 [ ][ ][P][P][ ][ ][ ][ ]
  3 [ ][N][ ][ ][ ][N][ ][ ]
  2 [P][P][ ][ ]|[P][P][P][P]
  1 [R][N][B][Q][K][B][ ][R]
    A  B  C  D  E  F  G  H`;

        // Switch Builder Tabs
        function switchTab(tab) {
            ['profile', 'puzzles', 'stats'].forEach(t => {
                const btn = document.getElementById(`tab-btn-${t}`);
                const content = document.getElementById(`tab-content-${t}`);
                if (t === tab) {
                    btn.className = "flex-1 py-2 px-3 text-sm font-medium rounded-lg transition-all duration-200 text-cyan-400 bg-slate-800/80 border border-slate-700/50 flex items-center justify-center gap-2";
                    content.classList.remove('hidden');
                    content.classList.add('flex');
                } else {
                    btn.className = "flex-1 py-2 px-3 text-sm font-medium rounded-lg transition-all duration-200 text-slate-400 hover:text-white flex items-center justify-center gap-2";
                    content.classList.add('hidden');
                    content.classList.remove('flex');
                }
            });
        }

        // Switch View Modes
        function setViewMode(mode) {
            const btnPrev = document.getElementById('view-btn-preview');
            const btnCode = document.getElementById('view-btn-code');
            const panPrev = document.getElementById('panel-preview');
            const panCode = document.getElementById('panel-code');

            if (mode === 'preview') {
                btnPrev.className = "px-4 py-1.5 text-xs font-semibold rounded-lg bg-cyan-500 text-slate-950 shadow-md";
                btnCode.className = "px-4 py-1.5 text-xs font-semibold rounded-lg text-slate-400 hover:text-white";
                panPrev.classList.remove('hidden');
                panCode.classList.add('hidden');
            } else {
                btnCode.className = "px-4 py-1.5 text-xs font-semibold rounded-lg bg-cyan-500 text-slate-950 shadow-md";
                btnPrev.className = "px-4 py-1.5 text-xs font-semibold rounded-lg text-slate-400 hover:text-white";
                panCode.classList.remove('hidden');
                panPrev.classList.add('hidden');
            }
        }

        // Convert string to hex payload
        function updateHexPayload() {
            const txt = document.getElementById('in-hex-text').value;
            state.hexText = txt;
            let hexStr = "";
            for (let i = 0; i < txt.length; i++) {
                hexStr += "0x" + txt.charCodeAt(i).toString(16).toUpperCase() + " ";
            }
            document.getElementById('lbl-hex-preview').innerText = "Payload: " + (hexStr || "0x00");
            updatePreview();
        }

        // Format Sudoku as Text Grid
        function formatSudokuAscii(grid) {
            let out = "+-------+-------+-------+\n";
            for (let r = 0; r < 9; r++) {
                let rowStr = "| ";
                for (let c = 0; c < 9; c++) {
                    const val = grid[r][c];
                    rowStr += (val === 0 ? "." : val) + " ";
                    if ((c + 1) % 3 === 0) rowStr += "| ";
                }
                out += rowStr + "\n";
                if ((r + 1) % 3 === 0) out += "+-------+-------+-------+\n";
            }
            return out.trim();
        }

        // Generate dynamic Markdown Code
        function generateMarkdownCode() {
            const uName = state.username || "YOUR-USERNAME";
            const badgesOS = [];
            if (state.os.kali) badgesOS.push(`![Kali Linux](https://img.shields.io/badge/Kali_Linux-557CDA?style=for-the-badge&logo=kali-linux&logoColor=white)`);
            if (state.os.linux) badgesOS.push(`![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)`);
            if (state.os.ubuntu) badgesOS.push(`![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)`);

            const badgesLangs = [];
            if (state.languages.c) badgesLangs.push(`![C](https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=black)`);
            if (state.languages.cpp) badgesLangs.push(`![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)`);
            if (state.languages.py) badgesLangs.push(`![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)`);
            if (state.languages.bash) badgesLangs.push(`![Bash](https://img.shields.io/badge/Shell_Scripting-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)`);

            // Hex Payload string
            let hexStr = "";
            for (let i = 0; i < state.hexText.length; i++) {
                hexStr += "0x" + state.hexText.charCodeAt(i).toString(16).toUpperCase() + " ";
            }

            let md = `<p align="center">
  <a href="https://instagram.com/${state.instagram}">
    <img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" />
  </a>
  <a href="mailto:${state.email}">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
</p>

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,12,23,34,45&height=180&section=header&text=${encodeURIComponent(state.name)}&fontSize=30&fontColor=ffffff&animation=fadeIn&fontAlignY=38" width="100%" />
</p>

<p align="center">
  <em>${state.tagline}</em>
</p>

---

## 🚀 About Me

${state.bio}

* 🔭 Always on the go with a new project
* 👯 Open to coding team-ups and tech brainstorming
* ⚡ Core Stack: C / C++, Kali Linux, and Low-Level Architecture

---

## 🛠️ Operating Systems & Languages

| Category | Technologies / Tools |
| :--- | :--- |
| **Operating Systems** | ${badgesOS.join(' ')} |
| **Languages** | ${badgesLangs.join(' ')} |
`;

            if (state.secChess) {
                md += `\n---\n\n## ♟️ The Imitation Game: Cryptographic Chess Puzzle\n\n> *"${state.turingQuote}"* — Alan Turing\n>\n> **The Scenario:** Inspired by *The Imitation Game*, calculate the tactical move to break the defense.\n\n\`\`\`text\n${chessBoardAscii}\n\`\`\`\n`;
            }

            if (state.secSudoku) {
                md += `\n---\n\n## 🧩 Hacker's Sudoku Challenge\n\n> **Can you solve this grid using algorithmic deduction (no brute forcing)?**\n\n\`\`\`text\n${formatSudokuAscii(state.sudokuGrid)}\n\`\`\`\n`;
            }

            if (state.secCipher) {
                md += `\n---\n\n## 🔑 Hex Cipher Challenge\n\n> Decode this hex ASCII payload:\n\`\`\`text\n${hexStr.trim()}\n\`\`\`\n`;
            }

            if (state.widgetArcade) {
                md += `\n---\n\n## 🎮 Take a Break (Interactive Arcade)\n\n<p align="center">\n  <a href="https://github.com/${uName}">\n    <img src="https://readme-swapping-game.vercel.app/api?username=${uName}&theme=dark" alt="Arcade Games" width="80%" />\n  </a>\n</p>\n`;
            }

            md += `\n---\n\n## 📊 GitHub Stats\n\n<p align="center">\n  <img src="https://github-readme-stats.vercel.app/api?username=${uName}&show_icons=true&theme=${state.theme}&hide_border=true&include_all_commits=true" width="48%" />\n  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=${uName}&layout=compact&theme=${state.theme}&hide_border=true" width="48%" />\n</p>\n`;

            if (state.widgetGraph) {
                md += `\n---\n\n## 📈 Contribution Graph\n\n<p align="center">\n  <img src="https://github-readme-activity-graph.vercel.app/graph?username=${uName}&theme=react-dark&hide_border=true" width="100%" />\n</p>\n`;
            }

            if (state.widgetSnake) {
                md += `\n---\n\n## 🐍 Contribution Snake\n\n<p align="center">\n  <img src="https://raw.githubusercontent.com/Platane/snk/output/github-contribution-grid-snake.svg" alt="Snake animation" />\n</p>\n`;
            }

            md += `\n---\n\n## 💭 Thoughts\n\n> *"Computer programs are powerful bombs and what you feed them can affect you in a powerful way."*\n\n<p align="center">\n  <img src="https://komarev.com/ghpvc/?username=${uName}&style=flat-square&color=blueviolet" alt="Profile Views" />\n</p>\n`;

            return md.trim();
        }

        // Live Update Preview Panel
        function updatePreview() {
            // Fetch Values
            state.username = document.getElementById('in-username').value;
            state.name = document.getElementById('in-name').value;
            state.tagline = document.getElementById('in-tagline').value;
            state.instagram = document.getElementById('in-instagram').value;
            state.email = document.getElementById('in-email').value;
            state.bio = document.getElementById('in-bio').value;

            state.os.kali = document.getElementById('chk-os-kali').checked;
            state.os.linux = document.getElementById('chk-os-linux').checked;
            state.os.ubuntu = document.getElementById('chk-os-ubuntu').checked;

            state.languages.c = document.getElementById('chk-lang-c').checked;
            state.languages.cpp = document.getElementById('chk-lang-cpp').checked;
            state.languages.py = document.getElementById('chk-lang-py').checked;
            state.languages.bash = document.getElementById('chk-lang-bash').checked;

            state.secChess = document.getElementById('chk-sec-chess').checked;
            state.secSudoku = document.getElementById('chk-sec-sudoku').checked;
            state.secCipher = document.getElementById('chk-sec-cipher').checked;
            state.turingQuote = document.getElementById('in-turing-quote').value;
            state.theme = document.getElementById('sel-stats-theme').value;

            state.widgetSnake = document.getElementById('chk-widget-snake').checked;
            state.widgetGraph = document.getElementById('chk-widget-graph').checked;
            state.widgetArcade = document.getElementById('chk-widget-arcade').checked;

            // DOM Visual Render
            document.getElementById('pv-name').innerText = "Hi, I'm " + (state.name || "Developer");
            document.getElementById('pv-tagline').innerText = state.tagline;
            document.getElementById('pv-bio').innerText = state.bio;
            document.getElementById('pv-turing-quote').innerText = `"${state.turingQuote}" — Alan Turing`;
            document.getElementById('pv-chess-grid').innerText = chessBoardAscii;
            document.getElementById('pv-sudoku-grid').innerText = formatSudokuAscii(state.sudokuGrid);
            document.getElementById('pv-stat-theme-name').innerText = state.theme;

            // Render Badges
            const bgContainer = document.getElementById('pv-badges-container');
            bgContainer.innerHTML = '';
            if (state.os.kali) bgContainer.innerHTML += `<span class="bg-indigo-900 border border-indigo-500 text-indigo-200 text-xs px-2.5 py-1 rounded font-mono font-bold">Kali Linux</span>`;
            if (state.os.linux) bgContainer.innerHTML += `<span class="bg-amber-900 border border-amber-500 text-amber-200 text-xs px-2.5 py-1 rounded font-mono font-bold">Linux</span>`;
            if (state.os.ubuntu) bgContainer.innerHTML += `<span class="bg-orange-900 border border-orange-500 text-orange-200 text-xs px-2.5 py-1 rounded font-mono font-bold">Ubuntu</span>`;
            if (state.languages.c) bgContainer.innerHTML += `<span class="bg-blue-950 border border-blue-500 text-blue-200 text-xs px-2.5 py-1 rounded font-mono font-bold">C</span>`;
            if (state.languages.cpp) bgContainer.innerHTML += `<span class="bg-cyan-950 border border-cyan-500 text-cyan-200 text-xs px-2.5 py-1 rounded font-mono font-bold">C++</span>`;
            if (state.languages.py) bgContainer.innerHTML += `<span class="bg-emerald-950 border border-emerald-500 text-emerald-200 text-xs px-2.5 py-1 rounded font-mono font-bold">Python</span>`;

            // Toggle visibility of preview blocks
            document.getElementById('pv-sec-chess-box').style.display = state.secChess ? 'block' : 'none';
            document.getElementById('pv-sec-sudoku-box').style.display = state.secSudoku ? 'block' : 'none';

            // Update raw code textarea
            document.getElementById('markdown-output').value = generateMarkdownCode();
        }

        // Copy Markdown to Clipboard
        function copyMarkdownCode() {
            const code = generateMarkdownCode();
            
            // Standard fallback using document.execCommand for iframe compatibility
            const tempTextArea = document.createElement('textarea');
            tempTextArea.value = code;
            document.body.appendChild(tempTextArea);
            tempTextArea.select();
            document.execCommand('copy');
            document.body.removeChild(tempTextArea);

            showToast("README Code copied to clipboard!");
        }

        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toast-msg').innerText = msg;
            toast.classList.remove('translate-y-20', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3000);
        }

        // Sandbox Interactive Grid Rendering
        function renderSandboxSudoku() {
            const container = document.getElementById('sudoku-grid-container');
            container.innerHTML = '';
            for (let r = 0; r < 9; r++) {
                for (let c = 0; c < 9; c++) {
                    const val = state.sudokuGrid[r][c];
                    const cell = document.createElement('div');
                    cell.className = `w-6 h-6 flex items-center justify-center font-mono text-xs font-bold rounded-sm ${
                        val === 0 ? 'bg-slate-900 text-cyan-400 border border-slate-700/60' : 'bg-slate-800 text-white'
                    }`;
                    cell.innerText = val === 0 ? '' : val;
                    container.appendChild(cell);
                }
            }
        }

        function solveSudokuStep() {
            // Simple visual solver step for demo
            for (let r = 0; r < 9; r++) {
                for (let c = 0; c < 9; c++) {
                    if (state.sudokuGrid[r][c] === 0) {
                        state.sudokuGrid[r][c] = Math.floor(Math.random() * 9) + 1;
                        renderSandboxSudoku();
                        updatePreview();
                        return;
                    }
                }
            }
        }

        function resetSudokuGrid() {
            state.sudokuGrid = [
                [5, 3, 0, 0, 7, 0, 0, 0, 0],
                [6, 0, 0, 1, 9, 5, 0, 0, 0],
                [0, 9, 8, 0, 0, 0, 0, 6, 0],
                [8, 0, 0, 0, 6, 0, 0, 0, 3],
                [4, 0, 0, 8, 0, 3, 0, 0, 1],
                [7, 0, 0, 0, 2, 0, 0, 0, 6],
                [0, 6, 0, 0, 0, 0, 2, 8, 0],
                [0, 0, 0, 4, 1, 9, 0, 0, 5],
                [0, 0, 0, 0, 8, 0, 0, 7, 9]
            ];
            renderSandboxSudoku();
            updatePreview();
        }

        function switchSandbox(mode) {
            const vSudoku = document.getElementById('sb-view-sudoku');
            const vChess = document.getElementById('sb-view-chess');
            const tSudoku = document.getElementById('sb-tab-sudoku');
            const tChess = document.getElementById('sb-tab-chess');

            if (mode === 'sudoku') {
                vSudoku.classList.remove('hidden');
                vSudoku.classList.add('flex');
                vChess.classList.add('hidden');
                vChess.classList.remove('flex');
                tSudoku.className = "text-xs font-mono text-cyan-400 font-bold border-b-2 border-cyan-400 pb-1";
                tChess.className = "text-xs font-mono text-slate-400 hover:text-white pb-1";
            } else {
                vChess.classList.remove('hidden');
                vChess.classList.add('flex');
                vSudoku.classList.add('hidden');
                vSudoku.classList.remove('flex');
                tChess.className = "text-xs font-mono text-amber-400 font-bold border-b-2 border-amber-400 pb-1";
                tSudoku.className = "text-xs font-mono text-slate-400 hover:text-white pb-1";
            }
        }

        // Initialize App
        window.onload = function() {
            renderSandboxSudoku();
            updateHexPayload();
            updatePreview();
        };
    </script>
</body>
</html>