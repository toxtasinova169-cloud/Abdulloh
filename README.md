# Abdulloh
```html
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alkanlar va Alkenlar: To'g'ri yoki Noto'g'ri</title>
    <!-- Tailwind CSS for styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Outfit', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#f0f9ff',
                            100: '#e0f2fe',
                            500: '#0284c7',
                            600: '#0369a1',
                            700: '#075985',
                            900: '#0c4a6e',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        body {
            font-family: 'Outfit', sans-serif;
            background: linear-gradient(135deg, #0f172a 0%, #1e1b4b 50%, #0f172a 100%);
            min-height: 100vh;
        }

        .glass-card {
            background: rgba(30, 41, 59, 0.7);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5);
        }

        .glow-green {
            box-shadow: 0 0 25px rgba(34, 197, 94, 0.4);
        }

        .glow-red {
            box-shadow: 0 0 25px rgba(239, 68, 68, 0.4);
        }

        .glow-blue {
            box-shadow: 0 0 25px rgba(56, 189, 248, 0.3);
        }

        /* Pulse animation for active streak */
        @keyframes pulse-streak {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.15); }
        }
        .streak-active {
            animation: pulse-streak 0.6s ease-in-out infinite alternate;
        }

        /* Progress Bar Animation */
        .timer-bar {
            transition: width 0.1s linear;
        }

        /* Custom scrollbar for report section */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: rgba(15, 23, 42, 0.6);
            border-radius: 8px;
        }
        ::-webkit-scrollbar-thumb {
            background: rgba(99, 102, 241, 0.5);
            border-radius: 8px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: rgba(99, 102, 241, 0.8);
        }
    </style>
</head>
<body class="text-slate-100 flex flex-col justify-between min-h-screen p-3 md:p-6 selection:bg-indigo-500 selection:text-white">

    <!-- Header Navigation -->
    <header class="max-w-4xl w-full mx-auto flex justify-between items-center py-3 px-4 rounded-2xl glass-card mb-4">
        <div class="flex items-center space-x-3">
            <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-cyan-500 to-indigo-500 flex items-center justify-center text-xl font-black shadow-lg">
                <i class="fa-solid font-bold text-white">⚗️</i>
            </div>
            <div>
                <h1 class="font-extrabold text-lg md:text-xl bg-clip-text text-transparent bg-gradient-to-r from-cyan-400 via-sky-300 to-indigo-300">
                    KimyoViktorina
                </h1>
                <p class="text-xs text-slate-400">Alkanlar va Alkenlar</p>
            </div>
        </div>

        <div class="flex items-center gap-3">
            <!-- Audio Toggle Button -->
            <button id="soundToggleBtn" onclick="toggleSound()" class="w-10 h-10 rounded-xl bg-slate-800/80 hover:bg-slate-700 flex items-center justify-center text-slate-300 hover:text-white transition duration-200 border border-slate-700/50" title="Ovozni yoqish/o'chirish">
                <i id="soundIcon" class="fa-solid fa-volume-high text-cyan-400"></i>
            </button>
            <!-- Restart Button (Active only in game) -->
            <button id="homeBtn" onclick="showScreen('welcomeScreen')" class="hidden px-3 py-2 rounded-xl bg-slate-800/80 hover:bg-slate-700 text-xs md:text-sm font-semibold text-slate-300 hover:text-white transition duration-200 border border-slate-700/50 flex items-center gap-2">
                <i class="fa-solid fa-house"></i>
                <span class="hidden sm:inline">Bosh menyu</span>
            </button>
        </div>
    </header>

    <!-- Main Container -->
    <main class="max-w-4xl w-full mx-auto my-auto flex-grow flex items-center justify-center relative">

        <!-- ================= WELCOME SCREEN ================= -->
        <section id="welcomeScreen" class="w-full glass-card rounded-3xl p-6 md:p-10 text-center relative overflow-hidden my-auto">
            <!-- Decorative Elements -->
            <div class="absolute -top-24 -left-24 w-48 h-48 bg-cyan-500/10 rounded-full blur-3xl pointer-events-none"></div>
            <div class="absolute -bottom-24 -right-24 w-48 h-48 bg-indigo-500/10 rounded-full blur-3xl pointer-events-none"></div>

            <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-cyan-500/10 border border-cyan-500/20 text-cyan-300 text-xs md:text-sm font-medium mb-6">
                <i class="fa-solid fa-atom animate-spin" style="animation-duration: 8s;"></i> 
                Interaktiv Kimyo Intellektual O'yini
            </div>

            <h2 class="text-3xl md:text-5xl font-extrabold text-white mb-4 tracking-tight leading-tight">
                Alkanlar & Alkenlar <br>
                <span class="bg-clip-text text-transparent bg-gradient-to-r from-cyan-400 via-sky-400 to-indigo-400">
                    To'g'ri yoki Noto'g'ri?
                </span>
            </h2>

            <p class="text-slate-300 max-w-xl mx-auto text-sm md:text-base mb-8 leading-relaxed">
                Organik kimyoning to'yingan va to'yinmagan uglevodorodlar bo'limi bo'yicha bilimlaringizni sinab ko'ring. Barcha savollarga to'g'ri javob berib, "Bosh Kimyogar" unvonini qo'lga kiriting!
            </p>

            <!-- Mode & Filter Selector -->
            <div class="max-w-md mx-auto space-y-4 mb-8 text-left">
                <div>
                    <label class="block text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">Mavzu filteri:</label>
                    <select id="categoryFilter" class="w-full bg-slate-900/80 border border-slate-700/70 rounded-xl px-4 py-3 text-sm text-slate-200 focus:outline-none focus:border-cyan-500 transition">
                        <option value="ALL">Barchasi (Aralash 20 ta savol)</option>
                        <option value="ALKAN">Faqat Alkanlar ( To'yingan uglevodorodlar )</option>
                        <option value="ALKEN">Faqat Alkenlar ( To'yinmagan uglevodorodlar )</option>
                        <option value="XOSSA">Kimyoviy va Fizikaviy Xossalar</option>
                    </select>
                </div>

                <div>
                    <label class="block text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">Vaqt rejimi:</label>
                    <div class="grid grid-cols-3 gap-2">
                        <button type="button" onclick="setTimerOption(10)" class="timer-opt-btn px-3 py-2.5 rounded-xl border border-slate-700 bg-slate-800/60 text-xs font-semibold text-slate-300 hover:border-cyan-500 transition" data-time="10">10 soniya</button>
                        <button type="button" onclick="setTimerOption(15)" class="timer-opt-btn active px-3 py-2.5 rounded-xl border border-cyan-500 bg-cyan-500/20 text-xs font-semibold text-cyan-300 transition" data-time="15">15 soniya</button>
                        <button type="button" onclick="setTimerOption(0)" class="timer-opt-btn px-3 py-2.5 rounded-xl border border-slate-700 bg-slate-800/60 text-xs font-semibold text-slate-300 hover:border-cyan-500 transition" data-time="0">Cheksiz</button>
                    </div>
                </div>
            </div>

            <!-- Start Button -->
            <button onclick="startGame()" class="w-full max-w-md py-4 rounded-2xl bg-gradient-to-r from-cyan-500 via-sky-500 to-indigo-600 hover:from-cyan-400 hover:to-indigo-500 text-white font-bold text-lg shadow-xl hover:shadow-cyan-500/25 transition-all duration-300 transform hover:-translate-y-0.5 active:translate-y-0 flex items-center justify-center gap-3 mx-auto">
                <i class="fa-solid fa-play"></i>
                O'yinni Boshlash
            </button>
        </section>

        <!-- ================= QUIZ GAME SCREEN ================= -->
        <section id="gameScreen" class="hidden w-full glass-card rounded-3xl p-5 md:p-8 relative">
            
            <!-- Top HUD Bar -->
            <div class="flex flex-wrap justify-between items-center gap-3 pb-4 mb-4 border-b border-slate-700/60 text-xs md:text-sm">
                <!-- Progress & Tag -->
                <div class="flex items-center gap-2">
                    <span id="questionCategoryTag" class="px-2.5 py-1 rounded-lg bg-indigo-500/20 text-indigo-300 border border-indigo-500/30 font-semibold uppercase tracking-wider text-[10px]">
                        Alkanlar
                    </span>
                    <span class="text-slate-400 font-medium">Savol: <strong id="currentQNum" class="text-white">1</strong>/<span id="totalQNum">15</span></span>
                </div>

                <!-- Stats: Streak & Score -->
                <div class="flex items-center gap-4">
                    <div class="flex items-center gap-1.5 text-amber-400 font-bold bg-amber-400/10 px-3 py-1 rounded-lg border border-amber-400/20">
                        <i id="streakIcon" class="fa-solid fa-fire text-amber-400"></i>
                        <span id="streakCount">0</span> Streak
                    </div>
                    <div class="flex items-center gap-1.5 text-emerald-400 font-bold bg-emerald-400/10 px-3 py-1 rounded-lg border border-emerald-400/20">
                        <i class="fa-solid fa-star"></i>
                        <span id="scoreDisplay">0</span> ball
                    </div>
                </div>
            </div>

            <!-- Timer Countdown Bar -->
            <div id="timerContainer" class="w-full bg-slate-900 rounded-full h-2 mb-6 overflow-hidden border border-slate-800">
                <div id="timerBar" class="timer-bar bg-gradient-to-r from-cyan-400 to-indigo-500 h-full w-full rounded-full"></div>
            </div>

            <!-- Question Card -->
            <div class="my-4 min-h-[140px] md:min-h-[160px] flex flex-col justify-center items-center text-center px-2">
                <h3 id="questionText" class="text-lg md:text-2xl font-bold text-white leading-relaxed md:leading-normal">
                    -- Savol yuklanmoqda --
                </h3>
            </div>

            <!-- True / False Action Buttons -->
            <div id="actionButtons" class="grid grid-cols-2 gap-4 my-6">
                <button onclick="submitAnswer(true)" class="group py-5 px-4 rounded-2xl bg-emerald-500/10 hover:bg-emerald-500/20 border-2 border-emerald-500/50 hover:border-emerald-400 text-emerald-300 font-extrabold text-lg md:text-xl transition-all duration-200 flex flex-col items-center justify-center gap-2 hover:scale-[1.02] active:scale-95 shadow-lg hover:shadow-emerald-500/10">
                    <i class="fa-solid fa-circle-check text-2xl text-emerald-400 group-hover:scale-110 transition"></i>
                    TO'G'RI
                </button>

                <button onclick="submitAnswer(false)" class="group py-5 px-4 rounded-2xl bg-rose-500/10 hover:bg-rose-500/20 border-2 border-rose-500/50 hover:border-rose-400 text-rose-300 font-extrabold text-lg md:text-xl transition-all duration-200 flex flex-col items-center justify-center gap-2 hover:scale-[1.02] active:scale-95 shadow-lg hover:shadow-rose-500/10">
                    <i class="fa-solid fa-circle-xmark text-2xl text-rose-400 group-hover:scale-110 transition"></i>
                    NOTO'G'RI
                </button>
            </div>

            <!-- Feedback & Explanation Modal Box (Appears after answer) -->
            <div id="explanationBox" class="hidden rounded-2xl p-4 md:p-5 mb-4 border transition-all duration-300">
                <div class="flex items-start gap-3">
                    <div id="feedbackIcon" class="text-2xl mt-0.5"></div>
                    <div class="flex-1">
                        <div id="feedbackTitle" class="font-extrabold text-base md:text-lg mb-1"></div>
                        <p id="explanationText" class="text-xs md:text-sm text-slate-300 leading-relaxed"></p>
                    </div>
                </div>
                <button onclick="nextQuestion()" class="mt-4 w-full py-3 rounded-xl bg-indigo-600 hover:bg-indigo-500 text-white font-bold text-sm transition flex items-center justify-center gap-2 shadow-md">
                    Keyingi Savol <i class="fa-solid fa-arrow-right"></i>
                </button>
            </div>

        </section>

        <!-- ================= RESULTS SCREEN ================= -->
        <section id="resultsScreen" class="hidden w-full glass-card rounded-3xl p-6 md:p-10 text-center my-auto">
            <!-- Trophy Badge -->
            <div class="w-20 h-20 mx-auto mb-4 rounded-3xl bg-gradient-to-tr from-amber-400 to-amber-600 flex items-center justify-center text-4xl text-slate-950 shadow-xl shadow-amber-500/20 animate-bounce" style="animation-duration: 2s;">
                <i class="fa-solid fa-trophy"></i>
            </div>

            <h2 class="text-2xl md:text-3xl font-extrabold text-white mb-1">O'yin Yakunlandi!</h2>
            <p id="performanceBadge" class="text-sm font-semibold text-cyan-400 uppercase tracking-widest mb-6">"Yosh Kimyogar"</p>

            <!-- Score Stats Grid -->
            <div class="grid grid-cols-2 md:grid-cols-4 gap-3 mb-6 max-w-2xl mx-auto">
                <div class="bg-slate-900/60 border border-slate-800 rounded-2xl p-3">
                    <span class="block text-xs text-slate-400 font-medium mb-1">Jami Ball</span>
                    <span id="finalScore" class="text-xl md:text-2xl font-black text-white">0</span>
                </div>
                <div class="bg-slate-900/60 border border-slate-800 rounded-2xl p-3">
                    <span class="block text-xs text-slate-400 font-medium mb-1">Aniqlik</span>
                    <span id="finalAccuracy" class="text-xl md:text-2xl font-black text-emerald-400">0%</span>
                </div>
                <div class="bg-slate-900/60 border border-slate-800 rounded-2xl p-3">
                    <span class="block text-xs text-slate-400 font-medium mb-1">To'g'ri Javoblar</span>
                    <span id="finalCorrect" class="text-xl md:text-2xl font-black text-cyan-400">0/0</span>
                </div>
                <div class="bg-slate-900/60 border border-slate-800 rounded-2xl p-3">
                    <span class="block text-xs text-slate-400 font-medium mb-1">Eng Yuqori Streak</span>
                    <span id="finalMaxStreak" class="text-xl md:text-2xl font-black text-amber-400">0</span>
                </div>
            </div>

            <!-- Detailed Question Review Section -->
            <div class="text-left mb-6">
                <h4 class="text-xs font-bold text-slate-400 uppercase tracking-wider mb-3 flex items-center gap-2">
                    <i class="fa-solid fa-list-check"></i> Savollar bo'yicha hisobot:
                </h4>
                <div id="reviewContainer" class="max-h-60 overflow-y-auto space-y-2 pr-1">
                    <!-- Dynamic review items inserted here -->
                </div>
            </div>

            <!-- Actions -->
            <div class="flex flex-col sm:flex-row gap-3 max-w-md mx-auto">
                <button onclick="startGame()" class="flex-1 py-3.5 rounded-xl bg-gradient-to-r from-cyan-500 to-indigo-600 hover:from-cyan-400 hover:to-indigo-500 text-white font-bold text-sm transition shadow-lg flex items-center justify-center gap-2">
                    <i class="fa-solid fa-rotate-right"></i> Qayta o'ynash
                </button>
                <button onclick="showScreen('welcomeScreen')" class="flex-1 py-3.5 rounded-xl bg-slate-800 hover:bg-slate-700 text-slate-200 font-bold text-sm transition border border-slate-700 flex items-center justify-center gap-2">
                    <i class="fa-solid fa-house"></i> Bosh Menyu
                </button>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="max-w-4xl w-full mx-auto text-center py-4 text-xs text-slate-500">
        Kimyo fani o'quvchilari va abituriyentlar uchun maxsus tayyorlandi &bull; Alkanlar va Alkenlar Interaktiv Testi
    </footer>

    <!-- ================= JAVASCRIPT LOGIC ================= -->
    <script>
        // QUESTION BANK (Comprehensive 20 questions in Uzbek)
        const questionBank = [
            {
                id: 1,
                category: "ALKAN",
                categoryLabel: "Alkanlar",
                question: "Alkanlarning umumiy formulasi C<sub>n</sub>H<sub>2n+2</sub> hisoblanadi.",
                answer: true,
                explanation: "To'g'ri! Alkanlar to'yingan uglevodorodlar bo'lib, ularning umumiy formulasi C<sub>n</sub>H<sub>2n+2</sub> ga teng."
            },
            {
                id: 2,
                category: "ALKEN",
                categoryLabel: "Alkenlar",
                question: "Alkenlar tarkibida kamida bitta uch bog' (C≡C) mavjud.",
                answer: false,
                explanation: "Noto'g'ri! Alkenlar tarkibida kamida bitta qo'sh bog' (C=C) bo'ladi. Uch bog' esa alkinlarga xosdir."
            },
            {
                id: 3,
                category: "ALKAN",
                categoryLabel: "Alkanlar",
                question: "Alkanlardagi barcha uglerod atomlari sp³ gibridlangan holatda bo'ladi.",
                answer: true,
                explanation: "To'g'ri! Alkanlarda har bir uglerod atomi faqat oddiy (sigma) bog'lar hosil qilgani uchun sp³ gibridlanishga ega va burchagi 109°28' ga teng."
            },
            {
                id: 4,
                category: "ALKEN",
                categoryLabel: "Alkenlar",
                question: "Eten (etilen) alkenlarning eng birinchi va oddiy vakilidir.",
                answer: true,
                explanation: "To'g'ri! Eten (C₂H₄) 2 ta uglerod atomidan tashkil topgan eng oddiy alken hisoblanadi."
            },
            {
                id: 5,
                category: "XOSSA",
                categoryLabel: "Kimyoviy Xossa",
                question: "Alkenlarni bromli suv (Br₂) orqali o'tkazilganda bromli suv rangi o'zgarmaydi.",
                answer: false,
                explanation: "Noto'g'ri! Alkenlar tarkibidagi qo'sh bog' uzilib brom qo'shilgani sababli bromli suv rangsizlanadi (bu to'yinmaganlik sifati reaksiyasidir)."
            },
            {
                id: 6,
                category: "XOSSA",
                categoryLabel: "Kimyoviy Xossa",
                question: "Markovnikov qoidasiga ko'ra, vodorod galogenid qo'shilganda vodorod atomi uglerod atomlaridan vodorodi ko'proq bo'lganiga birikadi.",
                answer: true,
                explanation: "To'g'ri! Markovnikov qoidasi bo'yicha H-X birikkanda, H atomi qo'sh bog'li uglerodlar orasidan vodorodi ko'prog'iga boradi."
            },
            {
                id: 7,
                category: "ALKAN",
                categoryLabel: "Alkanlar",
                question: "Metan (CH₄) gazi suvda juda yaxshi eriydi.",
                answer: false,
                explanation: "Noto'g'ri! Metan qutbsiz molekula bo'lgani uchun qutbli erituvchi bo'lgan suvda deyarli erimaydi."
            },
            {
                id: 8,
                category: "ALKEN",
                categoryLabel: "Alkenlar",
                question: "Alkenlardagi qo'sh bog'li uglerod atomlari sp² gibridlangan holatda bo'ladi.",
                answer: true,
                explanation: "To'g'ri! Qo'sh bog' hosil qilgan uglerod atomlari sp² gibridlangan va ularning valent burchagi 120° ga teng."
            },
            {
                id: 9,
                category: "XOSSA",
                categoryLabel: "Fizik Xossa",
                question: "Propan (C₃H₈) va Butan (C₄H₁₀) gazi odatdagi sharoitda suyuq holatda bo'ladi.",
                answer: false,
                explanation: "Noto'g'ri! Alkanlarning dastlabki 4 ta vakili (C₁ - C₄: metan, etan, propan, butan) gaz holatida bo'ladi."
            },
            {
                id: 10,
                category: "ALKEN",
                categoryLabel: "Alkenlar",
                question: "Etilen (C₂H₄) gazi mevalarning tezroq pishishiga yordam beruvchi gormonal ta'sirga ega.",
                answer: true,
                explanation: "To'g'ri! Etilen qishloq xo'jaligida mevalarni (banan, pomidor va h.k.) sun'iy va tez pishirishda keng qo'llaniladi."
            },
            {
                id: 11,
                category: "ALKAN",
                categoryLabel: "Alkanlar",
                question: "Alkanlar nur ta'sirida galogenlar bilan o'rinbosar bo'lish reaksiyasiga kirishadi.",
                answer: true,
                explanation: "To'g'ri! Masalan, metan xlorlanganda (hν nurida) vodorod atomlari bosqichma-bosqich xlorga almashinadi."
            },
            {
                id: 12,
                category: "ALKEN",
                categoryLabel: "Alkenlar",
                question: "Alkenlar birikish va polimerlanish reaksiyalariga kirisha olmaydi.",
                answer: false,
                explanation: "Noto'g'ri! Alkenlarning eng muhim xossasi bu qo'sh bog'dagi π-bog' uzilishi hisobiga birikish va polimerlanish reaksiyalariga oson kirishishidir."
            },
            {
                id: 13,
                category: "XOSSA",
                categoryLabel: "Kimyoviy Xossa",
                question: "Vagner reaksiyasida alkenlar Kaliy permanganat (KMnO₄) ertmasida diollarga (ikki atomli spirtlarga) oksidlanadi.",
                answer: true,
                explanation: "To'g'ri! Neytral yoki kuchsiz ishqoriy muhitda KMnO₄ ta'sirida alkenlar rangsizlanib, glikollar (diollar) hosil qiladi."
            },
            {
                id: 14,
                category: "ALKAN",
                categoryLabel: "Izomeriya",
                question: "Metan, etan va propan uglevodorodlarining struktura izomerlari mavjud emas.",
                answer: true,
                explanation: "To'g'ri! Alkanlarda zanjir izomeriyasi faqat 4-vakil ya'ni Butan (C₄H₁₀) dan boshlanadi."
            },
            {
                id: 15,
                category: "ALKEN",
                categoryLabel: "Izomeriya",
                question: "Alkenlarda Sis- va Trans- (geometrik) izomeriya mavjud bo'lishi mumkin.",
                answer: true,
                explanation: "To'g'ri! Qo'sh bog' atrofida erkin aylanish bo'lmagani sababli o'rinbosarlarning fazoviy joylashuviga ko'ra sis- va trans-izomerlar hosil bo'ladi."
            },
            {
                id: 16,
                category: "ALKAN",
                categoryLabel: "Alkanlar",
                question: "Alkanlarni yuqori haroratda havosiz parchalash jarayoni kreking deb ataladi.",
                answer: true,
                explanation: "To'g'ri! Kreking jarayonida og'ir alkanlar kichikroq molekulali alkan va alkenlarga parchalanadi."
            },
            {
                id: 17,
                category: "ALKEN",
                categoryLabel: "Alkenlar",
                question: "Alkenlarning umumiy formulasi C<sub>n</sub>H<sub>2n-2</sub> ga teng.",
                answer: false,
                explanation: "Noto'g'ri! Alkenlarning umumiy formulasi C<sub>n</sub>H<sub>2n</sub> bo'ladi. C<sub>n</sub>H<sub>2n-2</sub> esa Alkinlar yoki Dienlarning formulasidir."
            },
            {
                id: 18,
                category: "XOSSA",
                categoryLabel: "Kimyoviy Xossa",
                question: "Alkan va Alkenlar to'liq yonganda Karbonat angidrid (CO₂) va Suv (H₂O) hosil bo'ladi.",
                answer: true,
                explanation: "To'g me'yorida kislorod yetarli bo'lganda barcha uglevodorodlar yonib CO₂ va H₂O hamda ko'p miqdorda issiqlik ajratadi."
            },
            {
                id: 19,
                category: "ALKEN",
                categoryLabel: "Polimerlar",
                question: "Polietilen va Polipropilen moddalari alkenlarning polimerlanish reaksiyasi mahsulotidir.",
                answer: true,
                explanation: "To me'yorida etilen va propilen molekulalarining o'zaro birikishi natijasida muhim maishiy va sanoat plastmassalari olinadi."
            },
            {
                id: 20,
                category: "ALKAN",
                categoryLabel: "Alkanlar",
                question: "Alkanlar ikkinchi nomi 'Parafinlar' bo'lib, bu ularning kimyoviy jihatdan juda faol ekanligini anglatadi.",
                answer: false,
                explanation: "Noto'g'ri! 'Parafin' lotincha 'parum affinis' so'zidan olingan bo'lib, 'kam moyillikka ega' ya'ni kam faol degan ma'noni anglatadi."
            }
        ];

        // GAME STATE STATEFUL VARIABLES
        let currentQuestions = [];
        let currentIndex = 0;
        let score = 0;
        let streak = 0;
        let maxStreak = 0;
        let timerSeconds = 15;
        let currentTimer = 15;
        let timerInterval = null;
        let userAnswersHistory = [];
        let isSoundEnabled = true;

        // Audio Context (Synthesized sounds)
        let audioCtx = null;

        function initAudio() {
            if (!audioCtx) {
                audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            }
        }

        // Play Synthesized Sounds
        function playSound(type) {
            if (!isSoundEnabled) return;
            try {
                initAudio();
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                osc.connect(gain);
                gain.connect(audioCtx.destination);

                if (type === 'correct') {
                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(523.25, audioCtx.currentTime); // C5
                    osc.frequency.exponentialRampToValueAtTime(880, audioCtx.currentTime + 0.15); // A5
                    gain.gain.setValueAtTime(0.2, audioCtx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.3);
                    osc.start();
                    osc.stop(audioCtx.currentTime + 0.3);
                } else if (type === 'wrong') {
                    osc.type = 'sawtooth';
                    osc.frequency.setValueAtTime(220, audioCtx.currentTime); // A3
                    osc.frequency.exponentialRampToValueAtTime(110, audioCtx.currentTime + 0.2); // A2
                    gain.gain.setValueAtTime(0.25, audioCtx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.25);
                    osc.start();
                    osc.stop(audioCtx.currentTime + 0.25);
                } else if (type === 'click') {
                    osc.type = 'triangle';
                    osc.frequency.setValueAtTime(400, audioCtx.currentTime);
                    gain.gain.setValueAtTime(0.05, audioCtx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.05);
                    osc.start();
                    osc.stop(audioCtx.currentTime + 0.05);
                }
            } catch (e) {
                console.log("Audio play error", e);
            }
        }

        function toggleSound() {
            isSoundEnabled = !isSoundEnabled;
            const icon = document.getElementById('soundIcon');
            if (isSoundEnabled) {
                icon.className = "fa-solid fa-volume-high text-cyan-400";
            } else {
                icon.className = "fa-solid fa-volume-xmark text-slate-500";
            }
        }

        function setTimerOption(seconds) {
            playSound('click');
            timerSeconds = seconds;
            document.querySelectorAll('.timer-opt-btn').forEach(btn => {
                btn.classList.remove('active', 'border-cyan-500', 'bg-cyan-500/20', 'text-cyan-300');
                btn.classList.add('border-slate-700', 'bg-slate-800/60', 'text-slate-300');
                if (parseInt(btn.getAttribute('data-time')) === seconds) {
                    btn.classList.add('active', 'border-cyan-500', 'bg-cyan-500/20', 'text-cyan-300');
                    btn.classList.remove('border-slate-700', 'bg-slate-800/60', 'text-slate-300');
                }
            });
        }

        function showScreen(screenId) {
            playSound('click');
            document.getElementById('welcomeScreen').classList.add('hidden');
            document.getElementById('gameScreen').classList.add('hidden');
            document.getElementById('resultsScreen').classList.add('hidden');

            document.getElementById(screenId).classList.remove('hidden');

            const homeBtn = document.getElementById('homeBtn');
            if (screenId === 'gameScreen') {
                homeBtn.classList.remove('hidden');
            } else {
                homeBtn.classList.add('hidden');
            }
        }

        // Shuffle utility
        function shuffleArray(array) {
            return [...array].sort(() => Math.random() - 0.5);
        }

        // START GAME
        function startGame() {
            initAudio();
            const filterValue = document.getElementById('categoryFilter').value;
            
            let filtered = questionBank;
            if (filterValue !== 'ALL') {
                filtered = questionBank.filter(q => q.category === filterValue);
            }

            // Shuffle and pick max 15 questions
            currentQuestions = shuffleArray(filtered).slice(0, 15);
            
            currentIndex = 0;
            score = 0;
            streak = 0;
            maxStreak = 0;
            userAnswersHistory = [];

            document.getElementById('totalQNum').innerText = currentQuestions.length;
            document.getElementById('scoreDisplay').innerText = score;
            document.getElementById('streakCount').innerText = streak;

            showScreen('gameScreen');
            loadQuestion();
        }

        function loadQuestion() {
            clearInterval(timerInterval);

            // Hide explanation box & show buttons
            document.getElementById('explanationBox').classList.add('hidden');
            document.getElementById('actionButtons').classList.remove('hidden');
            document.getElementById('actionButtons').style.pointerEvents = 'auto';

            const q = currentQuestions[currentIndex];

            document.getElementById('currentQNum').innerText = currentIndex + 1;
            document.getElementById('questionCategoryTag').innerText = q.categoryLabel;
            document.getElementById('questionText').innerHTML = q.question;

            // Timer Setup
            const timerContainer = document.getElementById('timerContainer');
            if (timerSeconds > 0) {
                timerContainer.classList.remove('hidden');
                currentTimer = timerSeconds;
                updateTimerBar();

                timerInterval = setInterval(() => {
                    currentTimer -= 0.1;
                    if (currentTimer <= 0) {
                        currentTimer = 0;
                        updateTimerBar();
                        clearInterval(timerInterval);
                        timeOutAnswer();
                    } else {
                        updateTimerBar();
                    }
                }, 100);
            } else {
                timerContainer.classList.add('hidden');
            }
        }

        function updateTimerBar() {
            const timerBar = document.getElementById('timerBar');
            const percentage = (currentTimer / timerSeconds) * 100;
            timerBar.style.width = percentage + '%';

            if (percentage < 30) {
                timerBar.className = "timer-bar bg-gradient-to-r from-rose-500 to-red-600 h-full w-full rounded-full";
            } else {
                timerBar.className = "timer-bar bg-gradient-to-r from-cyan-400 to-indigo-500 h-full w-full rounded-full";
            }
        }

        function timeOutAnswer() {
            processAnswer(null, false, "Vaqt tugadi! O'ylash vaqti yakunlandi.");
        }

        function submitAnswer(userChoice) {
            clearInterval(timerInterval);
            const q = currentQuestions[currentIndex];
            const isCorrect = (userChoice === q.answer);
            processAnswer(userChoice, isCorrect, q.explanation);
        }

        function processAnswer(userChoice, isCorrect, explanationText) {
            // Disable action buttons
            document.getElementById('actionButtons').style.pointerEvents = 'none';

            const q = currentQuestions[currentIndex];

            if (isCorrect) {
                playSound('correct');
                streak++;
                if (streak > maxStreak) maxStreak = streak;
                
                // Score formula: Base 100 + Streak bonus
                const streakBonus = (streak > 1) ? (streak - 1) * 20 : 0;
                score += (100 + streakBonus);

                document.getElementById('streakIcon').classList.add('streak-active');
            } else {
                playSound('wrong');
                streak = 0;
                document.getElementById('streakIcon').classList.remove('streak-active');
            }

            document.getElementById('scoreDisplay').innerText = score;
            document.getElementById('streakCount').innerText = streak;

            // Save history
            userAnswersHistory.push({
                question: q.question,
                userChoice: userChoice,
                correctAnswer: q.answer,
                isCorrect: isCorrect,
                explanation: q.explanation
            });

            // Show explanation box with appropriate styling
            const expBox = document.getElementById('explanationBox');
            const expTitle = document.getElementById('feedbackTitle');
            const expText = document.getElementById('explanationText');
            const expIcon = document.getElementById('feedbackIcon');

            expBox.classList.remove('hidden');

            if (isCorrect) {
                expBox.className = "rounded-2xl p-4 md:p-5 mb-4 border transition-all duration-300 bg-emerald-950/60 border-emerald-500/40 text-emerald-200 glow-green";
                expIcon.innerHTML = '<i class="fa-solid fa-circle-check text-emerald-400"></i>';
                expTitle.className = "font-extrabold text-base md:text-lg mb-1 text-emerald-300";
                expTitle.innerText = "Barakalla! To'g'ri javob!";
            } else {
                expBox.className = "rounded-2xl p-4 md:p-5 mb-4 border transition-all duration-300 bg-rose-950/60 border-rose-500/40 text-rose-200 glow-red";
                expIcon.innerHTML = '<i class="fa-solid fa-circle-xmark text-rose-400"></i>';
                expTitle.className = "font-extrabold text-base md:text-lg mb-1 text-rose-300";
                expTitle.innerText = (userChoice === null) ? "Vaqt tugadi!" : "Xato javob!";
            }

            expText.innerHTML = explanationText;
        }

        function nextQuestion() {
            playSound('click');
            currentIndex++;
            if (currentIndex < currentQuestions.length) {
                loadQuestion();
            } else {
                finishGame();
            }
        }

        // END GAME & SHOW RESULTS
        function finishGame() {
            showScreen('resultsScreen');

            const total = currentQuestions.length;
            const correctCount = userAnswersHistory.filter(h => h.isCorrect).length;
            const accuracy = Math.round((correctCount / total) * 100);

            document.getElementById('finalScore').innerText = score;
            document.getElementById('finalAccuracy').innerText = accuracy + '%';
            document.getElementById('finalCorrect').innerText = `${correctCount}/${total}`;
            document.getElementById('finalMaxStreak').innerText = maxStreak;

            // Performance Title Badge
            const badge = document.getElementById('performanceBadge');
            if (accuracy === 100) {
                badge.innerText = "🏆 Akademik Kimyogar (Mukammal!)";
                badge.className = "text-sm font-extrabold text-amber-400 uppercase tracking-widest mb-6";
            } else if (accuracy >= 80) {
                badge.innerText = "🧪 Bilimdon Kimyogar";
                badge.className = "text-sm font-extrabold text-cyan-400 uppercase tracking-widest mb-6";
            } else if (accuracy >= 60) {
                badge.innerText = "📚 Izlanuvchi Talaba";
                badge.className = "text-sm font-extrabold text-indigo-400 uppercase tracking-widest mb-6";
            } else {
                badge.innerText = "🌱 Boshlang'ich Kimyogar (Yana takrorlang)";
                badge.className = "text-sm font-extrabold text-rose-400 uppercase tracking-widest mb-6";
            }

            // Render detailed answer breakdown
            const reviewContainer = document.getElementById('reviewContainer');
            reviewContainer.innerHTML = '';

            userAnswersHistory.forEach((item, idx) => {
                const itemDiv = document.createElement('div');
                itemDiv.className = `p-3 rounded-xl border text-xs leading-relaxed ${
                    item.isCorrect 
                    ? 'bg-emerald-950/30 border-emerald-500/30 text-slate-200' 
                    : 'bg-rose-950/30 border-rose-500/30 text-slate-200'
                }`;

                const userText = item.userChoice === null ? "Vaqt o'tdi" : (item.userChoice ? "To'g'ri" : "Noto'g'ri");
                const correctText = item.correctAnswer ? "To'g'ri" : "Noto'g'ri";

                itemDiv.innerHTML = `
                    <div class="flex items-start justify-between gap-2 mb-1">
                        <span class="font-bold text-slate-300">#${idx + 1}. ${item.question}</span>
                        <span class="font-extrabold shrink-0 ${item.isCorrect ? 'text-emerald-400' : 'text-rose-400'}">
                            ${item.isCorrect ? '<i class="fa-solid fa-check"></i>' : '<i class="fa-solid fa-xmark"></i>'}
                        </span>
                    </div>
                    <div class="text-[11px] text-slate-400">
                        Sizning javob: <strong class="${item.isCorrect ? 'text-emerald-300' : 'text-rose-300'}">${userText}</strong> | 
                        To'g'ri javob: <strong class="text-cyan-300">${correctText}</strong>
                    </div>
                    <p class="mt-1 text-[11px] text-slate-300 opacity-90 border-t border-slate-700/40 pt-1">${item.explanation}</p>
                `;
                reviewContainer.appendChild(itemDiv);
            });
        }
    </script>
</body>
</html>
```
