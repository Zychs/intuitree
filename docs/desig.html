<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dyslexistree — Interactive Pitch Canvas Board</title>
  
  <!-- Tailwind CSS Configuration -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Font integration -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Lexend:wght@300;400;500;600;700&display=swap" rel="stylesheet">

  <!-- KaTeX for beautiful mathematical rendering -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.css">
  <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.js"></script>
  <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/contrib/auto-render.min.js"></script>

  <style>
    :root {
      --bg-primary: #FDFBF7; /* Cozy warm paper */
      --text-primary: #1E1B16;
      --font-body: 'Lexend', sans-serif;
      --line-height: 1.7;
      --letter-spacing: 0.04em;
      --word-spacing: 0.08em;
      --focus-ring: 3px solid #D97706;
    }

    body {
      background-color: var(--bg-primary);
      color: var(--text-primary);
      font-family: var(--font-body);
      line-height: var(--line-height);
      letter-spacing: var(--letter-spacing);
      word-spacing: var(--word-spacing);
      transition: all 0.2s ease;
    }

    /* Accessibility focus visible rings */
    a:focus-visible, button:focus-visible, input:focus-visible, select:focus-visible {
      outline: var(--focus-ring);
      outline-offset: 2px;
    }

    /* Spacing panel classes */
    .bionic-bold {
      font-weight: 700;
      color: #000000;
    }

    /* Color Themes */
    .theme-contrast {
      --bg-primary: #121212;
      --text-primary: #FFFFE0;
      --focus-ring: 3px solid #FBBF24;
    }
    .theme-contrast .canvas-card {
      background-color: #1E1E1E !important;
      border-color: #333333 !important;
      color: #FFFFE0 !important;
    }
    .theme-contrast .canvas-card h3 {
      color: #FBBF24 !important;
    }
    .theme-contrast strong, .theme-contrast .bionic-bold {
      color: #FFFFFF !important;
    }

    .theme-sepia {
      --bg-primary: #FCF6EB;
      --text-primary: #433422;
    }
    .theme-sepia .canvas-card {
      background-color: #FAF2E3 !important;
      border-color: #E6D7C3 !important;
    }

    /* Reading Guide Ruler */
    #reading-ruler {
      position: absolute;
      left: 0;
      right: 0;
      height: 30px;
      background-color: rgba(217, 119, 6, 0.1);
      border-top: 1px dashed rgba(217, 119, 6, 0.4);
      border-bottom: 1px dashed rgba(217, 119, 6, 0.4);
      pointer-events: none;
      z-index: 100;
      display: none;
    }

    /* Focus dim feature */
    .focus-dim .canvas-card:not(:hover) {
      opacity: 0.4;
      filter: blur(1px);
    }
    .canvas-card {
      transition: opacity 0.25s ease, filter 0.25s ease, transform 0.2s ease;
    }
    .canvas-card:hover {
      transform: translateY(-2px);
    }
  </style>
