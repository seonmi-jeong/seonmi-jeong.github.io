<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nestory ARTISM | Premium Vocal Entertainment Academy</title>
    
    <!-- Google Fonts: Poppins (English/Headings), Noto Sans KR (Korean Body) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;700;900&family=Poppins:wght@400;600;700;800;900&display=swap" rel="stylesheet">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        nest: {
                            blue: '#2563EB',     /* Vibrant Blue for energetic pop feel */
                            lightblue: '#DBEAFE',
                            black: '#111827',
                            gray: '#F3F4F6',
                            white: '#FFFFFF',
                            orange: '#FF5A1F'    /* Accent for bouncy feel */
                        }
                    },
                    fontFamily: {
                        sans: ['"Noto Sans KR"', 'sans-serif'],
                        display: ['"Poppins"', 'sans-serif'],
                    },
                    boxShadow: {
                        'bouncy': '0 10px 25px -5px rgba(37, 99, 235, 0.3)',
                        'card': '0 4px 20px -2px rgba(0, 0, 0, 0.05)',
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #FAFAFA;
            color: #111827;
            -webkit-font-smoothing: antialiased;
        }
        
        /* Hide Scrollbar but keep functionality */
        .hide-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .hide-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }

        /* Bright Magazine Dropcap */
        .magazine-dropcap:first-letter {
            float: left;
            font-size: 4rem;
            line-height: 3.5rem;
            padding-right: 0.5rem;
            color: #2563EB;
            font-family: 'Poppins', sans-serif;
            font-weight: 800;
        }

        /* Hover animations for cards */
        .hover-bounce {
            transition: transform 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275), box-shadow 0.3s ease;
        }
        .hover-bounce:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        
        /* Fade in animation for page transitions */
        .fade-in {
            animation: fadeIn 0.4s ease-in-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Form submission loading spinner */
        .loader {
            border: 2px solid #f3f3f3;
            border-top: 2px solid #ffffff;
            border-radius: 50%;
            width: 16px;
            height: 16px;
            animation: spin 1s linear infinite;
            display: inline-block;
            vertical-align: middle;
            margin-right: 8px;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="font-sans selection:bg-nest-blue selection:text-white">

    <!-- Header / Navigation (Bright & Sticky) -->
    <header id="navbar" class="fixed w-full top-0 z-50 transition-all duration-300 py-4 px-6 md:px-10 flex justify-between items-center bg-white/90 backdrop-blur-md border-b border-gray-100 shadow-sm">
        <a onclick="changePage('home')" class="text-3xl font-display font-black tracking-tighter text-nest-black hover:text-nest-blue transition-colors cursor-pointer">
            NESTORY
        </a>
        
        <!-- Desktop Nav with Dropdowns -->
        <nav class="hidden md:flex space-x-8 text-sm font-display font-semibold tracking-wide text-gray-600">
            
            <!-- ABOUT Dropdown -->
            <div class="relative group py-2">
                <a onclick="changePage('about')" class="hover:text-nest-blue transition-colors flex items-center cursor-pointer">
                    ABOUT
                </a>
                <div class="absolute top-full left-0 mt-2 w-48 bg-white border border-gray-100 rounded-xl shadow-card opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-300 transform translate-y-2 group-hover:translate-y-0 overflow-hidden">
                    <a onclick="changePage('about')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors border-b border-gray-50 cursor-pointer">Philosophy (교육 철학)</a>
                    <a onclick="changePage('about', 'studio')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors cursor-pointer">Studio (시설 안내)</a>
                </div>
            </div>

            <!-- FILM Dropdown -->
            <div class="relative group py-2">
                <a onclick="changePage('home')" class="hover:text-nest-blue transition-colors flex items-center cursor-pointer">
                    FILM
                </a>
                <div class="absolute top-full left-0 mt-2 w-48 bg-white border border-gray-100 rounded-xl shadow-card opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-300 transform translate-y-2 group-hover:translate-y-0 overflow-hidden">
                    <a onclick="changePage('home')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors border-b border-gray-50 cursor-pointer">Brand Film</a>
                </div>
            </div>

            <!-- FACULTY Dropdown -->
            <div class="relative group py-2">
                <a onclick="changePage('faculty')" class="hover:text-nest-blue transition-colors flex items-center cursor-pointer">
                    FACULTY
                </a>
                <div class="absolute top-full left-0 mt-2 w-48 bg-white border border-gray-100 rounded-xl shadow-card opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-300 transform translate-y-2 group-hover:translate-y-0 overflow-hidden">
                    <a onclick="changePage('faculty')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors border-b border-gray-50 cursor-pointer">Instructors (강사진)</a>
                    <a onclick="changePage('faculty')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors cursor-pointer">Column (보컬 칼럼)</a>
                </div>
            </div>

            <!-- ARCHIVE Dropdown -->
            <div class="relative group py-2">
                <a onclick="changePage('archive')" class="hover:text-nest-blue transition-colors flex items-center cursor-pointer">
                    ARCHIVE
                </a>
                <div class="absolute top-full left-0 mt-2 w-48 bg-white border border-gray-100 rounded-xl shadow-card opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-300 transform translate-y-2 group-hover:translate-y-0 overflow-hidden">
                    <a onclick="changePage('archive')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors border-b border-gray-50 cursor-pointer">Elite (입시)</a>
                    <a onclick="changePage('archive')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors border-b border-gray-50 cursor-pointer">Pro (오디션)</a>
                    <a onclick="changePage('archive')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors cursor-pointer">Before & After</a>
                </div>
            </div>

            <!-- PROGRAM Dropdown -->
            <div class="relative group py-2">
                <a onclick="changePage('program')" class="hover:text-nest-blue transition-colors flex items-center cursor-pointer">
                    PROGRAM
                </a>
                <div class="absolute top-full right-0 mt-2 w-56 bg-white border border-gray-100 rounded-xl shadow-card opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-300 transform translate-y-2 group-hover:translate-y-0 overflow-hidden">
                    <a onclick="changePage('program')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors border-b border-gray-50 cursor-pointer">Elite Artist (국내/해외입시)</a>
                    <a onclick="changePage('program')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors border-b border-gray-50 cursor-pointer">Professional (오디션)</a>
                    <a onclick="changePage('program')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors border-b border-gray-50 cursor-pointer">Hobby / Life (취미)</a>
                    <a onclick="changePage('program')" class="block px-5 py-3 text-gray-700 hover:bg-nest-lightblue hover:text-nest-blue transition-colors cursor-pointer">Vocal Therapy (교정)</a>
                </div>
            </div>
        </nav>

        <a onclick="document.getElementById('contact').scrollIntoView({behavior: 'smooth'})" class="hidden md:inline-block bg-nest-blue text-white px-6 py-2.5 rounded-full text-sm font-display font-bold hover:bg-nest-orange hover:shadow-bouncy transition-all cursor-pointer">
            상담신청
        </a>

        <!-- Mobile Menu Button -->
        <button class="md:hidden text-nest-black focus:outline-none">
            <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
        </button>
    </header>

    <!-- MAIN CONTENT AREA (Page views will be swapped here) -->
    <main id="main-content" class="min-h-screen">
        
        <!-- PAGE 1: HOME -->
        <div id="page-home" class="page-view block fade-in">
            <section id="home" class="relative h-screen w-full flex items-center justify-center overflow-hidden">
                <!-- Background Video -->
                <video autoplay loop muted playsinline class="absolute z-0 w-auto min-w-full min-h-full max-w-none object-cover opacity-90">
                    <source src="https://assets.mixkit.co/videos/preview/mixkit-singer-recording-a-song-in-a-studio-4114-large.mp4" type="video/mp4">
                </video>
                
                <!-- Bright Overlay -->
                <div class="absolute inset-0 bg-gradient-to-b from-white/40 via-transparent to-gray-50/90 z-10"></div>
                
                <div class="relative z-20 text-center px-4 flex flex-col items-center mt-16 w-full max-w-5xl">
                    <div class="inline-block bg-nest-blue text-white font-bold px-5 py-2 rounded-full text-xs md:text-sm mb-6 tracking-widest uppercase shadow-lg shadow-blue-500/30 border border-blue-400">
                        Premium Vocal Academy
                    </div>
                    
                    <h1 class="text-5xl md:text-7xl lg:text-8xl font-display font-black tracking-tight text-nest-black leading-tight mb-6 drop-shadow-md">
                        Sing Your <span class="text-transparent bg-clip-text bg-gradient-to-r from-nest-blue to-nest-orange">Story.</span>
                    </h1>
                    
                    <p class="text-gray-800 font-bold max-w-2xl mx-auto text-base md:text-lg bg-white/60 backdrop-blur-md px-8 py-4 rounded-2xl shadow-sm border border-white/50 leading-relaxed">
                        단순한 보컬 트레이닝을 넘어 아티스트의 고유한 서사를 발굴합니다.<br>
                        당신의 목소리가 세상에 울려 퍼지는 곳, 네스토리.
                    </p>
                    
                    <a onclick="document.getElementById('home-programs').scrollIntoView({behavior: 'smooth'})" class="animate-bounce mt-12 bg-white/90 p-4 rounded-full shadow-lg text-nest-blue hover:bg-nest-blue hover:text-white hover:scale-110 transition-all duration-300 cursor-pointer">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path></svg>
                    </a>
                </div>
            </section>

            <!-- Quick Program Links (SM Universe Style Visual Navigation) -->
            <section id="home-programs" class="bg-white py-24 px-6 md:px-10">
                <div class="max-w-7xl mx-auto">
                    <div class="text-center mb-16">
                        <h3 class="font-display font-bold text-nest-blue text-lg tracking-widest uppercase mb-2">Explore</h3>
                        <h2 class="text-4xl md:text-5xl font-display font-black text-nest-black uppercase">Programs</h2>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                        <!-- Elite Artist Card -->
                        <div onclick="changePage('program', 'prog-elite')" class="relative h-80 rounded-3xl overflow-hidden cursor-pointer group shadow-card">
                            <img src="https://images.unsplash.com/photo-1514525253161-7a46d19cd819?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" alt="Elite Artist">
                            <div class="absolute inset-0 bg-gradient-to-t from-nest-black/80 via-nest-black/20 to-transparent"></div>
                            <div class="absolute bottom-0 left-0 p-8 w-full transform group-hover:-translate-y-2 transition-transform duration-300">
                                <span class="text-nest-blue text-xs font-bold uppercase tracking-widest mb-2 block bg-white/90 w-max px-3 py-1 rounded-full shadow-sm">예고·예대 입시</span>
                                <h4 class="text-white text-2xl font-display font-bold">Elite Artist</h4>
                            </div>
                        </div>
                        
                        <!-- Professional Card (BEST) -->
                        <div onclick="changePage('program', 'prog-pro')" class="relative h-80 rounded-3xl overflow-hidden cursor-pointer group shadow-card border-4 border-nest-orange">
                            <div class="absolute top-0 right-0 bg-nest-orange text-white text-xs font-bold px-4 py-2 rounded-bl-2xl z-20 shadow-md">BEST</div>
                            <img src="https://images.unsplash.com/photo-1520615967046-2415175bf744?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" alt="Professional">
                            <div class="absolute inset-0 bg-gradient-to-t from-nest-black/80 via-nest-black/20 to-transparent z-10"></div>
                            <div class="absolute bottom-0 left-0 p-8 w-full z-20 transform group-hover:-translate-y-2 transition-transform duration-300">
                                <span class="text-nest-orange text-xs font-bold uppercase tracking-widest mb-2 block bg-white/90 w-max px-3 py-1 rounded-full shadow-sm">오디션·가수</span>
                                <h4 class="text-white text-2xl font-display font-bold">Professional</h4>
                            </div>
                        </div>
                        
                        <!-- Hobby / Life Card -->
                        <div onclick="changePage('program', 'prog-hobby')" class="relative h-80 rounded-3xl overflow-hidden cursor-pointer group shadow-card">
                            <img src="https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" alt="Hobby / Life">
                            <div class="absolute inset-0 bg-gradient-to-t from-nest-black/80 via-nest-black/20 to-transparent"></div>
                            <div class="absolute bottom-0 left-0 p-8 w-full transform group-hover:-translate-y-2 transition-transform duration-300">
                                <span class="text-green-600 text-xs font-bold uppercase tracking-widest mb-2 block bg-white/90 w-max px-3 py-1 rounded-full shadow-sm">성인 취미</span>
                                <h4 class="text-white text-2xl font-display font-bold">Hobby / Life</h4>
                            </div>
                        </div>
                        
                        <!-- Vocal Therapy Card -->
                        <div onclick="changePage('program', 'prog-therapy')" class="relative h-80 rounded-3xl overflow-hidden cursor-pointer group shadow-card">
                            <img src="https://images.unsplash.com/photo-1598653222000-6b7b7a552625?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" alt="Vocal Therapy">
                            <div class="absolute inset-0 bg-gradient-to-t from-nest-black/80 via-nest-black/20 to-transparent"></div>
                            <div class="absolute bottom-0 left-0 p-8 w-full transform group-hover:-translate-y-2 transition-transform duration-300">
                                <span class="text-purple-600 text-xs font-bold uppercase tracking-widest mb-2 block bg-white/90 w-max px-3 py-1 rounded-full shadow-sm">발성 교정</span>
                                <h4 class="text-white text-2xl font-display font-bold">Vocal Therapy</h4>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </div>

        <!-- PAGE 2: ABOUT & STUDIO -->
        <div id="page-about" class="page-view hidden pt-24 fade-in">
            <!-- ABOUT (Brand Story) -->
            <section id="about" class="bg-white py-16 px-6 md:px-10">
                <div class="max-w-6xl mx-auto flex flex-col md:flex-row items-center gap-16">
                    <div class="w-full md:w-1/2 relative">
                        <div class="absolute -top-4 -left-4 w-24 h-24 bg-nest-blue rounded-full opacity-20"></div>
                        <div class="absolute -bottom-4 -right-4 w-32 h-32 bg-nest-orange rounded-full opacity-20"></div>
                        <img src="https://images.unsplash.com/photo-1598488035139-bdbb2231ce04?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Nestory Studio Vibe" class="w-full h-auto object-cover rounded-3xl relative z-10 shadow-card">
                    </div>
                    <div class="w-full md:w-1/2">
                        <h3 class="font-display font-bold text-nest-blue text-lg tracking-widest uppercase mb-4">Philosophy</h3>
                        <h2 class="text-4xl md:text-5xl font-display font-black mb-8 leading-tight text-nest-black">
                            Beyond Education,<br>
                            Into <span class="text-nest-orange">Artistry.</span>
                        </h2>
                        <div class="h-1 w-16 bg-nest-blue mb-8 rounded-full"></div>
                        <p class="text-gray-600 font-medium leading-relaxed text-lg">
                            네스토리(Nestory)는 단순한 입시, 취미 학원이 아닙니다.<br>
                            안락한 둥지(Nest) 안에서 각자의 이야기(Story)를 완성해 나가는 
                            <strong class="text-nest-black font-bold">프리미엄 엔터테인먼트 아카데미</strong>입니다.
                            현업 최고 전문가들의 디렉팅을 통해, 
                            원석을 찾아내어 빛나는 아티스트로 세공합니다.
                            우리는 결과로 말합니다.
                        </p>
                    </div>
                </div>
            </section>

            <!-- STUDIO (Facilities) -->
            <section id="studio" class="py-24 px-6 md:px-0 bg-white border-t border-gray-50">
                <div class="max-w-7xl mx-auto md:px-10 mb-12 text-center md:text-left flex flex-col md:flex-row justify-between items-end">
                    <div>
                        <h3 class="font-display font-bold text-nest-blue text-lg tracking-widest uppercase mb-2">The Space</h3>
                        <h2 class="text-4xl md:text-5xl font-display font-black text-nest-black uppercase">Studio</h2>
                    </div>
                    <p class="text-gray-600 font-medium max-w-xl text-base mt-4 md:mt-0 text-left">
                        오직 아티스트의 집중에 최적화된 하이엔드 공간입니다. 철저한 방음 설계와 최첨단 프로용 장비가 당신을 기다립니다.
                    </p>
                </div>

                <!-- Horizontal Scrolling Photos -->
                <div class="flex flex-col md:flex-row gap-6 overflow-x-auto hide-scrollbar md:px-10 pb-10">
                    <div class="min-w-[80vw] md:min-w-[500px] h-[350px] relative rounded-3xl overflow-hidden shadow-card group">
                        <img src="https://images.unsplash.com/photo-1598488035139-bdbb2231ce04?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80" alt="Main Recording Room" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                        <div class="absolute bottom-0 left-0 w-full p-6 bg-gradient-to-t from-black/70 to-transparent">
                            <div class="text-white text-xl font-bold uppercase tracking-wide">Main Recording Room</div>
                        </div>
                    </div>
                    <div class="min-w-[80vw] md:min-w-[400px] h-[350px] relative rounded-3xl overflow-hidden shadow-card group">
                        <img src="https://images.unsplash.com/photo-1559523161-0fc0d8b38a7a?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Private Practice Room" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                        <div class="absolute bottom-0 left-0 w-full p-6 bg-gradient-to-t from-black/70 to-transparent">
                            <div class="text-white text-xl font-bold uppercase tracking-wide">Private Rooms</div>
                        </div>
                    </div>
                    <div class="min-w-[80vw] md:min-w-[400px] h-[350px] relative rounded-3xl overflow-hidden shadow-card group">
                        <img src="https://images.unsplash.com/photo-1620959043743-988970e3ed6c?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Lounge Area" class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                        <div class="absolute bottom-0 left-0 w-full p-6 bg-gradient-to-t from-black/70 to-transparent">
                            <div class="text-white text-xl font-bold uppercase tracking-wide">Artist Lounge</div>
                        </div>
                    </div>
                </div>
            </section>
        </div>

        <!-- PAGE 3: FACULTY -->
        <div id="page-faculty" class="page-view hidden pt-24 fade-in">
            <section id="faculty" class="bg-nest-gray py-16 px-6 md:px-10 min-h-screen">
                <div class="max-w-7xl mx-auto">
                    <div class="flex flex-col md:flex-row justify-between items-end mb-16 gap-6">
                        <div>
                            <h3 class="font-display font-bold text-nest-orange text-lg tracking-widest uppercase mb-2">The Masters</h3>
                            <h2 class="text-4xl md:text-5xl font-display font-black text-nest-black uppercase">Faculty <br>& Column</h2>
                        </div>
                        <div class="text-right">
                            <p class="text-gray-500 font-medium mb-4">현업 최고 수준의 강사진 라인업</p>
                            <a href="https://blog.naver.com" target="_blank" class="inline-flex items-center space-x-2 text-sm font-bold text-white bg-[#03C75A] px-5 py-2.5 rounded-full hover:bg-green-600 transition-colors cursor-pointer">
                                <span>네이버 블로그에서 전체 칼럼 보기</span>
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"></path></svg>
                            </a>
                        </div>
                    </div>

                    <!-- Chief Director Layout Item -->
                    <div class="bg-white rounded-3xl p-8 md:p-12 shadow-card mb-16 flex flex-col md:flex-row gap-12 items-center relative overflow-hidden group">
                        <div class="absolute top-0 right-0 w-32 h-32 bg-nest-blue rounded-bl-full opacity-5 pointer-events-none"></div>
                        <div class="md:w-5/12 relative">
                            <img src="https://images.unsplash.com/photo-1516280440502-85078d05dd42?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Chief Director" class="w-full h-[500px] object-cover rounded-2xl shadow-lg grayscale group-hover:grayscale-0 transition duration-500">
                            <div class="absolute -top-4 -left-4 bg-nest-blue text-white text-sm font-bold px-5 py-2 rounded-lg shadow-md uppercase tracking-wider">Chief Director / 대표원장</div>
                        </div>
                        <div class="md:w-7/12">
                            <h4 class="text-3xl md:text-4xl font-display font-bold mb-6 text-nest-black leading-snug">"기술을 넘어, 당신 안에 숨겨진 진짜 서사를 끄집어내는 작업."</h4>
                            <p class="text-nest-orange font-bold text-xl mb-6">Director. J</p>
                            <div class="text-gray-600 font-medium leading-relaxed space-y-6">
                                <p class="magazine-dropcap">
                                    발성은 건물을 짓는 기초 공사와 같습니다. 네스토리의 교육 철학은 본연의 악기인 '성대'의 근본적인 메커니즘을 이해하고, 가장 건강하고 단단한 소리의 기반을 마련하는 것에서 출발합니다.
                                </p>
                                <p>
                                    학생 한 명 한 명을 하나의 독립된 아티스트로 대우합니다. 획일화된 발성법을 주입하는 것이 아닌, 각자가 가진 고유의 톤과 감성을 분석하여 그들만의 '무기'를 만들어냅니다. 오디션 합격이나 대학 입시는 이 과정에서 자연스럽게 따라오는 결과물일 뿐입니다.
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Additional Instructors Grid -->
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                        <!-- Instructor 1 -->
                        <div class="bg-white rounded-3xl overflow-hidden shadow-card group flex flex-col">
                            <div class="relative h-72">
                                <img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Vocal Trainer A" class="w-full h-full object-cover grayscale group-hover:scale-105 group-hover:grayscale-0 transition duration-500">
                                <div class="absolute top-4 left-4 bg-nest-orange text-white text-xs font-bold px-3 py-1.5 rounded-lg shadow-md z-10 uppercase tracking-widest">Vocal Trainer / 강사</div>
                            </div>
                            <div class="p-8 flex-grow">
                                <h5 class="text-2xl font-display font-bold mb-1 text-nest-black">Trainer. A</h5>
                                <p class="text-sm text-nest-blue font-bold mb-4">K-Pop / 오디션 전문</p>
                                <p class="text-gray-600 font-medium leading-relaxed">
                                    트렌디한 보컬 스타일링과 실전 위주의 디렉팅. 수많은 연습생을 배출한 노하우를 바탕으로 기획사가 원하는 확실한 톤 메이킹을 돕고, 무대 위에서의 장점을 극대화합니다.
                                </p>
                            </div>
                        </div>

                        <!-- Instructor 2 -->
                        <div class="bg-white rounded-3xl overflow-hidden shadow-card group flex flex-col">
                            <div class="relative h-72">
                                <img src="https://images.unsplash.com/photo-1568602471122-7832951cc4c5?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Vocal Trainer B" class="w-full h-full object-cover grayscale group-hover:scale-105 group-hover:grayscale-0 transition duration-500">
                                <div class="absolute top-4 left-4 bg-nest-orange text-white text-xs font-bold px-3 py-1.5 rounded-lg shadow-md z-10 uppercase tracking-widest">Vocal Trainer / 강사</div>
                            </div>
                            <div class="p-8 flex-grow">
                                <h5 class="text-2xl font-display font-bold mb-1 text-nest-black">Trainer. B</h5>
                                <p class="text-sm text-nest-blue font-bold mb-4">입시 / 기초 발성 전문</p>
                                <p class="text-gray-600 font-medium leading-relaxed">
                                    탄탄한 기초 발성과 호흡 메커니즘을 잡아줍니다. 예고 및 실용음악과 입시생들의 든든한 멘토로서 체계적인 분석과 전략을 통해 완벽한 실기 무대를 준비할 수 있도록 이끕니다.
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Special Guest Directors Section -->
                    <div class="mt-24 bg-white p-8 md:p-12 rounded-3xl shadow-card border border-gray-100">
                        <div class="text-center mb-10">
                            <h3 class="font-display font-bold text-nest-orange text-sm tracking-widest uppercase mb-2">Special Class</h3>
                            <h4 class="text-3xl font-display font-black text-nest-black uppercase">Guest Directors</h4>
                            <p class="text-gray-500 mt-3 font-medium">네스토리 수강생만을 위한 현업 최고의 전문가 특강 라인업</p>
                        </div>
                        
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                            <!-- Guest 1 -->
                            <div class="flex items-center gap-5 p-4 rounded-2xl hover:bg-gray-50 transition-colors border border-transparent hover:border-gray-100 group">
                                <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=80" alt="Guest Director" class="w-20 h-20 rounded-full object-cover grayscale group-hover:grayscale-0 transition duration-300 shadow-sm">
                                <div>
                                    <p class="text-xs text-nest-blue font-bold uppercase tracking-wider mb-1">現 대형 기획사 보컬 트레이너</p>
                                    <h5 class="text-xl font-display font-bold text-nest-black">Director. X</h5>
                                </div>
                            </div>
                            
                            <!-- Guest 2 -->
                            <div class="flex items-center gap-5 p-4 rounded-2xl hover:bg-gray-50 transition-colors border border-transparent hover:border-gray-100 group">
                                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=80" alt="Guest Director" class="w-20 h-20 rounded-full object-cover grayscale group-hover:grayscale-0 transition duration-300 shadow-sm">
                                <div>
                                    <p class="text-xs text-nest-orange font-bold uppercase tracking-wider mb-1">스타 프로듀서 / 작곡가</p>
                                    <h5 class="text-xl font-display font-bold text-nest-black">Producer. Y</h5>
                                </div>
                            </div>

                            <!-- Guest 3 -->
                            <div class="flex items-center gap-5 p-4 rounded-2xl hover:bg-gray-50 transition-colors border border-transparent hover:border-gray-100 group">
                                <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=200&q=80" alt="Guest Director" class="w-20 h-20 rounded-full object-cover grayscale group-hover:grayscale-0 transition duration-300 shadow-sm">
                                <div>
                                    <p class="text-xs text-green-600 font-bold uppercase tracking-wider mb-1">유명 레이블 A&R</p>
                                    <h5 class="text-xl font-display font-bold text-nest-black">Director. Z</h5>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </section>
        </div>

        <!-- PAGE 4: ARCHIVE -->
        <div id="page-archive" class="page-view hidden pt-24 fade-in">
            <section id="archive" class="bg-white py-16 px-6 md:px-10 min-h-screen">
                <div class="max-w-7xl mx-auto">
                    <div class="text-center mb-16">
                        <h3 class="font-display font-bold text-nest-blue text-lg tracking-widest uppercase mb-2">Artworks</h3>
                        <h2 class="text-4xl md:text-5xl font-display font-black text-nest-black uppercase mb-8">Video Archive</h2>
                        
                        <!-- Filter Buttons -->
                        <div class="flex flex-wrap justify-center gap-3 text-sm font-bold tracking-wide">
                            <button class="px-6 py-2.5 rounded-full bg-nest-black text-white shadow-md">ALL</button>
                            <button class="px-6 py-2.5 rounded-full bg-gray-100 text-gray-600 hover:bg-gray-200 transition">ELITE (입시)</button>
                            <button class="px-6 py-2.5 rounded-full bg-gray-100 text-gray-600 hover:bg-gray-200 transition">PRO (오디션)</button>
                            <button class="px-6 py-2.5 rounded-full bg-gray-100 text-gray-600 hover:bg-gray-200 transition">BEFORE & AFTER</button>
                        </div>
                    </div>

                    <!-- Video Grid -->
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                        <div class="bg-white rounded-2xl overflow-hidden shadow-card border border-gray-100">
                            <div class="aspect-video w-full bg-gray-200">
                                <iframe class="w-full h-full" src="https://www.youtube.com/embed/LXb3EKWsInQ?si=yvG1n-7jR0vK2GgZ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
                            </div>
                            <div class="p-6">
                                <span class="inline-block bg-blue-100 text-nest-blue text-xs font-bold px-2 py-1 rounded mb-3">PRO AUDITION</span>
                                <h4 class="text-lg font-bold text-nest-black">Vocal Cover - 최신 가요 트렌드 분석</h4>
                            </div>
                        </div>

                        <div class="bg-white rounded-2xl overflow-hidden shadow-card border border-gray-100">
                            <div class="aspect-video w-full bg-gray-200">
                                <iframe class="w-full h-full" src="https://www.youtube.com/embed/9bZkp7q19f0?si=O64k_X3gV2o54-jR" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
                            </div>
                            <div class="p-6">
                                <span class="inline-block bg-orange-100 text-nest-orange text-xs font-bold px-2 py-1 rounded mb-3">ELITE (입시)</span>
                                <h4 class="text-lg font-bold text-nest-black">24학년도 실용음악과 최종 합격작</h4>
                            </div>
                        </div>

                        <div class="bg-white rounded-2xl overflow-hidden shadow-card border border-gray-100">
                            <div class="aspect-video w-full bg-gray-200">
                                <video controls class="w-full h-full object-cover">
                                    <source src="https://assets.mixkit.co/videos/preview/mixkit-girl-singing-in-a-recording-studio-4113-large.mp4" type="video/mp4">
                                </video>
                            </div>
                            <div class="p-6">
                                <span class="inline-block bg-green-100 text-green-700 text-xs font-bold px-2 py-1 rounded mb-3">BEFORE & AFTER</span>
                                <h4 class="text-lg font-bold text-nest-black">보컬 교정 3개월의 완벽한 변화</h4>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </div>

        <!-- PAGE 5: PROGRAM -->
        <div id="page-program" class="page-view hidden pt-24 fade-in">
            <section id="program" class="bg-nest-blue py-16 px-6 md:px-10 min-h-screen">
                <div class="max-w-7xl mx-auto">
                    <h3 class="font-display font-bold text-blue-200 text-lg tracking-widest uppercase mb-2 text-center">Curriculum</h3>
                    <h2 class="text-4xl md:text-5xl font-display font-black text-white uppercase mb-16 text-center">Programs</h2>

                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                        <div id="prog-elite" class="bg-white p-8 rounded-3xl hover-bounce relative overflow-hidden group scroll-mt-32">
                            <div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                                <svg class="w-6 h-6 text-nest-blue" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l9-5-9-5-9 5 9 5z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z"></path></svg>
                            </div>
                            <h4 class="text-2xl font-display font-bold text-nest-black mb-1">Elite Artist</h4>
                            <p class="text-sm text-nest-blue font-bold mb-6">예고·예대 입시반</p>
                            <ul class="text-gray-600 text-sm font-medium space-y-3">
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 전략적 입시 곡 선정</li>
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 대학별 실기 트렌드 분석</li>
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 정기 모의 실기 평가</li>
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 시창/청음/화성학 연계</li>
                            </ul>
                        </div>

                        <div id="prog-pro" class="bg-white p-8 rounded-3xl hover-bounce relative overflow-hidden border-4 border-nest-orange scroll-mt-32">
                            <div class="absolute top-0 right-0 bg-nest-orange text-white text-xs font-bold px-3 py-1 rounded-bl-xl">BEST</div>
                            <div class="w-12 h-12 bg-orange-100 rounded-full flex items-center justify-center mb-6">
                                <svg class="w-6 h-6 text-nest-orange" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z"></path></svg>
                            </div>
                            <h4 class="text-2xl font-display font-bold text-nest-black mb-1">Professional</h4>
                            <p class="text-sm text-nest-orange font-bold mb-6">오디션·가수 지망생</p>
                            <ul class="text-gray-600 text-sm font-medium space-y-3">
                                <li class="flex items-start"><span class="text-nest-blue mr-2 font-bold">✓</span> 기획사 오디션 집중 대비</li>
                                <li class="flex items-start"><span class="text-nest-blue mr-2 font-bold">✓</span> 프로 레코딩 실습 및 디렉팅</li>
                                <li class="flex items-start"><span class="text-nest-blue mr-2 font-bold">✓</span> 영상 포트폴리오 제작</li>
                                <li class="flex items-start"><span class="text-nest-blue mr-2 font-bold">✓</span> 카메라 테스트 및 애티튜드</li>
                            </ul>
                        </div>

                        <div id="prog-hobby" class="bg-white p-8 rounded-3xl hover-bounce relative overflow-hidden group scroll-mt-32">
                            <div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                                <svg class="w-6 h-6 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                            </div>
                            <h4 class="text-2xl font-display font-bold text-nest-black mb-1">Hobby / Life</h4>
                            <p class="text-sm text-green-600 font-bold mb-6">성인 취미·자기계발</p>
                            <ul class="text-gray-600 text-sm font-medium space-y-3">
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 1:1 맞춤형 레퍼토리 레슨</li>
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 음치/박치 집중 클리닉</li>
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 고음 개발 및 발성 교정</li>
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 정기 레코딩 체험</li>
                            </ul>
                        </div>

                        <div id="prog-therapy" class="bg-white p-8 rounded-3xl hover-bounce relative overflow-hidden group scroll-mt-32">
                            <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                                <svg class="w-6 h-6 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"></path></svg>
                            </div>
                            <h4 class="text-2xl font-display font-bold text-nest-black mb-1">Vocal Therapy</h4>
                            <p class="text-sm text-purple-600 font-bold mb-6">전문 발성 교정</p>
                            <ul class="text-gray-600 text-sm font-medium space-y-3">
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 성대 결절 후 재활 발성</li>
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 스피치/뮤지컬 전문 발성</li>
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 호흡 메커니즘 전면 교정</li>
                                <li class="flex items-start"><span class="text-nest-orange mr-2 font-bold">✓</span> 목소리 톤 디자인</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <!-- GLOBAL FOOTER SECTION (Visible on all pages) -->
    <section id="contact" class="bg-nest-gray py-24 px-6 md:px-10 border-t border-gray-200">
        <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-16 items-center">
            
            <!-- Contact Info -->
            <div>
                <h2 class="text-4xl md:text-6xl font-display font-black text-nest-black mb-6 leading-tight">
                    Start Your<br><span class="text-nest-blue">Journey.</span>
                </h2>
                <p class="text-gray-600 font-medium mb-10 text-lg">
                    당신의 가능성을 확인하세요. <br>
                    네스토리는 준비된 아티스트를 기다립니다.
                </p>

                <div class="space-y-6 text-gray-800 font-medium bg-white p-8 rounded-3xl shadow-card">
                    <div class="flex items-start space-x-4">
                        <div class="w-10 h-10 bg-blue-50 rounded-full flex items-center justify-center flex-shrink-0">
                            <svg class="w-5 h-5 text-nest-blue" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                        </div>
                        <div>
                            <p class="text-sm font-bold text-gray-400 uppercase tracking-wider mb-1">Location</p>
                            <p>부산광역시 남구 용소로19번길 10, 2층 네스토리</p>
                        </div>
                    </div>
                    <div class="flex items-start space-x-4">
                        <div class="w-10 h-10 bg-orange-50 rounded-full flex items-center justify-center flex-shrink-0">
                            <svg class="w-5 h-5 text-nest-orange" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg>
                        </div>
                        <div>
                            <p class="text-sm font-bold text-gray-400 uppercase tracking-wider mb-1">Contact</p>
                            <p>051-XXX-XXXX<br>nestoryent@gmail.com</p>
                        </div>
                    </div>
                </div>

                <div class="mt-8">
                    <a href="https://map.naver.com/p/entry/place/30827190" target="_blank" class="inline-block bg-[#03C75A] text-white px-8 py-4 rounded-full font-bold text-sm tracking-wide uppercase hover:bg-green-600 transition-colors shadow-bouncy cursor-pointer">
                        네이버 예약하기
                    </a>
                </div>
            </div>

            <!-- Inquiry Form -->
            <div class="bg-white p-10 rounded-3xl shadow-xl border border-gray-100">
                <h3 class="text-2xl font-display font-bold text-nest-black mb-8">상담 신청</h3>
                <form id="consulting-form" class="space-y-5">
                    <div>
                        <label class="block text-xs font-bold text-gray-500 uppercase tracking-wider mb-2">Name</label>
                        <input type="text" name="name" required class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 text-gray-800 focus:outline-none focus:ring-2 focus:ring-nest-blue transition-all" placeholder="이름을 입력하세요">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-gray-500 uppercase tracking-wider mb-2">Phone</label>
                        <input type="tel" name="phone" required class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 text-gray-800 focus:outline-none focus:ring-2 focus:ring-nest-blue transition-all" placeholder="연락처를 입력하세요">
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-gray-500 uppercase tracking-wider mb-2">Program of Interest</label>
                        <select name="program" required class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 text-gray-800 focus:outline-none focus:ring-2 focus:ring-nest-blue transition-all appearance-none">
                            <option value="">관심 프로그램을 선택하세요</option>
                            <option value="elite">Elite Artist (국내/해외입시)</option>
                            <option value="pro">Professional (오디션)</option>
                            <option value="hobby">Hobby / Life (취미)</option>
                            <option value="therapy">Vocal Therapy (교정)</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-xs font-bold text-gray-500 uppercase tracking-wider mb-2">Message (Optional)</label>
                        <textarea name="message" rows="3" class="w-full bg-gray-50 border border-gray-200 rounded-xl px-4 py-3 text-gray-800 focus:outline-none focus:ring-2 focus:ring-nest-blue transition-all resize-none" placeholder="문의 사항을 남겨주세요."></textarea>
                    </div>
                    <button type="submit" id="submit-btn" class="w-full py-4 bg-nest-black text-white rounded-xl font-bold text-sm tracking-widest uppercase hover:bg-nest-blue transition-colors mt-2 shadow-md cursor-pointer flex justify-center items-center">
                        <span>신청하기</span>
                    </button>
                    <!-- Status message display -->
                    <p id="form-status" class="hidden"></p>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-white border-t border-gray-100 py-10 px-6 md:px-10">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center text-sm text-gray-500 font-medium">
            <p>&copy; 2026 NESTORY ENTERTAINMENT ARTISM. ALL RIGHTS RESERVED.</p>
            <div class="flex space-x-6 mt-4 md:mt-0 font-bold">
                <a href="#" class="hover:text-nest-blue transition-colors cursor-pointer">INSTAGRAM</a>
                <a href="https://blog.naver.com" target="_blank" class="hover:text-[#03C75A] transition-colors cursor-pointer">NAVER BLOG</a>
                <a href="#" class="hover:text-nest-blue transition-colors cursor-pointer">PRIVACY POLICY</a>
            </div>
        </div>
    </footer>

    <!-- JavaScript for Page Navigation and Form Submission -->
    <script>
        function changePage(pageId, sectionId = null) {
            // 모든 페이지 뷰 숨기기
            const pages = document.querySelectorAll('.page-view');
            pages.forEach(page => {
                page.classList.add('hidden');
                page.classList.remove('block');
            });

            // 선택된 페이지만 보이기
            const selectedPage = document.getElementById('page-' + pageId);
            if (selectedPage) {
                selectedPage.classList.remove('hidden');
                selectedPage.classList.add('block');
            }

            // 스크롤 처리 (특정 섹션이 지정된 경우 해당 섹션으로, 아니면 맨 위로)
            if (sectionId) {
                setTimeout(() => {
                    const section = document.getElementById(sectionId);
                    if (section) section.scrollIntoView({ behavior: 'smooth' });
                }, 50);
            } else {
                window.scrollTo({ top: 0, behavior: 'instant' });
            }
        }

        // Form Submission Logic
        document.getElementById('consulting-form').addEventListener('submit', function(e) {
            e.preventDefault(); // 기본 제출 방지
            
            const form = this;
            const btn = document.getElementById('submit-btn');
            const status = document.getElementById('form-status');
            
            // UI 변경: 제출 중 상태
            btn.innerHTML = '<span class="loader"></span> 전송 중...';
            btn.disabled = true;
            btn.classList.add('opacity-70', 'cursor-not-allowed');
            status.classList.add('hidden');

            const formData = new FormData(form);
            // 구글 Apps Script 전송 호환성을 높이기 위해 URLSearchParams 형식으로 변환
            const data = new URLSearchParams();
            for (const pair of formData) {
                data.append(pair[0], pair[1]);
            }

            // ==========================================
            // [중요] 아래 URL을 본인의 구글 웹 앱 URL로 교체하세요!
            // ==========================================
            const scriptURL = 'https://script.google.com/macros/s/AKfycbwLBvWwLYdEy4sC3p3BUZmmutijmUghcQqIXNPsJ2f_EBrLdmlD6hxBkbZt7rk0Hwd9Nw/exec'; 

            fetch(scriptURL, { method: 'POST', body: data })
                .then(response => {
                    // 성공 처리
                    status.textContent = '✅ 상담 신청이 성공적으로 접수되었습니다.';
                    status.className = 'text-green-600 text-sm font-bold text-center mt-4 block fade-in';
                    form.reset(); // 폼 초기화
                })
                .catch(error => {
                    // 에러 처리
                    status.textContent = '❌ 오류가 발생했습니다. 잠시 후 다시 시도해주세요.';
                    status.className = 'text-red-500 text-sm font-bold text-center mt-4 block fade-in';
                    console.error('Error!', error.message);
                })
                .finally(() => {
                    // UI 복구
                    btn.innerHTML = '<span>신청하기</span>';
                    btn.disabled = false;
                    btn.classList.remove('opacity-70', 'cursor-not-allowed');
                });
        });
    </script>
</body>
</html>
