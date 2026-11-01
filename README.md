<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MPI: الْحَفْلُ بِمَوْلِدِ الرَّسُوْل</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <!-- FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- html2pdf -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        arabic: ['Amiri', 'serif'],
                    },
                    colors: {
                        emerald: { 50: '#ecfdf5', 100: '#d1fae5', 500: '#10b981', 600: '#059669', 700: '#047857', 800: '#065f46', 900: '#064e3b' },
                        gold: { 400: '#fbbf24', 500: '#f59e0b', 600: '#d97706' }
                    }
                }
            }
        }
    </script>
    <style>
        body { background: linear-gradient(135deg, #ecfdf5 0%, #d1fae5 100%); min-height: 100vh; overflow-x: hidden; }
        .glass-panel { background: rgba(255, 255, 255, 0.85); backdrop-filter: blur(12px); border: 1px solid rgba(255,255,255,0.5); box-shadow: 0 10px 30px rgba(0,0,0,0.05); }
        .glass-modal { background: rgba(255, 255, 255, 0.95); backdrop-filter: blur(16px); border: 1px solid rgba(16, 185, 129, 0.2); }
        .animate-fade-in { animation: fadeIn 0.5s ease-out forwards; }
        .animate-slide-up { animation: slideUp 0.5s ease-out forwards; }
        .animate-bounce-slow { animation: bounce 3s infinite; }
        
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes slideUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        
        .hide { display: none !important; }
        .arabic-text { direction: rtl; text-align: right; line-height: 2.2; }
        
        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #f1f1f1; }
        ::-webkit-scrollbar-thumb { background: #10b981; border-radius: 4px; }
        ::-webkit-scrollbar-thumb:hover { background: #059669; }

        /* Interactive Elements */
        .option-btn { transition: all 0.2s; }
        .option-btn:active { transform: scale(0.98); }
        
        .floating-svg {
            animation: float 6s ease-in-out infinite;
        }
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }
    </style>
</head>
<body class="text-slate-800 antialiased font-sans selection:bg-emerald-200 selection:text-emerald-900">

    <!-- Global Modal Alert -->
    <div id="globalModal" class="fixed inset-0 z-50 flex items-center justify-center bg-slate-900/50 backdrop-blur-sm hide">
        <div class="glass-modal rounded-2xl p-6 md:p-8 max-w-sm w-full mx-4 shadow-2xl transform transition-all animate-slide-up text-center">
            <div id="modalIcon" class="text-4xl mb-4"></div>
            <h3 id="modalTitle" class="text-xl font-bold text-slate-800 mb-2"></h3>
            <p id="modalMessage" class="text-slate-600 mb-6 text-sm"></p>
            <button onclick="closeModal()" id="modalBtn" class="w-full bg-emerald-600 hover:bg-emerald-700 text-white font-semibold py-3 px-4 rounded-xl transition shadow-lg">Mengerti</button>
        </div>
    </div>

    <!-- 1. SPLASH SCREEN -->
    <section id="splashScreen" class="fixed inset-0 z-50 flex flex-col items-center justify-center bg-emerald-700 text-white transition-opacity duration-500">
        <div class="animate-bounce-slow text-center">
            <i class="fas fa-moon text-6xl text-gold-400 mb-4"></i>
            <h1 class="text-3xl font-arabic font-bold mb-2 arabic-text text-center">الْحَفْلُ بِمَوْلِدِ الرَّسُوْل</h1>
            <p class="text-emerald-100 tracking-wider text-sm uppercase">Media Pembelajaran Interaktif</p>
        </div>
        <div class="absolute bottom-10 text-emerald-300 text-xs">Memuat modul...</div>
    </section>

    <!-- 2. COVER SCREEN -->
    <section id="coverScreen" class="min-h-screen flex flex-col items-center justify-center p-4 hide relative overflow-hidden">
        <div class="absolute top-[-10%] left-[-10%] w-64 h-64 bg-emerald-300 rounded-full mix-blend-multiply filter blur-3xl opacity-50"></div>
        <div class="absolute bottom-[-10%] right-[-10%] w-64 h-64 bg-gold-300 rounded-full mix-blend-multiply filter blur-3xl opacity-50"></div>

        <div class="glass-panel p-8 md:p-12 rounded-3xl max-w-2xl w-full text-center relative z-10 animate-slide-up border-t-4 border-emerald-500">
            <span class="inline-block bg-emerald-100 text-emerald-800 text-xs font-bold px-3 py-1 rounded-full mb-6 uppercase tracking-wide">Bahasa Arab | Kelas IX (Fase D)</span>
            
            <div class="floating-svg mb-6">
                <svg class="w-32 h-32 mx-auto text-emerald-600 drop-shadow-md" viewBox="0 0 24 24" fill="currentColor">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/>
                </svg>
            </div>

            <h1 class="text-4xl md:text-5xl font-bold text-emerald-800 mb-2 font-arabic arabic-text text-center" dir="rtl">الْحَفْلُ بِمَوْلِدِ الرَّسُوْل</h1>
            <p class="text-slate-600 mb-8 font-medium">Perayaan Maulid Nabi Muhammad SAW</p>

            <div class="flex flex-col md:flex-row gap-3 justify-center mb-6">
                <button onclick="toggleModal('devModal')" class="bg-white hover:bg-slate-50 text-emerald-700 border border-emerald-200 font-semibold py-2 px-4 rounded-xl transition shadow-sm flex items-center justify-center gap-2">
                    <i class="fas fa-id-badge"></i> Pengembang
                </button>
                <button onclick="toggleModal('objModal')" class="bg-white hover:bg-slate-50 text-emerald-700 border border-emerald-200 font-semibold py-2 px-4 rounded-xl transition shadow-sm flex items-center justify-center gap-2">
                    <i class="fas fa-bullseye"></i> Tujuan Belajar
                </button>
            </div>
            
            <button onclick="goTo('formScreen')" class="w-full md:w-auto bg-gradient-to-r from-emerald-600 to-emerald-500 hover:from-emerald-700 hover:to-emerald-600 text-white font-bold py-4 px-12 rounded-2xl shadow-xl hover:shadow-2xl transition-all transform hover:-translate-y-1 text-lg">
                MULAI BELAJAR <i class="fas fa-arrow-right ml-2"></i>
            </button>
        </div>
    </section>

    <!-- Dev Info Floating Modal -->
    <div id="devModal" class="fixed inset-0 z-40 flex items-center justify-center bg-slate-900/60 backdrop-blur-sm hide">
        <div class="glass-modal rounded-3xl p-8 max-w-sm w-full mx-4 shadow-2xl relative text-center">
            <button onclick="toggleModal('devModal')" class="absolute top-4 right-4 text-slate-400 hover:text-slate-600"><i class="fas fa-times text-xl"></i></button>
            <div class="w-24 h-24 mx-auto bg-emerald-100 rounded-full border-4 border-white shadow-lg overflow-hidden mb-4 flex items-center justify-center">
                <img src="https://iili.io/nSJMP3X.md.jpg" alt="Mohamad Hasan" class="w-full h-full object-cover" onerror="this.onerror=null; this.src='https://placehold.co/150x150/10b981/ffffff?text=MH';">
            </div>
            <h2 class="text-xl font-bold text-slate-800">Mohamad Hasan</h2>
            <p class="text-emerald-600 font-medium text-sm mb-1">Senior Instructional Designer & Developer</p>
            <div class="bg-slate-50 rounded-xl p-3 mt-4 text-left text-sm text-slate-600">
                <p class="flex items-center gap-2 mb-2"><i class="fas fa-school text-emerald-500 w-4"></i> MTsS Al-Mubarak Marisa</p>
                <p class="flex items-center gap-2 mb-2"><i class="fas fa-map-marker-alt text-emerald-500 w-4"></i> Kab. Pohuwato</p>
                <p class="flex items-center gap-2"><i class="fas fa-envelope text-emerald-500 w-4"></i> hasanbisri6593@gmail.com</p>
            </div>
            <button onclick="toggleModal('devModal')" class="mt-6 w-full bg-slate-100 hover:bg-slate-200 text-slate-700 font-semibold py-2 rounded-xl transition">Kembali ke Cover</button>
        </div>
    </div>

    <!-- Objective Floating Modal -->
    <div id="objModal" class="fixed inset-0 z-40 flex items-center justify-center bg-slate-900/60 backdrop-blur-sm hide">
        <div class="glass-modal rounded-3xl p-6 md:p-8 max-w-lg w-full mx-4 shadow-2xl relative">
            <button onclick="toggleModal('objModal')" class="absolute top-4 right-4 text-slate-400 hover:text-slate-600"><i class="fas fa-times text-xl"></i></button>
            <h2 class="text-xl font-bold text-emerald-800 mb-4 flex items-center gap-2"><i class="fas fa-bullseye text-gold-500"></i> Tujuan Pembelajaran</h2>
            <div class="text-sm text-slate-700 space-y-4">
                <p class="leading-relaxed">Murid mampu Menganalisis kosa kata, pola kalimat, dan wacana tentang: <strong>الْحَفْلُ بِمَوْلِدِ الرَّسُوْل</strong> dengan pola kalimat <strong>مُحَمَّدٌ نَبِيٌّ – كَانَ مُحَمَّدٌ نَبِيًّا</strong>.</p>
                <div class="bg-emerald-50 border-l-4 border-emerald-500 p-3 rounded-r-xl">
                    <p class="font-arabic arabic-text text-xl mb-1 text-emerald-900">لَقَدْ كَانَ لَكُمْ فِي رَسُولِ اللَّهِ أُسْوَةٌ حَسَنَةٌ</p>
                    <p class="text-xs italic">"Sungguh, telah ada pada (diri) Rasulullah itu suri teladan yang baik bagimu..." (QS. Al-Ahzab: 21)</p>
                </div>
                <p class="leading-relaxed border-t pt-3 border-slate-200">
                    <span class="font-semibold text-emerald-700">Kurikulum Berbasis Cinta (KBC):</span> Pembelajaran ini dirancang sebagai wujud cinta Allah dan Rasul-Nya, cinta ilmu, serta cinta diri, sesama manusia, dan alam sekitar, khususnya mensyukuri kondisi alam pesisir Pohuwato.
                </p>
            </div>
            <button onclick="toggleModal('objModal')" class="mt-6 w-full bg-slate-100 hover:bg-slate-200 text-slate-700 font-semibold py-2 rounded-xl transition">Kembali ke Cover</button>
        </div>
    </div>

    <!-- 3. FORM SCREEN -->
    <section id="formScreen" class="min-h-screen flex items-center justify-center p-4 hide relative">
        <div class="glass-panel p-8 rounded-3xl max-w-md w-full animate-slide-up">
            <div class="text-center mb-8">
                <div class="w-16 h-16 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center text-2xl mx-auto mb-4"><i class="fas fa-user-graduate"></i></div>
                <h2 class="text-2xl font-bold text-slate-800">Data Diri Siswa</h2>
                <p class="text-slate-500 text-sm">Silakan isi data untuk memulai pembelajaran</p>
            </div>
            <div class="space-y-5">
                <div>
                    <label class="block text-sm font-semibold text-slate-700 mb-1">Nama Lengkap</label>
                    <input type="text" id="inputName" class="w-full px-4 py-3 rounded-xl border border-slate-200 focus:outline-none focus:ring-2 focus:ring-emerald-500 focus:border-transparent transition" placeholder="Masukkan nama...">
                </div>
                <div>
                    <label class="block text-sm font-semibold text-slate-700 mb-1">Kelas</label>
                    <select id="inputClass" class="w-full px-4 py-3 rounded-xl border border-slate-200 focus:outline-none focus:ring-2 focus:ring-emerald-500 transition">
                        <option value="">Pilih Kelas...</option>
                        <option value="IX-A">IX - A</option>
                        <option value="IX-B">IX - B</option>
                        <option value="IX-C">IX - C</option>
                    </select>
                </div>
                <button onclick="submitForm()" class="w-full bg-emerald-600 hover:bg-emerald-700 text-white font-bold py-3 px-4 rounded-xl shadow-md transition mt-4">
                    Lanjutkan <i class="fas fa-chevron-right ml-2"></i>
                </button>
            </div>
        </div>
    </section>

    <!-- 4. GUIDE SCREEN -->
    <section id="guideScreen" class="min-h-screen flex items-center justify-center p-4 hide">
        <div class="glass-panel p-6 md:p-10 rounded-3xl max-w-2xl w-full animate-fade-in relative">
            <h2 class="text-2xl md:text-3xl font-bold text-emerald-800 mb-2 text-center" id="welcomeText">Selamat Datang!</h2>
            <div class="flex justify-center mb-6">
                <div class="flex gap-2" id="guideIndicators">
                    <div class="w-3 h-3 rounded-full bg-emerald-600 transition-colors"></div>
                    <div class="w-3 h-3 rounded-full bg-slate-200 transition-colors"></div>
                    <div class="w-3 h-3 rounded-full bg-slate-200 transition-colors"></div>
                </div>
            </div>
            
            <div id="guideContent" class="text-center min-h-[200px] flex flex-col items-center justify-center"></div>

            <div class="flex justify-between mt-8">
                <button id="btnGuidePrev" onclick="changeGuide(-1)" class="text-slate-500 font-semibold px-4 py-2 invisible">Kembali</button>
                <button id="btnGuideNext" onclick="changeGuide(1)" class="bg-emerald-600 hover:bg-emerald-700 text-white font-semibold py-2 px-6 rounded-xl shadow transition">Selanjutnya</button>
            </div>
        </div>
    </section>

    <!-- 5. MAIN MENU DASHBOARD -->
    <section id="menuScreen" class="min-h-screen flex flex-col p-4 md:p-8 hide">
        <div class="max-w-4xl w-full mx-auto animate-fade-in">
            <div class="glass-panel p-5 rounded-2xl flex items-center justify-between mb-8">
                <div class="flex items-center gap-4">
                    <div class="w-12 h-12 bg-gradient-to-br from-emerald-400 to-emerald-600 text-white rounded-full flex items-center justify-center text-xl font-bold shadow-md">
                        <span id="initialsDisplay"></span>
                    </div>
                    <div>
                        <h3 id="nameDisplay" class="font-bold text-slate-800 text-lg"></h3>
                        <p id="classDisplay" class="text-emerald-600 text-sm font-semibold"></p>
                    </div>
                </div>
                <div class="text-right hidden md:block">
                    <p class="text-xs text-slate-500 uppercase tracking-wider font-bold">Progress Belajar</p>
                    <div class="flex items-center gap-2 mt-1">
                        <div class="w-32 h-2 bg-slate-200 rounded-full overflow-hidden">
                            <div id="progressBar" class="h-full bg-gold-500 w-0 transition-all duration-1000"></div>
                        </div>
                        <span id="progressText" class="text-sm font-bold text-slate-700">0%</span>
                    </div>
                </div>
            </div>

            <h2 class="text-2xl font-bold text-slate-800 mb-6 px-2">Peta Pembelajaran</h2>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- BELAJAR -->
                <div onclick="startSection('belajar')" class="glass-panel p-6 rounded-3xl cursor-pointer hover:-translate-y-2 transition-all duration-300 relative overflow-hidden group border-b-4 border-emerald-500">
                    <div class="absolute top-0 right-0 p-4 opacity-10 group-hover:opacity-20 transition text-6xl text-emerald-600"><i class="fas fa-book-open"></i></div>
                    <div class="w-14 h-14 bg-emerald-100 text-emerald-600 rounded-2xl flex items-center justify-center text-2xl mb-4 shadow-inner"><i class="fas fa-book-open"></i></div>
                    <h3 class="text-xl font-bold text-slate-800 mb-2">1. BELAJAR</h3>
                    <p class="text-sm text-slate-600 mb-4">Materi mufradat, qira'ah, dan qawaid (كَانَ) terpadu.</p>
                    <div class="flex justify-between items-center text-sm font-bold text-emerald-600">
                        <span>Status: Terbuka</span> <i class="fas fa-unlock"></i>
                    </div>
                </div>

                <!-- BERMAIN -->
                <div id="cardBermain" onclick="startSection('bermain')" class="glass-panel p-6 rounded-3xl cursor-pointer transition-all duration-300 relative overflow-hidden group border-b-4 border-slate-300 opacity-70">
                    <div class="absolute inset-0 bg-slate-100/50 backdrop-blur-[2px] z-10 flex items-center justify-center" id="lockBermain">
                        <div class="bg-white p-3 rounded-full shadow-lg text-slate-400"><i class="fas fa-lock text-xl"></i></div>
                    </div>
                    <div class="w-14 h-14 bg-amber-100 text-amber-600 rounded-2xl flex items-center justify-center text-2xl mb-4 shadow-inner"><i class="fas fa-gamepad"></i></div>
                    <h3 class="text-xl font-bold text-slate-800 mb-2">2. BERMAIN</h3>
                    <p class="text-sm text-slate-600 mb-4">10 Tantangan gamifikasi interaktif literasi & numerasi.</p>
                    <div class="flex justify-between items-center text-sm font-bold text-slate-500" id="statusBermainText">
                        <span>Status: Terkunci</span> <i class="fas fa-lock"></i>
                    </div>
                </div>

                <!-- BERLATIH -->
                <div id="cardBerlatih" onclick="startSection('berlatih')" class="glass-panel p-6 rounded-3xl cursor-pointer transition-all duration-300 relative overflow-hidden group border-b-4 border-slate-300 opacity-70">
                    <div class="absolute inset-0 bg-slate-100/50 backdrop-blur-[2px] z-10 flex items-center justify-center" id="lockBerlatih">
                        <div class="bg-white p-3 rounded-full shadow-lg text-slate-400"><i class="fas fa-lock text-xl"></i></div>
                    </div>
                    <div class="w-14 h-14 bg-blue-100 text-blue-600 rounded-2xl flex items-center justify-center text-2xl mb-4 shadow-inner"><i class="fas fa-tasks"></i></div>
                    <h3 class="text-xl font-bold text-slate-800 mb-2">3. BERLATIH</h3>
                    <p class="text-sm text-slate-600 mb-4">Asesmen berjenjang level 1 hingga HOTS (Level 3).</p>
                    <div class="flex justify-between items-center text-sm font-bold text-slate-500" id="statusBerlatihText">
                        <span>Status: Terkunci</span> <i class="fas fa-lock"></i>
                    </div>
                </div>
            </div>
            
            <div id="btnReportContainer" class="mt-8 text-center hide animate-slide-up">
                <button onclick="generateReport()" class="bg-slate-800 hover:bg-slate-900 text-white font-bold py-3 px-8 rounded-xl shadow-lg transition flex items-center mx-auto gap-2 mb-4">
                    <i class="fas fa-file-pdf text-red-400"></i> Lihat & Unduh Laporan PDF
                </button>
            </div>
        </div>
    </section>

    <!-- 6. BELAJAR CONTAINER -->
    <section id="belajarScreen" class="min-h-screen flex flex-col hide">
        <header class="bg-white/80 backdrop-blur shadow-sm p-4 sticky top-0 z-20">
            <div class="max-w-4xl mx-auto flex justify-between items-center">
                <h2 class="font-bold text-emerald-800 flex items-center gap-2"><i class="fas fa-book-open"></i> Sesi Belajar</h2>
                <button onclick="backToMenu()" class="text-slate-500 hover:text-red-500 font-semibold text-sm transition"><i class="fas fa-times"></i> Keluar</button>
            </div>
            <div class="max-w-4xl mx-auto mt-2 h-1 bg-slate-200 rounded-full">
                <div id="belajarProgressBar" class="h-full bg-emerald-500 w-1/6 transition-all duration-300"></div>
            </div>
        </header>
        <main class="flex-grow p-4 md:p-8 flex items-center justify-center overflow-y-auto">
            <div id="belajarContent" class="glass-panel p-6 md:p-10 rounded-3xl max-w-4xl w-full min-h-[60vh] animate-fade-in relative"></div>
        </main>
    </section>

    <!-- 7. BERMAIN CONTAINER -->
    <section id="bermainScreen" class="min-h-screen flex flex-col hide bg-amber-50">
        <header class="bg-white/90 backdrop-blur shadow-sm p-4 sticky top-0 z-20 border-b border-amber-200">
            <div class="max-w-4xl mx-auto flex justify-between items-center">
                <h2 class="font-bold text-amber-600 flex items-center gap-2"><i class="fas fa-gamepad"></i> Sesi Bermain</h2>
                <div class="font-bold text-slate-700 bg-amber-100 px-3 py-1 rounded-lg text-sm">Tantangan <span id="bermainCurrentNum">1</span>/10</div>
                <button onclick="backToMenu()" class="text-slate-500 hover:text-red-500 font-semibold text-sm transition"><i class="fas fa-times"></i></button>
            </div>
        </header>
        <main class="flex-grow p-4 md:p-6 flex items-center justify-center overflow-y-auto">
            <div id="bermainContent" class="bg-white p-6 md:p-8 rounded-3xl max-w-4xl w-full shadow-xl border border-amber-100 animate-slide-up"></div>
        </main>
    </section>

    <!-- 8. BERLATIH CONTAINER -->
    <section id="berlatihScreen" class="min-h-screen flex flex-col hide bg-blue-50">
        <header class="bg-white/90 backdrop-blur shadow-sm p-4 sticky top-0 z-20 border-b border-blue-200">
            <div class="max-w-4xl mx-auto flex justify-between items-center">
                <h2 class="font-bold text-blue-600 flex items-center gap-2"><i class="fas fa-tasks"></i> Asesmen Akhir</h2>
                <div class="flex items-center gap-4">
                    <span id="berlatihLevelBadge" class="text-xs font-bold text-white bg-blue-500 px-2 py-1 rounded">Level 1</span>
                    <span class="font-bold text-slate-700 text-sm">Soal <span id="berlatihCurrentNum">1</span>/10</span>
                </div>
            </div>
        </header>
        <main class="flex-grow p-4 md:p-6 flex items-center justify-center overflow-y-auto">
            <div id="berlatihContent" class="bg-white p-6 md:p-8 rounded-3xl max-w-4xl w-full shadow-xl border border-blue-100 animate-slide-up"></div>
        </main>
    </section>

    <!-- 9. REPORT SCREEN -->
    <section id="reportScreen" class="min-h-screen p-4 md:p-8 hide bg-slate-100 flex flex-col items-center">
        <div class="w-full max-w-3xl flex justify-between mb-4">
            <button onclick="backToMenu()" class="bg-white text-slate-600 px-4 py-2 rounded-lg shadow font-semibold hover:bg-slate-50"><i class="fas fa-arrow-left"></i> Menu</button>
            <button onclick="downloadPDF()" class="bg-emerald-600 text-white px-4 py-2 rounded-lg shadow font-bold hover:bg-emerald-700"><i class="fas fa-download"></i> Unduh PDF</button>
        </div>

        <div id="printableReport" class="bg-white w-full max-w-3xl shadow-2xl p-8 md:p-12 text-slate-800">
            <!-- Kop -->
            <div class="border-b-4 border-emerald-600 pb-4 mb-6 flex justify-between items-center">
                <div>
                    <h1 class="text-2xl font-bold text-emerald-800 uppercase">Laporan Hasil Belajar</h1>
                    <p class="text-sm font-semibold text-slate-600">MPI: الْحَفْلُ بِمَوْلِدِ الرَّسُوْل (Bahasa Arab Kelas IX)</p>
                </div>
                <div class="text-right text-xs text-slate-500">
                    <p>Dikembangkan oleh:</p>
                    <p class="font-bold text-slate-700">Mohamad Hasan</p>
                    <p>MTsS Al-Mubarak Marisa</p>
                </div>
            </div>

            <!-- Student Data -->
            <div class="bg-slate-50 p-4 rounded-lg mb-6 border border-slate-200">
                <table class="w-full text-sm">
                    <tr><td class="py-1 w-1/3 font-semibold text-slate-600">Nama Siswa</td><td class="font-bold">: <span id="repName"></span></td></tr>
                    <tr><td class="py-1 font-semibold text-slate-600">Kelas</td><td class="font-bold">: <span id="repClass"></span></td></tr>
                    <tr><td class="py-1 font-semibold text-slate-600">Tanggal</td><td class="font-bold">: <span id="repDate"></span></td></tr>
                </table>
            </div>

            <!-- Scores -->
            <div class="grid grid-cols-2 gap-6 mb-8">
                <div class="border border-amber-200 rounded-xl p-4 text-center bg-amber-50">
                    <h3 class="text-amber-800 font-bold mb-2">Nilai Bermain</h3>
                    <div class="text-4xl font-black text-amber-600" id="repBermainScore">0</div>
                    <p class="text-xs text-amber-700 mt-2">Akurasi Tantangan</p>
                </div>
                <div class="border border-blue-200 rounded-xl p-4 text-center bg-blue-50">
                    <h3 class="text-blue-800 font-bold mb-2">Nilai Berlatih (Asesmen)</h3>
                    <div class="text-4xl font-black text-blue-600" id="repBerlatihScore">0</div>
                    <p class="text-xs text-blue-700 mt-2 font-bold" id="repPredikat"></p>
                </div>
            </div>

            <!-- Breakdown -->
            <div class="mb-6">
                <h3 class="font-bold text-slate-800 border-b pb-2 mb-3">Rincian Penguasaan Materi (Asesmen)</h3>
                <ul class="text-sm space-y-2 text-slate-600">
                    <li class="flex justify-between"><span>Level 1 (Dasar & Kosakata):</span> <strong id="repL1">0/3</strong></li>
                    <li class="flex justify-between"><span>Level 2 (Penerapan Qawaid):</span> <strong id="repL2">0/4</strong></li>
                    <li class="flex justify-between"><span>Level 3 (HOTS & Literasi Kritis):</span> <strong id="repL3">0/3</strong></li>
                </ul>
            </div>

            <!-- KBC Notes -->
            <div class="bg-emerald-50 border-l-4 border-emerald-500 p-4 rounded-r-lg mb-8">
                <h3 class="font-bold text-emerald-800 text-sm mb-1">Catatan Kurikulum Berbasis Cinta (KBC):</h3>
                <p class="text-xs text-emerald-700 leading-relaxed text-justify">
                    Siswa telah menunjukkan partisipasi aktif dalam mempelajari nilai-nilai kecintaan kepada Rasulullah SAW, kelestarian lingkungan pesisir, dan kepedulian sosial melalui literasi kontekstual wilayah Pohuwato. Tingkatkan terus semangat cinta ilmu.
                </p>
            </div>

            <!-- Signatures -->
            <div class="flex justify-between text-center mt-12 text-sm">
                <div>
                    <p class="mb-16">Mengetahui,<br>Orang Tua / Wali</p>
                    <p class="border-t border-slate-400 pt-1 w-32 mx-auto">( ......................... )</p>
                </div>
                <div>
                    <p class="mb-16">Pohuwato, <span id="repDateSign"></span><br>Guru Mata Pelajaran</p>
                    <p class="border-t border-slate-400 pt-1 w-32 mx-auto font-bold text-slate-800">Mohamad Hasan</p>
                </div>
            </div>
        </div>
    </section>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        // ==========================================
        // KONFIGURASI GOOGLE APPS SCRIPT
        // ==========================================
        const GAS_URL = "URL_GAS_ANDA_DISINI"; // <-- GANTI DENGAN URL WEB APP ANDA
        
        // --- 1. STATE & DATA ---
        const state = {
            student: { name: '', class: '' },
            unlocked: { belajar: true, bermain: false, berlatih: false },
            belajarSlide: 0,
            belajarCompleted: [], 
            guideStep: 0,
            bermain: { current: 0, score: 0 },
            berlatih: { current: 0, score: 0, breakdown: { l1: 0, l2: 0, l3: 0 } },
            currentScreen: 'splashScreen',
            answers: { benar: 0, salah: 0, details: [] },
            isSaved: false
        };

        const belajarData = [
            {
                title: "1. Mengenal Tradisi Maulid",
                concept: "Maulid Nabi adalah peringatan hari lahir Nabi Muhammad SAW. Dalam bahasa Arab disebut الْحَفْلُ بِمَوْلِدِ الرَّسُوْل (Al-Haflu bimaulidir rasul).",
                local: "Di Kabupaten Pohuwato, khususnya di pesisir kawasan Pohon Cinta, para nelayan dan masyarakat berkumpul mengadakan doa bersama dan menyiapkan makanan khas daerah sebagai bentuk kegembiraan.",
                kbc: "Ini adalah wujud Cinta Allah dan Rasul-Nya (Mahabbah). Dengan berkumpul, warga juga memupuk cinta sesama manusia melalui silaturahmi yang rukun.",
                quran: { text: "قُلْ بِفَضْلِ اللَّهِ وَبِرَحْمَتِهِ فَبِذَٰلِكَ فَلْيَفْرَحُوا", surah: "QS. Yunus: 58", trans: "Katakanlah: 'Dengan kurnia Allah dan rahmat-Nya, hendaklah dengan itu mereka bergembira.'" },
                interactive: {
                    type: "mc",
                    q: "Apa nama perayaan hari lahir Nabi dalam bahasa Arab?",
                    opts: ["الْحَفْلُ بِالْهِجْرَةِ", "الْحَفْلُ بِمَوْلِدِ الرَّسُوْل", "الْحَفْلُ بِالنُّزُوْلِ"],
                    ans: 1,
                    feedback: "Benar! الْحَفْلُ بِمَوْلِدِ الرَّسُوْل artinya Perayaan Maulid Rasul."
                }
            },
            {
                title: "2. Kosakata (الْمُفْرَدَات) Tema Maulid",
                concept: "Mari perhatikan kosakata penting berikut: مَوْلِدٌ (Kelahiran), يَحْتَفِلُ (Merayakan), ذِكْرَى (Peringatan), الْمَسْجِدُ (Masjid), dan أُسْوَةٌ (Teladan).",
                local: "Keluarga penambang dan pedagang di Pohuwato menyempatkan diri meninggalkan aktivitas pasar sejenak menuju الْمَسْجِدُ untuk memperingati ذِكْرَى maulid.",
                kbc: "Cinta ilmu diwujudkan dengan bersemangat menghafal dan memahami bahasa Al-Qur'an (Bahasa Arab).",
                quran: { text: "إِنَّا أَنْزَلْنَاهُ قُرْآنًا عَرَبِيًّا لَعَلَّكُمْ تَعْقِلُونَ", surah: "QS. Yusuf: 2", trans: "Sesungguhnya Kami menurunkannya berupa Al Quran berbahasa Arab, agar kamu memahaminya." },
                interactive: {
                    type: "mc",
                    q: "Pilih arti kata yang tepat untuk 'يَحْتَفِلُ':",
                    opts: ["Mengingat", "Melahirkan", "Merayakan"],
                    ans: 2,
                    feedback: "Tepat! يَحْتَفِلُ artinya Merayakan."
                }
            },
            {
                title: "3. Nabi Muhammad Sebagai Teladan",
                concept: "Sebelum mengenal tata bahasa, pahami bahwa Rasulullah adalah teladan sempurna (أُسْوَةٌ حَسَنَةٌ). Sifat-sifat beliau seperti jujur (صَادِقٌ) dan penyayang (رَحِيْمٌ) harus dicontoh.",
                local: "Sebagaimana para nelayan di laut bergantung pada kompas, hidup manusia bergantung pada teladan Rasulullah agar selamat dunia akhirat.",
                kbc: "Kelestarian lingkungan: Nabi mengajarkan untuk tidak merusak alam. Ini harus diterapkan saat mengelola wilayah dataran rendah Pohuwato.",
                quran: { text: "لَقَدْ كَانَ لَكُمْ فِي رَسُولِ اللَّهِ أُسْوَةٌ حَسَنَةٌ", surah: "QS. Al-Ahzab: 21", trans: "Sungguh, telah ada pada (diri) Rasulullah itu suri teladan yang baik bagimu." },
                interactive: {
                    type: "mc",
                    q: "Apa arti dari 'أُسْوَةٌ حَسَنَةٌ'?",
                    opts: ["Suri Teladan yang Baik", "Hari Kelahiran", "Tempat Ibadah"],
                    ans: 0,
                    feedback: "Masya Allah, Benar!"
                }
            },
            {
                title: "4. Kaidah Dasar: Jumlah Ismiyyah",
                concept: "Pola kalimat dasar dalam bahasa Arab disebut Jumlah Ismiyyah (Mubtada' dan Khabar). Keduanya berharakat dhummah (Marfu').<br>Contoh: مُحَمَّدٌ نَبِيٌّ (Muhammad adalah seorang nabi).",
                local: "Sama halnya dengan 'Nelayan itu rajin' (الصَّيَّادُ نَشِيْطٌ), kaidah dasar ini membentuk kalimat yang sempurna.",
                kbc: "Keteraturan tata bahasa mengajarkan kita disiplin dan aturan kehidupan yang ditata rapi oleh Allah SWT.",
                quran: { text: "وَخَلَقَ كُلَّ شَيْءٍ فَقَدَّرَهُ تَقْدِيرًا", surah: "QS. Al-Furqan: 2", trans: "...dan Dia telah menciptakan segala sesuatu, dan Dia menetapkan ukuran-ukurannya dengan serapi-rapinya." },
                interactive: {
                    type: "mc",
                    q: "Manakah contoh pola kalimat Mubtada' & Khabar (Ismiyyah) yang benar?",
                    opts: ["مُحَمَّدٌ نَبِيًّا", "مُحَمَّدٌ نَبِيٌّ", "نَبِيٌّ مُحَمَّدٌ"],
                    ans: 1,
                    feedback: "Tepat! Keduanya berharakat Dhummah (Marfu')."
                }
            },
            {
                title: "5. Memasukkan كَانَ ke dalam Kalimat",
                concept: "Penting! Jika kata 'كَانَ' (Kaana) masuk ke dalam kalimat Jumlah Ismiyyah, maka aturannya berubah:<br>1. Mubtada' tetap dhummah (Isim Kaana).<br>2. Khabar BERUBAH menjadi Fathah/Fathatain (Khabar Kaana).<br><br>Asal: مُحَمَّدٌ نَبِيٌّ<br>Menjadi: <strong>كَانَ مُحَمَّدٌ نَبِيًّا</strong> (Adalah Muhammad seorang nabi).",
                local: "Perhatikan perubahan harakat ini seperti perubahan air laut pesisir Pohuwato saat pasang dan surut, sebuah ketetapan yang harus dipelajari.",
                kbc: "Cinta ilmu berarti sabar dan teliti memahami perubahan aturan (kaidah) untuk mendapatkan makna yang benar.",
                quran: { text: "وَكَانَ اللَّهُ غَفُورًا رَحِيمًا", surah: "QS. Al-Fath: 14", trans: "Dan adalah Allah Maha Pengampun lagi Maha Penyayang." },
                interactive: {
                    type: "mc",
                    q: "Ubah kalimat 'الطَّالِبُ نَشِيْطٌ' dengan memasukkan 'كَانَ':",
                    opts: ["كَانَ الطَّالِبَ نَشِيْطٌ", "كَانَ الطَّالِبُ نَشِيْطُ", "كَانَ الطَّالِبُ نَشِيْطًا"],
                    ans: 2,
                    feedback: "Luar Biasa! Isim Kaana (Marfu'), Khabar Kaana (Mansub/Fathatain)."
                }
            },
            {
                title: "6. Wacana Singkat (Qira'ah)",
                concept: "Mari baca wacana ini:<br>يَحْتَفِلُ الْمُسْلِمُوْنَ بِمَوْلِدِ الرَّسُوْلِ فِي شَهْرِ رَبِيْعِ الْأَوَّل. كَانَ مُحَمَّدٌ نَبِيًّا عَظِيْمًا. وَهُوَ أُسْوَةٌ حَسَنَةٌ لَنَا.<br>(Umat Islam merayakan maulid rasul di bulan Rabiul Awal. Adalah Muhammad seorang nabi yang agung. Dan beliau adalah teladan yang baik bagi kita).",
                local: "Wacana ini sering dibacakan oleh pemuka agama di kompleks perkantoran Pohuwato saat acara Maulid tingkat kabupaten.",
                kbc: "Cinta tanah air dan moderasi beragama tumbuh dengan merawat tradisi keislaman yang membawa pesan kedamaian (rahmatan lil 'alamin).",
                quran: { text: "وَمَا أَرْسَلْنَاكَ إِلَّا رَحْمَةً لِلْعَالَمِينَ", surah: "QS. Al-Anbiya: 107", trans: "Dan tiadalah Kami mengutus kamu, melainkan untuk (menjadi) rahmat bagi semesta alam." },
                interactive: {
                    type: "mc",
                    q: "Kapan umat Islam biasa merayakan Maulid Nabi berdasarkan teks?",
                    opts: ["Bulan Ramadhan", "Bulan Rabiul Awal", "Bulan Dzulhijjah"],
                    ans: 1,
                    feedback: "Alhamdulillah, seluruh materi telah tuntas! Lanjut ke menu BERMAIN."
                }
            }
        ];

        const bermainData = [
            { type: "mc", stimulus: "Di pagi hari yang cerah di kawasan pantai Pohon Cinta...", q: "Berdasarkan ilustrasi di atas, apa bahasa Arab dari 'Perayaan Maulid Rasul'?", opts: ["ذِكْرَى الْهِجْرَةِ", "الْحَفْلُ بِمَوْلِدِ الرَّسُوْل", "نُزُوْلُ الْقُرْآنِ", "عِيْدُ الْفِطْرِ"], ans: 1 },
            { type: "mc", stimulus: "Pak Rahman, seorang pedagang di pasar tradisional Marisa...", q: "Manakah penulisan kalimat 'Muhammad adalah seorang nabi' (tanpa kata Kaana) yang benar secara kaidah?", opts: ["مُحَمَّدًا نَبِيٌّ", "مُحَمَّدٌ نَبِيًّا", "مُحَمَّدٌ نَبِيٌّ", "مُحَمَّدٍ نَبِيٍّ"], ans: 2 },
            { type: "mc", stimulus: "Dalam sebuah pengajian di kompleks perkantoran...", q: "Apa terjemahan dari kata 'أُسْوَةٌ حَسَنَةٌ' yang sering diucapkan ustadz tersebut?", opts: ["Rahmat semesta alam", "Suri teladan yang baik", "Pemimpin yang adil", "Utusan Allah"], ans: 1 },
            { type: "match", stimulus: "Siswa MTsS Al-Mubarak Marisa sedang berlatih menerjemahkan...", q: "Cocokkan kata 'يَحْتَفِلُ' dengan arti bahasa Indonesianya!", opts: ["Menyanyi", "Merayakan", "Membaca"], ans: 1 },
            { type: "mc", stimulus: "Siti, seorang siswi kelas IX, sedang mempelajari kaidah 'Kana'...", q: "Jika ditambahkan 'كَانَ', kalimat 'الرَّسُوْلُ رَحِيْمٌ' berubah menjadi:", opts: ["كَانَ الرَّسُوْلُ رَحِيْمًا", "كَانَ الرَّسُوْلَ رَحِيْمٌ", "كَانَ الرَّسُوْلُ رَحِيْمٌ", "كَانَ الرَّسُوْلَ رَحِيْمًا"], ans: 0 },
            { type: "mc", stimulus: "Masyarakat di pedalaman Pohuwato yang berprofesi sebagai penambang...", q: "Kata 'نَبِيًّا' (Nabiyyan) dalam kalimat di atas berkedudukan sebagai?", opts: ["Isim Kaana (Marfu')", "Mubtada'", "Khabar Kaana (Mansub)", "Fa'il"], ans: 2 },
            { type: "match", stimulus: "Al-Qur'an diturunkan dalam bahasa Arab agar mudah dipahami...", q: "Pilih arti yang tepat untuk kosakata 'ذِكْرَى':", opts: ["Hari Lahir", "Peringatan", "Perayaan"], ans: 1 },
            { type: "mc", stimulus: "Kegiatan gotong royong membersihkan masjid di pesisir Pohuwato...", q: "Apa bahasa Arab dari kata 'Masjid' dalam bentuk tunggal?", opts: ["الْمَسْجِدُ", "الْمَدْرَسَةُ", "الْمَيْدَانُ", "السُّوْقُ"], ans: 0 },
            { type: "mc", stimulus: "Ustadz Hasan dari MTsS Al-Mubarak memberikan tugas tata bahasa...", q: "Bentuk kalimat yang benar setelah ditambah 'كَانَ' adalah?", opts: ["كَانَ اللهُ غَفُوْرٌ", "كَانَ اللهَ غَفُوْرًا", "كَانَ اللهُ غَفُوْرًا", "كَانَ اللهَ غَفُوْرٌ"], ans: 2 },
            { type: "mc", stimulus: "Akhir bulan Rabiul Awal telah tiba. Evaluasi pembelajaran sejarah...", q: "Kalimat bahasa Arab yang bermakna 'Umat Islam merayakan maulid nabi' adalah?", opts: ["يَحْتَفِلُ الْمُسْلِمُوْنَ بِمَوْلِدِ الرَّسُوْل", "ذَهَبَ الْمُسْلِمُوْنَ إِلَى الْمَسْجِد", "قَرَأَ الْمُسْلِمُوْنَ الْقُرْآن", "صَلَّى الْمُسْلِمُوْنَ فِي الْمَسْجِد"], ans: 0 }
        ];

        const berlatihData = [
            { level: 1, points: 8, type: "mc", stimulus: "Sebagai bentuk kecintaan (Mahabbah) terhadap budaya literasi...", q: "Kata 'مَوْلِدٌ' (Maulidun) secara harfiah memiliki arti...", opts: ["Perayaan", "Kelahiran", "Peringatan", "Kebangkitan"], ans: 1 },
            { level: 1, points: 8, type: "mc", stimulus: "Masyarakat Kabupaten Pohuwato, khususnya di dataran rendah...", q: "Terjemahan yang tepat untuk kata 'يَحْتَفِلُ' adalah...", opts: ["Berdoa", "Membaca", "Merayakan", "Berdiam diri"], ans: 2 },
            { level: 1, points: 8, type: "mc", stimulus: "Salah satu ayat yang sering dibaca saat peringatan Maulid...", q: "Potongan ayat yang berbunyi 'أُسْوَةٌ حَسَنَةٌ' bermakna...", opts: ["Pemimpin umat", "Rasul terakhir", "Suri teladan yang baik", "Orang yang terpercaya"], ans: 2 },
            { level: 2, points: 10, type: "mc", stimulus: "Ahmad sedang merenungkan kekuasaan Allah saat melihat luasnya lautan...", q: "Berdasarkan kaidah Jumlah Ismiyyah, kata 'رَحِيْمٌ' dalam kalimat 'اللهُ رَحِيْمٌ' berkedudukan sebagai...", opts: ["Mubtada'", "Khabar", "Fa'il", "Maf'ul Bih"], ans: 1 },
            { level: 2, points: 10, type: "mc", stimulus: "Guru bahasa Arab MTsS Al-Mubarak menjelaskan kaidah perubahan harakat...", q: "Jika dimasukkan kata 'كَانَ', kalimat 'الْجَوُّ حَارٌ' akan berubah menjadi...", opts: ["كَانَ الْجَوُّ حَارٌ", "كَانَ الْجَوَّ حَارًا", "كَانَ الْجَوُّ حَارًا", "كَانَ الْجَوَّ حَارٌ"], ans: 2 },
            { level: 2, points: 10, type: "mc", stimulus: "Di dalam Al-Qur'an, sering ditemukan penggunaan struktur kaidah Kana...", q: "Kata 'غَفُورًا' (Ghafuuran) pada ayat di atas berharakat fathatain karena ia berkedudukan sebagai...", opts: ["Mubtada'", "Isim Kaana", "Khabar Kaana", "Sifat"], ans: 2 },
            { level: 2, points: 10, type: "mc", stimulus: "Saat merayakan Maulid, seorang siswa membaca teks...", q: "Mengapa kata 'نَبِيًّا' (Nabiyyan) diakhiri dengan harakat fathatain (tanwin fathah)?", opts: ["Karena ia menjadi subjek kalimat", "Karena didahului oleh kata 'كَانَ' sehingga menjadi khabarnya", "Karena ia terletak di akhir kalimat", "Karena ia adalah nama orang"], ans: 1 },
            { level: 3, points: 12, type: "mc", stimulus: "Bacalah paragraf berikut: 'فِي شَهْرِ رَبِيْعِ الْأَوَّل، يَجْتَمِعُ النَّاسُ...", q: "Dari teks wacana di atas, apa gagasan utama/kesimpulan kegiatan masyarakat desa tersebut?", opts: ["Masyarakat membangun masjid baru di bulan Rabiul Awal", "Masyarakat mengadakan perayaan Maulid Nabi secara berjamaah untuk meneladani Rasulullah", "Nabi Muhammad pernah berkunjung ke desa Pohuwato", "Kegiatan masyarakat berpusat pada penangkapan ikan di laut"], ans: 1 },
            { level: 3, points: 12, type: "mc", stimulus: "Seorang peneliti pendidikan agama Islam dari Kementerian Agama RI...", q: "Secara struktur tata bahasa (Nahwu), apa perbedaan fundamental yang terjadi akibat penambahan kata 'كَانَ' dari kalimat (1) ke kalimat (2)?", opts: ["Tidak ada perubahan harakat, hanya beda arti waktu.", "Harakat mubtada' berubah menjadi fathah, khabar tetap dhummah.", "Status mubtada' berubah menjadi Isim Kana (tetap rafa'), dan status khabar berubah menjadi Khabar Kana (menjadi nashab).", "Kedua kata berubah menjadi majrur (kasrah)."], ans: 2 },
            { level: 3, points: 12, type: "mc", stimulus: "Dalam kehidupan nyata di pesisir Pohuwato, menjaga keseimbangan ekosistem...", q: "Jika kita ingin membuat kalimat baru 'Pesisir (الشَّاطِئُ) itu bersih (نَظِيْفٌ)' dengan menggunakan kaidah yang sama seperti ungkapan di atas (memakai Kana), susunan yang benar dan bermakna tepat adalah?", opts: ["كَانَ الشَّاطِئُ نَظِيْفٌ", "كَانَ الشَّاطِئَ نَظِيْفًا", "كَانَ الشَّاطِئُ نَظِيْفًا", "كَانَ الشَّاطِئِ نَظِيْفٍ"], ans: 2 }
        ];

        // --- CORE FUNCTIONS ---
        function initApp() {
            setTimeout(() => {
                document.getElementById('splashScreen').classList.add('opacity-0');
                setTimeout(() => {
                    document.getElementById('splashScreen').classList.add('hide');
                    document.getElementById('coverScreen').classList.remove('hide');
                }, 500);
            }, 2000);
        }

        function toggleModal(modalId) {
            const modal = document.getElementById(modalId);
            if (modal.classList.contains('hide')) modal.classList.remove('hide');
            else modal.classList.add('hide');
        }

        function showGlobalModal(title, msg, type = 'info', disableBtn = false) {
            document.getElementById('modalTitle').innerText = title;
            document.getElementById('modalMessage').innerText = msg;
            
            const icon = document.getElementById('modalIcon');
            if(type === 'error') icon.innerHTML = '<i class="fas fa-exclamation-circle text-red-500"></i>';
            else if(type === 'success') icon.innerHTML = '<i class="fas fa-check-circle text-emerald-500"></i>';
            else if(type === 'lock') icon.innerHTML = '<i class="fas fa-lock text-slate-500"></i>';
            else if(type === 'loading') icon.innerHTML = '<i class="fas fa-spinner fa-spin text-emerald-500"></i>';
            else icon.innerHTML = '<i class="fas fa-info-circle text-blue-500"></i>';

            document.getElementById('modalBtn').style.display = disableBtn ? 'none' : 'block';
            document.getElementById('globalModal').classList.remove('hide');
        }

        function closeModal() {
            document.getElementById('globalModal').classList.add('hide');
        }

        function goTo(screenId) {
            const screens = ['coverScreen', 'formScreen', 'guideScreen', 'menuScreen', 'belajarScreen', 'bermainScreen', 'berlatihScreen', 'reportScreen'];
            screens.forEach(s => document.getElementById(s).classList.add('hide'));
            document.getElementById(screenId).classList.remove('hide');
            state.currentScreen = screenId;
            
            if(screenId === 'guideScreen') renderGuide();
            if(screenId === 'menuScreen') updateDashboard();
        }

        function submitForm() {
            const name = document.getElementById('inputName').value.trim();
            const cls = document.getElementById('inputClass').value;
            
            if (!name || !cls) {
                showGlobalModal("Data Belum Lengkap", "Silakan masukkan Nama Lengkap dan Kelas Anda terlebih dahulu.", "error");
                return;
            }
            
            state.student.name = name;
            state.student.class = cls;
            goTo('guideScreen');
        }

        // --- GUIDE SCREEN LOGIC ---
        const guides = [
            { icon: "fa-book-open text-emerald-500", title: "1. Belajar Mendalam", text: "Pelajari materi tentang Maulid, kosa kata, dan kaidah bahasa Arab (Kana). Kerjakan aktivitas di tiap halaman." },
            { icon: "fa-gamepad text-amber-500", title: "2. Bermain & Tantangan", text: "Uji pemahamanmu lewat 10 tantangan interaktif berstimulus cerita menarik tentang daerah kita." },
            { icon: "fa-tasks text-blue-500", title: "3. Asesmen Akhir", text: "Kerjakan 10 soal dari level dasar hingga HOTS. Setelah tuntas, cetak laporan hasil belajarmu sebagai bukti." }
        ];

        function renderGuide() {
            document.getElementById('welcomeText').innerText = `Ahlan Wa Sahlan, ${state.student.name.split(' ')[0]}!`;
            const content = document.getElementById('guideContent');
            const data = guides[state.guideStep];
            
            content.innerHTML = `
                <div class="animate-fade-in w-full">
                    <i class="fas ${data.icon} text-6xl mb-6"></i>
                    <h3 class="text-xl font-bold text-slate-800 mb-2">${data.title}</h3>
                    <p class="text-slate-600 max-w-sm mx-auto">${data.text}</p>
                </div>
            `;

            const dots = document.getElementById('guideIndicators').children;
            for(let i=0; i<dots.length; i++) {
                dots[i].className = i === state.guideStep ? 'w-3 h-3 rounded-full bg-emerald-600 transition-colors' : 'w-3 h-3 rounded-full bg-slate-200 transition-colors';
            }

            document.getElementById('btnGuidePrev').className = state.guideStep === 0 ? 'text-slate-300 font-semibold px-4 py-2 cursor-not-allowed' : 'text-slate-500 hover:text-slate-700 font-semibold px-4 py-2 transition';
            const btnNext = document.getElementById('btnGuideNext');
            if (state.guideStep === guides.length - 1) {
                btnNext.innerText = "Masuk Menu Utama";
                btnNext.onclick = () => goTo('menuScreen');
            } else {
                btnNext.innerText = "Selanjutnya";
                btnNext.onclick = () => changeGuide(1);
            }
        }

        function changeGuide(dir) {
            if (dir === 1 && state.guideStep < guides.length - 1) state.guideStep++;
            else if (dir === -1 && state.guideStep > 0) state.guideStep--;
            renderGuide();
        }

        // --- MENU DASHBOARD LOGIC ---
        function updateDashboard() {
            document.getElementById('nameDisplay').innerText = state.student.name;
            document.getElementById('classDisplay').innerText = state.student.class;
            
            let initials = state.student.name.match(/\b\w/g) || [];
            initials = ((initials.shift() || '') + (initials.pop() || '')).toUpperCase();
            document.getElementById('initialsDisplay').innerText = initials || 'S';

            if (state.unlocked.bermain) {
                const cardBermain = document.getElementById('cardBermain');
                cardBermain.classList.remove('opacity-70');
                cardBermain.classList.replace('border-slate-300', 'border-amber-500');
                document.getElementById('lockBermain').classList.add('hide');
                const statusBermain = document.getElementById('statusBermainText');
                statusBermain.innerHTML = `<span>Status: Terbuka</span> <i class="fas fa-unlock text-amber-600"></i>`;
                statusBermain.classList.replace('text-slate-500', 'text-amber-600');
            }

            if (state.unlocked.berlatih) {
                const cardBerlatih = document.getElementById('cardBerlatih');
                cardBerlatih.classList.remove('opacity-70');
                cardBerlatih.classList.replace('border-slate-300', 'border-blue-500');
                document.getElementById('lockBerlatih').classList.add('hide');
                const statusBerlatih = document.getElementById('statusBerlatihText');
                statusBerlatih.innerHTML = `<span>Status: Terbuka</span> <i class="fas fa-unlock text-blue-600"></i>`;
                statusBerlatih.classList.replace('text-slate-500', 'text-blue-600');
            }

            let progressParts = state.belajarCompleted.length;
            if (state.unlocked.berlatih) progressParts += 1; 
            if (state.berlatih.score > 0) progressParts += 1; 
            
            const pct = Math.min(100, Math.round((progressParts / 8) * 100));
            document.getElementById('progressBar').style.width = `${pct}%`;
            document.getElementById('progressText').innerText = `${pct}%`;

            if (state.berlatih.score > 0) {
                document.getElementById('btnReportContainer').classList.remove('hide');
            }
        }

        function startSection(section) {
            if (section === 'bermain' && !state.unlocked.bermain) {
                showGlobalModal("Menu Terkunci", "Selesaikan seluruh materi di menu BELAJAR terlebih dahulu.", "lock");
                return;
            }
            if (section === 'berlatih' && !state.unlocked.berlatih) {
                showGlobalModal("Menu Terkunci", "Selesaikan tantangan di menu BERMAIN terlebih dahulu.", "lock");
                return;
            }
            goTo(`${section}Screen`);
            if (section === 'belajar') renderBelajar();
            if (section === 'bermain') renderBermain();
            if (section === 'berlatih') renderBerlatih();
        }

        function backToMenu() { goTo('menuScreen'); }

        // --- BELAJAR LOGIC ---
        function renderBelajar() {
            const data = belajarData[state.belajarSlide];
            const content = document.getElementById('belajarContent');
            document.getElementById('belajarProgressBar').style.width = `${((state.belajarSlide + 1) / belajarData.length) * 100}%`;
            const isCompleted = state.belajarCompleted.includes(state.belajarSlide);

            content.innerHTML = `
                <div class="animate-fade-in space-y-6 pb-20">
                    <h3 class="text-2xl font-bold text-emerald-800 border-b-2 border-emerald-100 pb-2">${data.title}</h3>
                    <div class="text-slate-700 leading-relaxed text-justify space-y-4">
                        <p class="font-medium bg-emerald-50 p-4 rounded-xl text-emerald-900 border-l-4 border-emerald-500">${data.concept}</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="bg-amber-50 p-4 rounded-xl border border-amber-200">
                                <h4 class="text-amber-800 font-bold mb-1 text-sm flex items-center gap-2"><i class="fas fa-map-marker-alt"></i> Konteks Pohuwato</h4>
                                <p class="text-sm text-slate-600">${data.local}</p>
                            </div>
                            <div class="bg-blue-50 p-4 rounded-xl border border-blue-200">
                                <h4 class="text-blue-800 font-bold mb-1 text-sm flex items-center gap-2"><i class="fas fa-heart"></i> Nilai KBC</h4>
                                <p class="text-sm text-slate-600">${data.kbc}</p>
                            </div>
                        </div>
                        <div class="bg-slate-50 p-5 rounded-xl border border-slate-200 mt-4 text-center">
                            <p class="font-arabic arabic-text text-2xl md:text-3xl text-slate-800 mb-3 leading-loose">${data.quran.text}</p>
                            <p class="text-xs font-bold text-emerald-600 mb-1">${data.quran.surah}</p>
                            <p class="text-sm text-slate-500 italic">"${data.quran.trans}"</p>
                        </div>
                    </div>
                    <div class="mt-8 pt-6 border-t-2 border-dashed border-slate-200">
                        <h4 class="font-bold text-slate-800 mb-4 flex items-center gap-2"><i class="fas fa-puzzle-piece text-amber-500"></i> Tantangan Pemahaman</h4>
                        <div id="interactiveContainer" class="${isCompleted ? 'pointer-events-none opacity-60' : ''}">
                            <p class="font-medium text-slate-700 mb-3">${data.interactive.q}</p>
                            <div class="grid grid-cols-1 gap-2">
                                ${data.interactive.opts.map((opt, idx) => `
                                    <button onclick="checkBelajarAns(${idx}, ${data.interactive.ans})" class="text-left px-4 py-3 rounded-xl border border-slate-200 hover:bg-emerald-50 hover:border-emerald-300 transition option-btn ${isCompleted && idx === data.interactive.ans ? 'bg-emerald-100 border-emerald-500 text-emerald-800' : 'bg-white'}">
                                        <span class="inline-block w-6 text-slate-400 font-bold">${String.fromCharCode(65+idx)}.</span> ${opt}
                                    </button>
                                `).join('')}
                            </div>
                        </div>
                        <div id="belajarFeedback" class="mt-4 font-bold text-sm hidden p-3 rounded-lg"></div>
                    </div>
                </div>
                <div class="absolute bottom-6 left-6 right-6 flex justify-between items-center bg-white pt-4">
                    <button onclick="changeBelajarSlide(-1)" class="text-slate-500 hover:text-emerald-600 font-bold px-4 py-2 transition ${state.belajarSlide === 0 ? 'invisible' : ''}"><i class="fas fa-chevron-left mr-2"></i> Sebelumnya</button>
                    <button id="btnNextBelajar" onclick="changeBelajarSlide(1)" class="bg-slate-300 text-slate-500 cursor-not-allowed font-bold py-2 px-6 rounded-xl transition ${isCompleted ? 'bg-emerald-600 hover:bg-emerald-700 text-white cursor-pointer shadow' : ''}">
                        ${state.belajarSlide === belajarData.length - 1 ? 'Selesai' : 'Lanjut <i class="fas fa-chevron-right ml-2"></i>'}
                    </button>
                </div>
            `;
        }

        function checkBelajarAns(selected, correct) {
            if (state.belajarCompleted.includes(state.belajarSlide)) return;
            const fb = document.getElementById('belajarFeedback');
            fb.classList.remove('hidden');

            if (selected === correct) {
                fb.className = "mt-4 font-bold text-sm bg-emerald-100 text-emerald-700 p-3 rounded-lg animate-fade-in";
                fb.innerHTML = `<i class="fas fa-check-circle mr-2"></i> ${belajarData[state.belajarSlide].interactive.feedback}`;
                
                state.belajarCompleted.push(state.belajarSlide);
                document.getElementById('btnNextBelajar').className = "bg-emerald-600 hover:bg-emerald-700 text-white cursor-pointer font-bold py-2 px-6 rounded-xl shadow transition";
                
                const btns = document.getElementById('interactiveContainer').querySelectorAll('button');
                btns.forEach((b, i) => {
                    b.disabled = true;
                    if(i === correct) b.className = "text-left px-4 py-3 rounded-xl border border-emerald-500 bg-emerald-50 text-emerald-800 transition option-btn font-semibold";
                    else b.classList.add('opacity-50');
                });

                if (state.belajarCompleted.length === belajarData.length) state.unlocked.bermain = true;
            } else {
                fb.className = "mt-4 font-bold text-sm bg-red-100 text-red-700 p-3 rounded-lg animate-fade-in";
                fb.innerHTML = `<i class="fas fa-times-circle mr-2"></i> Jawaban kurang tepat, coba lagi!`;
            }
        }

        function changeBelajarSlide(dir) {
            if (dir === 1) {
                if (!state.belajarCompleted.includes(state.belajarSlide)) {
                    showGlobalModal("Belum Selesai", "Silakan jawab tantangan terlebih dahulu.", "info");
                    return;
                }
                if (state.belajarSlide < belajarData.length - 1) {
                    state.belajarSlide++;
                    renderBelajar();
                } else {
                    showGlobalModal("Sesi Selesai", "Alhamdulillah, kamu telah menyelesaikan materi. Menu BERMAIN sekarang terbuka!", "success");
                    backToMenu();
                }
            } else if (dir === -1 && state.belajarSlide > 0) {
                state.belajarSlide--;
                renderBelajar();
            }
        }

        // --- BERMAIN LOGIC ---
        function renderBermain() {
            if (state.bermain.current >= bermainData.length) {
                finishBermain();
                return;
            }
            
            document.getElementById('bermainCurrentNum').innerText = state.bermain.current + 1;
            const data = bermainData[state.bermain.current];
            const content = document.getElementById('bermainContent');

            content.innerHTML = `
                <div class="animate-fade-in flex flex-col h-full">
                    <div class="bg-slate-50 p-5 rounded-2xl border border-slate-200 mb-6 max-h-48 overflow-y-auto custom-scrollbar shadow-inner">
                        <p class="text-sm text-slate-700 leading-relaxed text-justify indent-6">${data.stimulus}</p>
                    </div>
                    <h3 class="text-lg font-bold text-slate-800 mb-4">${data.q}</h3>
                    <div id="bermainOptsContainer" class="grid grid-cols-1 gap-3">
                        ${data.opts.map((opt, idx) => `
                            <button onclick="checkBermainAns(${idx}, ${data.ans})" class="text-left px-5 py-4 rounded-xl border-2 border-slate-100 hover:border-amber-300 hover:bg-amber-50 transition bg-white shadow-sm font-medium text-slate-700">
                                ${opt}
                            </button>
                        `).join('')}
                    </div>
                </div>
            `;
        }

        function checkBermainAns(selectedIdx, correctIdx) {
            const btns = document.getElementById('bermainOptsContainer').querySelectorAll('button');
            btns.forEach(b => b.disabled = true);
            const isCorrect = (selectedIdx === correctIdx);
            const data = bermainData[state.bermain.current];

            if (isCorrect) {
                state.bermain.score += 10;
                state.answers.benar++;
                btns[selectedIdx].className = "text-left px-5 py-4 rounded-xl border-2 border-emerald-500 bg-emerald-50 text-emerald-800 transition font-bold shadow-sm w-full relative";
                btns[selectedIdx].innerHTML += '<i class="fas fa-check-circle absolute right-4 top-1/2 transform -translate-y-1/2 text-emerald-500 text-xl"></i>';
            } else {
                state.answers.salah++;
                btns[selectedIdx].className = "text-left px-5 py-4 rounded-xl border-2 border-red-500 bg-red-50 text-red-800 transition font-bold shadow-sm w-full relative";
                btns[selectedIdx].innerHTML += '<i class="fas fa-times-circle absolute right-4 top-1/2 transform -translate-y-1/2 text-red-500 text-xl"></i>';
                btns[correctIdx].className = "text-left px-5 py-4 rounded-xl border-2 border-emerald-300 bg-emerald-50/50 text-emerald-700 transition font-medium shadow-sm w-full mt-2 opacity-80";
            }

            // Save details to send to GAS later
            state.answers.details.push(`[Bermain - ${state.bermain.current + 1}] Q: ${data.q} | Ans: ${data.opts[selectedIdx]} | Correct: ${isCorrect ? 'Ya' : 'Tidak'}`);

            setTimeout(() => {
                state.bermain.current++;
                renderBermain();
            }, 1500);
        }

        function finishBermain() {
            state.unlocked.berlatih = true;
            showGlobalModal("Bermain Selesai!", `Skor bermainmu: ${state.bermain.score}/100. Menu BERLATIH terbuka.`, "success");
            backToMenu();
        }

        // --- BERLATIH LOGIC ---
        function renderBerlatih() {
            if (state.berlatih.current >= berlatihData.length) {
                finishBerlatih();
                return;
            }
            
            const data = berlatihData[state.berlatih.current];
            document.getElementById('berlatihCurrentNum').innerText = state.berlatih.current + 1;
            
            const badge = document.getElementById('berlatihLevelBadge');
            badge.innerText = `Level ${data.level} ${data.level === 3 ? '(HOTS)' : ''}`;
            if(data.level === 1) badge.className = "text-xs font-bold text-white bg-emerald-500 px-2 py-1 rounded";
            if(data.level === 2) badge.className = "text-xs font-bold text-white bg-blue-500 px-2 py-1 rounded";
            if(data.level === 3) badge.className = "text-xs font-bold text-white bg-purple-500 px-2 py-1 rounded shadow-[0_0_10px_rgba(168,85,247,0.5)]";

            const content = document.getElementById('berlatihContent');
            content.innerHTML = `
                <div class="animate-fade-in flex flex-col h-full">
                    <div class="flex justify-between items-center mb-2">
                        <span class="text-xs font-bold text-slate-400">Bobot: ${data.points} Poin</span>
                    </div>
                    <div class="bg-blue-50/50 p-5 rounded-2xl border border-blue-100 mb-6 max-h-56 overflow-y-auto custom-scrollbar">
                        <p class="text-sm text-slate-700 leading-relaxed text-justify">${data.stimulus}</p>
                    </div>
                    <h3 class="text-lg font-bold text-slate-800 mb-4">${data.q}</h3>
                    <div class="grid grid-cols-1 gap-3" id="berlatihOptsContainer">
                        ${data.opts.map((opt, idx) => `
                            <button onclick="checkBerlatihAns(${idx}, ${data.ans}, ${data.points}, ${data.level})" class="text-left px-5 py-4 rounded-xl border border-slate-200 hover:border-blue-400 hover:bg-blue-50 transition bg-white font-medium text-slate-700 flex items-center gap-3">
                                <span class="w-8 h-8 rounded-full bg-slate-100 flex items-center justify-center font-bold text-slate-500 border border-slate-200">${String.fromCharCode(65+idx)}</span>
                                <span>${opt}</span>
                            </button>
                        `).join('')}
                    </div>
                </div>
            `;
        }

        function checkBerlatihAns(selectedIdx, correctIdx, points, level) {
            const btns = document.getElementById('berlatihOptsContainer').querySelectorAll('button');
            btns.forEach(b => b.disabled = true);
            const isCorrect = (selectedIdx === correctIdx);
            const data = berlatihData[state.berlatih.current];

            if (isCorrect) {
                state.berlatih.score += points;
                state.answers.benar++;
                if(level === 1) state.berlatih.breakdown.l1++;
                if(level === 2) state.berlatih.breakdown.l2++;
                if(level === 3) state.berlatih.breakdown.l3++;
                
                btns[selectedIdx].classList.replace('border-slate-200', 'border-emerald-500');
                btns[selectedIdx].classList.add('bg-emerald-50', 'text-emerald-800');
            } else {
                state.answers.salah++;
                btns[selectedIdx].classList.replace('border-slate-200', 'border-red-500');
                btns[selectedIdx].classList.add('bg-red-50', 'text-red-800');
            }

            // Save details to send to GAS later
            state.answers.details.push(`[Berlatih - ${state.berlatih.current + 1}] Q: ${data.q} | Ans: ${data.opts[selectedIdx]} | Correct: ${isCorrect ? 'Ya' : 'Tidak'}`);

            setTimeout(() => {
                state.berlatih.current++;
                renderBerlatih();
            }, 600);
        }

        function finishBerlatih() {
            if(!state.isSaved && GAS_URL !== "URL_GAS_ANDA_DISINI") {
                saveDataToGAS();
            } else {
                showGlobalModal("Asesmen Selesai", "Alhamdulillah, kamu telah menyelesaikan tes ini.", "success");
                backToMenu();
            }
        }

        // --- GOOGLE APPS SCRIPT INTEGRATION ---
        function saveDataToGAS() {
            showGlobalModal("Menyimpan Data", "Mohon tunggu, sedang mengirim hasil belajarmu ke server...", "loading", true);

            // Prepare all combined questions array for the "Data Soal" sheet
            let semuaSoal = [];
            bermainData.forEach((d, i) => {
                semuaSoal.push({
                    no: `Bermain-${i+1}`, tipe: 'Bermain', level: '-', pertanyaan: d.q, 
                    pilihan: d.opts.join(" | "), jawaban_benar: d.opts[d.ans]
                });
            });
            berlatihData.forEach((d, i) => {
                semuaSoal.push({
                    no: `Berlatih-${i+1}`, tipe: 'Berlatih', level: `Level ${d.level}`, pertanyaan: d.q, 
                    pilihan: d.opts.join(" | "), jawaban_benar: d.opts[d.ans]
                });
            });

            const payload = {
                nama: state.student.name,
                kelas: state.student.class,
                benar: state.answers.benar,
                salah: state.answers.salah,
                detail_jawaban: state.answers.details.join("\n"),
                data_soal: semuaSoal
            };

            fetch(GAS_URL, {
                method: 'POST',
                headers: { 'Content-Type': 'text/plain;charset=utf-8' },
                body: JSON.stringify(payload)
            })
            .then(response => response.json())
            .then(result => {
                state.isSaved = true;
                showGlobalModal("Berhasil!", "Data telah tersimpan di server. Silakan lihat laporan PDF.", "success", false);
                backToMenu();
            })
            .catch(error => {
                console.error('Error saving data:', error);
                showGlobalModal("Perhatian", "Data gagal dikirim, tapi kamu tetap bisa melihat laporan PDF-nya secara lokal.", "error", false);
                backToMenu();
            });
        }

        // --- REPORT LOGIC ---
        function generateReport() {
            goTo('reportScreen');
            document.getElementById('repName').innerText = state.student.name;
            document.getElementById('repClass').innerText = state.student.class;
            
            const dateStr = new Date().toLocaleDateString('id-ID', { year: 'numeric', month: 'long', day: 'numeric' });
            document.getElementById('repDate').innerText = dateStr;
            document.getElementById('repDateSign').innerText = dateStr;

            document.getElementById('repBermainScore').innerText = state.bermain.score;
            document.getElementById('repBerlatihScore').innerText = state.berlatih.score;

            let predikat = "";
            if(state.berlatih.score >= 85) predikat = "SANGAT BAIK (A)";
            else if(state.berlatih.score >= 70) predikat = "BAIK (B)";
            else if(state.berlatih.score >= 50) predikat = "CUKUP (C)";
            else predikat = "PERLU BIMBINGAN (D)";
            document.getElementById('repPredikat').innerText = `Predikat: ${predikat}`;

            document.getElementById('repL1').innerText = `${state.berlatih.breakdown.l1}/3`;
            document.getElementById('repL2').innerText = `${state.berlatih.breakdown.l2}/4`;
            document.getElementById('repL3').innerText = `${state.berlatih.breakdown.l3}/3`;
        }

        function downloadPDF() {
            const element = document.getElementById('printableReport');
            const opt = {
                margin: 10,
                filename: `Laporan_Maulid_${state.student.name.replace(/\s+/g, '_')}.pdf`,
                image: { type: 'jpeg', quality: 0.98 },
                html2canvas: { scale: 2, useCORS: true },
                jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' }
            };

            const btn = event.currentTarget;
            const originalText = btn.innerHTML;
            btn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Memproses...';
            btn.disabled = true;

            html2pdf().set(opt).from(element).save().then(() => {
                btn.innerHTML = originalText;
                btn.disabled = false;
            });
        }

        window.onload = initApp;
    </script>
</body>
</html>