</head>
<body class="min-h-screen p-4 md:p-8">

  <div id="reading-ruler"></div>

  <!-- Header Dashboard -->
  <header class="max-w-7xl mx-auto mb-8 bg-white p-6 rounded-2xl border border-stone-200 shadow-sm flex flex-col lg:flex-row justify-between items-start lg:items-center gap-6">
    <div>
      <div class="flex items-center gap-3">
        <span class="p-2.5 bg-amber-600 text-white rounded-xl text-2xl" aria-hidden="true">🌳</span>
        <div>
          <h1 class="text-2xl font-bold tracking-tight">Dyslexistree Pitch & Research Canvas</h1>
          <p class="text-xs text-stone-500 font-medium mt-0.5">A visual, dyslexia-accessible map of the systemic Windows exploration model.</p>
        </div>
      </div>
    </div>

    <!-- DyslexiUI Real-time Controls -->
    <div class="flex flex-wrap items-center gap-4 bg-stone-50 p-4 rounded-xl border border-stone-200 w-full lg:w-auto">
      <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 text-xs w-full lg:w-auto">
        <!-- Spacing / Size dials -->
        <div class="flex flex-col gap-1">
          <span class="font-bold text-stone-600">Text Size</span>
          <input type="range" id="dial-size" min="13" max="20" value="15" class="accent-amber-600" oninput="applyDials()">
        </div>
        <div class="flex flex-col gap-1">
          <span class="font-bold text-stone-600">Line Space</span>
          <input type="range" id="dial-line" min="1.4" max="2.2" step="0.1" value="1.7" class="accent-amber-600" oninput="applyDials()">
        </div>
        <div class="flex flex-col gap-1">
          <span class="font-bold text-stone-600">Word Space</span>
          <input type="range" id="dial-word" min="0.02" max="0.18" step="0.02" value="0.08" class="accent-amber-600" oninput="applyDials()">
        </div>
        <div class="flex flex-col gap-1">
          <span class="font-bold text-stone-600">Theme</span>
          <select id="theme-select" class="bg-white border rounded p-1 text-[11px]" onchange="setTheme(this.value)">
            <option value="warm">Warm Paper</option>
            <option value="sepia">Sepia Book</option>
            <option value="contrast">High Contrast</option>
          </select>
        </div>
      </div>

      <!-- Quick Toggles -->
      <div class="flex items-center gap-3 border-t lg:border-t-0 pt-2 lg:pt-0 border-stone-200 w-full lg:w-auto justify-between lg:justify-start">
        <label class="flex items-center gap-1.5 text-xs font-bold cursor-pointer">
          <input type="checkbox" id="toggle-bionic" class="accent-amber-600" onchange="toggleBionic(this.checked)">
          <span>Bionic Reading</span>
        </label>
        <label class="flex items-center gap-1.5 text-xs font-bold cursor-pointer">
          <input type="checkbox" id="toggle-ruler" class="accent-amber-600" onchange="toggleRuler(this.checked)">
          <span>Guide Ruler</span>
        </label>
        <label class="flex items-center gap-1.5 text-xs font-bold cursor-pointer">
          <input type="checkbox" id="toggle-focus" class="accent-amber-600" onchange="toggleFocusMode(this.checked)">
          <span>Focus Isolation</span>
        </label>
      </div>
    </div>
  </header>

  <!-- Interactive 5-Column Lean Canvas Grid -->
  <main class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-6" id="canvas-grid">
    
    <!-- Column 1: Problems & Segments -->
    <div class="lg:col-span-1 flex flex-col gap-6">
      
      <!-- 1. The Problem -->
      <section class="canvas-card bg-rose-50/50 border border-rose-200 p-5 rounded-2xl shadow-sm flex flex-col gap-3 min-h-[320px]" data-section="problem">
        <div class="flex justify-between items-start border-b border-rose-100 pb-2">
          <h3 class="font-bold text-rose-800 text-sm flex items-center gap-2">
            <span class="text-base">🚨</span> 1. The Problem
          </h3>
          <button onclick="enableEditing('problem')" class="text-[10px] bg-rose-100 hover:bg-rose-200 px-2 py-0.5 rounded text-rose-800 font-bold focus:outline-none">Edit</button>
        </div>
        <div class="text-xs text-stone-700 flex flex-col gap-2 grow overflow-y-auto" id="view-problem">
          <p class="font-semibold text-rose-900 mb-1">Standard tools prioritize pure visual density over structural readability:</p>
          <ul class="list-disc pl-4 space-y-2">
            <li><strong>Visual Opacity:</strong> Symlinks, junctions, stubs, and folders all share matching standard icons in Windows Explorer.</li>
            <li><strong>The OneDrive Drift:</strong> Automatic updates silently redirect local shell targets, breaking custom application configurations.</li>
            <li><strong>Regedit is Hostile:</strong> Modifying redirection values in HKCU offers no map context, zero translation, and no undo paths.</li>
          </ul>
        </div>
        <div class="hidden flex flex-col gap-2 text-xs" id="edit-problem">
          <textarea class="w-full h-48 p-2 border rounded font-mono text-[11px]" id="input-problem"></textarea>
          <button onclick="saveSection('problem')" class="bg-rose-700 text-white font-bold p-1 rounded text-[11px] focus:outline-none">Apply Changes</button>
        </div>
      </section>

      <!-- 2. Customer Segments -->
      <section class="canvas-card bg-blue-50/50 border border-blue-200 p-5 rounded-2xl shadow-sm flex flex-col gap-3 min-h-[220px]" data-section="segments">
        <div class="flex justify-between items-start border-b border-blue-100 pb-2">
          <h3 class="font-bold text-blue-800 text-sm flex items-center gap-2">
            <span class="text-base">👥</span> 2. Segments
          </h3>
          <button onclick="enableEditing('segments')" class="text-[10px] bg-blue-100 hover:bg-blue-200 px-2 py-0.5 rounded text-blue-800 font-bold focus:outline-none">Edit</button>
        </div>
        <div class="text-xs text-stone-700 flex flex-col gap-2 grow" id="view-segments">
          <ul class="list-disc pl-4 space-y-2">
            <li><strong>Neurodivergent Power Users:</strong> System builders seeking structured environment layouts without visual fatigue.</li>
            <li><strong>Non-Technical Novices:</strong> Families whose default folders got diverted by cloud installations.</li>
            <li><strong>Helpdesk Engineers:</strong> Admins looking for safe profile repair automation.</li>
          </ul>
        </div>
        <div class="hidden flex flex-col gap-2 text-xs" id="edit-segments">
          <textarea class="w-full h-36 p-2 border rounded font-mono text-[11px]" id="input-segments"></textarea>
          <button onclick="saveSection('segments')" class="bg-blue-700 text-white font-bold p-1 rounded text-[11px] focus:outline-none">Apply Changes</button>
        </div>
      </section>

    </div>

    <!-- Column 2: Solution & Channels -->
    <div class="lg:col-span-1 flex flex-col gap-6">
      
      <!-- 4. The Solution -->
      <section class="canvas-card bg-emerald-50/50 border border-emerald-200 p-5 rounded-2xl shadow-sm flex flex-col gap-3 min-h-[320px]" data-section="solution">
        <div class="flex justify-between items-start border-b border-emerald-100 pb-2">
          <h3 class="font-bold text-emerald-800 text-sm flex items-center gap-2">
            <span class="text-base">🛠️</span> 4. The Solution
          </h3>
          <button onclick="enableEditing('solution')" class="text-[10px] bg-emerald-100 hover:bg-emerald-200 px-2 py-0.5 rounded text-emerald-800 font-bold focus:outline-none">Edit</button>
        </div>
        <div class="text-xs text-stone-700 flex flex-col gap-2 grow" id="view-solution">
          <p class="font-semibold text-emerald-900 mb-1">A local system map that coordinates folders with corresponding registry configurations:</p>
          <ul class="list-disc pl-4 space-y-2">
            <li><strong>Bipartite System Map:</strong> Coordinates system values side-by-side with directory endpoints.</li>
            <li><strong>DyslexiUI Spacing Engine:</strong> Sliders to instantly adapt letter spacing, spacing gaps, and bionic emphasis.</li>
            <li><strong>Direct Translation Pane:</strong> Interprets confusing registry GUID parameters into normal, clear phrases.</li>
          </ul>
        </div>
        <div class="hidden flex flex-col gap-2 text-xs" id="edit-solution">
          <textarea class="w-full h-48 p-2 border rounded font-mono text-[11px]" id="input-solution"></textarea>
          <button onclick="saveSection('solution')" class="bg-emerald-700 text-white font-bold p-1 rounded text-[11px] focus:outline-none">Apply Changes</button>
        </div>
      </section>

      <!-- 5. Channels -->
      <section class="canvas-card bg-indigo-50/50 border border-indigo-200 p-5 rounded-2xl shadow-sm flex flex-col gap-3 min-h-[220px]" data-section="channels">
        <div class="flex justify-between items-start border-b border-indigo-100 pb-2">
          <h3 class="font-bold text-indigo-800 text-sm flex items-center gap-2">
            <span class="text-base">📢</span> 5. Channels
          </h3>
          <button onclick="enableEditing('channels')" class="text-[10px] bg-indigo-100 hover:bg-indigo-200 px-2 py-0.5 rounded text-indigo-800 font-bold focus:outline-none">Edit</button>
        </div>
        <div class="text-xs text-stone-700 flex flex-col gap-2 grow" id="view-channels">
          <ul class="list-disc pl-4 space-y-2">
            <li><strong>Ecosystem Integrations:</strong> IDE system trees, accessibility extensions, and community packages.</li>
            <li><strong>Power User Communities:</strong> Customization communities, administrative networks, and subreddits.</li>
            <li><strong>Organizations:</strong> Universities and support organizations specializing in neurodiversity.</li>
          </ul>
        </div>
        <div class="hidden flex flex-col gap-2 text-xs" id="edit-channels">
          <textarea class="w-full h-36 p-2 border rounded font-mono text-[11px]" id="input-channels"></textarea>
          <button onclick="saveSection('channels')" class="bg-indigo-700 text-white font-bold p-1 rounded text-[11px] focus:outline-none">Apply Changes</button>
        </div>
      </section>

    </div>

    <!-- Column 3: Unique Value Proposition (Centered Highlight Panel) -->
    <div class="lg:col-span-1 flex flex-col gap-6">
      <section class="canvas-card bg-amber-50 border border-amber-300 p-6 rounded-2xl shadow flex flex-col gap-4 grow min-h-[560px]" data-section="uvp">
        <div class="flex justify-between items-start border-b border-amber-200 pb-2">
          <h3 class="font-bold text-amber-800 text-sm flex items-center gap-2">
            <span class="text-base">⭐</span> 3. Value Proposition
          </h3>
          <button onclick="enableEditing('uvp')" class="text-[10px] bg-amber-100 hover:bg-amber-200 px-2 py-0.5 rounded text-amber-800 font-bold focus:outline-none">Edit</button>
        </div>
        
        <div class="flex flex-col gap-4 grow" id="view-uvp">
          <div class="p-4 bg-white rounded-xl border border-amber-200">
            <p class="font-bold text-amber-950 text-sm text-center leading-relaxed">
              "The first local-first, dyslexia-aware system map that unifies your Windows registry and filesystem into a single, interactive, safe-to-edit canvas."
            </p>
          </div>

          <div class="text-xs text-stone-700 flex flex-col gap-3">
            <div class="flex items-start gap-2.5">
              <span class="text-base leading-none">🎨</span>
              <div>
                <strong class="text-amber-900 block font-bold">Multi-Channel Legibility:</strong>
                Never rely on color alone. Folder types are visually anchored by distinct shapes and outlines.
              </div>
            </div>

            <div class="flex items-start gap-2.5">
              <span class="text-base leading-none">🛡️</span>
              <div>
                <strong class="text-amber-900 block font-bold">Zero-Risk Registry Sandbox:</strong>
                Simulate your redirection ideas in a virtual preview pane before committing changes to actual hives.
              </div>
            </div>

            <div class="flex items-start gap-2.5">
              <span class="text-base leading-none">🚀</span>
              <div>
                <strong class="text-amber-900 block font-bold">Local-First Privacy:</strong>
                Zero network requests, zero telemetry. High security execution directly on your local device.
              </div>
            </div>
          </div>
        </div>

        <div class="hidden flex flex-col gap-2 text-xs" id="edit-uvp">
          <textarea class="w-full h-96 p-2 border rounded font-mono text-[11px]" id="input-uvp"></textarea>
          <button onclick="saveSection('uvp')" class="bg-amber-700 text-white font-bold p-1 rounded text-[11px] focus:outline-none">Apply Changes</button>
        </div>
      </section>
    </div>

    <!-- Column 4: Key Metrics & High-Level Concept -->
    <div class="lg:col-span-1 flex flex-col gap-6">
      
      <!-- 6. Key Metrics -->
      <section class="canvas-card bg-purple-50/50 border border-purple-200 p-5 rounded-2xl shadow-sm flex flex-col gap-3 min-h-[320px]" data-section="metrics">
        <div class="flex justify-between items-start border-b border-purple-100 pb-2">
          <h3 class="font-bold text-purple-800 text-sm flex items-center gap-2">
            <span class="text-base">📊</span> 6. Key Metrics
          </h3>
          <button onclick="enableEditing('metrics')" class="text-[10px] bg-purple-100 hover:bg-purple-200 px-2 py-0.5 rounded text-purple-800 font-bold focus:outline-none">Edit</button>
        </div>
        <div class="text-xs text-stone-700 flex flex-col gap-2 grow" id="view-metrics">
          <ul class="list-disc pl-4 space-y-2">
            <li><strong>Path Reach Efficiency:</strong> Users can find nested file system variations in $\le 5$ direct clicks.</li>
            <li><strong>Cognitive Comfort Score:</strong> Target reading fatigue indicators reduction of $\ge 50\%$ compared to standard tools.</li>
            <li><strong>Data Loss Probability:</strong> Guarantees absolutely safe restoration procedures:
              <div class="my-1.5 p-1 bg-white rounded border border-purple-100 text-center font-mono text-[11px]">
                $$P(\text{Data Loss}) = 0$$
              </div>
            </li>
          </ul>
        </div>
        <div class="hidden flex flex-col gap-2 text-xs" id="edit-metrics">
          <textarea class="w-full h-48 p-2 border rounded font-mono text-[11px]" id="input-metrics"></textarea>
          <button onclick="saveSection('metrics')" class="bg-purple-700 text-white font-bold p-1 rounded text-[11px] focus:outline-none">Apply Changes</button>
        </div>
      </section>

      <!-- 7. High-Level Concept -->
      <section class="canvas-card bg-teal-50/50 border border-teal-200 p-5 rounded-2xl shadow-sm flex flex-col gap-3 min-h-[220px]" data-section="concept">
        <div class="flex justify-between items-start border-b border-teal-100 pb-2">
          <h3 class="font-bold text-teal-800 text-sm flex items-center gap-2">
            <span class="text-base">📐</span> 7. The Concept
          </h3>
          <button onclick="enableEditing('concept')" class="text-[10px] bg-teal-100 hover:bg-teal-200 px-2 py-0.5 rounded text-teal-800 font-bold focus:outline-none">Edit</button>
        </div>
        <div class="text-xs text-stone-700 flex flex-col gap-2 grow" id="view-concept">
          <p class="font-semibold text-teal-900">Bipartite map representation:</p>
          <p class="italic text-[11px] leading-relaxed">
            Let $R$ represent the set of Registry keys and $F$ the set of system directories. An edge $e = (r, f)$ is formed when key $r \in R$ resolves to directory $f \in F$.
          </p>
          <div class="p-1.5 bg-white border border-teal-100 rounded text-center font-mono text-[10px] mt-1">
            Registry Nodes ➜ Real Directories
          </div>
        </div>
        <div class="hidden flex flex-col gap-2 text-xs" id="edit-concept">
          <textarea class="w-full h-36 p-2 border rounded font-mono text-[11px]" id="input-concept"></textarea>
          <button onclick="saveSection('concept')" class="bg-teal-700 text-white font-bold p-1 rounded text-[11px] focus:outline-none">Apply Changes</button>
        </div>
      </section>

    </div>

    <!-- Column 5: Costs & Value Realization -->
    <div class="lg:col-span-1 flex flex-col gap-6">
      
      <!-- 8. Cost Structure -->
      <section class="canvas-card bg-orange-50/50 border border-orange-200 p-5 rounded-2xl shadow-sm flex flex-col gap-3 min-h-[320px]" data-section="costs">
        <div class="flex justify-between items-start border-b border-orange-100 pb-2">
          <h3 class="font-bold text-orange-800 text-sm flex items-center gap-2">
            <span class="text-base">💸</span> 8. Cost Structure
          </h3>
          <button onclick="enableEditing('costs')" class="text-[10px] bg-orange-100 hover:bg-orange-200 px-2 py-0.5 rounded text-orange-800 font-bold focus:outline-none">Edit</button>
        </div>
        <div class="text-xs text-stone-700 flex flex-col gap-2 grow" id="view-costs">
          <ul class="list-disc pl-4 space-y-2">
            <li><strong>Zero Remote Overhead:</strong> $100\%$ local filesystem processing translates to $0$ ongoing API database costs.</li>
            <li><strong>Certification:</strong> Windows application signing certificates for security validation.</li>
            <li><strong>Developer Resources:</strong> Open-source contributions, developer hours, and accessibility auditing tools.</li>
          </ul>
        </div>
        <div class="hidden flex flex-col gap-2 text-xs" id="edit-costs">
          <textarea class="w-full h-48 p-2 border rounded font-mono text-[11px]" id="input-costs"></textarea>
          <button onclick="saveSection('costs')" class="bg-orange-700 text-white font-bold p-1 rounded text-[11px] focus:outline-none">Apply Changes</button>
        </div>
      </section>

      <!-- 9. Value Realization -->
      <section class="canvas-card bg-stone-100/70 border border-stone-300 p-5 rounded-2xl shadow-sm flex flex-col gap-3 min-h-[220px]" data-section="value">
        <div class="flex justify-between items-start border-b border-stone-200 pb-2">
          <h3 class="font-bold text-stone-800 text-sm flex items-center gap-2">
            <span class="text-base">💡</span> 9. Value Realization
          </h3>
          <button onclick="enableEditing('value')" class="text-[10px] bg-stone-200 hover:bg-stone-300 px-2 py-0.5 rounded text-stone-800 font-bold focus:outline-none">Edit</button>
        </div>
        <div class="text-xs text-stone-700 flex flex-col gap-2 grow" id="view-value">
          <ul class="list-disc pl-4 space-y-2">
            <li><strong>Open-Core Model:</strong> A fully functional local analyzer tool available to everyone.</li>
            <li><strong>Licensing:</strong> Specialized, enterprise diagnostics tooling for team admins.</li>
            <li><strong>Community Support:</strong> Donations, sponsorships, and research grants.</li>
          </ul>
        </div>
        <div class="hidden flex flex-col gap-2 text-xs" id="edit-value">
          <textarea class="w-full h-36 p-2 border rounded font-mono text-[11px]" id="input-value"></textarea>
          <button onclick="saveSection('value')" class="bg-stone-700 text-white font-bold p-1 rounded text-[11px] focus:outline-none">Apply Changes</button>
        </div>
      </section>

    </div>

  </main>

  <!-- Export Panel -->
  <footer class="max-w-7xl mx-auto mt-8 flex flex-col sm:flex-row justify-between items-center gap-4 bg-white p-5 rounded-2xl border border-stone-200 shadow-sm">
    <div class="text-xs text-stone-500 font-medium">
      Proposals edit dynamically. Clean local storage at any time to recover the default presentation layout.
    </div>
    <div class="flex items-center gap-3">
      <button onclick="resetToDefaults()" class="px-4 py-2 bg-stone-100 hover:bg-stone-200 text-stone-700 rounded-xl font-bold text-xs transition focus:outline-none">
        Reset Defaults
      </button>
      <button onclick="exportCanvas()" class="px-4 py-2 bg-amber-600 hover:bg-amber-700 text-white rounded-xl font-bold text-xs transition shadow-sm focus:outline-none">
        Export JSON Config
      </button>
    </div>
  </footer>

  <script>
    // Initial Pitch Canvas Data Model
    const DEFAULT_CANVAS_DATA = {
      problem: `<strong>Standard tools prioritize pure visual density over structural readability:</strong><br><br><ul class="list-disc pl-4 space-y-2"><li><strong>Visual Opacity:</strong> Symlinks, junctions, stubs, and folders all share matching standard icons in Windows Explorer.</li><li><strong>The OneDrive Drift:</strong> Automatic updates silently redirect local shell targets, breaking custom application configurations.</li><li><strong>Regedit is Hostile:</strong> Modifying redirection values in HKCU offers no map context, zero translation, and no undo paths.</li></ul>`,
      segments: `<ul class="list-disc pl-4 space-y-2"><li><strong>Neurodivergent Power Users:</strong> System builders seeking structured environment layouts without visual fatigue.</li><li><strong>Non-Technical Novices:</strong> Families whose default folders got diverted by cloud installations.</li><li><strong>Helpdesk Engineers:</strong> Admins looking for safe profile repair automation.</li></ul>`,
      solution: `<strong>A local system map that coordinates folders with corresponding registry configurations:</strong><br><br><ul class="list-disc pl-4 space-y-2"><li><strong>Bipartite System Map:</strong> Coordinates system values side-by-side with directory endpoints.</li><li><strong>DyslexiUI Spacing Engine:</strong> Sliders to instantly adapt letter spacing, spacing gaps, and bionic emphasis.</li><li><strong>Direct Translation Pane:</strong> Interprets confusing registry GUID parameters into normal, clear phrases.</li></ul>`,
      channels: `<ul class="list-disc pl-4 space-y-2"><li><strong>Ecosystem Integrations:</strong> IDE system trees, accessibility extensions, and community packages.</li><li><strong>Power User Communities:</strong> Customization communities, administrative networks, and subreddits.</li><li><strong>Organizations:</strong> Universities and support organizations specializing in neurodiversity.</li></ul>`,
      uvp: `<div class="p-4 bg-white rounded-xl border border-amber-200 mb-3"><p class="font-bold text-amber-950 text-sm text-center leading-relaxed">"The first local-first, dyslexia-aware system map that unifies your Windows registry and filesystem into a single, interactive, safe-to-edit canvas."</p></div><div class="text-xs text-stone-700 flex flex-col gap-3"><div><strong class="text-amber-900 block font-bold">Multi-Channel Legibility:</strong>Never rely on color alone. Folder types are visually anchored by distinct shapes and outlines.</div><div><strong class="text-amber-900 block font-bold">Zero-Risk Registry Sandbox:</strong>Simulate your redirection ideas in a virtual preview pane before committing changes to actual hives.</div><div><strong class="text-amber-900 block font-bold">Local-First Privacy:</strong>Zero network requests, zero telemetry. High security execution directly on your local device.</div></div>`,
      metrics: `<ul class="list-disc pl-4 space-y-2"><li><strong>Path Reach Efficiency:</strong> Users can find nested file system variations in $\\le 5$ direct clicks.</li><li><strong>Cognitive Comfort Score:</strong> Target reading fatigue indicators reduction of $\\ge 50\\%$ compared to standard tools.</li><li><strong>Data Loss Probability:</strong> Guarantees absolutely safe restoration procedures:<div class="my-1.5 p-1 bg-white rounded border border-purple-100 text-center font-mono text-[11px]">$$P(\\text{Data Loss}) = 0$$</div></li></ul>`,
      concept: `<p class="font-semibold text-teal-900">Bipartite map representation:</p><p class="italic text-[11px] leading-relaxed">Let $R$ represent the set of Registry keys and $F$ the set of system directories. An edge $e = (r, f)$ is formed when key $r \\in R$ resolves to directory $f \\in F$.</p><div class="p-1.5 bg-white border border-teal-100 rounded text-center font-mono text-[10px] mt-1">Registry Nodes ➜ Real Directories</div>`,
      costs: `<ul class="list-disc pl-4 space-y-2"><li><strong>Zero Remote Overhead:</strong> $100\\%$ local filesystem processing translates to $0$ ongoing API database costs.</li><li><strong>Certification:</strong> Windows application signing certificates for security validation.</li><li><strong>Developer Resources:</strong> Open-source contributions, developer hours, and accessibility auditing tools.</li></ul>`,
      value: `<ul class="list-disc pl-4 space-y-2"><li><strong>Open-Core Model:</strong> A fully functional local analyzer tool available to everyone.</li><li><strong>Licensing:</strong> Specialized, enterprise diagnostics tooling for team admins.</li><li><strong>Community Support:</strong> Donations, sponsorships, and research grants.</li></ul>`
    };

    let activeData = {};
    let bionicActive = false;

    // Load active layout settings
    window.addEventListener("DOMContentLoaded", () => {
      initData();
      applyDials();
      initMouseRuler();
    });

    function initData() {
      const stored = localStorage.getItem("dyslexistree_pitch_data");
      if (stored) {
        activeData = JSON.parse(stored);
      } else {
        activeData = { ...DEFAULT_CANVAS_DATA };
      }
      renderAll();
    }

    // High quality representation parsing
    function renderAll() {
      Object.keys(activeData).forEach(key => {
        const el = document.getElementById(`view-${key}`);
        if (el) {
          let text = activeData[key];
          if (bionicActive) {
            text = applyBionicFormat(text);
          }
          el.innerHTML = text;
        }
      });
      
      // Force KaTeX to render our newly written math strings
      if (window.renderMathInElement) {
        renderMathInElement(document.body, {
          delimiters: [
            {left: '$$', right: '$$', display: true},
            {left: '$', right: '$', display: false}
          ],
          throwOnError : false
        });
      }
    }

    // Editable Panels interface
    function enableEditing(key) {
      document.getElementById(`view-${key}`).classList.add("hidden");
      const editBox = document.getElementById(`edit-${key}`);
      editBox.classList.remove("hidden");
      
      // Convert current display clean markdown layout back to pure editable string
      document.getElementById(`input-${key}`).value = activeData[key]
        .replace(/<br>/g, "\n")
        .replace(/<\/?[^>]+(>|$)/g, ""); // Strip helper formatting
    }

    function saveSection(key) {
      const inputVal = document.getElementById(`input-${key}`).value;
      // Basic formatting helpers for text lists
      let htmlFormatted = inputVal.split("\n").map(line => {
        if (line.startsWith("- ")) {
          return `<li>${line.slice(2)}</li>`;
        }
        return line ? `<p>${line}</p>` : "<br>";
      }).join("");

      if (htmlFormatted.includes("<li>")) {
        htmlFormatted = htmlFormatted.replace(/(<li>.*<\/li>)/g, `<ul class="list-disc pl-4 space-y-2">$1</ul>`);
      }

      activeData[key] = htmlFormatted;
      localStorage.setItem("dyslexistree_pitch_data", JSON.stringify(activeData));

      document.getElementById(`edit-${key}`).classList.add("hidden");
      document.getElementById(`view-${key}`).classList.remove("hidden");
      
      renderAll();
    }

    function resetToDefaults() {
      if (confirm("Reset layout to standard research specifications?")) {
        localStorage.removeItem("dyslexistree_pitch_data");
        initData();
      }
    }

    function exportCanvas() {
      const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(activeData, null, 2));
      const downloadAnchor = document.createElement('a');
      downloadAnchor.setAttribute("href", dataStr);
      downloadAnchor.setAttribute("download", "dyslexistree_canvas_export.json");
      document.body.appendChild(downloadAnchor);
      downloadAnchor.click();
      downloadAnchor.remove();
    }

    // DyslexiUI Engine adjustments
    function applyDials() {
      const sizeVal = document.getElementById("dial-size").value;
      const lineVal = document.getElementById("dial-line").value;
      const wordVal = document.getElementById("dial-word").value;

      document.documentElement.style.setProperty("--line-height", lineVal);
      document.documentElement.style.setProperty("--word-spacing", `${wordVal}em`);
      
      const cards = document.querySelectorAll(".canvas-card text-xs, .canvas-card p, .canvas-card li");
      cards.forEach(el => {
        el.style.fontSize = `${sizeVal}px`;
      });
    }

    function setTheme(theme) {
      document.body.className = "min-h-screen p-4 md:p-8";
      if (theme !== "warm") {
        document.body.classList.add(`theme-${theme}`);
      }
    }

    // Bionic Reading Emphasis
    function applyBionicFormat(htmlStr) {
      const tempDiv = document.createElement("div");
      tempDiv.innerHTML = htmlStr;

      function traverseAndBionic(node) {
        if (node.nodeType === Node.TEXT_NODE) {
          const words = node.textContent.split(/\s+/);
          const formatted = words.map(word => {
            if (word.length <= 1) return word;
            if (word.length <= 3) return `<span class="bionic-bold">${word.slice(0, 1)}</span>${word.slice(1)}`;
            const mid = Math.ceil(word.length / 2);
            return `<span class="bionic-bold">${word.slice(0, mid)}</span>${word.slice(mid)}`;
          }).join(" ");
          
          const wrapperSpan = document.createElement("span");
          wrapperSpan.innerHTML = formatted;
          node.parentNode.replaceChild(wrapperSpan, node);
        } else {
          for (let i = node.childNodes.length - 1; i >= 0; i--) {
            traverseAndBionic(node.childNodes[i]);
          }
        }
      }

      traverseAndBionic(tempDiv);
      return tempDiv.innerHTML;
    }

    function toggleBionic(checked) {
      bionicActive = checked;
      renderAll();
    }

    // Guide ruler implementation
    function initMouseRuler() {
      const ruler = document.getElementById("reading-ruler");
      window.addEventListener("mousemove", (e) => {
        if (document.getElementById("toggle-ruler").checked) {
          ruler.style.top = `${e.pageY - 15}px`;
        }
      });
    }

    function toggleRuler(checked) {
      document.getElementById("reading-ruler").style.display = checked ? "block" : "none";
    }

    function toggleFocusMode(checked) {
      const grid = document.getElementById("canvas-grid");
      if (checked) {
        grid.classList.add("focus-dim");
      } else {
        grid.classList.remove("focus-dim");
      }
    }
  </script>
</body>
</html>
