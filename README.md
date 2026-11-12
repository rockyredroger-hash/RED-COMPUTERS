<!DOCTYPE html>
<html lang="en" class="scroll-smooth dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RED COMPUTERS | High-Performance Gaming PCs & Hardware Sri Lanka</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Orbitron for cyber headers & Inter for clean readability -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Orbitron:wght@600;700;800;900&display=swap" rel="stylesheet">
    <!-- Font Awesome for crisp tech & UI icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        cyber: ['Orbitron', 'sans-serif'],
                    },
                    colors: {
                        cyber: {
                            bg: '#0a0a0c',
                            surface: '#121216',
                            card: '#18181f',
                            border: '#272732',
                            red: '#ff1e1e',
                            redDark: '#b80000',
                            redGlow: 'rgba(255, 30, 30, 0.35)'
                        }
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #0a0a0c;
            color: #f4f4f6;
            overflow-x: hidden;
        }
        .cyber-grid {
            background-image: 
                linear-gradient(to right, rgba(255, 30, 30, 0.06) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(255, 30, 30, 0.06) 1px, transparent 1px);
            background-size: 40px 40px;
        }
        .neon-glow {
            box-shadow: 0 0 20px rgba(255, 30, 30, 0.35);
        }
        .neon-glow-hover:hover {
            box-shadow: 0 0 25px rgba(255, 30, 30, 0.55);
        }
        .neon-text {
            text-shadow: 0 0 12px rgba(255, 30, 30, 0.6);
        }
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0a0a0c;
        }
        ::-webkit-scrollbar-thumb {
            background: #272732;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #ff1e1e;
        }
    </style>
