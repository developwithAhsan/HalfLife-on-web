<template>
  <div class="page-container">
    <!-- Ambient particle background -->
    <canvas ref="particleCanvas" class="particles-canvas"></canvas>

    <!-- Top Sticky Navigation Bar -->
    <header class="top-nav">
      <div class="nav-inner">
        <!-- Brand Logo -->
        <a href="#game-launcher" class="nav-brand">
          <div class="nav-lambda-glyph">λ</div>
          <div class="nav-brand-text">
            <span class="nav-title">WEBXASH</span>
            <span class="nav-tag">GOLDSRC WASM</span>
          </div>
        </a>

        <!-- Main Navigation Links -->
        <nav class="nav-links">
          <a href="#game-launcher" class="nav-link">Play</a>
          <a href="#article-guide" class="nav-link">Guide</a>
          <a href="#weapons-guide" class="nav-link">Weapons</a>
          <a href="#faq-section" class="nav-link">FAQ</a>
          <a href="#community-comments" class="nav-link">Comments</a>
        </nav>

        <!-- Header Action Buttons -->
        <div class="nav-actions">
          <button
            class="nav-icon-btn"
            title="Toggle Fullscreen"
            aria-label="Toggle Fullscreen"
            @click="toggleFullscreen"
          >
            <svg class="nav-svg-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/>
            </svg>
            <span class="btn-text-desktop">Fullscreen</span>
          </button>

          <button class="nav-launch-btn" @click="startUplink">
            <svg class="nav-play-icon" viewBox="0 0 24 24" fill="currentColor">
              <path d="M8 5v14l11-7z"/>
            </svg>
            <span>START GAME</span>
          </button>
        </div>
      </div>
    </header>

    <!-- Main Content Area -->
    <main v-if="!loading" class="content-wrapper">
      
      <!-- HERO / GAME LAUNCHER SECTION -->
      <section id="game-launcher" class="hero-section">
        <div class="launch-card">
          <!-- Card Header & Status -->
          <div class="card-header">
            <div class="lambda-badge">
              <span class="lambda-char">λ</span>
            </div>
            <div class="header-text">
              <div class="status-indicator">
                <span class="status-dot"></span>
                <span class="status-text">WEBASSEMBLY 64-BIT ENGINE READY</span>
              </div>
              <h1 class="game-title">HALF-LIFE: UPLINK</h1>
              <p class="game-subtitle">Official Standalone Black Mesa Chapter in Your Browser</p>
            </div>
          </div>

          <!-- Feature Badges -->
          <div class="tags-row">
            <span class="tag-pill">WebGL 2.0 Shaders</span>
            <span class="tag-pill">60+ FPS Native</span>
            <span class="tag-pill">Stereo 3D Audio</span>
            <span class="tag-pill">Local Save Persistence</span>
          </div>

          <!-- Primary Launch CTA -->
          <button class="primary-launch-btn" @click="startUplink">
            <svg class="play-icon" viewBox="0 0 24 24" fill="currentColor">
              <path d="M8 5v14l11-7z"/>
            </svg>
            <span>LAUNCH GAME NOW</span>
          </button>

          <!-- Controls Grid -->
          <div class="controls-box">
            <div class="controls-header">
              <span class="controls-title">DEFAULT CONTROLS</span>
              <span class="controls-hint">POINTER LOCK SUPPORTED</span>
            </div>
            <div class="controls-grid">
              <div class="control-item"><kbd>W</kbd><kbd>A</kbd><kbd>S</kbd><kbd>D</kbd><span>Move</span></div>
              <div class="control-item"><kbd>Mouse</kbd><span>Aim / Look</span></div>
              <div class="control-item"><kbd>L-Click</kbd><span>Primary Fire</span></div>
              <div class="control-item"><kbd>R-Click</kbd><span>Secondary Fire</span></div>
              <div class="control-item"><kbd>E</kbd><span>Interact / Open</span></div>
              <div class="control-item"><kbd>Space</kbd><span>Jump</span></div>
              <div class="control-item"><kbd>Ctrl</kbd><span>Crouch</span></div>
              <div class="control-item"><kbd>R</kbd><span>Reload Weapon</span></div>
            </div>
          </div>

          <!-- Utility Actions -->
          <div class="actions-row">
            <button class="ghost-btn" title="Toggle Fullscreen Mode" @click="toggleFullscreen">
              <svg class="btn-icon-svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/>
              </svg>
              <span>Fullscreen</span>
            </button>
            <button class="ghost-btn" title="Copy Share Link" @click="handleShare">
              <svg class="btn-icon-svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M4 12v8a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2v-8m-4-6l-4-4-4 4m4-4v13"/>
              </svg>
              <span>Share Game</span>
            </button>
          </div>
        </div>
      </section>

      <!-- SEO ARTICLE & GAME GUIDE -->
      <article id="article-guide" class="seo-article">
        <header class="article-header">
          <div class="article-meta-badge">COMPREHENSIVE RETROSPECTIVE & ENGINE GUIDE</div>
          <h2 class="article-main-title">
            Half-Life: Uplink in WebAssembly — History, Gameplay Mechanics & WebGL Architecture
          </h2>
          <p class="article-lead">
            An in-depth look into Valve’s legendary 1999 standalone demo and how modern WebAssembly and Xash3D FWGS deliver the complete GoldSource experience directly inside the browser.
          </p>
        </header>

        <!-- Chapter 1: Storyline and Setting -->
        <section class="article-section">
          <h3 class="section-title">1. The Black Mesa Incident & The Story of Uplink</h3>
          <p>
            Released on February 12, 1999, <strong>Half-Life: Uplink</strong> is a standalone demo and self-contained chapter created by Valve Corporation. Unlike conventional demos that simply replay the opening chapters of the retail release, <em>Uplink</em> features distinct map layouts and scenarios originally developed and cut from the full <em>Half-Life</em> campaign.
          </p>
          <p>
            Set approximately 48 hours following the disastrous Resonance Cascade within the subterranean <strong>Black Mesa Research Facility</strong>, players assume the role of Dr. Gordon Freeman. Encased in the Mark IV Hazardous Environment Suit (HEV), Freeman must navigate compromised containment sectors, align an omnidirectional transmitter dish, and broadcast a vital distress message to the surface Lambda team.
          </p>
          <div class="callout-box">
            <div class="callout-icon">💡</div>
            <div class="callout-text">
              <strong>Narrative Placement:</strong> Chronologically situated between the main campaign chapters <em>"Forget About Freeman!"</em> and <em>"Lambda Core"</em>, Uplink tests players against intense combined encounters involving Hazardous Environment Combat Unit (HECU) Marines, Headcrabs, Houndeyes, and Vortigaunts.
            </div>
          </div>
        </section>

        <!-- Chapter 2: Technical Architecture -->
        <section class="article-section">
          <h3 class="section-title">2. WebAssembly (WASM) & WebGL 2 Engine Architecture</h3>
          <p>
            Executing a full 3D C/C++ engine inside a modern browser environment is made possible through <strong>Xash3D FWGS</strong>, an open-source GoldSource-compatible engine compiled to <strong>WebAssembly (WASM)</strong> using the Emscripten toolchain.
          </p>
          <div class="tech-grid">
            <div class="tech-card">
              <div class="tech-icon">⚡</div>
              <h4>Near-Native WASM Execution</h4>
              <p>Engine physics, entity logic, and artificial intelligence routines compile directly into optimized WebAssembly bytecode.</p>
            </div>
            <div class="tech-card">
              <div class="tech-icon">🎮</div>
              <h4>Hardware WebGL 2 Pipeline</h4>
              <p>Hardware-accelerated dynamic lightmaps, animated studio meshes, and BSP geometry rendered directly onto HTML5 Canvas.</p>
            </div>
            <div class="tech-card">
              <div class="tech-icon">💾</div>
              <h4>IndexedDB Virtual Filesystem</h4>
              <p>Game saves, custom keybinds, and console configuration files are preserved persistently in client-side storage.</p>
            </div>
            <div class="tech-card">
              <div class="tech-icon">🔊</div>
              <h4>Spatial Web Audio</h4>
              <p>Positional 3D audio cues, reverberation, and voice line streaming delivered with low latency via the Web Audio API.</p>
            </div>
          </div>
        </section>

        <!-- Chapter 3: Weapons Guide -->
        <section id="weapons-guide" class="article-section">
          <h3 class="section-title">3. Weapons Arsenal & Combat Strategy</h3>
          <p>
            Overcoming hostile forces in Black Mesa requires strategic resource management and familiarity with Dr. Freeman’s arsenal:
          </p>

          <div class="table-container">
            <table class="weapons-table">
              <thead>
                <tr>
                  <th>Weapon</th>
                  <th>Ammunition</th>
                  <th>Primary Action</th>
                  <th>Secondary Action</th>
                  <th>Tactical Role</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td class="weapon-name"><strong>Crowbar</strong></td>
                  <td>Melee</td>
                  <td>Fast blunt strike</td>
                  <td>—</td>
                  <td>Conserving ammo, breaking crates, Headcrabs</td>
                </tr>
                <tr>
                  <td class="weapon-name"><strong>Glock 17 (9mm)</strong></td>
                  <td>9x19mm Parabellum</td>
                  <td>Accurate semi-auto fire</td>
                  <td>High-speed burst fire</td>
                  <td>Distant targets, underwater engagement</td>
                </tr>
                <tr>
                  <td class="weapon-name"><strong>SPAS-12 Shotgun</strong></td>
                  <td>12 Gauge Buckshot</td>
                  <td>Single-barrel spread</td>
                  <td>Double-barrel heavy blast</td>
                  <td>Close-quarters clearing, Bullsquids, HECU</td>
                </tr>
                <tr>
                  <td class="weapon-name"><strong>MP5 Submachine Gun</strong></td>
                  <td>9mm / 40mm Grenades</td>
                  <td>Full-automatic sustained fire</td>
                  <td>M203 impact grenade launcher</td>
                  <td>Crowd control, fortified soldier squads</td>
                </tr>
                <tr>
                  <td class="weapon-name"><strong>Hand Grenade</strong></td>
                  <td>High Explosive</td>
                  <td>Timed fragmentation throw</td>
                  <td>Short roll / lob</td>
                  <td>Bunkers, blind corners, turret suppression</td>
                </tr>
              </tbody>
            </table>
          </div>
        </section>

        <!-- Chapter 4: System Requirements & Compatibility -->
        <section class="article-section">
          <h3 class="section-title">4. System Requirements & Browser Compatibility</h3>
          <p>
            WebXash Half-Life operates smoothly across modern operating systems and web browsers without third-party plugins.
          </p>
          <div class="specs-grid">
            <div class="specs-col">
              <h4 class="specs-heading">Minimum Requirements</h4>
              <ul class="specs-list">
                <li><strong>Operating System:</strong> Windows 10/11, macOS 10.15+, Linux, ChromeOS</li>
                <li><strong>Browser:</strong> Google Chrome 90+, Mozilla Firefox 88+, Microsoft Edge 90+, Apple Safari 15+</li>
                <li><strong>CPU:</strong> Dual-Core 1.8 GHz or equivalent modern processor</li>
                <li><strong>Memory:</strong> 2 GB RAM available</li>
                <li><strong>Graphics:</strong> WebGL 2.0 compatible integrated or dedicated GPU</li>
              </ul>
            </div>
            <div class="specs-col">
              <h4 class="specs-heading">Recommended Setup</h4>
              <ul class="specs-list">
                <li><strong>Display:</strong> 1080p 60Hz+ with Fullscreen enabled</li>
                <li><strong>Controls:</strong> Hardware Keyboard & Mouse with Pointer Lock</li>
                <li><strong>Audio:</strong> Stereo Headphones for spatial enemy awareness</li>
                <li><strong>Storage:</strong> Standard browser cache enabled for offline game assets</li>
              </ul>
            </div>
          </div>
        </section>
      </article>

      <!-- INTERACTIVE FAQ SECTION -->
      <section id="faq-section" class="faq-container">
        <div class="faq-header">
          <div class="section-badge">FREQUENTLY ASKED QUESTIONS</div>
          <h2 class="section-main-heading">Common Questions & Troubleshooting</h2>
          <p class="section-sub-heading">Immediate answers regarding controls, save games, performance, and browser support.</p>
          
          <!-- Category Tabs & Controls -->
          <div class="faq-toolbar">
            <div class="faq-categories">
              <button
                v-for="cat in faqCategories"
                :key="cat"
                class="faq-cat-btn"
                :class="{ 'faq-cat-btn--active': selectedFaqCategory === cat }"
                @click="selectedFaqCategory = cat"
              >
                {{ cat }}
              </button>
            </div>
            <button class="faq-expand-all-btn" @click="toggleExpandAll">
              {{ areAllFaqsOpen ? 'Collapse All' : 'Expand All' }}
            </button>
          </div>

          <!-- Search / Filter Input -->
          <div class="faq-search-wrapper">
            <input
              v-model="faqSearchQuery"
              type="text"
              class="faq-search-input"
              placeholder="Search FAQ questions (e.g., saves, controls, fps, audio)..."
            />
          </div>
        </div>

        <div class="faq-list">
          <div
            v-for="(item, index) in filteredFaqs"
            :key="index"
            class="faq-card"
            :class="{ 'faq-card--open': openFaqMap[item.id] }"
            @click="toggleFaq(item.id)"
          >
            <div class="faq-question-row">
              <div class="faq-q-title-group">
                <span class="faq-cat-tag">{{ item.category }}</span>
                <h3 class="faq-question">{{ item.q }}</h3>
              </div>
              <div class="faq-toggle-icon">{{ openFaqMap[item.id] ? '−' : '+' }}</div>
            </div>
            <div v-show="openFaqMap[item.id]" class="faq-answer-row">
              <p>{{ item.a }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- DISQUS COMMENTS & COMMUNITY SECTION -->
      <section id="community-comments" class="comments-section">
        <div class="comments-header">
          <div class="section-badge">COMMUNITY DISCUSSION</div>
          <h2 class="section-main-heading">Player Comments & Feedback</h2>
          <p class="section-sub-heading">
            Share speedrun strategies, combat tactics, and feedback with fellow Black Mesa researchers.
          </p>
        </div>

        <!-- Disqus Integration Box -->
        <div class="disqus-wrapper">
          <div class="disqus-controls-bar">
            <div class="disqus-config-group">
              <label for="disqus-shortname" class="disqus-label">Disqus Shortname:</label>
              <input
                id="disqus-shortname"
                v-model="disqusShortname"
                type="text"
                class="disqus-input"
                placeholder="e.g. webxash-community"
              />
              <button class="disqus-load-btn" @click="initDisqus">
                <span>Connect / Reload Disqus</span>
              </button>
            </div>
            <span class="disqus-status-pill" :class="{ 'connected': disqusLoaded }">
              {{ disqusLoaded ? 'Disqus Active' : 'Ready to Connect' }}
            </span>
          </div>

          <!-- Official Disqus Thread Mount Point -->
          <div id="disqus_thread" class="disqus-thread-container">
            <div v-if="!disqusLoaded" class="disqus-placeholder">
              <div class="disqus-placeholder-icon">💬</div>
              <h4>Disqus Community Board</h4>
              <p>Click "Connect / Reload Disqus" above to initialize threaded comments.</p>
              <button class="primary-launch-btn-small" @click="initDisqus">
                <span>CONNECT DISQUS FORUM</span>
              </button>
            </div>
          </div>

          <!-- Instant Feedback Fallback -->
          <div class="local-comments-block">
            <h4 class="local-comments-title">Instant Community Feed</h4>
            <div class="comment-input-row">
              <input
                v-model="newCommentAuthor"
                type="text"
                class="comment-name-input"
                placeholder="Your Name (e.g. Gordon Freeman)"
              />
              <input
                v-model="newCommentText"
                type="text"
                class="comment-text-input"
                placeholder="Share a tip or comment..."
                @keyup.enter="postLocalComment"
              />
              <button class="comment-post-btn" @click="postLocalComment">
                <span>Post</span>
              </button>
            </div>

            <!-- List of Community Messages -->
            <div class="comments-stream">
              <div v-for="(comment, cIndex) in communityComments" :key="cIndex" class="comment-bubble">
                <div class="comment-meta">
                  <span class="comment-author">{{ comment.author }}</span>
                  <span class="comment-time">{{ comment.time }}</span>
                </div>
                <p class="comment-body">{{ comment.text }}</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- FOOTER -->
      <footer class="page-footer">
        <div class="footer-content">
          <div class="footer-brand">
            <span class="footer-lambda">λ</span>
            <span>WEBXASH // GOLDSURCE WASM ENGINE</span>
          </div>
          <p class="footer-disclaimer">
            Half-Life is a registered trademark of Valve Corporation. This project is a community-driven WebAssembly port powered by the open-source Xash3D FWGS engine.
          </p>
          <div class="footer-links">
            <a href="#game-launcher">Play Game</a>
            <span>•</span>
            <a href="#article-guide">Game Lore</a>
            <span>•</span>
            <a href="#faq-section">FAQ</a>
            <span>•</span>
            <a href="#community-comments">Disqus Comments</a>
          </div>
        </div>
      </footer>
    </main>

    <!-- Active Loading Overlay (Game Engine Initializing) -->
    <XashLoading v-if="loading" />

    <!-- Toast Notification -->
    <transition name="simple-toast">
      <div v-if="toastMessage" class="simple-toast">
        {{ toastMessage }}
      </div>
    </transition>
  </div>
</template>

<script setup lang="ts">
  import { ref, computed, onMounted, onUnmounted } from 'vue';
  import { storeToRefs } from 'pinia';
  import { useXashStore } from '/@/stores/store';
  import { XashLoader } from '/@/services';
  import XashLoading from '/@/components/XashLoading.vue';
  import setCanvasLoading from '/@/utils/setCanvasLoading';

  const store = useXashStore();
  const {
    loading,
    loadingProgress,
    maxLoadingAmount,
    selectedGame,
    selectedZip,
    selectedLocalFolder,
    xashCanvas,
    launchOptions,
    fullScreen,
    enableConsole,
    enableCheats,
    fpsLimit,
    touchControls,
    toastMessage,
    customGameArg,
  } = storeToRefs(store);

  const { onStartLoading, onEndLoading, refreshSavesList } = store;

  // Background Particle System
  const particleCanvas = ref<HTMLCanvasElement | null>(null);
  let animationFrameId: number | null = null;
  let resizeHandler: (() => void) | null = null;

  interface Particle {
    x: number;
    y: number;
    vx: number;
    vy: number;
    size: number;
    baseAlpha: number;
    alpha: number;
    pulseSpeed: number;
    pulseOffset: number;
    color: string;
  }

  // FAQ State
  const faqCategories = ['All', 'Getting Started', 'Controls', 'Saves & Tech', 'Performance'];
  const selectedFaqCategory = ref('All');
  const faqSearchQuery = ref('');
  const openFaqMap = ref<Record<string, boolean>>({
    'start-1': true,
    'ctrl-1': true,
    'save-1': true,
    'compat-1': true,
  });

  const faqData = [
    {
      id: 'start-1',
      category: 'Getting Started',
      q: 'How do I play Half-Life: Uplink directly in my web browser?',
      a: 'Simply click the "START GAME" button at the top of the page. The WebAssembly engine files and Half-Life: Uplink game archive will be downloaded and decompressed directly into your browser’s virtual memory. No installations, plugins, or software downloads are required.',
    },
    {
      id: 'ctrl-1',
      category: 'Controls',
      q: 'Does it support full mouse-look and keyboard controls?',
      a: 'Yes! The game features full Pointer Lock support. Once the game boots, clicking inside the window captures your mouse for 360-degree free-look. You can use standard WASD movement, Space to jump, Ctrl to crouch, E to interact, and R to reload.',
    },
    {
      id: 'save-1',
      category: 'Saves & Tech',
      q: 'Are my save games and configurations preserved between sessions?',
      a: 'Yes. Save games created via the in-game menu or quicksave (F6) and your custom binds in config.cfg are persisted in your browser’s IndexedDB storage. As long as you do not clear your browser data, your progress will remain intact.',
    },
    {
      id: 'compat-1',
      category: 'Getting Started',
      q: 'Which web browsers and platforms are supported?',
      a: 'Any modern browser with WebGL 2.0 and WebAssembly capabilities is fully supported, including Google Chrome, Mozilla Firefox, Microsoft Edge, Apple Safari, Opera, and Brave on Windows, macOS, Linux, and ChromeOS.',
    },
    {
      id: 'lore-1',
      category: 'Getting Started',
      q: 'What is the difference between Half-Life and Half-Life: Uplink?',
      a: 'Half-Life: Uplink was a standalone demo chapter released by Valve in February 1999. It showcases distinct, original levels cut from the main game during production, presenting a standalone scenario where Gordon Freeman must transmit a critical distress signal.',
    },
    {
      id: 'ctrl-2',
      category: 'Controls',
      q: 'How do I enable cheats or developer console?',
      a: 'The engine features full GoldSource console access. You can open the developer console using the Tilde key (~) and enter commands such as "god", "noclip", "give item_healthkit", or "fps_max 144".',
    },
    {
      id: 'perf-1',
      category: 'Performance',
      q: 'Why does the engine perform so smoothly in the browser?',
      a: 'WebXash is powered by Xash3D FWGS, a specialized recreation of the GoldSource engine compiled to WebAssembly. By compiling C code directly into high-performance WASM bytecode with direct WebGL 2 shader bindings, it runs at 60+ FPS with hardware GPU acceleration.',
    },
    {
      id: 'save-2',
      category: 'Saves & Tech',
      q: 'Can I import my own custom GoldSource maps or mods?',
      a: 'Yes! The engine supports mounting custom .bsp maps and GoldSource PAK/ZIP files through WebAssembly file system wrappers.',
    },
  ];

  const filteredFaqs = computed(() => {
    let list = faqData;
    if (selectedFaqCategory.value !== 'All') {
      list = list.filter((item) => item.category === selectedFaqCategory.value);
    }
    if (faqSearchQuery.value.trim()) {
      const query = faqSearchQuery.value.toLowerCase();
      list = list.filter(
        (item) => item.q.toLowerCase().includes(query) || item.a.toLowerCase().includes(query)
      );
    }
    return list;
  });

  const areAllFaqsOpen = computed(() => {
    return filteredFaqs.value.every((item) => openFaqMap.value[item.id]);
  });

  const toggleFaq = (id: string) => {
    openFaqMap.value[id] = !openFaqMap.value[id];
  };

  const toggleExpandAll = () => {
    const shouldOpen = !areAllFaqsOpen.value;
    filteredFaqs.value.forEach((item) => {
      openFaqMap.value[item.id] = shouldOpen;
    });
  };

  // Disqus Integration State
  const disqusShortname = ref('webxash-community');
  const disqusLoaded = ref(false);

  const initDisqus = () => {
    const shortname = disqusShortname.value.trim() || 'webxash-community';
    const container = document.getElementById('disqus_thread');
    if (!container) return;

    const existingScript = document.getElementById('dsq-embed-scr');
    if (existingScript) {
      existingScript.remove();
    }

    (window as any).disqus_config = function (this: any) {
      this.page.url = window.location.href;
      this.page.identifier = 'webxash-halflife-uplink';
      this.page.title = 'Half-Life: Uplink WebAssembly Browser Port';
    };

    const d = document;
    const s = d.createElement('script');
    s.id = 'dsq-embed-scr';
    s.src = `https://${shortname}.disqus.com/embed.js`;
    s.setAttribute('data-timestamp', String(+new Date()));
    (d.head || d.body).appendChild(s);

    disqusLoaded.value = true;
    showToast(`CONNECTING DISQUS: ${shortname.toUpperCase()}`);
  };

  // Local Community Messages
  const newCommentAuthor = ref('');
  const newCommentText = ref('');
  const communityComments = ref([
    {
      author: 'Gordon F.',
      time: 'Just now',
      text: 'The SPAS-12 double blast against Bullsquids is essential in the communications courtyard!',
    },
    {
      author: 'Barney Calhoun',
      time: '12 minutes ago',
      text: 'Runs at solid 60 FPS on my laptop. Remember to grab the Glock ammunition in the side lab.',
    },
    {
      author: 'Dr. Kleiner',
      time: '1 hour ago',
      text: 'Superb WebAssembly compilation. The WebGL 2 shader pipeline captures the original GoldSource atmosphere accurately.',
    },
  ]);

  const postLocalComment = () => {
    if (!newCommentText.value.trim()) return;
    const author = newCommentAuthor.value.trim() || 'Anonymous Researcher';
    communityComments.value.unshift({
      author,
      time: 'Just now',
      text: newCommentText.value.trim(),
    });
    newCommentText.value = '';
    showToast('COMMENT POSTED');
  };

  let toastTimer: number | null = null;
  const showToast = (message: string) => {
    toastMessage.value = message;
    if (toastTimer) clearTimeout(toastTimer);
    toastTimer = window.setTimeout(() => {
      toastMessage.value = '';
    }, 2800);
  };

  const handleShare = () => {
    navigator.clipboard.writeText(window.location.href).then(() => {
      showToast('SHARE URL COPIED TO CLIPBOARD');
    }).catch(() => {
      showToast('FAILED TO COPY LINK');
    });
  };

  const toggleFullscreen = () => {
    if (!document.fullscreenElement) {
      document.documentElement.requestFullscreen().catch(() => {
        showToast('FULLSCREEN NOT SUPPORTED');
      });
    } else {
      document.exitFullscreen().catch(() => {});
    }
  };

  const startUplink = async () => {
    const canvas = xashCanvas.value || (document.getElementById('canvas') as HTMLCanvasElement);
    if (!canvas) {
      showToast('ERROR: ENGINE CANVAS NOT FOUND');
      return;
    }
    xashCanvas.value = canvas;

    setCanvasLoading();
    selectedZip.value = 'uplink.zip';
    onStartLoading();
    maxLoadingAmount.value = 100;
    loadingProgress.value = 5;

    try {
      const zip = await XashLoader.downloadZip(
        'uplink.zip',
        selectedGame.value.publicDir,
        (progress: number) => {
          loadingProgress.value = Math.max(5, Math.min(95, progress));
        },
      );

      if (!zip) {
        loading.value = false;
        showToast('FAILED TO RETRIEVE ASSETS');
        return;
      }

      loadingProgress.value = 96;

      const xash = await XashLoader.startGameZip(zip, {
        canvas,
        selectedGame: selectedGame.value,
        selectedZip: 'uplink.zip',
        selectedLocalFolder: selectedLocalFolder.value,
        launchOptions: launchOptions.value,
        fullScreen: fullScreen.value,
        enableConsole: enableConsole.value,
        enableCheats: enableCheats.value,
        fpsLimit: fpsLimit.value,
        touchControls: touchControls.value,
        onStartLoading,
        onEndLoading,
        onProgress: (progress) => {
          if (typeof progress === 'number') {
            loadingProgress.value = progress;
          } else if (progress && typeof progress.current === 'number') {
            loadingProgress.value = progress.current;
          }
        },
      });

      loadingProgress.value = 100;

      await XashLoader.onAfterLoad({
        xash,
        selectedGame: selectedGame.value,
        customGameArg: customGameArg.value,
        enableCheats: enableCheats.value,
      });

      XashLoader.initConsoleCallbacks(
        xash,
        selectedGame.value.consoleCallbacks,
      ).catch((err) => console.warn('Console callback listener error:', err));

      await refreshSavesList();

      setTimeout(() => {
        canvas.focus();
      }, 100);
    } catch (error: any) {
      console.error('Failed to start Half-Life Uplink:', error);
      loading.value = false;
      showToast(`ERROR: ${error?.message || 'FAILED TO LAUNCH ENGINE'}`);
    }
  };

  onMounted(() => {
    const canvas = particleCanvas.value;
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    if (!ctx) return;

    let width = (canvas.width = window.innerWidth);
    let height = (canvas.height = window.innerHeight);

    const colors = [
      'rgba(245, 158, 11,',
      'rgba(251, 191, 36,',
      'rgba(217, 119, 6,',
      'rgba(56, 189, 248,',
    ];

    const particleCount = Math.min(Math.floor((width * height) / 18000), 45);
    const particles: Particle[] = [];

    for (let i = 0; i < particleCount; i++) {
      particles.push({
        x: Math.random() * width,
        y: Math.random() * height,
        vx: (Math.random() - 0.5) * 0.3,
        vy: (Math.random() - 0.5) * 0.3 - 0.08,
        size: Math.random() * 1.8 + 0.8,
        baseAlpha: Math.random() * 0.3 + 0.15,
        alpha: 0.2,
        pulseSpeed: Math.random() * 0.02 + 0.008,
        pulseOffset: Math.random() * Math.PI * 2,
        color: colors[Math.floor(Math.random() * colors.length)],
      });
    }

    resizeHandler = () => {
      width = canvas.width = window.innerWidth;
      height = canvas.height = window.innerHeight;
    };
    window.addEventListener('resize', resizeHandler);

    let time = 0;
    const animate = () => {
      time += 0.02;
      ctx.clearRect(0, 0, width, height);

      for (let i = 0; i < particles.length; i++) {
        const p = particles[i];
        p.x += p.vx;
        p.y += p.vy;

        if (p.x < 0) p.x = width;
        if (p.x > width) p.x = 0;
        if (p.y < 0) p.y = height;
        if (p.y > height) p.y = 0;

        const pulse = Math.sin(time * 1.5 + p.pulseOffset);
        p.alpha = Math.max(0.05, p.baseAlpha + pulse * 0.1);

        ctx.fillStyle = `${p.color} ${p.alpha})`;
        ctx.beginPath();
        ctx.arc(p.x, p.y, p.size, 0, Math.PI * 2);
        ctx.fill();
      }

      animationFrameId = requestAnimationFrame(animate);
    };

    animate();
  });

  onUnmounted(() => {
    if (animationFrameId) cancelAnimationFrame(animationFrameId);
    if (resizeHandler) window.removeEventListener('resize', resizeHandler);
    if (toastTimer) clearTimeout(toastTimer);
  });
</script>

<style scoped>
  /* Root Container */
  .page-container {
    position: relative;
    width: 100%;
    min-height: 100vh;
    background: #0a0e17;
    color: #f3f4f6;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    overflow-x: hidden;
  }

  /* Ambient Particle Canvas */
  .particles-canvas {
    position: fixed;
    inset: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 1;
    opacity: 0.5;
  }

  /* TOP STICKY NAVIGATION BAR */
  .top-nav {
    position: sticky;
    top: 0;
    z-index: 40;
    background: rgba(10, 14, 23, 0.88);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  }

  .nav-inner {
    max-width: 1120px;
    margin: 0 auto;
    padding: 10px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 16px;
  }

  .nav-brand {
    display: flex;
    align-items: center;
    gap: 10px;
    text-decoration: none;
    color: inherit;
    flex-shrink: 0;
  }

  .nav-lambda-glyph {
    width: 32px;
    height: 32px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #111827;
    border: 1px solid #f59e0b;
    border-radius: 6px;
    color: #f59e0b;
    font-family: Georgia, serif;
    font-weight: 900;
    font-size: 19px;
    line-height: 1;
  }

  .nav-brand-text {
    display: flex;
    flex-direction: column;
  }

  .nav-title {
    font-size: 13px;
    font-weight: 800;
    letter-spacing: 0.05em;
    color: #ffffff;
  }

  .nav-tag {
    font-size: 9.5px;
    font-weight: 700;
    letter-spacing: 0.08em;
    color: #f59e0b;
  }

  .nav-links {
    display: flex;
    align-items: center;
    gap: 6px;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.06);
    padding: 3px 6px;
    border-radius: 8px;
  }

  .nav-link {
    font-size: 13px;
    font-weight: 600;
    color: #9ca3af;
    text-decoration: none;
    padding: 6px 12px;
    border-radius: 6px;
    transition: all 0.15s ease;
  }

  .nav-link:hover {
    color: #ffffff;
    background: rgba(255, 255, 255, 0.06);
  }

  .nav-actions {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .nav-icon-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 7px 12px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 6px;
    color: #d1d5db;
    font-size: 12.5px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .nav-icon-btn:hover {
    background: rgba(255, 255, 255, 0.08);
    border-color: rgba(255, 255, 255, 0.2);
    color: #ffffff;
  }

  .nav-svg-icon {
    width: 15px;
    height: 15px;
  }

  .nav-launch-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 16px;
    background: #f59e0b;
    color: #0f172a;
    border: none;
    border-radius: 6px;
    font-size: 12.5px;
    font-weight: 800;
    letter-spacing: 0.03em;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .nav-launch-btn:hover {
    background: #fbbf24;
    transform: translateY(-1px);
  }

  .nav-play-icon {
    width: 14px;
    height: 14px;
  }

  /* Content Wrapper */
  .content-wrapper {
    position: relative;
    z-index: 2;
    max-width: 980px;
    margin: 0 auto;
    padding: 40px 20px 80px;
    display: flex;
    flex-direction: column;
    gap: 56px;
  }

  /* HERO / LAUNCHER SECTION */
  .hero-section {
    display: flex;
    justify-content: center;
  }

  .launch-card {
    width: 100%;
    max-width: 580px;
    background: rgba(17, 24, 39, 0.85);
    backdrop-filter: blur(16px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 12px;
    padding: 32px 28px;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .card-header {
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .lambda-badge {
    width: 52px;
    height: 52px;
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #111827;
    border: 1.5px solid #f59e0b;
    border-radius: 10px;
  }

  .lambda-char {
    font-size: 32px;
    font-weight: 900;
    color: #f59e0b;
    font-family: Georgia, serif;
    line-height: 1;
  }

  .header-text {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .status-indicator {
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .status-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #10b981;
    box-shadow: 0 0 6px #10b981;
  }

  .status-text {
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 0.08em;
    color: #10b981;
  }

  .game-title {
    margin: 0;
    font-size: 22px;
    font-weight: 800;
    letter-spacing: 0.02em;
    color: #ffffff;
  }

  .game-subtitle {
    margin: 0;
    font-size: 13px;
    color: #9ca3af;
  }

  .tags-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag-pill {
    font-size: 11px;
    font-weight: 600;
    padding: 4px 10px;
    border-radius: 6px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.08);
    color: #d1d5db;
  }

  .primary-launch-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    width: 100%;
    padding: 15px 24px;
    background: #f59e0b;
    color: #0f172a;
    border: none;
    border-radius: 8px;
    font-size: 15px;
    font-weight: 800;
    letter-spacing: 0.04em;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .primary-launch-btn:hover {
    background: #fbbf24;
    transform: translateY(-1px);
  }

  .primary-launch-btn-small {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    padding: 10px 18px;
    background: #f59e0b;
    color: #0f172a;
    border: none;
    border-radius: 6px;
    font-size: 12.5px;
    font-weight: 800;
    cursor: pointer;
    margin-top: 14px;
    transition: all 0.15s ease;
  }

  .primary-launch-btn-small:hover {
    background: #fbbf24;
  }

  .play-icon {
    width: 18px;
    height: 18px;
  }

  .controls-box {
    background: rgba(0, 0, 0, 0.35);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 8px;
    padding: 16px;
  }

  .controls-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 12px;
  }

  .controls-title {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.08em;
    color: #9ca3af;
  }

  .controls-hint {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.06em;
    color: #6b7280;
  }

  .controls-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px 16px;
  }

  .control-item {
    display: flex;
    align-items: center;
    gap: 6px;
    font-size: 12px;
    color: #d1d5db;
  }

  kbd {
    background: #1f2937;
    border: 1px solid #374151;
    border-radius: 4px;
    padding: 2px 6px;
    font-size: 11px;
    font-family: ui-monospace, monospace;
    font-weight: 700;
    color: #fbbf24;
  }

  .actions-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .ghost-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    padding: 9px 16px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 6px;
    color: #9ca3af;
    font-size: 12.5px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .ghost-btn:hover {
    background: rgba(255, 255, 255, 0.08);
    border-color: rgba(255, 255, 255, 0.15);
    color: #ffffff;
  }

  .btn-icon-svg {
    width: 15px;
    height: 15px;
  }

  /* Section Scroll Margins */
  #game-launcher,
  #article-guide,
  #weapons-guide,
  #faq-section,
  #community-comments {
    scroll-margin-top: 72px;
  }

  /* SEO ARTICLE SECTION */
  .seo-article {
    background: rgba(17, 24, 39, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    padding: 36px 32px;
    line-height: 1.65;
    color: #d1d5db;
  }

  .article-header {
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    padding-bottom: 24px;
    margin-bottom: 28px;
  }

  .article-meta-badge {
    display: inline-block;
    font-size: 10.5px;
    font-weight: 800;
    color: #f59e0b;
    letter-spacing: 0.1em;
    margin-bottom: 10px;
  }

  .article-main-title {
    font-size: 26px;
    font-weight: 800;
    color: #ffffff;
    line-height: 1.3;
    margin: 0 0 14px 0;
  }

  .article-lead {
    font-size: 15px;
    color: #9ca3af;
    margin: 0;
  }

  .article-section {
    margin-bottom: 36px;
  }

  .section-title {
    font-size: 19px;
    font-weight: 700;
    color: #f3f4f6;
    margin: 0 0 14px 0;
  }

  .callout-box {
    display: flex;
    gap: 14px;
    background: rgba(245, 158, 11, 0.06);
    border: 1px solid rgba(245, 158, 11, 0.2);
    border-left: 3px solid #f59e0b;
    border-radius: 6px;
    padding: 16px;
    margin: 18px 0;
  }

  .callout-icon {
    font-size: 18px;
    flex-shrink: 0;
  }

  .callout-text {
    font-size: 13.5px;
    color: #e5e7eb;
  }

  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 14px;
    margin-top: 18px;
  }

  .tech-card {
    background: rgba(0, 0, 0, 0.3);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 8px;
    padding: 18px 16px;
  }

  .tech-icon {
    font-size: 22px;
    margin-bottom: 6px;
  }

  .tech-card h4 {
    margin: 0 0 6px 0;
    font-size: 14px;
    color: #ffffff;
    font-weight: 700;
  }

  .tech-card p {
    margin: 0;
    font-size: 12.5px;
    color: #9ca3af;
    line-height: 1.5;
  }

  /* Weapons Table */
  .table-container {
    overflow-x: auto;
    margin: 18px 0;
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 8px;
  }

  .weapons-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
    text-align: left;
  }

  .weapons-table th {
    background: #1f2937;
    color: #f59e0b;
    padding: 11px 14px;
    font-weight: 700;
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  }

  .weapons-table td {
    padding: 11px 14px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.04);
  }

  .weapons-table tr:hover {
    background: rgba(255, 255, 255, 0.02);
  }

  .weapon-name {
    color: #ffffff;
  }

  /* Specs Grid */
  .specs-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 14px;
  }

  .specs-col {
    background: rgba(0, 0, 0, 0.3);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 8px;
    padding: 18px;
  }

  .specs-heading {
    margin: 0 0 12px 0;
    font-size: 14px;
    color: #f59e0b;
    font-weight: 700;
  }

  .specs-list {
    margin: 0;
    padding-left: 18px;
    font-size: 13px;
    color: #d1d5db;
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  /* FAQ SECTION */
  .faq-container {
    background: rgba(17, 24, 39, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    padding: 36px 32px;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .faq-toolbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 14px;
  }

  .faq-categories {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 6px;
  }

  .faq-cat-btn {
    padding: 5px 12px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 6px;
    color: #9ca3af;
    font-size: 12px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .faq-cat-btn:hover {
    background: rgba(255, 255, 255, 0.08);
    color: #ffffff;
  }

  .faq-cat-btn--active {
    background: #f59e0b;
    border-color: #f59e0b;
    color: #0f172a;
    font-weight: 700;
  }

  .faq-expand-all-btn {
    padding: 5px 12px;
    background: transparent;
    border: 1px solid rgba(245, 158, 11, 0.3);
    border-radius: 6px;
    color: #f59e0b;
    font-size: 12px;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .faq-expand-all-btn:hover {
    background: rgba(245, 158, 11, 0.08);
  }

  .faq-q-title-group {
    display: flex;
    align-items: center;
    gap: 8px;
    flex-wrap: wrap;
  }

  .faq-cat-tag {
    font-size: 9.5px;
    font-weight: 700;
    text-transform: uppercase;
    padding: 2px 6px;
    background: rgba(245, 158, 11, 0.12);
    border: 1px solid rgba(245, 158, 11, 0.25);
    color: #f59e0b;
    border-radius: 4px;
    letter-spacing: 0.04em;
  }

  .section-badge {
    font-size: 10.5px;
    font-weight: 800;
    color: #f59e0b;
    letter-spacing: 0.1em;
    margin-bottom: 6px;
  }

  .section-main-heading {
    font-size: 22px;
    font-weight: 800;
    color: #ffffff;
    margin: 0 0 6px 0;
  }

  .section-sub-heading {
    font-size: 13.5px;
    color: #9ca3af;
    margin: 0 0 16px 0;
  }

  .faq-search-input {
    width: 100%;
    padding: 11px 16px;
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 8px;
    color: #ffffff;
    font-size: 13.5px;
    outline: none;
    transition: border-color 0.15s ease;
  }

  .faq-search-input:focus {
    border-color: #f59e0b;
  }

  .faq-list {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .faq-card {
    background: rgba(17, 24, 39, 0.7);
    border: 1px solid rgba(255, 255, 255, 0.06);
    border-radius: 8px;
    padding: 16px 18px;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .faq-card:hover {
    border-color: rgba(245, 158, 11, 0.25);
  }

  .faq-card--open {
    border-color: #f59e0b;
    background: rgba(17, 24, 39, 0.95);
  }

  .faq-question-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
  }

  .faq-question {
    margin: 0;
    font-size: 14.5px;
    font-weight: 700;
    color: #ffffff;
  }

  .faq-toggle-icon {
    font-size: 18px;
    font-weight: 700;
    color: #f59e0b;
  }

  .faq-answer-row {
    margin-top: 10px;
    padding-top: 10px;
    border-top: 1px solid rgba(255, 255, 255, 0.05);
    font-size: 13.5px;
    color: #9ca3af;
    line-height: 1.55;
  }

  .faq-answer-row p {
    margin: 0;
  }

  /* COMMENTS / DISQUS SECTION */
  .comments-section {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .disqus-wrapper {
    background: rgba(17, 24, 39, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 12px;
    padding: 28px;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .disqus-controls-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    padding-bottom: 16px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.06);
  }

  .disqus-config-group {
    display: flex;
    align-items: center;
    gap: 8px;
    flex-wrap: wrap;
  }

  .disqus-label {
    font-size: 12.5px;
    font-weight: 600;
    color: #d1d5db;
  }

  .disqus-input {
    padding: 7px 12px;
    background: #0f172a;
    border: 1px solid #374151;
    border-radius: 6px;
    color: #ffffff;
    font-size: 12.5px;
  }

  .disqus-load-btn {
    padding: 7px 14px;
    background: #374151;
    color: #ffffff;
    border: 1px solid #4b5563;
    border-radius: 6px;
    font-size: 12.5px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.15s ease;
  }

  .disqus-load-btn:hover {
    background: #4b5563;
  }

  .disqus-status-pill {
    font-size: 11px;
    font-weight: 700;
    padding: 4px 8px;
    border-radius: 6px;
    background: #1f2937;
    color: #9ca3af;
  }

  .disqus-status-pill.connected {
    background: rgba(16, 185, 129, 0.15);
    color: #10b981;
    border: 1px solid rgba(16, 185, 129, 0.3);
  }

  .disqus-placeholder {
    text-align: center;
    padding: 32px 20px;
    background: rgba(0, 0, 0, 0.2);
    border: 1px dashed rgba(255, 255, 255, 0.12);
    border-radius: 8px;
  }

  .disqus-placeholder-icon {
    font-size: 28px;
    margin-bottom: 6px;
  }

  .disqus-placeholder h4 {
    margin: 0 0 6px 0;
    font-size: 15px;
    color: #ffffff;
  }

  .disqus-placeholder p {
    margin: 0;
    font-size: 13px;
    color: #9ca3af;
  }

  /* Local Comments Feed */
  .local-comments-block {
    background: rgba(0, 0, 0, 0.25);
    border-radius: 8px;
    padding: 18px;
  }

  .local-comments-title {
    margin: 0 0 12px 0;
    font-size: 13px;
    font-weight: 700;
    color: #f59e0b;
    letter-spacing: 0.04em;
  }

  .comment-input-row {
    display: flex;
    gap: 8px;
    margin-bottom: 16px;
    flex-wrap: wrap;
  }

  .comment-name-input {
    width: 180px;
    padding: 9px 12px;
    background: #111827;
    border: 1px solid #374151;
    border-radius: 6px;
    color: #ffffff;
    font-size: 12.5px;
  }

  .comment-text-input {
    flex: 1;
    min-width: 220px;
    padding: 9px 12px;
    background: #111827;
    border: 1px solid #374151;
    border-radius: 6px;
    color: #ffffff;
    font-size: 12.5px;
  }

  .comment-post-btn {
    padding: 9px 18px;
    background: #f59e0b;
    color: #0f172a;
    border: none;
    border-radius: 6px;
    font-size: 12.5px;
    font-weight: 700;
    cursor: pointer;
  }

  .comment-post-btn:hover {
    background: #fbbf24;
  }

  .comments-stream {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .comment-bubble {
    background: #111827;
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 6px;
    padding: 10px 14px;
  }

  .comment-meta {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 3px;
  }

  .comment-author {
    font-size: 12.5px;
    font-weight: 700;
    color: #ffffff;
  }

  .comment-time {
    font-size: 11px;
    color: #6b7280;
  }

  .comment-body {
    margin: 0;
    font-size: 13px;
    color: #d1d5db;
    line-height: 1.45;
  }

  /* FOOTER */
  .page-footer {
    border-top: 1px solid rgba(255, 255, 255, 0.08);
    padding-top: 28px;
    text-align: center;
  }

  .footer-brand {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    font-size: 12.5px;
    font-weight: 800;
    color: #f59e0b;
    margin-bottom: 10px;
  }

  .footer-lambda {
    font-size: 16px;
    font-family: Georgia, serif;
  }

  .footer-disclaimer {
    font-size: 11.5px;
    color: #6b7280;
    max-width: 640px;
    margin: 0 auto 14px;
    line-height: 1.55;
  }

  .footer-links {
    display: flex;
    justify-content: center;
    gap: 10px;
    font-size: 12px;
    color: #9ca3af;
  }

  .footer-links a {
    color: #9ca3af;
    text-decoration: none;
  }

  .footer-links a:hover {
    color: #f59e0b;
  }

  /* TOAST NOTIFICATION */
  .simple-toast {
    position: fixed;
    bottom: 24px;
    left: 50%;
    transform: translateX(-50%);
    background: #1f2937;
    border: 1px solid #f59e0b;
    color: #ffffff;
    padding: 9px 18px;
    border-radius: 6px;
    font-size: 12.5px;
    font-weight: 700;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.7);
    z-index: 999;
  }

  .simple-toast-enter-active,
  .simple-toast-leave-active {
    transition: all 0.2s ease;
  }

  .simple-toast-enter-from,
  .simple-toast-leave-to {
    opacity: 0;
    transform: translate(-50%, 10px);
  }

  /* RESPONSIVE DESIGN */
  @media (max-width: 768px) {
    .nav-links {
      display: none;
    }

    .btn-text-desktop {
      display: none;
    }

    .seo-article {
      padding: 24px 18px;
    }

    .specs-grid {
      grid-template-columns: 1fr;
    }

    .controls-grid {
      grid-template-columns: 1fr;
    }
  }
</style>
