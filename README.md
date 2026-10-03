```html
<!DOCTYPE html>
<html lang="am" dir="ltr" class="scroll-smooth">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LeSew Initiative | @wederjojo | ሰው መሆን ይቀድማል</title>

<!-- Fonts & Tailwind CSS -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Ethiopic:wght@300;400;600;700;900&family=Plus+Jakarta+Sans:wght@300;400;600;700;800&family=Tajawal:wght@400;700;900&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          brand: {
            deep: '#0B1120',
            navy: '#1E293B',
            gold: '#F59E0B',
            amber: '#D97706',
            emerald: '#10B981',
            sky: '#0284C7',
            rose: '#F43F5E'
          }
        },
        fontFamily: {
          amharic: ['Noto Sans Ethiopic', 'sans-serif'],
          english: ['Plus Jakarta Sans', 'sans-serif'],
          arabic: ['Tajawal', 'sans-serif']
        }
      }
    }
  }
</script>

<style>
  body {
    background-color: #0b1120;
    color: #f8fafc;
    font-family: 'Noto Sans Ethiopic', 'Plus Jakarta Sans', 'Tajawal', sans-serif;
  }

  .glass-card {
    background: rgba(30, 41, 59, 0.7);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border: 1px solid rgba(255, 255, 255, 0.1);
  }

  .glass-card-gold {
    background: rgba(245, 158, 11, 0.08);
    backdrop-filter: blur(16px);
    border: 1px solid rgba(245, 158, 11, 0.25);
  }

  .gold-gradient-text {
    background: linear-gradient(135deg, #FDE047 0%, #F59E0B 50%, #D97706 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .habesha-tilet-frame {
    background: linear-gradient(135deg, #10B981 0%, #F59E0B 25%, #EF4444 50%, #F59E0B 75%, #10B981 100%);
    box-shadow: 0 0 30px rgba(245, 158, 11, 0.4);
  }

  .animate-float {
    animation: float 5s ease-in-out infinite;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
  }

  /* Custom Scrollbar */
  ::-webkit-scrollbar { width: 8px; }
  ::-webkit-scrollbar-track { background: #0b1120; }
  ::-webkit-scrollbar-thumb { background: #334155; border-radius: 4px; }
  ::-webkit-scrollbar-thumb:hover { background: #F59E0B; }

  /* Print Styles for CV Output */
  @media print {
    body * {
      visibility: hidden;
    }
    #printableArea, #printableArea * {
      visibility: visible;
    }
    #printableArea {
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      background: #ffffff !important;
      color: #0f172a !important;
      padding: 20px;
    }
    .no-print {
      display: none !important;
    }
  }
</style>
</head>
<body class="min-h-screen relative overflow-x-hidden selection:bg-amber-500 selection:text-slate-950">

<!-- Navigation -->
<header class="sticky top-0 z-50 glass-card border-b border-white/10 bg-slate-950/85 backdrop-blur-md">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 py-4 flex items-center justify-between">
    <!-- Brand Identity -->
    <a href="#hero" class="flex items-center gap-3 group">
      <div class="w-10 h-10 rounded-xl habesha-tilet-frame p-0.5 flex items-center justify-center font-black text-slate-950 text-xl shadow-lg shadow-amber-500/20 group-hover:scale-105 transition-transform">
        <div class="w-full h-full rounded-[10px] bg-slate-950 flex items-center justify-center text-amber-400 font-extrabold text-lg">
          ለ
        </div>
      </div>
      <div>
        <div class="font-black text-lg text-white leading-none tracking-wide" id="brand-name">LeSew Initiative</div>
        <div class="text-[10px] text-amber-400 font-bold tracking-wider mt-0.5" id="brand-handle">Eyerusalem Hailu (Jerry) • @wederjojo</div>
      </div>
    </a>

    <!-- Desktop Navigation -->
    <nav class="hidden lg:flex items-center gap-6 text-sm font-medium text-slate-300">
      <a href="#about" class="hover:text-amber-400 transition-colors" id="nav-about">ስለ እኛ</a>
      <a href="#lesew-bridge" class="hover:text-amber-400 transition-colors" id="nav-lesew">የለሰው መድረክ</a>
      <a href="#cv-builder" class="hover:text-amber-400 transition-colors font-bold text-amber-300" id="nav-cv">📄 CV ማዘጋጃ</a>
      <a href="#pillars" class="hover:text-amber-400 transition-colors" id="nav-pillars">አዕማድ</a>
      <a href="#four-creatures" class="hover:text-amber-400 transition-colors" id="nav-kids">ትምህርትና ልጆች</a>
      <a href="#ai-assistant" class="hover:text-amber-400 transition-colors font-bold text-cyan-300" id="nav-ai">🤖 የኤአይ መሪ ረዳት</a>
    </nav>

    <!-- Language Selector & AI Quick Link Button -->
    <div class="flex items-center gap-3">
      <div class="flex items-center glass-card p-1 rounded-xl text-xs font-bold border-amber-400/30">
        <button onclick="setLanguage('am')" id="lang-btn-am" class="px-2.5 py-1 rounded-lg bg-amber-500 text-slate-950 font-black transition-all">🇪🇹 አማ</button>
        <button onclick="setLanguage('en')" id="lang-btn-en" class="px-2.5 py-1 rounded-lg hover:text-amber-400 text-slate-300 transition-all">🇬🇧 EN</button>
        <button onclick="setLanguage('ar')" id="lang-btn-ar" class="px-2.5 py-1 rounded-lg hover:text-amber-400 text-slate-300 transition-all">🇦🇪 عربي</button>
      </div>

      <a href="#ai-assistant" class="inline-flex items-center gap-2 px-3.5 py-2 rounded-xl bg-gradient-to-r from-cyan-500 to-sky-500 text-slate-950 font-black text-xs hover:shadow-lg hover:shadow-cyan-500/20 transition-all active:scale-95">
        <i class="fas fa-robot text-xs"></i>
        <span id="btn-quick-ai">AI Career Assistant</span>
      </a>
    </div>
  </div>
</header>

<!-- HERO SECTION -->
<section id="hero" class="relative min-h-[85vh] flex flex-col justify-center items-center text-center px-4 py-16 overflow-hidden">
  <div class="absolute top-1/4 left-1/2 -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-amber-500/10 rounded-full blur-3xl pointer-events-none"></div>
  <div class="absolute bottom-10 right-10 w-80 h-80 bg-emerald-500/10 rounded-full blur-3xl pointer-events-none"></div>

  <div class="max-w-4xl mx-auto space-y-6 relative z-10">
    <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-amber-400/10 text-amber-300 border border-amber-400/30 text-xs font-extrabold tracking-widest uppercase shadow-md">
      ✨ <span id="hero-badge">LESEW INITIATIVE • ለሰው መድረክ</span>
    </div>

    <h1 id="hero-title" class="text-4xl sm:text-6xl lg:text-7xl font-black tracking-tight leading-tight text-white">
      ሰው መሆን ይቀድማል።
    </h1>

    <p id="hero-subtitle" class="text-xl sm:text-2xl text-amber-300 font-extrabold max-w-2xl mx-auto">
      Being Human Comes First.
    </p>

    <!-- Founder Portrait Frame & Social Handle Ribbon -->
    <div class="flex flex-col items-center justify-center my-4">
      <div class="relative group">
        <div class="w-32 h-32 sm:w-36 sm:h-36 rounded-full p-1.5 habesha-tilet-frame shadow-2xl transform group-hover:scale-105 transition-all relative">
          <div class="w-full h-full rounded-full bg-slate-950 overflow-hidden flex flex-col items-center justify-center border-2 border-slate-900 relative">
            <div class="w-full h-full flex flex-col items-center justify-center bg-slate-950 relative z-10 overflow-hidden rounded-full">
              <img src="1000142296.jpg" alt="Eyerusalem Hailu (Jerry)" class="w-full h-full object-cover object-top transform scale-110" id="founder-photo" onerror="this.onerror=null; this.src='jerry.jpg';">
            </div>
          </div>
        </div>
      </div>

      <div class="mt-4 inline-flex items-center gap-2 px-3.5 py-1.5 rounded-xl bg-slate-900/90 border border-amber-400/30 text-xs text-slate-300 shadow-md">
        <span class="font-bold text-white">Eyerusalem Hailu (Jerry)</span>
        <span class="text-slate-500">•</span>
        <span class="text-amber-400 font-extrabold">@wederjojo</span>
        <span class="text-slate-500">•</span>
        <div class="flex items-center gap-2 text-amber-400">
          <i class="fab fa-tiktok" title="TikTok"></i>
          <i class="fab fa-youtube" title="YouTube"></i>
          <i class="fab fa-facebook" title="Facebook"></i>
          <i class="fab fa-instagram" title="Instagram"></i>
        </div>
      </div>
    </div>

    <p id="hero-desc" class="text-slate-300 text-base sm:text-lg max-w-3xl mx-auto leading-relaxed">
      ከትምህርት፣ ከስራ፣ ከቴክኖሎጂ፣ ከስኬትና ከማንኛውም ማዕረግ በፊት ሰውን እናያለን። ለሰው ልጅ እድገት፣ ክብርና ማብቃት የተገነባ የሰው-ማዕከል መድረክ።
    </p>

    <!-- CTAs -->
    <div class="flex flex-wrap justify-center items-center gap-4 pt-4">
      <a href="#cv-builder" class="px-6 py-3.5 rounded-xl bg-gradient-to-r from-amber-400 to-amber-500 text-slate-950 font-black text-xs sm:text-sm hover:shadow-lg hover:shadow-amber-500/25 transition-all active:scale-95 flex items-center gap-2">
        <i class="fas fa-file-invoice text-xs"></i>
        <span id="cta-cv-hero">📄 CV እና ሸኘ ደብዳቤ በይነመረብ ላይ ስራ</span>
      </a>

      <a href="#ai-assistant" class="px-6 py-3.5 rounded-xl glass-card hover:bg-slate-800 text-white font-bold text-xs sm:text-sm border-cyan-400/30 transition-all active:scale-95 flex items-center gap-2">
        <i class="fas fa-robot text-xs text-cyan-400"></i>
        <span id="cta-ai-hero">የኤአይ ረዳታችንን ይጠይቁ</span>
      </a>
    </div>

    <!-- Philosophy Matrix Cards -->
    <div class="grid grid-cols-2 md:grid-cols-4 gap-4 max-w-4xl mx-auto pt-10 text-left">
      <div class="glass-card p-4 rounded-xl border-amber-400/20">
        <div class="text-amber-400 font-black text-[10px] uppercase mb-1" id="matrix-t1">ዓላማ</div>
        <div class="text-xs sm:text-sm font-bold text-white" id="matrix-v1">ሰው የሁሉም ዓላማ ነው</div>
      </div>
      <div class="glass-card p-4 rounded-xl border-emerald-400/20">
        <div class="text-emerald-400 font-black text-[10px] uppercase mb-1" id="matrix-t2">መሣሪያ</div>
        <div class="text-xs sm:text-sm font-bold text-white" id="matrix-v2">ቴክኖሎጂ ማገልገያ ነው</div>
      </div>
      <div class="glass-card p-4 rounded-xl border-sky-400/20">
        <div class="text-sky-400 font-black text-[10px] uppercase mb-1" id="matrix-t3">ጉዞ</div>
        <div class="text-xs sm:text-sm font-bold text-white" id="matrix-v3">መማር ዘላቂ ጉዞ ነው</div>
      </div>
      <div class="glass-card p-4 rounded-xl border-rose-400/20">
        <div class="text-rose-400 font-black text-[10px] uppercase mb-1" id="matrix-t4">ውጤት</div>
        <div class="text-xs sm:text-sm font-bold text-white" id="matrix-v4">ማብቃት የእኛ ስኬት ነው</div>
      </div>
    </div>
  </div>
</section>

<!-- SECTION: MULTILINGUAL AI ASSISTANT (ENHANCED FOR UAE JOB SEEKERS & MENTORSHIP) -->
<section id="ai-assistant" class="py-24 px-4 border-t border-slate-800 bg-slate-900/80">
  <div class="max-w-5xl mx-auto">
    <div class="text-center mb-12">
      <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-cyan-500/20 text-cyan-300 text-xs font-bold uppercase mb-3 shadow-lg" id="ai-badge">
        🤖 24/7 ኤአይ መሪ ረዳት • UAE JOB & GROWTH AI COMPANION
      </div>
      <h2 class="text-3xl sm:text-5xl font-black text-white" id="ai-title">Wederjojo AI Companion</h2>
      <p class="text-slate-300 text-xs sm:text-sm max-w-2xl mx-auto mt-2 leading-relaxed" id="ai-desc">
        ለማንኛውም ጥያቄያችሁ — በUAE የሥራ ዕድሎች፣ ይፋዊ መረጃዎች፣ የቪዛ ማረጋገጫ፣ የቃለ መጠይቅ ዝግጅት እና በህይወት ዕድገት ዙሪያ AI ረዳታችንን ይጠይቁ።
      </p>
    </div>

    <!-- AI Chat Box -->
    <div class="glass-card p-6 sm:p-8 rounded-3xl border-cyan-500/30 shadow-2xl relative">
      <!-- AI Status Header -->
      <div class="flex flex-wrap items-center justify-between pb-4 border-b border-slate-700 mb-4 gap-4">
        <div class="flex items-center gap-3">
          <div class="w-12 h-12 rounded-2xl bg-cyan-500/20 border border-cyan-400/40 flex items-center justify-center text-cyan-300 font-bold text-2xl shadow-md">
            🤖
          </div>
          <div>
            <div class="text-sm font-black text-white flex items-center gap-2">
              <span>Wederjojo AI Guide</span>
              <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
            </div>
            <div class="text-[11px] text-slate-400 font-semibold mt-0.5" id="ai-status">● ባለሙያ • UAE Verified Jobs, MOHRE Guidelines & Life Mentorship</div>
          </div>
        </div>

        <div class="flex items-center gap-2">
          <button onclick="clearChatHistory()" class="px-3 py-1.5 rounded-xl bg-slate-800 hover:bg-slate-700 text-slate-300 text-xs font-bold transition-all border border-slate-700 flex items-center gap-1.5">
            <i class="fas fa-trash-alt text-[10px]"></i>
            <span id="btn-clear-chat">ውይይት አጽዳ</span>
          </button>
          <span class="text-xs bg-cyan-500/10 text-cyan-300 px-3 py-1.5 rounded-full border border-cyan-400/30 font-extrabold" id="ai-pill">Smart AI Assistant</span>
        </div>
      </div>

      <!-- Quick Category Filter Pills -->
      <div class="mb-4 flex flex-wrap gap-2 text-xs" id="ai-category-pills">
        <button onclick="filterAiPrompts('all')" class="px-3 py-1 rounded-xl bg-cyan-500 text-slate-950 font-bold transition-all" id="pill-all">ሁሉም (All)</button>
        <button onclick="filterAiPrompts('jobs')" class="px-3 py-1 rounded-xl glass-card hover:bg-slate-800 text-slate-300 transition-all" id="pill-jobs">🇦🇪 UAE ሠራተኛና ሥራዎች</button>
        <button onclick="filterAiPrompts('cv')" class="px-3 py-1 rounded-xl glass-card hover:bg-slate-800 text-slate-300 transition-all" id="pill-cv">📄 CV እና ቃለ መጠይቅ</button>
        <button onclick="filterAiPrompts('human')" class="px-3 py-1 rounded-xl glass-card hover:bg-slate-800 text-slate-300 transition-all" id="pill-human">❤️ ሰው መሆን ይቀድማል</button>
      </div>

      <!-- Chat History Container -->
      <div id="chatHistory" class="space-y-4 max-h-[380px] overflow-y-auto pr-3 mb-4 scrollbar-thin">
        <div class="flex gap-3">
          <div class="w-9 h-9 rounded-xl bg-cyan-500/20 border border-cyan-400/30 flex items-center justify-center text-cyan-300 text-xs font-black shrink-0">W</div>
          <div class="p-4 rounded-2xl bg-slate-800/90 text-xs text-slate-200 leading-relaxed max-w-xl border border-cyan-400/25 shadow-md" id="ai-welcome">
            ሰላም! Welcome! أهلاً بك! I am your Wederjojo AI assistant, built for the LeSew Initiative. I can help you find verified UAE job search channels (like MOHRE, Dubizzle, LinkedIn), prepare ATS-friendly CVs, understand UAE labor regulations, and guide your personal growth with our core value: "Being Human Comes First." How can I help you today?
          </div>
        </div>
      </div>

      <!-- Quick Preset Prompt Buttons -->
      <div class="flex flex-wrap gap-2 mb-4" id="ai-prompts"></div>

      <!-- Chat Input Area -->
      <div class="flex gap-2">
        <input type="text" id="chatInput" placeholder="በ UAE ስራ፣ በቪዛ፣ በ CV ወይም በሕይወት ዕድገት ዙሪያ ይጠይቁ..." class="flex-1 bg-slate-950/80 border border-slate-700 rounded-2xl px-4 py-3.5 text-xs text-white focus:outline-none focus:border-cyan-400 transition-colors shadow-inner" onkeydown="if(event.key === 'Enter') sendChatMessage()">
        <button onclick="sendChatMessage()" class="px-6 py-3.5 rounded-2xl bg-gradient-to-r from-cyan-500 to-sky-500 text-slate-950 font-black text-xs hover:shadow-lg hover:shadow-cyan-500/25 transition-all active:scale-95 shrink-0 flex items-center gap-2">
          <i class="fas fa-paper-plane text-xs"></i>
          <span id="btn-send">ላክ / Send</span>
        </button>
      </div>
    </div>
  </div>
</section>

<!-- SECTION 1: CV & COVER LETTER AUTOMATED MAKER -->
<section id="cv-builder" class="py-20 px-4 border-t border-slate-800 bg-slate-900/80">
  <div class="max-w-6xl mx-auto">
    <div class="text-center mb-12">
      <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-amber-400/20 text-amber-300 text-xs font-bold uppercase mb-3" id="cv-badge">
        📄 FREE AUTOMATED CV & COVER LETTER GENERATOR
      </div>
      <h2 class="text-3xl sm:text-5xl font-black text-white" id="cv-section-title">የሥራ CV እና የሸኘ ደብዳቤ ማዘጋጃ (CV & Cover Letter Builder)</h2>
      <p class="text-slate-300 text-xs sm:text-sm max-w-2xl mx-auto mt-2 leading-relaxed" id="cv-section-desc">
        መረጃዎን፣ ፎቶዎንና ልምድዎን ያስገቡ፤ መድረካችን በ UAE እና በዓለም አቀፍ ደረጃ ተቀባይነት ያለው ATS-Friendly CV እና የተዘጋጀ የሸኘ ደብዳቤ (Cover Letter) ያዘጋጅልዎታል!
      </p>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-start">
      <!-- Input Form Card -->
      <div class="lg:col-span-5 glass-card p-6 rounded-3xl border-amber-400/30 space-y-4">
        <h3 class="text-base font-black text-amber-400 border-b border-slate-700 pb-3 flex items-center justify-between" id="form-header">
          <span>📝 የእርስዎን መረጃ ያስገቡ</span>
          <span class="text-[10px] bg-emerald-500/20 text-emerald-300 px-2 py-0.5 rounded font-bold">100% Free</span>
        </h3>

        <div class="space-y-3 text-xs">
          <div>
            <label class="block font-bold text-slate-300 mb-1" id="lbl-fullname">ሙሉ ስም (Full Name)</label>
            <input type="text" id="cvFullName" placeholder="ምሳሌ፡ Selamawit Tadesse" class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none">
          </div>

          <div class="grid grid-cols-2 gap-3">
            <div>
              <label class="block font-bold text-slate-300 mb-1" id="lbl-phone">ስልክ / WhatsApp</label>
              <input type="text" id="cvPhone" placeholder="+971 50 123 4567" class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none">
            </div>
            <div>
              <label class="block font-bold text-slate-300 mb-1" id="lbl-email">ኢሜይል (Email)</label>
              <input type="email" id="cvEmail" placeholder="selam@gmail.com" class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none">
            </div>
          </div>

          <div class="grid grid-cols-2 gap-3">
            <div>
              <label class="block font-bold text-slate-300 mb-1" id="lbl-location">አድራሻ / ከተማ (Location)</label>
              <input type="text" id="cvLocation" placeholder="Dubai, UAE / Addis Ababa" class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none">
            </div>
            <div>
              <label class="block font-bold text-slate-300 mb-1" id="lbl-jobtitle">የሚፈልጉት የሥራ ዘርፍ (Target Job)</label>
              <input type="text" id="cvTargetRole" placeholder="Customer Support / Sales / Hospitality" class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none">
            </div>
          </div>

          <div>
            <label class="block font-bold text-slate-300 mb-1" id="lbl-photo">የፎቶ ሊንክ / Photo URL (Optional)</label>
            <input type="text" id="cvPhotoUrl" placeholder="https://example.com/myphoto.jpg" class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none">
          </div>

          <div>
            <label class="block font-bold text-slate-300 mb-1" id="lbl-skills">ልዩ ክህሎቶችና ቋንቋዎች (Key Skills & Languages)</label>
            <input type="text" id="cvSkills" placeholder="English, Amharic, Customer Care, MS Office, Teamwork" class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none">
          </div>

          <div>
            <label class="block font-bold text-slate-300 mb-1" id="lbl-experience">የሥራ ተሞክሮ (Work Experience)</label>
            <textarea id="cvExperience" rows="3" placeholder="ምሳሌ፡ Sales Associate at Grand Mall (2022-2024) - Handled customer service, sales, and inventory management." class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none"></textarea>
          </div>

          <div>
            <label class="block font-bold text-slate-300 mb-1" id="lbl-education">ትምህርትና ሥልጠና (Education)</label>
            <input type="text" id="cvEducation" placeholder="Diploma in Business Admin / High School Certificate" class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none">
          </div>

          <div>
            <label class="block font-bold text-slate-300 mb-1" id="lbl-company">የሚያመቻቹት ኩባንያ ስም (Target Company Name for Cover Letter)</label>
            <input type="text" id="cvCompanyName" placeholder="e.g. Al Maya Group / Luxury Hotel Dubai" class="w-full bg-slate-950/80 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:border-amber-400 focus:outline-none">
          </div>

          <button onclick="generateCVAndCoverLetter()" class="w-full py-3.5 rounded-xl bg-gradient-to-r from-amber-400 to-amber-500 text-slate-950 font-black text-xs hover:shadow-lg hover:shadow-amber-500/20 transition-all active:scale-95 flex items-center justify-center gap-2">
            <i class="fas fa-magic"></i>
            <span id="btn-generate-cv">✨ CV እና Cover Letter አዘጋጅ</span>
          </button>
        </div>
      </div>

      <!-- Preview & Output Container -->
      <div class="lg:col-span-7 glass-card p-6 rounded-3xl border-emerald-400/30 flex flex-col min-h-[600px]">
        <!-- Output Switcher Tabs -->
        <div class="flex items-center justify-between border-b border-slate-700 pb-4 mb-4">
          <div class="flex items-center gap-2">
            <button onclick="switchCvTab('cv')" id="tab-btn-cv" class="px-4 py-2 rounded-xl bg-amber-500 text-slate-950 font-black text-xs transition-all">
              📄 CV Preview
            </button>
            <button onclick="switchCvTab('cover')" id="tab-btn-cover" class="px-4 py-2 rounded-xl glass-card hover:text-amber-400 text-slate-300 font-black text-xs transition-all">
              ✉️ Cover Letter
            </button>
          </div>

          <!-- Quick Action Buttons -->
          <div class="flex items-center gap-2">
            <button onclick="printGeneratedCV()" class="px-3 py-1.5 rounded-lg bg-emerald-500 text-slate-950 font-extrabold text-xs hover:bg-emerald-400 transition-all flex items-center gap-1.5">
              <i class="fas fa-print text-xs"></i>
              <span id="btn-print">Print / PDF</span>
            </button>
            <button onclick="copyGeneratedText()" class="px-3 py-1.5 rounded-lg glass-card hover:bg-slate-800 text-amber-300 font-extrabold text-xs transition-all flex items-center gap-1.5 border-amber-400/30">
              <i class="fas fa-copy text-xs"></i>
              <span id="btn-copy">Copy Text</span>
            </button>
          </div>
        </div>

        <!-- Printable Canvas View Container -->
        <div id="printableArea" class="flex-1 bg-white text-slate-900 p-6 sm:p-8 rounded-2xl shadow-2xl overflow-y-auto font-sans leading-relaxed text-xs">
          <div id="cvOutputContainer">
            <!-- Default Placeholder CV State -->
            <div class="text-center py-12 text-slate-400 space-y-3">
              <div class="text-5xl">📄</div>
              <p class="font-bold text-slate-600" id="placeholder-msg">በግራ በኩል ያለውን ፎርም ሞልተው "CV እና Cover Letter አዘጋጅ" የሚለውን ይጫኑ!</p>
              <p class="text-[11px] text-slate-500">Fill in the details on the left to generate your ATS-compliant CV and Cover Letter instantly.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SECTION 2: ABOUT & FOUNDER PROFILE -->
<section id="about" class="py-20 px-4 border-t border-slate-800 bg-slate-900/40">
  <div class="max-w-6xl mx-auto">
    <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
      <!-- Founder Profile Card -->
      <div class="glass-card p-8 rounded-3xl border-amber-400/20 relative overflow-hidden shadow-2xl">
        <div class="absolute top-0 right-0 w-32 h-32 bg-amber-400/10 rounded-full blur-2xl pointer-events-none"></div>

        <div class="flex flex-col sm:flex-row items-center sm:items-start gap-5 mb-6 pb-6 border-b border-slate-800 text-center sm:text-left">
          <div class="relative shrink-0">
            <div class="w-28 h-28 rounded-2xl p-1 habesha-tilet-frame shadow-xl overflow-hidden">
              <div class="w-full h-full rounded-xl bg-slate-950 flex flex-col items-center justify-center overflow-hidden relative">
                <img src="1000142296.jpg" alt="Eyerusalem Hailu (Jerry)" class="w-full h-full object-cover object-top transform scale-110" onerror="this.onerror=null; this.src='jerry.jpg';">
              </div>
            </div>
            <span class="absolute -bottom-1 -right-1 px-2 py-0.5 bg-emerald-500 text-slate-950 text-[9px] font-black rounded-md shadow-md">🇪🇹 🇦🇪</span>
          </div>

          <div>
            <h3 class="text-2xl font-black text-white" id="about-founder-name">Eyerusalem Hailu (Jerry)</h3>
            <p class="text-xs text-amber-400 font-bold uppercase tracking-wider mt-0.5" id="about-founder-title">Founder & Community Mentor • @wederjojo</p>

            <div class="flex flex-wrap items-center justify-center sm:justify-start gap-1.5 mt-2.5">
              <span class="px-2 py-0.5 rounded bg-amber-500/20 text-amber-300 text-[10px] font-bold border border-amber-500/30 flex items-center gap-1">
                <i class="fab fa-tiktok text-amber-400"></i> TikTok
              </span>
              <span class="px-2 py-0.5 rounded bg-rose-500/20 text-rose-300 text-[10px] font-bold border border-rose-500/30 flex items-center gap-1">
                <i class="fab fa-youtube text-rose-400"></i> YouTube
              </span>
              <span class="px-2 py-0.5 rounded bg-sky-500/20 text-sky-300 text-[10px] font-bold border border-sky-500/30 flex items-center gap-1">
                <i class="fab fa-facebook text-sky-400"></i> Facebook
              </span>
              <span class="px-2 py-0.5 rounded bg-emerald-500/20 text-emerald-300 text-[10px] font-bold border border-emerald-500/30 flex items-center gap-1">
                <i class="fab fa-instagram text-emerald-400"></i> Instagram
              </span>
            </div>
          </div>
        </div>

        <p id="about-p1" class="text-slate-300 text-sm leading-relaxed mb-4">
          ከስኬት፣ ከቴክኖሎጂ፣ ከትምህርት፣ ከስራ፣ ከንግድ ወይም ከማንኛውም ማዕረግ በፊት ሰውን እናያለን። እያንዳንዱ ሰው ክብር፣ ታሪክ፣ የሚማረውና የሚያበረክተው አቅም አለው።
        </p>

        <p id="about-p2" class="text-slate-300 text-sm leading-relaxed mb-6">
          የወደርጆጆና የለሰው መድረክ ዓላማ ሰዎች የሚማሩበት፣ የሚያድጉበት፣ አቅማቸውን አውቀው ወደ አዎንታዊ ተፅዕኖና ውጤታማ ሥራ የሚያሸጋገሩበትን ድልድይ መገንባት ነው።
        </p>

        <div class="p-4 rounded-2xl bg-amber-400/10 border border-amber-400/30 text-amber-200 text-xs font-bold leading-relaxed" id="about-quote">
          "ቴክኖሎጂ የእውቀትና ዕድል መክፈቻ ነው። ነገር ግን ቴክኖሎጂ ሰውን ሊያገለግል እንጂ የሰውን ልጅ ቦታ ሊተካ አይገባም።"
        </div>
      </div>

      <!-- Strategy & Brand Architecture -->
      <div class="space-y-6">
        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-emerald-500/20 text-emerald-300 text-xs font-bold uppercase" id="arch-badge">
          ⚖️ የብራንድ ፍልስፍናና የመድረክ አወቃቀር
        </div>

        <h2 id="arch-title" class="text-3xl sm:text-4xl font-black text-white leading-snug">
          «ሰው መሆን ይቀድማል» እና «ለሰው መድረክ» እንዴት አብረው ይሠራሉ?
        </h2>

        <div class="space-y-4">
          <div class="p-4 rounded-2xl glass-card border-amber-400/20">
            <div class="text-xs font-black text-amber-400 uppercase" id="arch-h1">1. መሪ ፍልስፍና (Brand Heart)</div>
            <div class="text-sm font-bold text-white mt-1" id="arch-sub1">«ሰው መሆን ይቀድማል» (Humanity First)</div>
            <p class="text-xs text-slate-300 mt-1 leading-relaxed" id="arch-d1">
              ይህ የማንነታችንና የሥነ-ምግባራችን መሪ መርህ ነው። ለማንኛውም የይዘት፣ የሥልጠናና የቴክኖሎጂ ሥራችን መነሻና መመሪያ ነው።
            </p>
          </div>

          <div class="p-4 rounded-2xl glass-card border-emerald-400/20">
            <div class="text-xs font-black text-emerald-400 uppercase" id="arch-h2">2. የመድረኩ ስም (Platform Name)</div>
            <div class="text-sm font-bold text-white mt-1" id="arch-sub2">«ለሰው» (LeSew Initiative)</div>
            <p class="text-xs text-slate-300 mt-1 leading-relaxed" id="arch-d2">
              በተባበሩት አረብ ኤሚሬቶችና በኢትዮጵያ መካከል ያሉ ሥራ ፈላጊዎችንና ቀጣሪዎችን የሚያገናኝ፣ ሰውን የሚያበቃ አጭርና የማይረሳ የመድረክ ስም።
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SECTION 3: LESEW INITIATIVE PLATFORM BRIDGE -->
<section id="lesew-bridge" class="py-20 px-4 border-t border-slate-800 bg-slate-900/60">
  <div class="max-w-6xl mx-auto">
    <div class="text-center mb-14">
      <span class="text-amber-400 font-black text-xs tracking-widest uppercase" id="lesew-tag">LESEW COMMUNITY BRIDGE</span>
      <h2 class="text-3xl sm:text-5xl font-black text-white mt-2" id="lesew-title">የለሰው (LeSew) የሥራና የክህሎት ድልድይ</h2>
      <p class="text-slate-300 text-sm sm:text-base max-w-2xl mx-auto mt-3" id="lesew-desc">
        በተባበሩት አረብ ኤሚሬቶች (UAE) እና በኢትዮጵያ መካከል በሰብዓዊ ክብርና በታማኝነት ላይ የተመሠረተ የሥራና የችሎታ ግንኙነት መድረክ።
      </p>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="glass-card p-6 rounded-3xl border-amber-400/30 hover:border-amber-400 transition-all">
        <div class="w-12 h-12 rounded-2xl bg-amber-500/20 border border-amber-400/30 flex items-center justify-center text-2xl mb-4">
          🤝
        </div>
        <h3 class="text-lg font-black text-white" id="bridge-c1-t">ታማኝ ግንኙነት (Verified Matching)</h3>
        <p class="text-xs text-slate-300 mt-2 leading-relaxed" id="bridge-c1-d">
          ሥራ ፈላጊዎችንና የተረጋገጡ ቀጣሪዎችን በተገቢው ክህሎትና በሰብዓዊ ክብር ማገናኘት።
        </p>
      </div>

      <div class="glass-card p-6 rounded-3xl border-emerald-400/30 hover:border-emerald-400 transition-all">
        <div class="w-12 h-12 rounded-2xl bg-emerald-500/20 border border-emerald-400/30 flex items-center justify-center text-2xl mb-4">
          🎓
        </div>
        <h3 class="text-lg font-black text-white" id="bridge-c2-t">የክህሎት ማበልጸጊያ (Talent Growth)</h3>
        <p class="text-xs text-slate-300 mt-2 leading-relaxed" id="bridge-c2-d">
          የቋንቋ፣ የቴክኖሎጂና የሥራ ቦታ ዝግጅት ሥልጠናዎችን በመስጠት ሰዎችን ለተሻለ ስኬት ማዘጋጀት።
        </p>
      </div>

      <div class="glass-card p-6 rounded-3xl border-sky-400/30 hover:border-sky-400 transition-all">
        <div class="w-12 h-12 rounded-2xl bg-sky-500/20 border border-sky-400/30 flex items-center justify-center text-2xl mb-4">
          🛡
        </div>
        <h3 class="text-lg font-black text-white" id="bridge-c3-t">ሰብዓዊ ጥበቃና ድጋፍ (Dignity & Protection)</h3>
        <p class="text-xs text-slate-300 mt-2 leading-relaxed" id="bridge-c3-d">
          ከምንም ነገር በፊት የሰዎችን ደህንነት፣ መብትና ክብር ማስቀደድ።
        </p>
      </div>
    </div>
  </div>
</section>

<!-- SECTION 4: THE 8 BRAND PILLARS -->
<section id="pillars" class="py-24 px-4 border-t border-slate-800">
  <div class="max-w-6xl mx-auto">
    <div class="text-center mb-16">
      <span class="text-amber-400 font-extrabold text-xs tracking-widest uppercase">OUR 8 BRAND PILLARS</span>
      <h2 id="pillars-title" class="text-3xl sm:text-5xl font-black text-white mt-2">የብራንዳችን 8ቱ ዋና አዕማዶች</h2>
      <p id="pillars-subtitle" class="text-slate-400 text-sm sm:text-base max-w-2xl mx-auto mt-3">
        ማንኛውም ይዘት፣ ትምህርት፣ የቴክኖሎጂ መሣሪያና የማኅበረሰብ እንቅስቃሴ በዚህ መዋቅር ውስጥ ያልፋል።
      </p>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6" id="pillars-grid">
      <!-- Generated dynamically in JS -->
    </div>
  </div>
</section>

<!-- SECTION 5: FEATURED RESOURCE - KIDS & FAMILY (4 WISE CREATURES) -->
<section id="four-creatures" class="py-24 px-4 border-t border-slate-800 bg-slate-900/60">
  <div class="max-w-6xl mx-auto">
    <div class="text-center mb-12">
      <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-amber-400/20 text-amber-300 text-xs font-bold uppercase mb-3" id="kids-badge">
        📖 የልጆችና የቤተሰብ ትምህርት
      </div>
      <h2 class="text-3xl sm:text-5xl font-black text-white" id="creatures-title">አራት ጠቢብ ፍጥረቶች (Four Wise Creatures)</h2>
      <p class="text-amber-300 text-sm sm:text-base mt-2 font-bold" id="creatures-sub">በምሳሌ 30:24-28 የተመሠረተ ለልጆችና ለቤተሰብ</p>
      <p class="text-slate-400 text-xs sm:text-sm max-w-2xl mx-auto mt-2" id="creatures-verse">
        "በምድር ላይ አራት ነገሮች ትንንሽ ናቸው፤ ሆኖም እጅግ ጠቢባን ናቸው!"
      </p>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 mb-12" id="creatures-grid">
      <!-- Rendered via JS -->
    </div>

    <!-- Kids Memory Game -->
    <div class="glass-card p-6 sm:p-8 rounded-3xl border-amber-400/20 text-center max-w-2xl mx-auto">
      <h3 class="text-lg font-black text-white mb-2" id="game-title">🧠 የሕፃናት የማስታወስ ጨዋታ (Memory Game)</h3>
      <p class="text-xs text-slate-300 mb-6" id="game-subtitle">ተመሳሳይ ሆኑትን ፍጥረቶች ፈልገው ያዛምዱ!</p>
      <div id="memoryBoard" class="grid grid-cols-4 gap-3 max-w-md mx-auto mb-4"></div>
      <button onclick="initMemoryGame()" class="px-5 py-2 rounded-full bg-emerald-500 text-slate-950 font-bold text-xs hover:bg-emerald-400 transition-all" id="btn-reset-game">
        🔄 ጨዋታውን እንደገና ጀምር
      </button>
    </div>
  </div>
</section>

<!-- SECTION 7: GUIDING QUESTION & REFLECTION TOOL -->
<section id="reflection-tool" class="py-24 px-4 border-t border-slate-800 bg-slate-900/40">
  <div class="max-w-3xl mx-auto text-center">
    <div class="glass-card-gold p-8 sm:p-12 rounded-3xl border-amber-400/40 relative shadow-2xl">
      <span class="text-xs font-black text-amber-400 tracking-widest uppercase block mb-3" id="refl-badge">OUR GUIDING QUESTION • የእለት ተእለት መሪ ጥያቄ</span>
      
      <h2 id="guiding-title" class="text-2xl sm:text-4xl font-black text-white leading-snug mb-6">
        "Whenever we create something new, we ask:<br>
        <span class="text-amber-300" id="guiding-motto">Does it remember that being human comes first?</span>"
      </h2>

      <div id="reflectionBox" class="p-6 rounded-2xl bg-slate-950/70 border border-amber-400/30 mb-6 text-left">
        <div class="text-[10px] font-bold text-amber-400 uppercase mb-2" id="refl-label">Daily Reflection Prompt / የዕለቱ ማሰላሰያ</div>
        <div id="reflectionPrompt" class="text-sm font-bold text-slate-100">
          "ዛሬ በዙሪያህ ያሉትን ሰዎች ከስኬት፣ ከስራ ወይም ከማንነታቸው በፊት እንደ ሰው ተመልከተሃቸዋል?"
        </div>
      </div>

      <button onclick="generateReflection()" class="px-6 py-3 rounded-xl bg-gradient-to-r from-amber-400 to-amber-500 text-slate-950 font-black text-xs hover:shadow-lg hover:shadow-amber-500/20 transition-all active:scale-95" id="btn-new-refl">
        ✨ ሌላ ማሰላሰያ አውጣ (New Reflection Prompt)
      </button>
    </div>
  </div>
</section>

<!-- FOOTER & CONTACT -->
<footer id="contact" class="border-t border-slate-800 bg-slate-950 py-16 px-4">
  <div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-10">
    <!-- Brand Info -->
    <div class="space-y-4">
      <div class="flex items-center gap-3">
        <div class="w-10 h-10 rounded-xl habesha-tilet-frame p-0.5 flex items-center justify-center font-black text-slate-950 text-xl">
          <div class="w-full h-full rounded-[10px] bg-slate-950 flex items-center justify-center text-amber-400 font-extrabold text-lg">
            ለ
          </div>
        </div>
        <span class="font-black text-xl text-white">LeSew Initiative</span>
      </div>
      <p class="text-xs text-slate-400 leading-relaxed" id="footer-desc">
        ሰው መሆን ይቀድማል። Being Human Comes First. A people-centred platform connecting growth, employment, talent, and humanity.
      </p>
      <div class="text-xs font-bold text-amber-400" id="footer-identity">
        Eyerusalem Hailu (Jerry) • Unified Handle @wederjojo (TikTok, YouTube, Facebook, Instagram)
      </div>
    </div>

    <!-- Links -->
    <div class="space-y-3">
      <div class="text-xs font-black text-white uppercase tracking-widest" id="footer-nav-title">Navigation</div>
      <ul class="space-y-2 text-xs text-slate-400">
        <li><a href="#about" class="hover:text-amber-400 transition-colors" id="f-nav-1">Our Foundation</a></li>
        <li><a href="#lesew-bridge" class="hover:text-amber-400 transition-colors" id="f-nav-2">LeSew Talent Bridge</a></li>
        <li><a href="#cv-builder" class="hover:text-amber-400 transition-colors" id="f-nav-cv">Automated CV Builder</a></li>
        <li><a href="#pillars" class="hover:text-amber-400 transition-colors" id="f-nav-3">The 8 Brand Pillars</a></li>
        <li><a href="#four-creatures" class="hover:text-amber-400 transition-colors" id="f-nav-4">Children Resource</a></li>
        <li><a href="#ai-assistant" class="hover:text-amber-400 transition-colors" id="f-nav-5">Multilingual AI Companion</a></li>
      </ul>
    </div>

    <!-- Languages -->
    <div class="space-y-3">
      <div class="text-xs font-black text-white uppercase tracking-widest" id="footer-community-title">Community Bridge</div>
      <p class="text-xs text-slate-400 leading-relaxed" id="footer-comm-desc">
        Connecting across Ethiopia 🇪🇹, the United Arab Emirates 🇦🇪, and the global digital community through Amharic, English, and Arabic.
      </p>
      <div class="p-3 rounded-xl glass-card text-xs text-slate-300 italic border-amber-400/20" id="footer-quote">
        "Rooted in Faith. Leading with Love. Empowering People."
      </div>
    </div>
  </div>

  <div class="max-w-6xl mx-auto pt-10 mt-10 border-t border-slate-900 text-center text-[11px] text-slate-600">
    &copy; 2026 LeSew Initiative by Eyerusalem Hailu (@wederjojo). All Rights Reserved.
  </div>
</footer>

<script>
  let currentLang = 'am';
  let activeCvTab = 'cv';
  let currentCvData = null;
  let currentAiCategory = 'all';

  // 8 PILLARS DICTIONARY
  const pillarsData = {
    am: [
      { icon: '❤️', title: 'ሰው መሆን ይቀድማል', desc: 'ከስራ፣ ከስኬትና ከቴክኖሎጂ በፊት ሰውን ማስቀደም።' },
      { icon: '🌱', title: 'መማርና ዕድገት', desc: 'ዘላቂ የእውቀት፣ የክህሎትና የግል ዕድገት።' },
      { icon: '🤝', title: 'ማብቃትና ድጋፍ', desc: 'ሰዎች አቅማቸውን እንዲያውቁና እንዲጠቀሙ መርዳት።' },
      { icon: '🎯', title: 'ሕይወትና ዓላማ', desc: 'የሕይወትን ዓላማ መረዳትና በተግባር መኖር።' },
      { icon: '💡', title: 'ምክርና አመራር', desc: 'በተሞክሮና በዕውቀት ላይ የተመሠረተ አዎንታዊ መሪነት።' },
      { icon: '🤖', title: 'ቴክኖሎጂና ኤአይ', desc: 'ቴክኖሎጂን ለሰው ልጅ አገልግሎትና እድገት ማዋል።' },
      { icon: '🌍', title: 'ማኅበረሰብና ተፅዕኖ', desc: 'በማኅበረሰብ ውስጥ ዘላቂ አዎንታዊ ተፅዕኖ መፍጠር።' },
      { icon: '✨', title: 'እምነትና እሴቶች', desc: 'በፍቅር፣ በታማኝነትና በሰብዓዊ እሴት መመራት።' }
    ],
    en: [
      { icon: '❤️', title: 'Humanity First', desc: 'Prioritizing people over achievements, jobs, or technology.' },
      { icon: '🌱', title: 'Continuous Growth', desc: 'Lifelong learning and personal development.' },
      { icon: '🤝', title: 'Empowerment', desc: 'Helping individuals discover and unlock their true potential.' },
      { icon: '🎯', title: 'Purposeful Life', desc: 'Understanding life’s purpose and living it with clarity.' },
      { icon: '💡', title: 'Mentorship', desc: 'Guiding through experience, wisdom, and leadership.' },
      { icon: '🤖', title: 'Ethical Tech', desc: 'Leveraging AI and technology to serve human wellbeing.' },
      { icon: '🌍', title: 'Community Impact', desc: 'Creating lasting positive societal change.' },
      { icon: '✨', title: 'Faith & Values', desc: 'Grounded in love, honesty, and moral foundation.' }
    ],
    ar: [
      { icon: '❤️', title: 'الإنسانية أولاً', desc: 'تقديم كرامة الإنسان على الوظيفة والتكنولوجيا والنجاح.' },
      { icon: '🌱', title: 'النمو المستمر', desc: 'التعلم والتطوير الذاتي المستمر مدى الحياة.' },
      { icon: '🤝', title: 'التمكين والدعم', desc: 'مساعدة الأفراد على اكتشاف واستغلال طاقاتهم.' },
      { icon: '🎯', title: 'الحياة والهدف', desc: 'فهم هدف الحياة والعيش بوعي وإيجابية.' },
      { icon: '💡', title: 'التوجيه والقيادة', desc: 'قيادة القدوة والحكمة القائمة على الخبرة.' },
      { icon: '🤖', title: 'التكنولوجيا الأخلاقية', desc: 'تسخير الذكاء الاصطناعي والتكنولوجيا لخدمة الإنسان.' },
      { icon: '🌍', title: 'الأثر المجتمعي', desc: 'صناعة أثر إيجابي ومستدام في المجتمع.' },
      { icon: '✨', title: 'الإيمان والقيم', desc: 'الارتكاز على المحبة والأمانة والقيم الإنسانية.' }
    ]
  };

  // 4 WISE CREATURES DICTIONARY
  const creaturesData = {
    am: [
      { emoji: '🐜', name: 'ጕንዳን (Ants)', ref: 'ምሳሌ 30:25', desc: 'ኃይል የሌላቸው፤ ነገር ግን በመኸር ምግባቸውን የሚያከማቹ። (ትጋትና ቅድመ-ዝግጅት)', btn: 'ትጋትን ተማር' },
      { emoji: '🦔', name: 'ሸዋን (Rock Badgers)', ref: 'ምሳሌ 30:26', desc: 'ብርቱ ያልሆኑ፤ ነገር ግን ቤታቸውን በዓለት ላይ የሚያደርጉ። (ጥበብና መሠረት)', btn: 'መሠረትህን ገንባ' },
      { emoji: '🦗', name: 'አንበጣ (Locusts)', ref: 'ምሳሌ 30:27', desc: 'ንግሥት የሌላቸው፤ ነገር ግን በሥርዓት የሚገሠግሡ። (አንድነትና ሥርዓት)', btn: 'አንድነትን ተለማመድ' },
      { emoji: '🦎', name: 'እንሽላሊት (Lizards)', ref: 'ምሳሌ 30:28', desc: 'በእጅ የምትያዝ፤ ነገር ግን በነገሥታት ቤተ-መንግሥት የምትገኝ። (ትሕትናና ተፅዕኖ)', btn: 'ተፅዕኖ ፈጣሪ ሁን' }
    ],
    en: [
      { emoji: '🐜', name: 'The Ants', ref: 'Proverbs 30:25', desc: 'Small without strength, yet they prepare their food in the summer. (Diligence)', btn: 'Learn Diligence' },
      { emoji: '🦔', name: 'Rock Badgers', ref: 'Proverbs 30:26', desc: 'Creatures of little power, yet they make their home in the crags. (Wisdom)', btn: 'Build Foundation' },
      { emoji: '🦗', name: 'The Locusts', ref: 'Proverbs 30:27', desc: 'They have no king, yet they advance together in ranks. (Unity & Order)', btn: 'Practice Unity' },
      { emoji: '🦎', name: 'The Lizard', ref: 'Proverbs 30:28', desc: 'You can catch with your hand, yet it is in king\'s palaces. (Resilience)', btn: 'Build Impact' }
    ],
    ar: [
      { emoji: '🐜', name: 'النمل', ref: 'أمثال 30: 25', desc: 'طائفة غير قوية، ولكنها تعد طعامها في الصيف. (الاجتهاد والتخطيط)', btn: 'تعلم الاجتهاد' },
      { emoji: '🦔', name: 'الوبر', ref: 'أمثال 30: 26', desc: 'طائفة ضعيفة، ولكنها تجعل بيوتها في الصخر. (الحكمة والأساس)', btn: 'ابنِ أساسك' },
      { emoji: '🦗', name: 'الجراد', ref: 'أمثال 30: 27', desc: 'ليس له ملك، ولكنه يخرج كله فرقا فرقا. (الوحدة والنظام)', btn: 'مارس الاتحاد' },
      { emoji: '🦎', name: 'السحلية', ref: 'أمثال 30: 28', desc: 'تمسكها بيدك، وهي في قصور الملوك. (التواضع والأثر)', btn: 'اصنع أثراً' }
    ]
  };

  // ENHANCED AI PROMPTS CATEGORIZED FOR JOB SEEKERS & MENTORSHIP
  const aiPromptsData = {
    am: [
      { cat: 'jobs', text: "በ UAE ውስጥ በታማኝነት የሥራ ዕድል እንዴት አገኛለሁ?" },
      { cat: 'jobs', text: "የ UAE የሥራ ሚኒስቴር (MOHRE) ደንቦች ምንድን ናቸው?" },
      { cat: 'cv', text: "ATS-friendly CV በምን መልኩ ማዘጋጀት እችላለሁ?" },
      { cat: 'cv', text: "የቃለ መጠይቅ (Interview) ስኬት ምስጢሮች ምንድን ናቸው?" },
      { cat: 'human', text: "በሥራ ቦታ ክብርን እና ሰብአዊ መብትን እንዴት ማስጠበቅ ይቻላል?" }
    ],
    en: [
      { cat: 'jobs', text: "What are the verified job portals in the UAE (MOHRE, Dubizzle, LinkedIn)?" },
      { cat: 'jobs', text: "How can I check if a UAE job offer and visa is legitimate?" },
      { cat: 'cv', text: "How do I make my CV pass ATS software for UAE employers?" },
      { cat: 'cv', text: "What are the top interview tips for customer service & sales roles?" },
      { cat: 'human', text: "How does the LeSew Initiative uphold 'Humanity First' in careers?" }
    ],
    ar: [
      { cat: 'jobs', text: "ما هي القنوات الموثوقة للبحث عن عمل في الإمارات (MOHRE)؟" },
      { cat: 'jobs', text: "كيف أتأكد من صحة عرض العمل وتأشيرة الإمارات؟" },
      { cat: 'cv', text: "كيف أجعل سيرتي الذاتية متوافقة مع نظام ATS في الإمارات؟" },
      { cat: 'cv', text: "ما هي أفضل نصائح اجتياز المقابلات الشخصية بنجاح؟" },
      { cat: 'human', text: "كيف تطبق مبادرة لِسو مبدأ الإنسانية أولاً في العمل؟" }
    ]
  };

  const i18n = {
    am: {
      brandName: "LeSew Initiative",
      brandHandle: "ኢየሩሳሌም ኃይሉ (ጄሪ) • @wederjojo",
      navAbout: "ስለ እኛ",
      navLesew: "የለሰው መድረክ",
      navCv: "📄 CV ማዘጋጃ",
      navPillars: "አዕማድ",
      navKids: "ትምህርትና ልጆች",
      navAi: "🤖 የኤአይ መሪ ረዳት",
      btnQuickAi: "AI Career Assistant",
      heroBadge: "LESEW INITIATIVE • ለሰው መድረክ",
      heroTitle: "ሰው መሆን ይቀድማል።",
      heroSubtitle: "Being Human Comes First.",
      heroDesc: "ከትምህርት፣ ከስራ፣ ከቴክኖሎጂ፣ ከስኬትና ከማንኛውም ማዕረግ በፊት ሰውን እናያለን። ለሰው ልጅ እድገት፣ ክብርና ማብቃት የተገነባ የሰው-ማዕከል መድረክ።",
      ctaCvHero: "📄 CV እና ሸኘ ደብዳቤ በይነመረብ ላይ ስራ",
      ctaAiHero: "የኤአይ ረዳታችንን ይጠይቁ",
      matrixT1: "ዓላማ", matrixV1: "ሰው የሁሉም ዓላማ ነው",
      matrixT2: "መሣሪያ", matrixV2: "ቴክኖሎጂ ማገልገያ ነው",
      matrixT3: "ጉዞ", matrixV3: "መማር ዘላቂ ጉዞ ነው",
      matrixT4: "ውጤት", matrixV4: "ማብቃት የእኛ ስኬት ነው",
      cvBadge: "📄 FREE AUTOMATED CV & COVER LETTER GENERATOR",
      cvSectionTitle: "የሥራ CV እና የሸኘ ደብዳቤ ማዘጋጃ (CV & Cover Letter Builder)",
      cvSectionDesc: "መረጃዎን፣ ፎቶዎንና ልምድዎን ያስገቡ፤ መድረካችን በ UAE እና በዓለም አቀፍ ደረጃ ተቀባይነት ያለው ATS-Friendly CV እና የተዘጋጀ የሸኘ ደብዳቤ (Cover Letter) ያዘጋጅልዎታል!",
      formHeader: "📝 የእርስዎን መረጃ ያስገቡ",
      lblFullName: "ሙሉ ስም (Full Name)",
      lblPhone: "ስልክ / WhatsApp",
      lblEmail: "ኢሜይል (Email)",
      lblLocation: "አድራሻ / ከተማ (Location)",
      lblJobTitle: "የሚፈልጉት የሥራ ዘርፍ (Target Job)",
      lblPhoto: "የፎቶ ሊንክ / Photo URL (Optional)",
      lblSkills: "ልዩ ክህሎቶችና ቋንቋዎች (Key Skills)",
      lblExperience: "የሥራ ተሞክሮ (Work Experience)",
      lblEducation: "ትምህርትና ሥልጠና (Education)",
      lblCompany: "የሚያመቻቹት ኩባንያ ስም (Company Name)",
      btnGenerateCv: "✨ CV እና Cover Letter አዘጋጅ",
      btnPrint: "Print / PDF",
      btnCopy: "Copy Text",
      placeholderMsg: "በግራ በኩል ያለውን ፎርም ሞልተው \"CV እና Cover Letter አዘጋጅ\" የሚለውን ይጫኑ!",
      aboutFounderName: "ኢየሩሳሌም ኃይሉ (ጄሪ)",
      aboutFounderTitle: "መሥራችና የማኅበረሰብ መሪ • @wederjojo",
      aboutP1: "ከስኬት፣ ከቴክኖሎጂ፣ ከትምህርት፣ ከስራ፣ ከንግድ ወይም ከማንኛውም ማዕረግ በፊት ሰውን እናያለን። እያንዳንዱ ሰው ክብር፣ ታሪክ፣ የሚማረውና የሚያበረክተው አቅም አለው።",
      aboutP2: "የወደርጆጆና የለሰው መድረክ ዓላማ ሰዎች የሚማሩበት፣ የሚያድጉበት፣ አቅማቸውን አውቀው ወደ አዎንታዊ ተፅዕኖና ውጤታማ ሥራ የሚያሸጋገሩበትን ድልድይ መገንባት ነው።",
      aboutQuote: "«ቴክኖሎጂ የእውቀትና ዕድል መክፈቻ ነው። ነገር ግን ቴክኖሎጂ ሰውን ሊያገለግል እንጂ የሰውን ልጅ ቦታ ሊተካ አይገባም።»",
      archBadge: "⚖️ የብራንድ ፍልስፍናና የመድረክ አወቃቀር",
      archTitle: "«ሰው መሆን ይቀድማል» እና «ለሰው መድረክ» እንዴት አብረው ይሠራሉ?",
      archH1: "1. መሪ ፍልስፍና (Brand Heart)",
      archSub1: "«ሰው መሆን ይቀድማል» (Humanity First)",
      archD1: "ይህ የማንነታችንና የሥነ-ምግባራችን መሪ መርህ ነው። ለማንኛውም የይዘት፣ የሥልጠናና የቴክኖሎጂ ሥራችን መነሻና መመሪያ ነው።",
      archH2: "2. የመድረኩ ስም (Platform Name)",
      archSub2: "«ለሰው» (LeSew Initiative)",
      archD2: "በተባበሩት አረብ ኤሚሬቶችና በኢትዮጵያ መካከል ያሉ ሥራ ፈላጊዎችንና ቀጣሪዎችን የሚያገናኝ፣ ሰውን የሚያበቃ አጭርና የማይረሳ የመድረክ ስም።",
      lesewTag: "LESEW COMMUNITY BRIDGE",
      lesewTitle: "የለሰው (LeSew) የሥራና የክህሎት ድልድይ",
      lesewDesc: "በተባበሩት አረብ ኤሚሬቶች (UAE) እና በኢትዮጵያ መካከል በሰብዓዊ ክብርና በታማኝነት ላይ የተመሠረተ የሥራና የችሎታ ግንኙነት መድረክ።",
      bridgeC1T: "ታማኝ ግንኙነት", bridgeC1D: "ሥራ ፈላጊዎችንና የተረጋገጡ ቀጣሪዎችን በተገቢው ክህሎትና በሰብዓዊ ክብር ማገናኘት።",
      bridgeC2T: "የክህሎት ማበልጸጊያ", bridgeC2D: "የቋንቋ፣ የቴክኖሎጂና የሥራ ቦታ ዝግጅት ሥልጠናዎችን በመስጠት ሰዎችን ለተሻለ ስኬት ማዘጋጀት።",
      bridgeC3T: "ሰብዓዊ ጥበቃና ድጋፍ", bridgeC3D: "ከምንም ነገር በፊት የሰዎችን ደህንነት፣ መብትና ክብር ማስቀደድ።",
      pillarsTitle: "የብራንዳችን 8ቱ ዋና አዕማዶች",
      pillarsSubtitle: "ማንኛውም ይዘት፣ ትምህርት፣ የቴክኖሎጂ መሣሪያና የማኅበረሰብ እንቅስቃሴ በዚህ መዋቅር ውስጥ ያልፋል።",
      kidsBadge: "📖 የልጆችና የቤተሰብ ትምህርት",
      creaturesTitle: "አራት ጠቢብ ፍጥረቶች (Four Wise Creatures)",
      creaturesSub: "በምሳሌ 30:24-28 የተመሠረተ ለልጆችና ለቤተሰብ",
      creaturesVerse: "«በምድር ላይ አራት ነገሮች ትንንሽ ናቸው፤ ሆኖም እጅግ ጠቢባን ናቸው!»",
      gameTitle: "🧠 የሕፃናት የማስታወስ ጨዋታ (Memory Game)",
      gameSubtitle: "ተመሳሳይ የሆኑትን ፍጥረቶች ፈልገው ያዛምዱ!",
      btnResetGame: "🔄 ጨዋታውን እንደገና ጀምር",
      aiBadge: "🤖 24/7 ኤአይ መሪ ረዳት • UAE JOB & GROWTH AI COMPANION",
      aiTitle: "Wederjojo AI Companion",
      aiDesc: "ለማንኛውም ጥያቄያችሁ — በUAE የሥራ ዕድሎች፣ ይፋዊ መረጃዎች፣ የቪዛ ማረጋገጫ፣ የቃለ መጠይቅ ዝግጅት እና በህይወት ዕድገት ዙሪያ AI ረዳታችንን ይጠይቁ።",
      aiStatus: "● ባለሙያ • UAE Verified Jobs, MOHRE Guidelines & Life Mentorship",
      aiPill: "Smart AI Assistant",
      aiWelcome: "ሰላም! Welcome! أهلاً بك! I am your Wederjojo AI assistant, built for the LeSew Initiative. I can help you find verified UAE job search channels (like MOHRE, Dubizzle, LinkedIn), prepare ATS-friendly CVs, understand UAE labor regulations, and guide your personal growth with our core value: \"Being Human Comes First.\" How can I help you today?",
      btnClearChat: "ውይይት አጽዳ",
      pillAll: "ሁሉም (All)",
      pillJobs: "🇦🇪 UAE ሠራተኛና ሥራዎች",
      pillCv: "📄 CV እና ቃለ መጠይቅ",
      pillHuman: "❤️ ሰው መሆን ይቀድማል",
      btnSend: "ላክ / Send",
      reflBadge: "OUR GUIDING QUESTION • የእለት ተእለት መሪ ጥያቄ",
      guidingMotto: "Does it remember that being human comes first?",
      reflLabel: "Daily Reflection Prompt / የዕለቱ ማሰላሰያ",
      btnNewRefl: "✨ ሌላ ማሰላሰያ አውጣ (New Reflection)",
      footerDesc: "ሰው መሆን ይቀድማል። Being Human Comes First. A people-centred platform connecting growth, employment, talent, and faith.",
      footerIdentity: "ኢየሩሳሌም ኃይሉ (ጄሪ) • ማኅበራዊ ሚዲያ @wederjojo (TikTok, YouTube, Facebook, Instagram)",
      footerNavTitle: "የገጽ መውጫዎች",
      fNav1: "መሠረታችን", fNav2: "የለሰው ድልድይ", fNavCv: "CV Builder", fNav3: "8ቱ አዕማዶች", fNav4: "የልጆች ትምህርት", fNav5: "የኤአይ ረዳት",
      footerCommunityTitle: "የማኅበረሰብ ግንኙነት",
      footerCommDesc: "በኢትዮጵያ 🇪🇹፣ በተባበሩት አረብ ኤሚሬቶች 🇦🇪 እና በዓለም አቀፍ ደረጃ በቋንቋዎቻችን ማገናኘት።",
      footerQuote: "«በእምነት የተመሠረተ • በፍቅር የሚመራ • ሰውን የሚያበቃ»"
    },
    en: {
      brandName: "LeSew Initiative",
      brandHandle: "Eyerusalem Hailu (Jerry) • @wederjojo",
      navAbout: "About Us",
      navLesew: "LeSew Platform",
      navCv: "📄 CV Builder",
      navPillars: "Pillars",
      navKids: "Kids & Learning",
      navAi: "🤖 AI Career Assistant",
      btnQuickAi: "AI Career Assistant",
      heroBadge: "LESEW INITIATIVE • HUMANITY FIRST",
      heroTitle: "Being Human Comes First.",
      heroSubtitle: "ሰው መሆን ይቀድማል።",
      heroDesc: "Before achievement, technology, education, career, business, status, or success, we see the person. A people-centred platform for growth and empowerment.",
      ctaCvHero: "📄 Build CV & Cover Letter Now",
      ctaAiHero: "Ask Our AI Companion Anything",
      matrixT1: "PURPOSE", matrixV1: "People are the purpose",
      matrixT2: "TOOL", matrixV2: "Technology is the tool",
      matrixT3: "JOURNEY", matrixV3: "Learning is the journey",
      matrixT4: "OUTCOME", matrixV4: "Empowerment is outcome",
      cvBadge: "📄 FREE AUTOMATED CV & COVER LETTER GENERATOR",
      cvSectionTitle: "CV & Cover Letter Builder for Job Seekers",
      cvSectionDesc: "Enter your details, optional photo, and work experience. Our tool instantly formats a clean, ATS-compliant CV and personalized Cover Letter tailored for UAE and international jobs!",
      formHeader: "📝 Enter Your Career Details",
      lblFullName: "Full Name",
      lblPhone: "Phone / WhatsApp",
      lblEmail: "Email Address",
      lblLocation: "Location / City",
      lblJobTitle: "Target Job Title",
      lblPhoto: "Photo URL (Optional)",
      lblSkills: "Key Skills & Languages",
      lblExperience: "Work Experience Summary",
      lblEducation: "Education & Certifications",
      lblCompany: "Target Company Name (for Cover Letter)",
      btnGenerateCv: "✨ Generate My CV & Cover Letter",
      btnPrint: "Print / Save PDF",
      btnCopy: "Copy Text",
      placeholderMsg: "Fill out the form on the left and click 'Generate My CV & Cover Letter'!",
      aboutFounderName: "Eyerusalem Hailu (Jerry)",
      aboutFounderTitle: "Founder & Community Mentor • @wederjojo",
      aboutP1: "Before achievement, technology, education, career, or status, we see the person. Every individual possesses dignity, potential, and room to grow.",
      aboutP2: "Wederjojo and the LeSew Initiative exist to create spaces where people learn, grow, discover their potential, and transition into meaningful opportunities.",
      aboutQuote: "\"Technology can expand access to opportunity, but technology should serve people—never replace humanity.\"",
      archBadge: "⚖️ BRAND ARCHITECTURE & PHILOSOPHY",
      archTitle: "How 'Humanity First' and 'LeSew Initiative' Work Together",
      archH1: "1. Core Philosophy (Brand Heart)",
      archSub1: "\"Humanity First\" (ሰው መሆን ይቀድማል)",
      archD1: "Our guiding ethical compass and identity foundation. Every piece of content and technology stems from this principle.",
      archH2: "2. Platform Name (Community Bridge)",
      archSub2: "\"LeSew Initiative\" (ለሰው)",
      archD2: "The actionable platform bridging job seekers and vetted employers across the UAE and Ethiopia with dignity.",
      lesewTag: "LESEW COMMUNITY BRIDGE",
      lesewTitle: "The LeSew Job & Talent Bridge",
      lesewDesc: "Connecting verified employers and talent across the UAE and Ethiopia based on trust, dignity, and empowerment.",
      bridgeC1T: "Verified Matching", bridgeC1D: "Connecting job seekers with vetted employers through dignity and mutual respect.",
      bridgeC2T: "Talent Development", bridgeC2D: "Upskilling candidates in digital tools, workplace readiness, and language skills.",
      bridgeC3T: "Protection & Support", bridgeC3D: "Prioritizing individual safety, rights, and ethical work environments.",
      pillarsTitle: "Our 8 Core Brand Pillars",
      pillarsSubtitle: "Every article, coaching program, tool, and initiative flows through these structured pillars.",
      kidsBadge: "📖 KIDS & FAMILY RESOURCE",
      creaturesTitle: "Four Wise Creatures (አራት ጠቢባን)",
      creaturesSub: "Based on Proverbs 30:24-28 for Kids & Families",
      creaturesVerse: "\"Four things on earth are small, yet they are extremely wise!\"",
      gameTitle: "🧠 Kids Memory Game",
      gameSubtitle: "Match the wise creatures to test your memory!",
      btnResetGame: "🔄 Reset Game",
      aiBadge: "🤖 24/7 AI COMPANION & UAE JOB GUIDE",
      aiTitle: "Wederjojo AI Companion",
      aiDesc: "Ask our AI guide about UAE job search channels, verified resources, local employment guidance, and personal empowerment.",
      aiStatus: "● Expert • UAE Verified Jobs, MOHRE Guidelines & Life Mentorship",
      aiPill: "Smart AI Assistant",
      aiWelcome: "Welcome! I am your Wederjojo AI assistant, built for the LeSew Initiative. I can help you find verified UAE job search channels (like MOHRE, Dubizzle, LinkedIn), prepare ATS-friendly CVs, understand UAE labor regulations, and guide your personal growth with our core value: \"Being Human Comes First.\" How can I help you today?",
      btnClearChat: "Clear Chat",
      pillAll: "All Topics",
      pillJobs: "🇦🇪 UAE Jobs & Labor",
      pillCv: "📄 CV & Interview",
      pillHuman: "❤️ Humanity First",
      btnSend: "Send",
      reflBadge: "OUR GUIDING QUESTION",
      guidingMotto: "Does it remember that being human comes first?",
      reflLabel: "Daily Reflection Prompt",
      btnNewRefl: "✨ New Reflection Prompt",
      footerDesc: "Being Human Comes First. A people-centred platform connecting growth, employment, talent, and faith.",
      footerIdentity: "Eyerusalem Hailu (Jerry) • Social Identity @wederjojo (TikTok, YouTube, Facebook, Instagram)",
      footerNavTitle: "Navigation",
      fNav1: "Our Foundation", fNav2: "LeSew Bridge", fNavCv: "CV Builder", fNav3: "8 Pillars", fNav4: "Kids Resource", fNav5: "AI Assistant",
      footerCommunityTitle: "Community Bridge",
      footerCommDesc: "Connecting across Ethiopia 🇪🇹, the UAE 🇦🇪, and globally in native languages.",
      footerQuote: "\"Rooted in Faith. Leading with Love. Empowering People.\""
    },
    ar: {
      brandName: "مبادرة لِسو (LeSew)",
      brandHandle: "إيروشاليم هايلو (جيري) • @wederjojo",
      navAbout: "عن المبادرة",
      navLesew: "منصة لِسو",
      navCv: "📄 صانع السيرة الذاتية",
      navPillars: "الركائز",
      navKids: "الأطفال والتعليم",
      navAi: "🤖 المساعد الذكي للعمل",
      btnQuickAi: "المساعد الذكي",
      heroBadge: "مبادرة لِسو • الإنسانية أولاً",
      heroTitle: "الإنسانية تأتي أولاً.",
      heroSubtitle: "Being Human Comes First.",
      heroDesc: "قبل الإنجاز، والتكنولوجيا، والمهنة، والنجاح، نرى الإنسان أولاً. منصة مكرسة لكرامة الإنسان وتنميته.",
      ctaCvHero: "📄 أنشئ سيرتك الذاتية ورسالة التغطية الآن",
      ctaAiHero: "اسأل المساعد الذكي عن أي موضوع",
      matrixT1: "الهدف", matrixV1: "الإنسان هو الهدف",
      matrixT2: "الأداة", matrixV2: "التكنولوجيا أداة خدمة",
      matrixT3: "الرحلة", matrixV3: "التعلم رحلة مستمرة",
      matrixT4: "النتيجة", matrixV4: "التمكين هو نجاحنا",
      cvBadge: "📄 صانع السيرة الذاتية ورسائل التغطية المجاني",
      cvSectionTitle: "صانع السيرة الذاتية ورسائل التغطية المباشر",
      cvSectionDesc: "أدخل بياناتك وخبراتك؛ ستوفر لك المنصة سيرة ذاتية جاهزة ومطابقة لمعايير التوظيف في الإمارات مع رسالة تغطية احترافية!",
      formHeader: "📝 أدخل بياناتك المهنية",
      lblFullName: "الاسم الكامل",
      lblPhone: "الهاتف / واتساب",
      lblEmail: "البريد الإلكتروني",
      lblLocation: "الموقع / المدينة",
      lblJobTitle: "المسمى الوظيفي المستهدف",
      lblPhoto: "رابط الصورة (اختياري)",
      lblSkills: "المهارات واللغات",
      lblExperience: "ملخص الخبرة العملية",
      lblEducation: "التعليم والشهادات",
      lblCompany: "اسم الشركة المستهدفة",
      btnGenerateCv: "✨ إنشاء السيرة الذاتية ورسالة التغطية",
      btnPrint: "طباعة / حفظ PDF",
      btnCopy: "نسخ النص",
      placeholderMsg: "أدخل بياناتك في النموذج على اليسار وانقر على 'إنشاء السيرة الذاتية'!",
      aboutFounderName: "إيروشاليم هايلو (جيري)",
      aboutFounderTitle: "المؤسسة والموجهة المجتمعية • @wederjojo",
      aboutP1: "قبل التكنولوجيا والمهن والنجاحات، نرى الإنسان. يمتلك كل فرد الكرامة والقدرة المستمرة على النمو.",
      aboutP2: "توجد مبادرة Wederjojo و LeSew لخلق جسور تمكّن الأفراد من التعلم والنمو والانتقال لفرص عمل كريمة.",
      aboutQuote: "«التكنولوجيا تفتح آفاق الفرص، لكنها وجدت لخدمة الإنسان وليس لاستبداله.»",
      archBadge: "⚖ فلسفة العلامة وهيكل المنصة",
      archTitle: "كيف تتكامل «الإنسانية تأتي أولاً» مع «مبادرة لِسو»؟",
      archH1: "1. الفلسفة الجوهرية (Brand Heart)",
      archSub1: "«الإنسانية تأتي أولاً» (ሰው መሆን ይቀድማል)",
      archD1: "الموجّه الأخلاقي المباشر لكافة المحتويات والمبادرات الموجهة للمجتمع.",
      archH2: "2. اسم المنصة (Platform Name)",
      archSub2: "«مبادرة لِسو - للإنسان» (LeSew Initiative)",
      archD2: "اسم المنصة الميدانية لربط الباحثين عن عمل مع أصحاب العمل الموثوقين في الإمارات وإثيوبيا.",
      lesewTag: "LESEW COMMUNITY BRIDGE",
      lesewTitle: "جسر لِسو (LeSew) للعمل والمهارات",
      lesewDesc: "منصة تربط بين أصحاب العمل الموثوقين والكوادر بين دولة الإمارات وإثيوبيا بكرامة وموثوقية.",
      bridgeC1T: "التطابق الموثوق", bridgeC1D: "ربط الكوادر بأصحاب العمل الموثوقين وفق أعلى معايير الأحترام والكرامة.",
      bridgeC2T: "تطوير المهارات", bridgeC2D: "تدريب المتقدمين على المهارات الرقمية واللغوية والجاهزية لبيئة العمل.",
      bridgeC3T: "الحماية والدعم", bridgeC3D: "إعطاء الأولوية القصوى لسلامة الأفراد وحقوقهم وكرامتهم.",
      pillarsTitle: "ركائزنا الثمانية الأساسية",
      pillarsSubtitle: "جميع المحتويات والبرامج والمبادرات تنطلق من هذه الركائز.",
      kidsBadge: "📖 تعليم الأطفال والعائلة",
      creaturesTitle: "المخلوقات الأربعة الحكيمة (Four Wise Creatures)",
      creaturesSub: "مستوحاة من أمثال 30: 24-28 للأطفال والعائلات",
      creaturesVerse: "«أربعة هي الأصغر في الأرض، ولكنها حكيمة جداً!»",
      gameTitle: "🧠 لعبة الذاكرة للأطفال",
      gameSubtitle: "طابق المخلوقات الحكيمة واختبر ذاكرتك!",
      btnResetGame: "🔄 إعادة اللعبة",
      aiBadge: "🤖 المساعد الذكي للعمل في الإمارات ومستجدات الفرص",
      aiTitle: "Wederjojo AI Companion",
      aiDesc: "اسأل مساعدنا الذكي عن القنوات الموثوقة للبحث عن عمل في الإمارات، وقوانين التوظيف الرسمية وتوجيهات التمكين الشخصي.",
      aiStatus: "● خبير • UAE Verified Jobs, MOHRE Guidelines & Life Mentorship",
      aiPill: "Smart AI Assistant",
      aiWelcome: "أهلاً بك! أنا مساعدك الذكي Wederjojo، المصمم لمبادرة لِسو. يمكنني مساعدتك في العثور على منصات التوظيف الموثوقة في الإمارات (مثل MOHRE و Dubizzle)، وتجهيز سيرة ذاتية متوافقة مع أنظمة ATS، وفهم قوانين العمل، وتوجيه مسارك الشخصي بمبدأ: «الإنسانية تأتي أولاً». كيف يمكنني مساعدتك اليوم؟",
      btnClearChat: "مسح المحادثة",
      pillAll: "جميع المواضيع",
      pillJobs: "🇦🇪 وظائف وقوانين الإمارات",
      pillCv: "📄 السيرة الذاتية والمقابلات",
      pillHuman: "❤️ الإنسانية أولاً",
      btnSend: "إرسال",
      reflBadge: "سؤالنا الموجه دائماً",
      guidingMotto: "هل يراعي هذا المبدأ أن الإنسانية تأتي أولاً؟",
      reflLabel: "تأمل اليوم",
      btnNewRefl: "✨ تأمل جديد",
      footerDesc: "الإنسانية تأتي أولاً. منصة إنسانية تربط بين النمو، والعمل، والتمكين، والإيمان.",
      footerIdentity: "إيروشاليم هايلو (جيري) • حساب التواصل الاجتماعي @wederjojo (TikTok, YouTube, Facebook, Instagram)",
      footerNavTitle: "تنقل في الموقع",
      fNav1: "عن المبادرة", fNav2: "جسر لِسو", fNavCv: "صانع السيرة الذاتية", fNav3: "الركائز الـ 8", fNav4: "تعليم الأطفال", fNav5: "المساعد الذكي",
      footerCommunityTitle: "الجسر المجتمعي",
      footerCommDesc: "نربط بين إثيوبيا 🇪🇹 والإمارات 🇦🇪 والمجتمع العالمي بلغاتنا الأصلية.",
      footerQuote: "«راسخون في الإيمان • نقود بالمحبة • نمكّن الإنسان»"
    }
  };

  function setLanguage(lang) {
    currentLang = lang;
    const data = i18n[lang];
    if (!data) return;

    document.getElementById('lang-btn-am').className = "px-2.5 py-1 rounded-lg hover:text-amber-400 text-slate-300 transition-all";
    document.getElementById('lang-btn-en').className = "px-2.5 py-1 rounded-lg hover:text-amber-400 text-slate-300 transition-all";
    document.getElementById('lang-btn-ar').className = "px-2.5 py-1 rounded-lg hover:text-amber-400 text-slate-300 transition-all";
    document.getElementById(`lang-btn-${lang}`).className = "px-2.5 py-1 rounded-lg bg-amber-500 text-slate-950 font-black transition-all";

    document.getElementById('brand-name').innerText = data.brandName;
    document.getElementById('brand-handle').innerText = data.brandHandle;
    document.getElementById('nav-about').innerText = data.navAbout;
    document.getElementById('nav-lesew').innerText = data.navLesew;
    document.getElementById('nav-cv').innerText = data.navCv;
    document.getElementById('nav-pillars').innerText = data.navPillars;
    document.getElementById('nav-kids').innerText = data.navKids;
    document.getElementById('nav-ai').innerText = data.navAi;
    document.getElementById('btn-quick-ai').innerText = data.btnQuickAi;

    document.getElementById('hero-badge').innerText = data.heroBadge;
    document.getElementById('hero-title').innerText = data.heroTitle;
    document.getElementById('hero-subtitle').innerText = data.heroSubtitle;
    document.getElementById('hero-desc').innerText = data.heroDesc;
    document.getElementById('cta-cv-hero').innerText = data.ctaCvHero;
    document.getElementById('cta-ai-hero').innerText = data.ctaAiHero;

    document.getElementById('matrix-t1').innerText = data.matrixT1;
    document.getElementById('matrix-v1').innerText = data.matrixV1;
    document.getElementById('matrix-t2').innerText = data.matrixT2;
    document.getElementById('matrix-v2').innerText = data.matrixV2;
    document.getElementById('matrix-t3').innerText = data.matrixT3;
    document.getElementById('matrix-v3').innerText = data.matrixV3;
    document.getElementById('matrix-t4').innerText = data.matrixT4;
    document.getElementById('matrix-v4').innerText = data.matrixV4;

    document.getElementById('cv-badge').innerText = data.cvBadge;
    document.getElementById('cv-section-title').innerText = data.cvSectionTitle;
    document.getElementById('cv-section-desc').innerText = data.cvSectionDesc;
    document.getElementById('form-header').innerHTML = `<span>${data.formHeader}</span><span class="text-[10px] bg-emerald-500/20 text-emerald-300 px-2 py-0.5 rounded font-bold">100% Free</span>`;
    
    document.getElementById('lbl-fullname').innerText = data.lblFullName;
    document.getElementById('lbl-phone').innerText = data.lblPhone;
    document.getElementById('lbl-email').innerText = data.lblEmail;
    document.getElementById('lbl-location').innerText = data.lblLocation;
    document.getElementById('lbl-jobtitle').innerText = data.lblJobTitle;
    document.getElementById('lbl-photo').innerText = data.lblPhoto;
    document.getElementById('lbl-skills').innerText = data.lblSkills;
    document.getElementById('lbl-experience').innerText = data.lblExperience;
    document.getElementById('lbl-education').innerText = data.lblEducation;
    document.getElementById('lbl-company').innerText = data.lblCompany;
    document.getElementById('btn-generate-cv').innerText = data.btnGenerateCv;
    document.getElementById('btn-print').innerText = data.btnPrint;
    document.getElementById('btn-copy').innerText = data.btnCopy;

    document.getElementById('about-founder-name').innerText = data.aboutFounderName;
    document.getElementById('about-founder-title').innerText = data.aboutFounderTitle;
    document.getElementById('about-p1').innerText = data.aboutP1;
    document.getElementById('about-p2').innerText = data.aboutP2;
    document.getElementById('about-quote').innerText = data.aboutQuote;
    document.getElementById('arch-badge').innerText = data.archBadge;
    document.getElementById('arch-title').innerText = data.archTitle;
    document.getElementById('arch-h1').innerText = data.archH1;
    document.getElementById('arch-sub1').innerText = data.archSub1;
    document.getElementById('arch-d1').innerText = data.archD1;
    document.getElementById('arch-h2').innerText = data.archH2;
    document.getElementById('arch-sub2').innerText = data.archSub2;
    document.getElementById('arch-d2').innerText = data.archD2;

    document.getElementById('lesew-tag').innerText = data.lesewTag;
    document.getElementById('lesew-title').innerText = data.lesewTitle;
    document.getElementById('lesew-desc').innerText = data.lesewDesc;
    document.getElementById('bridge-c1-t').innerText = data.bridgeC1T;
    document.getElementById('bridge-c1-d').innerText = data.bridgeC1D;
    document.getElementById('bridge-c2-t').innerText = data.bridgeC2T;
    document.getElementById('bridge-c2-d').innerText = data.bridgeC2D;
    document.getElementById('bridge-c3-t').innerText = data.bridgeC3T;
    document.getElementById('bridge-c3-d').innerText = data.bridgeC3D;

    document.getElementById('pillars-title').innerText = data.pillarsTitle;
    document.getElementById('pillars-subtitle').innerText = data.pillarsSubtitle;

    document.getElementById('kids-badge').innerText = data.kidsBadge;
    document.getElementById('creatures-title').innerText = data.creaturesTitle;
    document.getElementById('creatures-sub').innerText = data.creaturesSub;
    document.getElementById('creatures-verse').innerText = data.creaturesVerse;
    document.getElementById('game-title').innerText = data.gameTitle;
    document.getElementById('game-subtitle').innerText = data.gameSubtitle;
    document.getElementById('btn-reset-game').innerText = data.btnResetGame;

    document.getElementById('ai-badge').innerText = data.aiBadge;
    document.getElementById('ai-title').innerText = data.aiTitle;
    document.getElementById('ai-desc').innerText = data.aiDesc;
    document.getElementById('ai-status').innerText = data.aiStatus;
    document.getElementById('ai-pill').innerText = data.aiPill;
    document.getElementById('ai-welcome').innerText = data.aiWelcome;
    document.getElementById('btn-clear-chat').innerText = data.btnClearChat;
    document.getElementById('pill-all').innerText = data.pillAll;
    document.getElementById('pill-jobs').innerText = data.pillJobs;
    document.getElementById('pill-cv').innerText = data.pillCv;
    document.getElementById('pill-human').innerText = data.pillHuman;
    document.getElementById('btn-send').innerText = data.btnSend;

    document.getElementById('refl-badge').innerText = data.reflBadge;
    document.getElementById('guiding-motto').innerText = data.guidingMotto;
    document.getElementById('refl-label').innerText = data.reflLabel;
    document.getElementById('btn-new-refl').innerText = data.btnNewRefl;

    document.getElementById('footer-desc').innerText = data.footerDesc;
    document.getElementById('footer-identity').innerText = data.footerIdentity;
    document.getElementById('footer-nav-title').innerText = data.footerNavTitle;
    document.getElementById('f-nav-1').innerText = data.fNav1;
    document.getElementById('f-nav-2').innerText = data.fNav2;
    document.getElementById('f-nav-cv').innerText = data.fNavCv;
    document.getElementById('f-nav-3').innerText = data.fNav3;
    document.getElementById('f-nav-4').innerText = data.fNav4;
    document.getElementById('f-nav-5').innerText = data.fNav5;
    document.getElementById('footer-community-title').innerText = data.footerCommunityTitle;
    document.getElementById('footer-comm-desc').innerText = data.footerCommDesc;
    document.getElementById('footer-quote').innerText = data.footerQuote;

    if (lang === 'ar') {
      document.documentElement.dir = 'rtl';
    } else {
      document.documentElement.dir = 'ltr';
    }

    renderPillars(lang);
    renderCreatures(lang);
    renderAiPrompts(lang, currentAiCategory);
    generateReflection();
  }

  function renderPillars(lang) {
    const grid = document.getElementById('pillars-grid');
    grid.innerHTML = '';
    pillarsData[lang].forEach((p) => {
      grid.innerHTML += `
        <div class="glass-card p-6 rounded-3xl hover:border-amber-400/50 transition-all transform hover:-translate-y-1">
          <div class="w-12 h-12 rounded-2xl bg-amber-500/20 border border-amber-400/30 flex items-center justify-center text-2xl mb-4">
            ${p.icon}
          </div>
          <h3 class="text-base font-black text-white mb-2">${p.title}</h3>
          <p class="text-xs text-slate-300 leading-relaxed">${p.desc}</p>
        </div>
      `;
    });
  }

  function renderCreatures(lang) {
    const grid = document.getElementById('creatures-grid');
    grid.innerHTML = '';
    creaturesData[lang].forEach((c) => {
      grid.innerHTML += `
        <div class="glass-card p-6 rounded-3xl text-center border-amber-500/30 hover:border-amber-400 transition-all">
          <div class="text-6xl mb-3 animate-float">${c.emoji}</div>
          <div class="text-xs font-bold text-amber-400 uppercase">${c.ref}</div>
          <h3 class="text-lg font-black text-white mt-1">${c.name}</h3>
          <p class="text-xs text-slate-300 mt-2 leading-relaxed">${c.desc}</p>
          <button onclick="triggerCreatureAction()" class="mt-4 px-4 py-2 rounded-xl bg-amber-500 text-slate-950 font-bold text-xs hover:bg-amber-400 transition-all">
            ${c.btn}
          </button>
        </div>
      `;
    });
  }

  function renderAiPrompts(lang, category = 'all') {
    currentAiCategory = category;
    const container = document.getElementById('ai-prompts');
    container.innerHTML = '';

    const list = aiPromptsData[lang] || aiPromptsData['am'];
    const filtered = category === 'all' ? list : list.filter(item => item.cat === category);

    filtered.forEach((item) => {
      container.innerHTML += `
        <button onclick="askPreset('${item.text}')" class="text-[11px] px-3 py-1.5 rounded-xl glass-card hover:bg-cyan-500 hover:text-slate-950 text-slate-300 transition-all border border-cyan-400/20 flex items-center gap-1.5">
          <i class="fas fa-question-circle text-cyan-400"></i>
          <span>"${item.text}"</span>
        </button>
      `;
    });
  }

  function filterAiPrompts(category) {
    playClick(480, 0.08);
    document.getElementById('pill-all').className = category === 'all' ? "px-3 py-1 rounded-xl bg-cyan-500 text-slate-950 font-bold transition-all" : "px-3 py-1 rounded-xl glass-card hover:bg-slate-800 text-slate-300 transition-all";
    document.getElementById('pill-jobs').className = category === 'jobs' ? "px-3 py-1 rounded-xl bg-cyan-500 text-slate-950 font-bold transition-all" : "px-3 py-1 rounded-xl glass-card hover:bg-slate-800 text-slate-300 transition-all";
    document.getElementById('pill-cv').className = category === 'cv' ? "px-3 py-1 rounded-xl bg-cyan-500 text-slate-950 font-bold transition-all" : "px-3 py-1 rounded-xl glass-card hover:bg-slate-800 text-slate-300 transition-all";
    document.getElementById('pill-human').className = category === 'human' ? "px-3 py-1 rounded-xl bg-cyan-500 text-slate-950 font-bold transition-all" : "px-3 py-1 rounded-xl glass-card hover:bg-slate-800 text-slate-300 transition-all";
    
    renderAiPrompts(currentLang, category);
  }

  // AUDIO EFFECT
  const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
  function playClick(freq = 520, duration = 0.1) {
    try {
      if (audioCtx.state === 'suspended') audioCtx.resume();
      const osc = audioCtx.createOscillator();
      const gain = audioCtx.createGain();
      osc.frequency.setValueAtTime(freq, audioCtx.currentTime);
      gain.gain.setValueAtTime(0.08, audioCtx.currentTime);
      gain.gain.exponentialRampToValueAtTime(0.0001, audioCtx.currentTime + duration);
      osc.connect(gain);
      gain.connect(audioCtx.destination);
      osc.start();
      osc.stop(audioCtx.currentTime + duration);
    } catch(e) {}
  }

  function triggerCreatureAction() {
    playClick(600, 0.15);
    confetti({ particleCount: 35, spread: 60 });
  }

  // AUTOMATED CV & COVER LETTER GENERATOR LOGIC
  function generateCVAndCoverLetter() {
    const fullName = document.getElementById('cvFullName').value.trim() || 'Selamawit Tadesse';
    const phone = document.getElementById('cvPhone').value.trim() || '+971 50 123 4567';
    const email = document.getElementById('cvEmail').value.trim() || 'selamawit@example.com';
    const location = document.getElementById('cvLocation').value.trim() || 'Dubai, UAE';
    const targetRole = document.getElementById('cvTargetRole').value.trim() || 'Customer Service & Sales Representative';
    const photoUrl = document.getElementById('cvPhotoUrl').value.trim();
    const skills = document.getElementById('cvSkills').value.trim() || 'Customer Relations, English Fluency, Amharic, Problem Solving, Team Work';
    const experience = document.getElementById('cvExperience').value.trim() || 'Sales Associate at Retail Stores (2 years) - Assisted clients, managed cash registers, ensured client satisfaction and team support.';
    const education = document.getElementById('cvEducation').value.trim() || 'Diploma / Secondary Education Certificate';
    const company = document.getElementById('cvCompanyName').value.trim() || 'Hiring Manager & Recruitment Team';

    currentCvData = { fullName, phone, email, location, targetRole, photoUrl, skills, experience, education, company };

    renderCvPreview();
    playClick(650, 0.2);
    confetti({ particleCount: 45, spread: 70 });
  }

  function switchCvTab(tab) {
    activeCvTab = tab;
    document.getElementById('tab-btn-cv').className = tab === 'cv' ? 'px-4 py-2 rounded-xl bg-amber-500 text-slate-950 font-black text-xs transition-all' : 'px-4 py-2 rounded-xl glass-card hover:text-amber-400 text-slate-300 font-black text-xs transition-all';
    document.getElementById('tab-btn-cover').className = tab === 'cover' ? 'px-4 py-2 rounded-xl bg-amber-500 text-slate-950 font-black text-xs transition-all' : 'px-4 py-2 rounded-xl glass-card hover:text-amber-400 text-slate-300 font-black text-xs transition-all';
    renderCvPreview();
  }

  function renderCvPreview() {
    const container = document.getElementById('cvOutputContainer');
    if (!currentCvData) return;

    const { fullName, phone, email, location, targetRole, photoUrl, skills, experience, education, company } = currentCvData;

    if (activeCvTab === 'cv') {
      container.innerHTML = `
        <div class="space-y-6">
          <!-- Header Bar -->
          <div class="flex items-center justify-between border-b-2 border-slate-900 pb-4">
            <div>
              <h1 class="text-2xl font-black uppercase tracking-wide text-slate-900">${fullName}</h1>
              <p class="text-sm font-bold text-amber-600 mt-0.5">${targetRole}</p>
              <div class="flex flex-wrap gap-3 text-[11px] text-slate-600 font-medium mt-2">
                <span>📍 ${location}</span>
                <span>📞 ${phone}</span>
                <span>✉️ ${email}</span>
              </div>
            </div>
            ${photoUrl ? `<img src="${photoUrl}" class="w-20 h-20 rounded-xl object-cover border-2 border-amber-500 shadow-md">` : `<div class="w-16 h-16 rounded-xl bg-slate-200 flex items-center justify-center text-slate-500 font-black text-xl">👤</div>`}
          </div>

          <!-- Professional Summary -->
          <div>
            <h3 class="font-black text-xs uppercase tracking-wider text-slate-900 border-b border-slate-200 pb-1 mb-2">Professional Summary / ሙያዊ ማጠቃለያ</h3>
            <p class="text-slate-700 leading-relaxed text-[11px]">
              Dedicated, reliable, and goal-oriented professional seeking to leverage skills as a <strong>${targetRole}</strong>. Committed to providing human-centered excellence, dignity in workplace service, and productive contributions to team goals.
            </p>
          </div>

          <!-- Key Skills -->
          <div>
            <h3 class="font-black text-xs uppercase tracking-wider text-slate-900 border-b border-slate-200 pb-1 mb-2">Key Competencies & Languages / ክህሎቶች</h3>
            <div class="flex flex-wrap gap-1.5">
              ${skills.split(',').map(s => `<span class="bg-slate-100 text-slate-800 font-bold px-2.5 py-1 rounded-md text-[10px] border border-slate-300">${s.trim()}</span>`).join('')}
            </div>
          </div>

          <!-- Experience -->
          <div>
            <h3 class="font-black text-xs uppercase tracking-wider text-slate-900 border-b border-slate-200 pb-1 mb-2">Work Experience / የሥራ ተሞክሮ</h3>
            <p class="text-slate-700 whitespace-pre-line text-[11px] leading-relaxed">${experience}</p>
          </div>

          <!-- Education -->
          <div>
            <h3 class="font-black text-xs uppercase tracking-wider text-slate-900 border-b border-slate-200 pb-1 mb-2">Education & Training / ትምህርት</h3>
            <p class="text-slate-700 font-medium text-[11px]">${education}</p>
          </div>

          <!-- LeSew Platform Verification Tag -->
          <div class="pt-4 border-t border-slate-200 flex items-center justify-between text-[10px] text-slate-500">
            <span>✨ Created via LeSew Initiative (@wederjojo) • Dignity First</span>
            <span>Ref: LSW-${Math.floor(100000 + Math.random() * 900000)}</span>
          </div>
        </div>
      `;
    } else {
      container.innerHTML = `
        <div class="space-y-4 text-slate-800 text-[11px] leading-relaxed">
          <div class="border-b border-slate-200 pb-3">
            <h2 class="text-lg font-black text-slate-900">${fullName}</h2>
            <p class="text-slate-600">📍 ${location} | 📞 ${phone} | ✉️ ${email}</p>
          </div>

          <div class="text-slate-600 font-semibold">
            Date: ${new Date().toLocaleDateString()}<br>
            To: Hiring Manager / HR Team at <strong>${company}</strong><br>
            Subject: Application for <strong>${targetRole}</strong> position
          </div>

          <p>Dear Hiring Manager,</p>

          <p>I am writing to express my enthusiastic interest in the <strong>${targetRole}</strong> role at <strong>${company}</strong>. With a strong commitment to work ethic, reliability, and human-centered dedication, I am eager to contribute my skills to your esteemed organization.</p>

          <p>My background includes hands-on experience in: <em>${experience}</em>. Furthermore, I bring key strengths in <strong>${skills}</strong>, enabling me to communicate effectively and deliver excellent service to clients and colleagues alike.</p>

          <p>Guided by the principle that diligence and mutual respect are essential to every career, I am ready to adapt, learn, and add immediate value to your team in ${location}.</p>

          <p>Thank you for considering my application. I welcome the opportunity to discuss how my enthusiasm and capabilities fit your team's goals.</p>

          <p class="pt-2 font-bold">
            Sincerely,<br>
            <span class="text-slate-900 font-black text-sm">${fullName}</span>
          </p>
        </div>
      `;
    }
  }

  function printGeneratedCV() {
    if (!currentCvData) {
      alert("Please generate your CV first!");
      return;
    }
    window.print();
  }

  function copyGeneratedText() {
    const container = document.getElementById('cvOutputContainer');
    if (!container || !currentCvData) {
      alert("Please generate your CV first!");
      return;
    }
    navigator.clipboard.writeText(container.innerText);
    alert("CV / Cover Letter text copied to clipboard!");
  }

  // Memory Game
  const memoryIcons = ['🐜', '🐜', '🦔', '🦔', '🦗', '🦗', '🦎', '🦎'];
  let flipped = [];

  function initMemoryGame() {
    const board = document.getElementById('memoryBoard');
    board.innerHTML = '';
    flipped = [];

    const shuffled = [...memoryIcons].sort(() => Math.random() - 0.5);
    shuffled.forEach((emoji) => {
      const card = document.createElement('div');
      card.className = "h-16 rounded-xl glass-card flex items-center justify-center text-2xl cursor-pointer select-none border border-white/10 hover:border-amber-400/40 transition-all";
      card.dataset.emoji = emoji;
      card.innerText = '❓';
      card.onclick = () => handleCardClick(card, emoji);
      board.appendChild(card);
    });
  }

  function handleCardClick(card, emoji) {
    if (card.classList.contains('matched') || flipped.length >= 2 || card.dataset.revealed === 'true') return;
    playClick(440, 0.08);
    card.innerText = emoji;
    card.dataset.revealed = 'true';
    card.classList.add('bg-amber-500/20', 'border-amber-400');
    flipped.push(card);

    if (flipped.length === 2) {
      setTimeout(() => {
        if (flipped[0].dataset.emoji === flipped[1].dataset.emoji) {
          flipped.forEach(c => {
            c.classList.add('matched', 'bg-emerald-500/20', 'border-emerald-400');
            c.classList.remove('bg-amber-500/20');
          });
          playClick(880, 0.2);
          confetti({ particleCount: 20, spread: 40 });
        } else {
          flipped.forEach(c => {
            c.innerText = '❓';
            c.dataset.revealed = 'false';
            c.classList.remove('bg-amber-500/20', 'border-amber-400');
          });
        }
        flipped = [];
      }, 700);
    }
  }

  // ENHANCED ADVANCED AI CHAT ASSISTANT LOGIC
  function askPreset(promptText) {
    document.getElementById('chatInput').value = promptText;
    sendChatMessage();
  }

  function clearChatHistory() {
    const history = document.getElementById('chatHistory');
    const welcomeText = i18n[currentLang].aiWelcome;
    history.innerHTML = `
      <div class="flex gap-3">
        <div class="w-9 h-9 rounded-xl bg-cyan-500/20 border border-cyan-400/30 flex items-center justify-center text-cyan-300 text-xs font-black shrink-0">W</div>
        <div class="p-4 rounded-2xl bg-slate-800/90 text-xs text-slate-200 leading-relaxed max-w-xl border border-cyan-400/25 shadow-md">
          ${welcomeText}
        </div>
      </div>
    `;
    playClick(400, 0.1);
  }

  function sendChatMessage() {
    const input = document.getElementById('chatInput');
    const history = document.getElementById('chatHistory');
    const text = input.value.trim();
    if (!text) return;

    // Append User Message
    history.innerHTML += `
      <div class="flex gap-3 justify-end">
        <div class="p-4 rounded-2xl bg-gradient-to-r from-cyan-500 to-sky-500 text-slate-950 text-xs font-bold leading-relaxed max-w-md shadow-lg">
          ${text}
        </div>
        <div class="w-9 h-9 rounded-xl bg-cyan-400/20 flex items-center justify-center text-cyan-300 text-xs font-bold shrink-0 border border-cyan-400/30">You</div>
      </div>
    `;
    input.value = '';
    history.scrollTop = history.scrollHeight;

    // Intelligent Contextual Response Engine
    setTimeout(() => {
      let reply = generateAiSmartResponse(text, currentLang);

      history.innerHTML += `
        <div class="flex gap-3">
          <div class="w-9 h-9 rounded-xl bg-cyan-500/20 border border-cyan-400/30 flex items-center justify-center text-cyan-300 text-xs font-black shrink-0">W</div>
          <div class="p-4 rounded-2xl bg-slate-800/95 text-xs text-slate-200 leading-relaxed max-w-xl border border-cyan-400/30 shadow-xl space-y-2">
            ${reply}
          </div>
        </div>
      `;
      history.scrollTop = history.scrollHeight;
      playClick(600, 0.15);
      confetti({ particleCount: 15, spread: 40 });
    }, 700);
  }

  function generateAiSmartResponse(query, lang) {
    const q = query.toLowerCase();

    if (lang === 'am') {
      if (q.includes('ቪዛ') || q.includes('ስራ') || q.includes('mohre') || q.includes('dubizzle') || q.includes('አገናኝ')) {
        return `
          <div class="font-bold text-cyan-300 mb-1">🇦🇪 የ UAE ሥራ ፍለጋና ቪዛ መመሪያ (LeSew Guide)</div>
          <p>በUAE ውስጥ ሥራ ሲፈልጉ የሚከተሉትን ይፋዊና ደህንነታቸው የተረጋገጠ መድረኮች ይጠቀሙ፡</p>
          <ul class="list-disc pl-4 space-y-1 mt-1 text-slate-300">
            <li><strong>MOHRE (Ministry of Human Resources and Emiratization):</strong> ለოፊሻል የሥራ ውልና ፈቃድ ማረጋገጫ።</li>
            <li><strong>Dubizzle & LinkedIn:</strong> ለተረጋገጡ የኮርፖሬት፣ የሆቴልና የደንበኛ አገልግሎት (Customer Support) ሥራዎች።</li>
            <li><strong>የቪዛ ማረጋገጫ:</strong> ማንኛውም የስራ ቪዛ ሲደርሰዎት በ ICA / Amer Dubai በኩል ትክክለኛነቱን ያረጋግጡ።</li>
          </ul>
          <p class="mt-2 text-amber-400 font-semibold">✨ ምክር፡ ከምንም ነገር በፊት 'ሰው መሆን ይቀድማል' — የራስዎን ውል በውል ያንብቡ!</p>
        `;
      } else if (q.includes('cv') || q.includes('ቃለ መጠይቅ') || q.includes('interview')) {
        return `
          <div class="font-bold text-cyan-300 mb-1">📄 ATS-Friendly CV እና የቃለ መጠይቅ ምክር</div>
          <p>ለ UAE ቀጣሪዎች የሚሆን ጠንካራ CV ለማዘጋጀት፡</p>
          <ul class="list-disc pl-4 space-y-1 mt-1 text-slate-300">
            <li>ቀላል እና ግልጽ ፎርማት ይጠቀሙ (ከላይ ያለውን የእኛን <strong>CV Maker</strong> በነጻ ይጠቀሙ!)</li>
            <li>እንደ <em>Customer Service, Sales, Communication, Team Work</em> ያሉ ቁልፍ ቃላትን (Keywords) ያካትቱ።</li>
            <li>በቃለ መጠይቅ ወቅት ፈገግታ፣ በራስ መተማመን እና የሰውን ዋጋ ማስቀደምዎን ያሳዩ።</li>
          </ul>
        `;
      } else {
        return `
          <div class="font-bold text-cyan-300 mb-1">🤖 የወደርጆጆ ኤአይ ረዳት መልስ</div>
          <p>ጥያቄዎን ተረድቻለሁ! እንደ <strong>LeSew Initiative</strong> መርህ፡ <em>«ሰው መሆን ይቀድማል»</em>። በ UAE የሥራ ዕድሎች፣ በ CV ዝግጅት ወይም በግል ዕድገት ዙሪያ ተጨማሪ ጥያቄ ካለዎት ከታች ካሉት አዝራሮች መምረጥ ይችላሉ።</p>
        `;
      }
    } else if (lang === 'ar') {
      if (q.includes('visa') || q.includes('عمل') || q.includes('mohre') || q.includes('dubizzle')) {
        return `
          <div class="font-bold text-cyan-300 mb-1">🇦🇪 دليل البحث عن عمل وتأشيرات الإمارات</div>
          <p>للابتعاد عن الوظائف الوهمية في الإمارات، اعتمد دائماً على المنصات الرسمية والموثوقة:</p>
          <ul class="list-disc pl-4 space-y-1 mt-1 text-slate-300">
            <li><strong>وزارة الموارد البشرية والتوطين (MOHRE):</strong> للتحقق من عقود العمل الرسمية.</li>
            <li><strong>LinkedIn & Dubizzle:</strong> للبحث عن الوظائف الشاغرة في الفنادق وخدمة العملاء.</li>
            <li><strong>التحقق من التأشيرة:</strong> تأكد دائماً عبر قنوات ICA أو آمر في دبي من صحة تأشيرتك.</li>
          </ul>
        `;
      } else {
        return `
          <div class="font-bold text-cyan-300 mb-1">🤖 مساعد Wederjojo الذكي</div>
          <p>أهلاً بك! تذكر دائماً مبدأنا الأساسي: <em>«الإنسانية تأتي أولاً»</em>. يمكنك سؤالي عن السيرة الذاتية، أو قوانين العمل في الإمارات، وسأكون سعيداً بمساعدتك!</p>
        `;
      }
    } else {
      if (q.includes('visa') || q.includes('job') || q.includes('mohre') || q.includes('dubizzle') || q.includes('work')) {
        return `
          <div class="font-bold text-cyan-300 mb-1">🇦🇪 Verified UAE Job Search & Visa Guide</div>
          <p>To secure a legitimate, dignified job in the UAE, always rely on verified channels:</p>
          <ul class="list-disc pl-4 space-y-1 mt-1 text-slate-300">
            <li><strong>MOHRE (Ministry of Human Resources & Emiratization):</strong> Check official labor contracts and company registration.</li>
            <li><strong>LinkedIn & Dubizzle:</strong> Leading platforms for hospitality, customer service, and sales roles.</li>
            <li><strong>Visa Verification:</strong> Always authenticate entry permits via official ICA or Amer channels before travel.</li>
          </ul>
          <p class="mt-2 text-amber-400 font-semibold">✨ Remember: Being Human Comes First—protect your rights and dignity always!</p>
        `;
      } else if (q.includes('cv') || q.includes('interview') || q.includes('resume')) {
        return `
          <div class="font-bold text-cyan-300 mb-1">📄 ATS CV & Interview Success Tips</div>
          <p>To stand out to UAE recruiters:</p>
          <ul class="list-disc pl-4 space-y-1 mt-1 text-slate-300">
            <li>Use a clean, single-column ATS-friendly layout (try our <strong>Free CV Builder</strong> above!).</li>
            <li>Highlight transferable skills like communication, client satisfaction, and problem-solving.</li>
            <li>Always approach interviews with genuine enthusiasm and respect.</li>
          </ul>
        `;
      } else {
        return `
          <div class="font-bold text-cyan-300 mb-1">🤖 Wederjojo AI Companion Response</div>
          <p>Thank you for your question! Guided by the LeSew Initiative motto—<em>"Being Human Comes First"</em>—I am here to help you navigate UAE career opportunities, CV optimization, and personal empowerment with integrity.</p>
        `;
      }
    }
  }

  // Reflection Prompts
  const reflectionPrompts = {
    am: [
      "ዛሬ በዙሪያህ ያሉትን ሰዎች ከስኬት፣ ከስራ ወይም ከማንነታቸው በፊት እንደ ሰው ተመልከተሃቸዋል?",
      "ለአንድ ችግር መፍትሔ ስትሰጥ ከቴክኖሎጂ ወይም ከሂደት በፊት የሰውን ልጅ ክብር አስቀድመሃል?",
      "ዛሬ ለአንድ ሰው ፈገግታ በመስጠት ወይም በመርዳት ምን ያህል አዎንታዊ ተፅዕኖ ፈጥረዋል?",
      "የምታደርገው ማንኛውም ሥራ 'ሰው መሆን ይቀድማል' ከሚለው መርህ ጋር ይጣጣማል?"
    ],
    en: [
      "Today, did you see the people around you as human beings before their title or status?",
      "When solving a problem today, did you prioritize human dignity above technical efficiency?",
      "How did you uplift someone today through genuine kindness or listening?",
      "Does your current goal align with the truth that being human comes first?"
    ],
    ar: [
      "هل نظرت اليوم لمن حولك كبشر قبل مناصبهم أو إنجازاتهم؟",
      "عند حل أي مشكلة اليوم، هل أعطيت الأولوية لكرامة الإنسان قبل أي شيء آخر؟",
      "كيف صنعت أثراً إيجابياً أو أدخلت السرور على شخص ما اليوم؟",
      "هل يتوافق عملك الحالي مع مبدأ أن الإنسانية تأتي أولاً؟"
    ]
  };

  function generateReflection() {
    const prompts = reflectionPrompts[currentLang] || reflectionPrompts['am'];
    const randomPrompt = prompts[Math.floor(Math.random() * prompts.length)];
    document.getElementById('reflectionPrompt').innerText = `"${randomPrompt}"`;
    playClick(700, 0.12);
    confetti({ particleCount: 25, spread: 50 });
  }

  // Initialization on Load
  window.onload = () => {
    renderPillars('am');
    renderCreatures('am');
    renderAiPrompts('am', 'all');
    initMemoryGame();
  };
</script>
</body>
</html>
```
eof

I have successfully updated the immersive document editor with the enhanced **Wederjojo AI Assistant** feature set! 

### What's New in the AI Assistant:
1. **UAE Job Market Intelligence & MOHRE Guidance:** Instant advice on verified job portals (LinkedIn, Dubizzle), official labor ministry checks, and UAE visa verification.
2. **Category Filter Pills:** Quick filters allowing users to switch between All Topics, UAE Jobs & Labor, CV & Interviews, and Humanity First principles.
3. **Multilingual Context Engine:** Fully localized AI responses in Amharic, English, and Arabic.
4. **Interactive Chat Controls:** Quick preset question buttons, clear chat history button, and smooth keyboard submission (`Enter`).

Let me know what you'd like to refine or add next!
``