</head>
<body class="antialiased selection:bg-cyber-red selection:text-white">

    <!-- Toast Notification Container (Replaces alert()) -->
    <div id="toast-container" class="fixed bottom-5 right-5 z-50 flex flex-col gap-3 pointer-events-none"></div>

    <!-- Header / Navigation -->
    <header class="sticky top-0 z-40 bg-cyber-bg/90 backdrop-blur-md border-b border-cyber-border">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20 gap-4">
                <!-- Logo -->
                <a href="#home" class="flex items-center gap-3 group shrink-0">
                    <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-cyber-red to-cyber-redDark flex items-center justify-center neon-glow group-hover:scale-105 transition-transform">
                        <i class="fa-solid fa-microchip text-white text-xl"></i>
                    </div>
                    <div class="flex flex-col">
                        <span class="font-cyber font-black text-xl tracking-wider text-white leading-none">RED <span class="text-cyber-red">COMPUTERS</span></span>
                        <span class="text-[10px] tracking-[0.25em] text-gray-400 uppercase mt-1">Sri Lanka • Pro Hardware</span>
                    </div>
                </a>

                <!-- Desktop Navigation Links -->
                <nav class="hidden lg:flex items-center space-x-8 text-sm font-medium">
                    <a href="#home" class="text-gray-300 hover:text-cyber-red transition-colors">Home</a>
                    <a href="#products" class="text-gray-300 hover:text-cyber-red transition-colors">Products</a>
                    <a href="#pc-builder" class="text-gray-300 hover:text-cyber-red transition-colors flex items-center gap-1.5">
                        <span class="w-2 h-2 rounded-full bg-cyber-red animate-pulse"></span>
                        Custom PC Builder
                    </a>
                    <a href="#services" class="text-gray-300 hover:text-cyber-red transition-colors">Services</a>
                    <a href="#contact" class="text-gray-300 hover:text-cyber-red transition-colors">Contact</a>
                </nav>

                <!-- Search & Cart Actions -->
                <div class="flex items-center gap-3 sm:gap-4">
                    <!-- Search Bar -->
                    <div class="relative hidden sm:block w-48 md:w-64">
                        <input type="text" id="search-input" placeholder="Search RTX, Ryzen, Laptops..." 
                            class="w-full bg-cyber-surface border border-cyber-border rounded-lg pl-9 pr-3 py-2 text-sm text-white placeholder-gray-500 focus:outline-none focus:border-cyber-red transition-colors">
                        <i class="fa-solid fa-magnifying-glass absolute left-3 top-1/2 -translate-y-1/2 text-gray-500 text-xs"></i>
                    </div>

                    <!-- Cart Button -->
                    <button onclick="toggleCart(true)" class="relative p-2.5 rounded-lg bg-cyber-surface border border-cyber-border hover:border-cyber-red text-gray-200 hover:text-white transition-all group">
                        <i class="fa-solid fa-cart-shopping text-lg group-hover:text-cyber-red transition-colors"></i>
                        <span id="cart-badge" class="absolute -top-2 -right-2 bg-cyber-red text-white text-xs font-bold w-5 h-5 rounded-full flex items-center justify-center shadow-lg">0</span>
                    </button>

                    <!-- Mobile Menu Toggle -->
                    <button onclick="toggleMobileMenu()" class="lg:hidden p-2.5 rounded-lg bg-cyber-surface border border-cyber-border text-gray-200 hover:text-cyber-red">
                        <i class="fa-solid fa-bars text-lg"></i>
                    </button>
                </div>
            </div>

            <!-- Mobile Search & Menu -->
            <div id="mobile-menu" class="hidden lg:hidden pb-4 border-t border-cyber-border pt-4 space-y-3">
                <div class="relative sm:hidden">
                    <input type="text" id="mobile-search-input" placeholder="Search hardware..." 
                        class="w-full bg-cyber-surface border border-cyber-border rounded-lg pl-9 pr-3 py-2 text-sm text-white placeholder-gray-500 focus:outline-none focus:border-cyber-red">
                    <i class="fa-solid fa-magnifying-glass absolute left-3 top-1/2 -translate-y-1/2 text-gray-500 text-xs"></i>
                </div>
                <div class="flex flex-col space-y-2 text-sm font-medium">
                    <a href="#home" onclick="toggleMobileMenu()" class="px-3 py-2 rounded-lg hover:bg-cyber-surface text-gray-200 hover:text-cyber-red">Home</a>
                    <a href="#products" onclick="toggleMobileMenu()" class="px-3 py-2 rounded-lg hover:bg-cyber-surface text-gray-200 hover:text-cyber-red">Products</a>
                    <a href="#pc-builder" onclick="toggleMobileMenu()" class="px-3 py-2 rounded-lg hover:bg-cyber-surface text-cyber-red font-semibold">Custom PC Builder</a>
                    <a href="#services" onclick="toggleMobileMenu()" class="px-3 py-2 rounded-lg hover:bg-cyber-surface text-gray-200 hover:text-cyber-red">Services</a>
                    <a href="#contact" onclick="toggleMobileMenu()" class="px-3 py-2 rounded-lg hover:bg-cyber-surface text-gray-200 hover:text-cyber-red">Contact</a>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="relative cyber-grid border-b border-cyber-border overflow-hidden">
        <!-- Ambient Red Glow Blobs -->
        <div class="absolute -top-24 -left-24 w-96 h-96 bg-cyber-red/20 rounded-full blur-[120px] pointer-events-none"></div>
        <div class="absolute bottom-0 right-0 w-96 h-96 bg-cyber-red/15 rounded-full blur-[130px] pointer-events-none"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 md:py-24 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
                <!-- Left Copy -->
                <div class="lg:col-span-7 space-y-6 text-center lg:text-left">
                    <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-cyber-red/10 border border-cyber-red/30 text-cyber-red text-xs font-semibold tracking-wider uppercase">
                        <i class="fa-solid fa-bolt"></i> Sri Lanka's #1 Custom Rig Destination
                    </div>
                    <h1 class="font-cyber text-4xl sm:text-5xl lg:text-6xl font-black tracking-tight text-white leading-tight">
                        UNLEASH EXTREME <br>
                        <span class="text-cyber-red neon-text">GAMING POWER</span>
                    </h1>
                    <p class="text-gray-400 text-base sm:text-lg max-w-2xl mx-auto lg:mx-0 leading-relaxed">
                        Precision-engineered custom gaming PCs, flagship creator workstations, and genuine next-gen components delivered islandwide across Sri Lanka with official agent warranties.
                    </p>
                    <div class="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4 pt-2">
                        <a href="#products" class="w-full sm:w-auto px-8 py-4 rounded-xl bg-cyber-red hover:bg-red-600 text-white font-bold text-sm tracking-wider uppercase transition-all neon-glow neon-glow-hover flex items-center justify-center gap-2">
                            <i class="fa-solid fa-bag-shopping"></i> Shop Hardware
                        </a>
                        <a href="#pc-builder" class="w-full sm:w-auto px-8 py-4 rounded-xl bg-cyber-surface hover:bg-cyber-card border border-cyber-border hover:border-cyber-red text-white font-bold text-sm tracking-wider uppercase transition-all flex items-center justify-center gap-2">
                            <i class="fa-solid fa-screwdriver-wrench text-cyber-red"></i> Build Your PC
                        </a>
                    </div>
                    <!-- Trust Metrics -->
                    <div class="grid grid-cols-3 gap-4 pt-6 border-t border-cyber-border/80 max-w-lg mx-auto lg:mx-0">
                        <div>
                            <div class="font-cyber text-xl sm:text-2xl font-bold text-white">3 YR</div>
                            <div class="text-xs text-gray-400">Official Warranty</div>
                        </div>
                        <div>
                            <div class="font-cyber text-xl sm:text-2xl font-bold text-cyber-red">24-48H</div>
                            <div class="text-xs text-gray-400">Islandwide Delivery</div>
                        </div>
                        <div>
                            <div class="font-cyber text-xl sm:text-2xl font-bold text-white">100%</div>
                            <div class="text-xs text-gray-400">Genuine Parts</div>
                        </div>
                    </div>
                </div>

                <!-- Right Showcase Visual -->
                <div class="lg:col-span-5">
                    <div class="relative rounded-2xl bg-gradient-to-b from-cyber-card to-cyber-bg p-2 border border-cyber-border shadow-2xl group">
                        <div class="absolute -inset-0.5 bg-gradient-to-r from-cyber-red to-transparent rounded-2xl opacity-30 group-hover:opacity-60 transition duration-500 blur"></div>
                        <div class="relative rounded-xl overflow-hidden bg-cyber-surface">
                            <img src="https://images.unsplash.com/photo-1587202372775-e229f172b9d7?auto=format&fit=crop&w=900&q=80" 
                                 onerror="this.src='https://placehold.co/800x650/18181f/ff1e1e?text=RED+COMPUTERS+FLAGSHIP+RIG'"
                                 alt="Red Computers Custom RGB Gaming PC" 
                                 class="w-full h-72 sm:h-96 object-cover object-center group-hover:scale-105 transition-transform duration-700">
                            <div class="absolute inset-0 bg-gradient-to-t from-cyber-bg via-transparent to-transparent"></div>
                            <div class="absolute bottom-4 left-4 right-4 p-4 rounded-xl bg-cyber-bg/90 backdrop-blur-md border border-cyber-border flex items-center justify-between">
                                <div>
                                    <span class="text-[11px] font-bold uppercase tracking-wider text-cyber-red">Featured Flagship</span>
                                    <h3 class="font-cyber font-bold text-white text-sm sm:text-base">RED VENOM RTX 4090 EDITION</h3>
                                    <p class="text-xs text-gray-400">i9-14900K • 64GB DDR5 • 2TB Gen5 NVMe</p>
                                </div>
                                <button onclick="quickAddHeroRig()" class="px-3.5 py-2 rounded-lg bg-cyber-red hover:bg-red-600 text-white text-xs font-bold transition-colors shrink-0">
                                    + Cart
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Products Section -->
    <section id="products" class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-10">
            <div>
                <span class="text-cyber-red font-bold text-xs uppercase tracking-[0.2em]">Catalog</span>
                <h2 class="font-cyber text-3xl sm:text-4xl font-bold text-white mt-1">FEATURED HARDWARE</h2>
            </div>

            <!-- Category Filter Pills -->
            <div id="category-filters" class="flex flex-wrap gap-2">
                <button data-category="All" class="filter-btn active px-4 py-2 rounded-lg text-xs sm:text-sm font-semibold bg-cyber-red text-white transition-all">All</button>
                <button data-category="Gaming PCs" class="filter-btn px-4 py-2 rounded-lg text-xs sm:text-sm font-semibold bg-cyber-surface border border-cyber-border text-gray-300 hover:border-cyber-red hover:text-white transition-all">Gaming PCs</button>
                <button data-category="Laptops" class="filter-btn px-4 py-2 rounded-lg text-xs sm:text-sm font-semibold bg-cyber-surface border border-cyber-border text-gray-300 hover:border-cyber-red hover:text-white transition-all">Laptops</button>
                <button data-category="GPUs & CPUs" class="filter-btn px-4 py-2 rounded-lg text-xs sm:text-sm font-semibold bg-cyber-surface border border-cyber-border text-gray-300 hover:border-cyber-red hover:text-white transition-all">GPUs & CPUs</button>
                <button data-category="Peripherals" class="filter-btn px-4 py-2 rounded-lg text-xs sm:text-sm font-semibold bg-cyber-surface border border-cyber-border text-gray-300 hover:border-cyber-red hover:text-white transition-all">Peripherals</button>
            </div>
        </div>

        <!-- Product Grid -->
        <div id="product-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
            <!-- Dynamically populated by JS -->
        </div>

        <!-- Empty Search State -->
        <div id="empty-search" class="hidden text-center py-16 bg-cyber-surface rounded-2xl border border-cyber-border">
            <i class="fa-solid fa-magnifying-glass text-4xl text-gray-600 mb-3"></i>
            <h3 class="font-cyber text-lg font-bold text-white">No hardware found</h3>
            <p class="text-sm text-gray-400 mt-1">Try adjusting your search keywords or category filter.</p>
            <button onclick="resetFilters()" class="mt-4 px-5 py-2 rounded-lg bg-cyber-red text-white text-xs font-bold uppercase">Reset Filters</button>
        </div>
    </section>

    <!-- Interactive Custom PC Builder Section -->
    <section id="pc-builder" class="py-20 bg-cyber-surface/60 border-y border-cyber-border relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-2xl mx-auto mb-12">
                <span class="text-cyber-red font-bold text-xs uppercase tracking-[0.2em]">Configurator</span>
                <h2 class="font-cyber text-3xl sm:text-4xl font-bold text-white mt-1">CUSTOM PC BUILDER</h2>
                <p class="text-gray-400 text-sm sm:text-base mt-3">
                    Select your core components below to estimate your custom build price in LKR. Includes professional assembly, stress-testing, and cable management.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-start">
                <!-- Component Selectors -->
                <div class="lg:col-span-7 bg-cyber-card border border-cyber-border rounded-2xl p-6 sm:p-8 space-y-6">
                    <!-- CPU -->
                    <div>
                        <label class="flex items-center justify-between text-sm font-semibold text-gray-200 mb-2">
                            <span><i class="fa-solid fa-microchip text-cyber-red mr-2"></i>Processor (CPU)</span>
                            <span id="cpu-price-tag" class="text-xs text-cyber-red font-mono">Rs. 118,500</span>
                        </label>
                        <select id="builder-cpu" onchange="updateBuilder()" class="w-full bg-cyber-bg border border-cyber-border rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-cyber-red">
                            <option value="118500" data-name="Intel Core i5-14600K (14 Cores)">Intel Core i5-14600K (14 Cores / 20 Threads) - Rs. 118,500</option>
                            <option value="124000" data-name="AMD Ryzen 7 7800X3D">AMD Ryzen 7 7800X3D (Gaming King) - Rs. 124,000</option>
                            <option value="165000" data-name="Intel Core i7-14700K">Intel Core i7-14700K (20 Cores / 28 Threads) - Rs. 165,000</option>
                            <option value="215000" data-name="Intel Core i9-14900K">Intel Core i9-14900K (24 Cores / 32 Threads) - Rs. 215,000</option>
                        </select>
                    </div>

                    <!-- GPU -->
                    <div>
                        <label class="flex items-center justify-between text-sm font-semibold text-gray-200 mb-2">
                            <span><i class="fa-solid fa-vr-cardboard text-cyber-red mr-2"></i>Graphics Card (GPU)</span>
                            <span id="gpu-price-tag" class="text-xs text-cyber-red font-mono">Rs. 135,000</span>
                        </label>
                        <select id="builder-gpu" onchange="updateBuilder()" class="w-full bg-cyber-bg border border-cyber-border rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-cyber-red">
                            <option value="135000" data-name="NVIDIA GeForce RTX 4060 8GB">NVIDIA GeForce RTX 4060 8GB OC - Rs. 135,000</option>
                            <option value="238000" data-name="NVIDIA GeForce RTX 4070 SUPER 12GB">NVIDIA GeForce RTX 4070 SUPER 12GB - Rs. 238,000</option>
                            <option value="395000" data-name="NVIDIA GeForce RTX 4080 SUPER 16GB">NVIDIA GeForce RTX 4080 SUPER 16GB - Rs. 395,000</option>
                            <option value="695000" data-name="ASUS ROG Strix RTX 4090 24GB">ASUS ROG Strix RTX 4090 24GB OC - Rs. 695,000</option>
                        </select>
                    </div>

                    <!-- RAM -->
                    <div>
                        <label class="flex items-center justify-between text-sm font-semibold text-gray-200 mb-2">
                            <span><i class="fa-solid fa-memory text-cyber-red mr-2"></i>Memory (RAM)</span>
                            <span id="ram-price-tag" class="text-xs text-cyber-red font-mono">Rs. 24,500</span>
                        </label>
                        <select id="builder-ram" onchange="updateBuilder()" class="w-full bg-cyber-bg border border-cyber-border rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-cyber-red">
                            <option value="24500" data-name="16GB DDR5 5600MHz RGB">16GB (2x8GB) DDR5 5600MHz RGB - Rs. 24,500</option>
                            <option value="44000" data-name="32GB DDR5 6000MHz CL30 RGB">32GB (2x16GB) DDR5 6000MHz CL30 RGB - Rs. 44,000</option>
                            <option value="86000" data-name="64GB DDR5 6400MHz Dominator RGB">64GB (2x32GB) DDR5 6400MHz RGB - Rs. 86,000</option>
                        </select>
                    </div>

                    <!-- Storage -->
                    <div>
                        <label class="flex items-center justify-between text-sm font-semibold text-gray-200 mb-2">
                            <span><i class="fa-solid fa-hard-drive text-cyber-red mr-2"></i>Primary NVMe Storage</span>
                            <span id="storage-price-tag" class="text-xs text-cyber-red font-mono">Rs. 29,500</span>
                        </label>
                        <select id="builder-storage" onchange="updateBuilder()" class="w-full bg-cyber-bg border border-cyber-border rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-cyber-red">
                            <option value="29500" data-name="1TB Samsung 990 PRO Gen4 NVMe">1TB Samsung 990 PRO Gen4 NVMe SSD - Rs. 29,500</option>
                            <option value="54000" data-name="2TB WD Black SN850X Gen4 NVMe">2TB WD Black SN850X Gen4 NVMe SSD - Rs. 54,000</option>
                            <option value="105000" data-name="4TB Kingston Fury Renegade NVMe">4TB Kingston Fury Renegade Gen4 NVMe - Rs. 105,000</option>
                        </select>
                    </div>
                </div>

                <!-- Live Summary Card -->
                <div class="lg:col-span-5 bg-gradient-to-b from-cyber-card to-cyber-bg border border-cyber-red/40 rounded-2xl p-6 sm:p-8 shadow-2xl">
                    <div class="flex items-center justify-between border-b border-cyber-border pb-4 mb-5">
                        <div>
                            <span class="text-xs uppercase tracking-wider text-cyber-red font-bold">Live Spec Sheet</span>
                            <h3 class="font-cyber text-xl font-bold text-white">YOUR CUSTOM RIG</h3>
                        </div>
                        <span class="px-3 py-1 rounded-full bg-emerald-500/10 border border-emerald-500/30 text-emerald-400 text-xs font-semibold">
                            <i class="fa-solid fa-check-circle mr-1"></i>Compatible
                        </span>
                    </div>

                    <ul id="builder-summary-list" class="space-y-3 text-sm text-gray-300 mb-6">
                        <!-- Populated by JS -->
                    </ul>

                    <div class="p-4 rounded-xl bg-cyber-surface border border-cyber-border mb-6 space-y-2">
                        <div class="flex justify-between text-xs text-gray-400">
                            <span>Pro Assembly & Thermal Paste</span>
                            <span class="text-emerald-400 font-semibold">FREE</span>
                        </div>
                        <div class="flex justify-between text-xs text-gray-400">
                            <span>Base Chassis, PSU & Motherboard Bundle</span>
                            <span>Rs. 85,000</span>
                        </div>
                        <div class="border-t border-cyber-border pt-2 flex items-baseline justify-between">
                            <span class="text-sm font-semibold text-white">Estimated Total:</span>
                            <span id="builder-total-price" class="font-cyber text-2xl font-black text-cyber-red">Rs. 392,500</span>
                        </div>
                    </div>

                    <button onclick="addCustomBuildToCart()" class="w-full py-4 rounded-xl bg-cyber-red hover:bg-red-600 text-white font-bold text-sm uppercase tracking-wider transition-all neon-glow neon-glow-hover flex items-center justify-center gap-2">
                        <i class="fa-solid fa-cart-plus"></i> Add Custom Rig to Cart
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-2xl mx-auto mb-14">
            <span class="text-cyber-red font-bold text-xs uppercase tracking-[0.2em]">Beyond Hardware</span>
            <h2 class="font-cyber text-3xl sm:text-4xl font-bold text-white mt-1">ELITE TECH SERVICES</h2>
            <p class="text-gray-400 text-sm sm:text-base mt-3">
                Our certified technicians in Colombo keep your battle station running at peak thermal and frame-rate efficiency.
            </p>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
            <!-- Service 1 -->
            <div class="p-6 rounded-2xl bg-cyber-card border border-cyber-border hover:border-cyber-red transition-all group">
                <div class="w-12 h-12 rounded-xl bg-cyber-red/10 border border-cyber-red/30 flex items-center justify-center text-cyber-red text-xl mb-5 group-hover:bg-cyber-red group-hover:text-white transition-colors">
                    <i class="fa-solid fa-screwdriver-wrench"></i>
                </div>
                <h3 class="font-cyber text-lg font-bold text-white mb-2">PC Repairs & Diagnostics</h3>
                <p class="text-sm text-gray-400 leading-relaxed">
                    Chip-level motherboard diagnostics, thermal repasting, deep dust cleaning, and OS optimization.
                </p>
            </div>

            <!-- Service 2 -->
            <div class="p-6 rounded-2xl bg-cyber-card border border-cyber-border hover:border-cyber-red transition-all group">
                <div class="w-12 h-12 rounded-xl bg-cyber-red/10 border border-cyber-red/30 flex items-center justify-center text-cyber-red text-xl mb-5 group-hover:bg-cyber-red group-hover:text-white transition-colors">
                    <i class="fa-solid fa-water"></i>
                </div>
                <h3 class="font-cyber text-lg font-bold text-white mb-2">Custom Water Cooling</h3>
                <p class="text-sm text-gray-400 leading-relaxed">
                    Bespoke hardline & soft-tube liquid cooling loops engineered for whisper-quiet, sub-zero thermals.
                </p>
            </div>

            <!-- Service 3 -->
            <div class="p-6 rounded-2xl bg-cyber-card border border-cyber-border hover:border-cyber-red transition-all group">
                <div class="w-12 h-12 rounded-xl bg-cyber-red/10 border border-cyber-red/30 flex items-center justify-center text-cyber-red text-xl mb-5 group-hover:bg-cyber-red group-hover:text-white transition-colors">
                    <i class="fa-solid fa-gauge-high"></i>
                </div>
                <h3 class="font-cyber text-lg font-bold text-white mb-2">Upgrade Consultations</h3>
                <p class="text-sm text-gray-400 leading-relaxed">
                    Bottleneck analysis and tailored hardware upgrade paths for gamers, 3D artists, and streamers.
                </p>
            </div>

            <!-- Service 4 -->
            <div class="p-6 rounded-2xl bg-cyber-card border border-cyber-border hover:border-cyber-red transition-all group">
                <div class="w-12 h-12 rounded-xl bg-cyber-red/10 border border-cyber-red/30 flex items-center justify-center text-cyber-red text-xl mb-5 group-hover:bg-cyber-red group-hover:text-white transition-colors">
                    <i class="fa-solid fa-truck-fast"></i>
                </div>
                <h3 class="font-cyber text-lg font-bold text-white mb-2">Islandwide Delivery</h3>
                <p class="text-sm text-gray-400 leading-relaxed">
                    Insured, shock-proof courier shipping from Colombo to Kandy, Galle, Jaffna, and everywhere in SL.
                </p>
            </div>
        </div>
    </section>

    <!-- Contact & Showroom Section -->
    <section id="contact" class="py-20 bg-cyber-surface border-t border-cyber-border">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
                <!-- Contact Info -->
                <div class="lg:col-span-5 space-y-6">
                    <div>
                        <span class="text-cyber-red font-bold text-xs uppercase tracking-[0.2em]">Visit Our Showroom</span>
                        <h2 class="font-cyber text-3xl font-bold text-white mt-1">GET IN TOUCH</h2>
                        <p class="text-gray-400 text-sm mt-2">
                            Experience live demo rigs at our Colombo flagship store or message our sales team for instant quotes.
                        </p>
                    </div>

                    <div class="space-y-4">
                        <div class="flex items-start gap-4 p-4 rounded-xl bg-cyber-bg border border-cyber-border">
                            <i class="fa-solid fa-location-dot text-cyber-red text-lg mt-1"></i>
                            <div>
                                <h4 class="font-semibold text-white text-sm">Colombo Flagship Store</h4>
                                <p class="text-xs text-gray-400 mt-0.5">No. 428, Galle Road, Kollupitiya, Colombo 03, Sri Lanka</p>
                            </div>
                        </div>

                        <div class="flex items-start gap-4 p-4 rounded-xl bg-cyber-bg border border-cyber-border">
                            <i class="fa-solid fa-phone-volume text-cyber-red text-lg mt-1"></i>
                            <div>
                                <h4 class="font-semibold text-white text-sm">Hotline & WhatsApp</h4>
                                <p class="text-xs text-gray-400 mt-0.5">+94 11 234 5678  |  +94 77 890 1234</p>
                            </div>
                        </div>

                        <div class="flex items-start gap-4 p-4 rounded-xl bg-cyber-bg border border-cyber-border">
                            <i class="fa-solid fa-clock text-cyber-red text-lg mt-1"></i>
                            <div>
                                <h4 class="font-semibold text-white text-sm">Operating Hours</h4>
                                <p class="text-xs text-gray-400 mt-0.5">Mon – Sat: 9:30 AM – 7:30 PM | Sun: 10:00 AM – 4:00 PM</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Contact Form -->
                <div class="lg:col-span-7 bg-cyber-bg border border-cyber-border rounded-2xl p-6 sm:p-8">
                    <h3 class="font-cyber text-xl font-bold text-white mb-5">SEND US A MESSAGE</h3>
                    <form onsubmit="handleContactSubmit(event)" class="space-y-4">
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-xs font-medium text-gray-400 mb-1.5">Your Name</label>
                                <input type="text" required placeholder="Kasun Perera" class="w-full bg-cyber-surface border border-cyber-border rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-cyber-red">
                            </div>
                            <div>
                                <label class="block text-xs font-medium text-gray-400 mb-1.5">Phone / WhatsApp</label>
                                <input type="tel" required placeholder="077 123 4567" class="w-full bg-cyber-surface border border-cyber-border rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-cyber-red">
                            </div>
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-gray-400 mb-1.5">Inquiry Type</label>
                            <select class="w-full bg-cyber-surface border border-cyber-border rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-cyber-red">
                                <option>Custom PC Build Quotation</option>
                                <option>Component Stock Availability</option>
                                <option>Repair / Warranty Support</option>
                                <option>Corporate / Bulk Order</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-gray-400 mb-1.5">Message</label>
                            <textarea rows="4" required placeholder="Tell us your budget or the parts you are looking for..." class="w-full bg-cyber-surface border border-cyber-border rounded-xl px-4 py-3 text-sm text-white focus:outline-none focus:border-cyber-red"></textarea>
                        </div>
                        <button type="submit" class="px-8 py-3.5 rounded-xl bg-cyber-red hover:bg-red-600 text-white font-bold text-sm uppercase tracking-wider transition-all neon-glow">
                            Send Inquiry <i class="fa-solid fa-paper-plane ml-1.5"></i>
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-cyber-bg border-t border-cyber-border py-10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row items-center justify-between gap-6">
            <div class="flex items-center gap-3">
                <div class="w-8 h-8 rounded-lg bg-cyber-red flex items-center justify-center">
                    <i class="fa-solid fa-microchip text-white text-sm"></i>
                </div>
                <span class="font-cyber font-bold text-lg text-white">RED <span class="text-cyber-red">COMPUTERS</span></span>
            </div>

            <p class="text-xs text-gray-500 text-center">
                &copy; 2026 Red Computers (Pvt) Ltd. Colombo, Sri Lanka. All Rights Reserved.
            </p>

            <div class="flex items-center gap-4">
                <a href="#contact" aria-label="Facebook" class="w-9 h-9 rounded-lg bg-cyber-surface border border-cyber-border hover:border-cyber-red flex items-center justify-center text-gray-400 hover:text-cyber-red transition-colors">
                    <i class="fa-brands fa-facebook-f"></i>
                </a>
                <a href="#contact" aria-label="Instagram" class="w-9 h-9 rounded-lg bg-cyber-surface border border-cyber-border hover:border-cyber-red flex items-center justify-center text-gray-400 hover:text-cyber-red transition-colors">
                    <i class="fa-brands fa-instagram"></i>
                </a>
                <a href="#contact" aria-label="YouTube" class="w-9 h-9 rounded-lg bg-cyber-surface border border-cyber-border hover:border-cyber-red flex items-center justify-center text-gray-400 hover:text-cyber-red transition-colors">
                    <i class="fa-brands fa-youtube"></i>
                </a>
                <a href="#contact" aria-label="WhatsApp" class="w-9 h-9 rounded-lg bg-cyber-surface border border-cyber-border hover:border-cyber-red flex items-center justify-center text-gray-400 hover:text-cyber-red transition-colors">
                    <i class="fa-brands fa-whatsapp"></i>
                </a>
            </div>
        </div>
    </footer>

    <!-- Interactive Shopping Cart Slide-over Drawer -->
    <div id="cart-drawer" class="fixed inset-0 z-50 hidden">
        <!-- Backdrop -->
        <div onclick="toggleCart(false)" class="absolute inset-0 bg-black/75 backdrop-blur-sm transition-opacity"></div>
        
        <!-- Drawer Panel -->
        <div class="absolute right-0 top-0 bottom-0 w-full max-w-md bg-cyber-surface border-l border-cyber-border shadow-2xl flex flex-col">
            <!-- Cart Header -->
            <div class="p-6 border-b border-cyber-border flex items-center justify-between">
                <div class="flex items-center gap-2.5">
                    <i class="fa-solid fa-cart-shopping text-cyber-red text-xl"></i>
                    <h3 class="font-cyber text-lg font-bold text-white">YOUR CART</h3>
                </div>
                <button onclick="toggleCart(false)" class="w-8 h-8 rounded-lg bg-cyber-bg border border-cyber-border text-gray-400 hover:text-white flex items-center justify-center">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <!-- Cart Items List -->
            <div id="cart-items-container" class="flex-1 overflow-y-auto p-6 space-y-4">
                <!-- Populated dynamically -->
            </div>

            <!-- Cart Footer / Checkout Summary -->
            <div class="p-6 border-t border-cyber-border bg-cyber-bg space-y-4">
                <div class="space-y-1.5 text-sm">
                    <div class="flex justify-between text-gray-400">
                        <span>Subtotal</span>
                        <span id="cart-subtotal">Rs. 0</span>
                    </div>
                    <div class="flex justify-between text-gray-400">
                        <span>Islandwide Delivery</span>
                        <span class="text-emerald-400 font-medium">FREE</span>
                    </div>
                    <div class="flex justify-between text-base font-bold text-white pt-2 border-t border-cyber-border">
                        <span>Total (LKR)</span>
                        <span id="cart-total" class="font-cyber text-cyber-red text-lg">Rs. 0</span>
                    </div>
                </div>

                <button onclick="handleCheckout()" id="checkout-btn" class="w-full py-3.5 rounded-xl bg-cyber-red hover:bg-red-600 disabled:opacity-40 disabled:pointer-events-none text-white font-bold text-sm uppercase tracking-wider transition-all neon-glow">
                    Proceed to Checkout
                </button>
            </div>
        </div>
    </div>

    <!-- JavaScript Application Logic -->
    <script>
        // Product Catalog Data (Realistic Sri Lankan PC Store Pricing in LKR)
        const products = [
            {
                id: 1,
                name: "RED PHANTOM RTX 4070 Ti SUPER",
                category: "Gaming PCs",
                specs: "Ryzen 7 7800X3D • 32GB DDR5 • 1TB NVMe",
                price: 585000,
                inStock: true,
                image: "https://images.unsplash.com/photo-1593640408182-31c70c8268f5?auto=format&fit=crop&w=600&q=80"
            },
            {
                id: 2,
                name: "ASUS ROG Strix G16 (2025)",
                category: "Laptops",
                specs: "i9-14900HX • RTX 4070 8GB • 16\" 240Hz QHD",
                price: 645000,
                inStock: true,
                image: "https://images.unsplash.com/photo-1603302576837-37561b2e2302?auto=format&fit=crop&w=600&q=80"
            },
            {
                id: 3,
                name: "MSI GeForce RTX 4080 SUPER Gaming X",
                category: "GPUs & CPUs",
                specs: "16GB GDDR6X • Tri Frozr 3 • Ray Tracing",
                price: 415000,
                inStock: true,
                image: "https://images.unsplash.com/photo-1591488320449-011701bb6704?auto=format&fit=crop&w=600&q=80"
            },
            {
                id: 4,
                name: "Logitech G Pro X Superlight 2",
                category: "Peripherals",
                specs: "60g Ultra-Lightweight • HERO 2 32K Sensor",
                price: 52500,
                inStock: true,
                image: "https://images.unsplash.com/photo-1527814050087-3793815479db?auto=format&fit=crop&w=600&q=80"
            },
            {
                id: 5,
                name: "RED STRIKER RTX 4060 Starter Rig",
                category: "Gaming PCs",
                specs: "Core i5-14400F • 16GB DDR5 • 1TB Gen4 SSD",
                price: 315000,
                inStock: true,
                image: "https://images.unsplash.com/photo-1587202372634-32705e3bf49c?auto=format&fit=crop&w=600&q=80"
            },
            {
                id: 6,
                name: "Lenovo Legion Pro 5i Gen 9",
                category: "Laptops",
                specs: "Core i7-14700HX • RTX 4060 • 32GB RAM",
                price: 498000,
                inStock: true,
                image: "https://images.unsplash.com/photo-1525547719571-a2d4ac8945e2?auto=format&fit=crop&w=600&q=80"
            },
            {
                id: 7,
                name: "AMD Ryzen 9 7950X3D Processor",
                category: "GPUs & CPUs",
                specs: "16 Cores • 32 Threads • 144MB 3D V-Cache",
                price: 212000,
                inStock: false,
                image: "https://images.unsplash.com/photo-1555617981-dac3880eac6e?auto=format&fit=crop&w=600&q=80"
            },
            {
                id: 8,
                name: "Keychron Q1 Pro Wireless Mechanical",
                category: "Peripherals",
                specs: "QMK/VIA Custom • Aluminum Body • Red Switch",
                price: 68000,
                inStock: true,
                image: "https://images.unsplash.com/photo-1595225476474-87563907a212?auto=format&fit=crop&w=600&q=80"
            }
        ];

        // State
        let cart = [];
        let activeCategory = 'All';
        let searchQuery = '';

        // Format currency in LKR
        function formatLKR(amount) {
            return 'Rs. ' + amount.toLocaleString('en-LK');
        }

        // Custom Toast Notification (No alert())
        function showToast(message, type = 'success') {
            const container = document.getElementById('toast-container');
            const toast = document.createElement('div');
            const icon = type === 'success' ? 'fa-circle-check text-cyber-red' : 'fa-circle-info text-amber-400';
            
            toast.className = 'pointer-events-auto flex items-center gap-3 px-4 py-3 rounded-xl bg-cyber-card border border-cyber-red/50 text-white text-sm shadow-2xl transform transition-all duration-300 translate-y-2 opacity-0';
            toast.innerHTML = `<i class="fa-solid ${icon} text-base"></i><span>${message}</span>`;
            
            container.appendChild(toast);
            requestAnimationFrame(() => {
                toast.classList.remove('translate-y-2', 'opacity-0');
            });

            setTimeout(() => {
                toast.classList.add('opacity-0', 'translate-y-2');
                setTimeout(() => toast.remove(), 300);
            }, 3000);
        }

        // Render Product Cards
        function renderProducts() {
            const grid = document.getElementById('product-grid');
            const emptyState = document.getElementById('empty-search');
            
            const filtered = products.filter(p => {
                const matchesCat = activeCategory === 'All' || p.category === activeCategory;
                const matchesSearch = p.name.toLowerCase().includes(searchQuery.toLowerCase()) || 
                                      p.specs.toLowerCase().includes(searchQuery.toLowerCase());
                return matchesCat && matchesSearch;
            });

            if (filtered.length === 0) {
                grid.innerHTML = '';
                emptyState.classList.remove('hidden');
                return;
            }

            emptyState.classList.add('hidden');
            grid.innerHTML = filtered.map(product => `
                <div class="bg-cyber-card border border-cyber-border hover:border-cyber-red rounded-2xl overflow-hidden flex flex-col justify-between transition-all duration-300 group">
                    <div>
                        <div class="relative h-48 bg-cyber-surface overflow-hidden">
                            <img src="${product.image}" 
                                 onerror="this.src='https://placehold.co/600x400/18181f/ff1e1e?text=${encodeURIComponent(product.category)}'"
                                 alt="${product.name}" 
                                 class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                            <span class="absolute top-3 left-3 px-2.5 py-1 rounded-md bg-cyber-bg/90 backdrop-blur-sm border border-cyber-border text-[10px] font-bold uppercase tracking-wider text-gray-300">
                                ${product.category}
                            </span>
                            <span class="absolute top-3 right-3 px-2.5 py-1 rounded-md text-[10px] font-bold uppercase ${product.inStock ? 'bg-emerald-500/20 text-emerald-400 border border-emerald-500/30' : 'bg-red-500/20 text-red-400 border border-red-500/30'}">
                                ${product.inStock ? 'In Stock' : 'Pre-Order'}
                            </span>
                        </div>
                        <div class="p-5">
                            <h3 class="font-bold text-white text-base leading-snug group-hover:text-cyber-red transition-colors">${product.name}</h3>
                            <p class="text-xs text-gray-400 mt-1.5 line-clamp-2">${product.specs}</p>
                        </div>
                    </div>
                    <div class="px-5 pb-5 pt-2 flex items-center justify-between border-t border-cyber-border/50 mt-2">
                        <div>
                            <span class="text-[10px] text-gray-500 uppercase block">Cash Price</span>
                            <span class="font-cyber font-bold text-base text-white">${formatLKR(product.price)}</span>
                        </div>
                        <button onclick="addToCart(${product.id})" 
                            class="px-3.5 py-2.5 rounded-xl bg-cyber-surface hover:bg-cyber-red border border-cyber-border hover:border-cyber-red text-white text-xs font-bold transition-all flex items-center gap-1.5">
                            <i class="fa-solid fa-cart-plus"></i> Add
                        </button>
                    </div>
                </div>
            `).join('');
        }

        // Category Filter Listeners
        document.querySelectorAll('.filter-btn').forEach(btn => {
            btn.addEventListener('click', () => {
                document.querySelectorAll('.filter-btn').forEach(b => {
                    b.classList.remove('bg-cyber-red', 'text-white');
                    b.classList.add('bg-cyber-surface', 'border', 'border-cyber-border', 'text-gray-300');
                });
                btn.classList.remove('bg-cyber-surface', 'border', 'border-cyber-border', 'text-gray-300');
                btn.classList.add('bg-cyber-red', 'text-white');
                
                activeCategory = btn.dataset.category;
                renderProducts();
            });
        });

        // Search Listeners
        ['search-input', 'mobile-search-input'].forEach(id => {
            const el = document.getElementById(id);
            if (el) {
                el.addEventListener('input', (e) => {
                    searchQuery = e.target.value;
                    renderProducts();
                });
            }
        });

        function resetFilters() {
            activeCategory = 'All';
            searchQuery = '';
            document.getElementById('search-input').value = '';
            const mob = document.getElementById('mobile-search-input');
            if (mob) mob.value = '';
            document.querySelector('[data-category="All"]').click();
        }

        // Cart Management
        function addToCart(productId) {
            const item = products.find(p => p.id === productId);
            if (!item) return;

            const existing = cart.find(c => c.id === productId);
            if (existing) {
                existing.qty += 1;
            } else {
                cart.push({ ...item, qty: 1 });
            }
            updateCartUI();
            showToast(`Added "${item.name}" to cart`);
        }

        function quickAddHeroRig() {
            const heroRig = {
                id: 'hero-venom-4090',
                name: 'RED VENOM RTX 4090 EDITION',
                specs: 'i9-14900K • 64GB DDR5 • 2TB Gen5 NVMe',
                price: 1150000,
                image: 'https://images.unsplash.com/photo-1587202372775-e229f172b9d7?auto=format&fit=crop&w=600&q=80'
            };
            const existing = cart.find(c => c.id === heroRig.id);
            if (existing) {
                existing.qty += 1;
            } else {
                cart.push({ ...heroRig, qty: 1 });
            }
            updateCartUI();
            showToast('Added Flagship RTX 4090 Rig to cart!');
        }

        function updateQty(id, delta) {
            const index = cart.findIndex(c => String(c.id) === String(id));
            if (index === -1) return;
            cart[index].qty += delta;
            if (cart[index].qty <= 0) {
                cart.splice(index, 1);
            }
            updateCartUI();
        }

        function updateCartUI() {
            const badge = document.getElementById('cart-badge');
            const container = document.getElementById('cart-items-container');
            const subtotalEl = document.getElementById('cart-subtotal');
            const totalEl = document.getElementById('cart-total');
            const checkoutBtn = document.getElementById('checkout-btn');

            const totalItems = cart.reduce((sum, item) => sum + item.qty, 0);
            const totalAmount = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);

            badge.textContent = totalItems;
            subtotalEl.textContent = formatLKR(totalAmount);
            totalEl.textContent = formatLKR(totalAmount);
            checkoutBtn.disabled = cart.length === 0;

            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="h-full flex flex-col items-center justify-center text-center py-12">
                        <i class="fa-solid fa-box-open text-4xl text-gray-600 mb-3"></i>
                        <p class="font-cyber text-sm font-bold text-gray-300">YOUR CART IS EMPTY</p>
                        <p class="text-xs text-gray-500 mt-1">Explore our hardware catalog or build a custom PC.</p>
                    </div>
                `;
                return;
            }

            container.innerHTML = cart.map(item => `
                <div class="flex gap-3.5 p-3.5 rounded-xl bg-cyber-bg border border-cyber-border">
                    <img src="${item.image}" alt="${item.name}" class="w-16 h-16 rounded-lg object-cover shrink-0 bg-cyber-surface">
                    <div class="flex-1 min-w-0">
                        <h4 class="text-xs font-bold text-white truncate">${item.name}</h4>
                        <p class="text-[11px] text-gray-400 truncate mt-0.5">${item.specs}</p>
                        <div class="flex items-center justify-between mt-2.5">
                            <span class="font-cyber text-xs font-bold text-cyber-red">${formatLKR(item.price * item.qty)}</span>
                            <div class="flex items-center gap-2 bg-cyber-surface border border-cyber-border rounded-lg px-2 py-0.5">
                                <button onclick="updateQty('${item.id}', -1)" class="text-gray-400 hover:text-white text-xs px-1">-</button>
                                <span class="text-xs font-bold text-white">${item.qty}</span>
                                <button onclick="updateQty('${item.id}', 1)" class="text-gray-400 hover:text-white text-xs px-1">+</button>
                            </div>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        function toggleCart(open) {
            const drawer = document.getElementById('cart-drawer');
            if (open) {
                drawer.classList.remove('hidden');
            } else {
                drawer.classList.add('hidden');
            }
        }

        function toggleMobileMenu() {
            document.getElementById('mobile-menu').classList.toggle('hidden');
        }

        function handleCheckout() {
            if (cart.length === 0) return;
            cart = [];
            updateCartUI();
            toggleCart(false);
            showToast('Order placed! Our Colombo team will call you shortly to confirm delivery.');
        }

        // Custom PC Builder Logic
        const BASE_BUNDLE_PRICE = 85000; // Case, PSU, Motherboard

        function updateBuilder() {
            const cpuSel = document.getElementById('builder-cpu');
            const gpuSel = document.getElementById('builder-gpu');
            const ramSel = document.getElementById('builder-ram');
            const storageSel = document.getElementById('builder-storage');

            const cpuPrice = Number(cpuSel.value);
            const gpuPrice = Number(gpuSel.value);
            const ramPrice = Number(ramSel.value);
            const storagePrice = Number(storageSel.value);

            document.getElementById('cpu-price-tag').textContent = formatLKR(cpuPrice);
            document.getElementById('gpu-price-tag').textContent = formatLKR(gpuPrice);
            document.getElementById('ram-price-tag').textContent = formatLKR(ramPrice);
            document.getElementById('storage-price-tag').textContent = formatLKR(storagePrice);

            const cpuName = cpuSel.options[cpuSel.selectedIndex].dataset.name;
            const gpuName = gpuSel.options[gpuSel.selectedIndex].dataset.name;
            const ramName = ramSel.options[ramSel.selectedIndex].dataset.name;
            const storageName = storageSel.options[storageSel.selectedIndex].dataset.name;

            document.getElementById('builder-summary-list').innerHTML = `
                <li class="flex items-center gap-2.5"><i class="fa-solid fa-microchip text-cyber-red w-4"></i><span>${cpuName}</span></li>
                <li class="flex items-center gap-2.5"><i class="fa-solid fa-vr-cardboard text-cyber-red w-4"></i><span>${gpuName}</span></li>
                <li class="flex items-center gap-2.5"><i class="fa-solid fa-memory text-cyber-red w-4"></i><span>${ramName}</span></li>
                <li class="flex items-center gap-2.5"><i class="fa-solid fa-hard-drive text-cyber-red w-4"></i><span>${storageName}</span></li>
                <li class="flex items-center gap-2.5"><i class="fa-solid fa-server text-cyber-red w-4"></i><span>RED Airflow ATX Case + 850W Gold PSU + B760/B650 Board</span></li>
            `;

            const total = cpuPrice + gpuPrice + ramPrice + storagePrice + BASE_BUNDLE_PRICE;
            document.getElementById('builder-total-price').textContent = formatLKR(total);
        }

        function addCustomBuildToCart() {
            const cpuSel = document.getElementById('builder-cpu');
            const gpuSel = document.getElementById('builder-gpu');
            const ramSel = document.getElementById('builder-ram');
            const storageSel = document.getElementById('builder-storage');

            const total = Number(cpuSel.value) + Number(gpuSel.value) + Number(ramSel.value) + Number(storageSel.value) + BASE_BUNDLE_PRICE;
            const specsSummary = `${cpuSel.options[cpuSel.selectedIndex].dataset.name} • ${gpuSel.options[gpuSel.selectedIndex].dataset.name}`;

            cart.push({
                id: 'custom-' + Date.now(),
                name: 'CUSTOM RED BUILD RIG',
                specs: specsSummary,
                price: total,
                qty: 1,
                image: 'https://images.unsplash.com/photo-1587202372775-e229f172b9d7?auto=format&fit=crop&w=600&q=80'
            });

            updateCartUI();
            toggleCart(true);
            showToast('Custom PC Build added to your cart!');
        }

        function handleContactSubmit(e) {
            e.preventDefault();
            e.target.reset();
            showToast('Inquiry received! A Red Computers specialist will contact you soon.');
        }

        // Initialize on load
        window.addEventListener('DOMContentLoaded', () => {
            renderProducts();
            updateBuilder();
            updateCartUI();
        });
    </script>
</body>
</html>
