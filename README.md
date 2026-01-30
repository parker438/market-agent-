<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nikal Do - Buy & Sell Locally</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#fff7ed',
                            100: '#ffedd5',
                            500: '#f97316',
                            600: '#ea580c',
                            700: '#c2410c',
                            900: '#7c2d12',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .hero-pattern {
            background-image: radial-gradient(circle at 1px 1px, rgba(255,255,255,0.15) 1px, transparent 0);
            background-size: 20px 20px;
        }
        .category-card:hover .category-icon {
            transform: scale(1.1) rotate(5deg);
        }
        .listing-card {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .listing-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        .gradient-text {
            background: linear-gradient(135deg, #ea580c 0%, #f97316 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .chat-bubble {
            position: relative;
            background: #f3f4f6;
            border-radius: 12px;
            padding: 12px 16px;
        }
        .chat-bubble:after {
            content: '';
            position: absolute;
            left: -8px;
            top: 12px;
            width: 0;
            height: 0;
            border: 8px solid transparent;
            border-right-color: #f3f4f6;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        .animate-float {
            animation: float 3s ease-in-out infinite;
        }
        .scroll-hidden::-webkit-scrollbar {
            display: none;
        }
        .scroll-hidden {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
    </style>
</head>
<body class="bg-gray-50 font-sans antialiased">

    <!-- Navigation -->
    <nav class="bg-white shadow-sm sticky top-0 z-50 border-b border-gray-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Logo -->
                <div class="flex items-center cursor-pointer" onclick="showPage('home')">
                    <div class="flex items-center space-x-2">
                        <div class="w-10 h-10 bg-gradient-to-br from-brand-500 to-brand-700 rounded-xl flex items-center justify-center text-white font-bold text-xl shadow-lg">
                            <i class="fas fa-hand-holding-usd"></i>
                        </div>
                        <span class="text-2xl font-bold text-gray-900 tracking-tight">Nikal Do</span>
                    </div>
                </div>

                <!-- Search Bar - Desktop -->
                <div class="hidden md:flex flex-1 max-w-2xl mx-8">
                    <div class="relative w-full">
                        <input type="text" id="searchInput" placeholder="Search for anything... cars, phones, furniture" 
                               class="w-full pl-12 pr-4 py-2.5 bg-gray-100 border-transparent focus:bg-white focus:border-brand-500 focus:ring-2 focus:ring-brand-200 rounded-full transition-all duration-200 text-sm">
                        <i class="fas fa-search absolute left-4 top-3.5 text-gray-400"></i>
                        <button onclick="handleSearch()" class="absolute right-2 top-1.5 bg-brand-600 text-white px-4 py-1.5 rounded-full text-sm font-medium hover:bg-brand-700 transition-colors">
                            Search
                        </button>
                    </div>
                </div>

                <!-- Right Menu -->
                <div class="flex items-center space-x-4">
                    <button onclick="showPage('chat')" class="hidden md:flex items-center space-x-1 text-gray-600 hover:text-brand-600 transition-colors relative">
                        <i class="fas fa-comment-dots text-xl"></i>
                        <span class="absolute -top-1 -right-1 w-4 h-4 bg-red-500 text-white text-xs rounded-full flex items-center justify-center">3</span>
                    </button>
                    
                    <button onclick="toggleLanguage()" class="hidden md:flex items-center space-x-1 text-gray-600 hover:text-brand-600 font-medium">
                        <i class="fas fa-globe"></i>
                        <span class="text-sm">EN</span>
                    </button>

                    <button onclick="showPage('sell')" class="bg-brand-600 text-white px-6 py-2 rounded-full font-semibold hover:bg-brand-700 transition-all shadow-lg hover:shadow-xl transform hover:-translate-y-0.5 flex items-center space-x-2">
                        <i class="fas fa-plus"></i>
                        <span>Sell</span>
                    </button>

                    <div class="relative group">
                        <button onclick="toggleProfile()" class="flex items-center space-x-2 text-gray-700 hover:text-gray-900">
                            <div class="w-9 h-9 bg-gradient-to-br from-gray-700 to-gray-900 rounded-full flex items-center justify-center text-white">
                                <i class="fas fa-user"></i>
                            </div>
                            <i class="fas fa-chevron-down text-xs hidden md:block"></i>
                        </button>
                        
                        <!-- Profile Dropdown -->
                        <div id="profileDropdown" class="hidden absolute right-0 mt-2 w-64 bg-white rounded-2xl shadow-xl border border-gray-100 py-2 z-50">
                            <div class="px-4 py-3 border-b border-gray-100">
                                <p class="text-sm font-semibold text-gray-900">Welcome to Nikal Do</p>
                                <p class="text-xs text-gray-500 mt-1">Sign in to manage your listings</p>
                            </div>
                            <button onclick="showAuthModal('login')" class="w-full text-left px-4 py-3 text-sm text-gray-700 hover:bg-gray-50 flex items-center space-x-3">
                                <i class="fas fa-sign-in-alt text-brand-600"></i>
                                <span>Login</span>
                            </button>
                            <button onclick="showAuthModal('register')" class="w-full text-left px-4 py-3 text-sm text-gray-700 hover:bg-gray-50 flex items-center space-x-3">
                                <i class="fas fa-user-plus text-brand-600"></i>
                                <span>Register</span>
                            </button>
                            <div class="border-t border-gray-100 mt-2 pt-2">
                                <button onclick="showPage('myads')" class="w-full text-left px-4 py-2 text-sm text-gray-700 hover:bg-gray-50 flex items-center space-x-3">
                                    <i class="fas fa-ad text-gray-400"></i>
                                    <span>My Ads</span>
                                </button>
                                <button onclick="showPage('saved')" class="w-full text-left px-4 py-2 text-sm text-gray-700 hover:bg-gray-50 flex items-center space-x-3">
                                    <i class="fas fa-heart text-gray-400"></i>
                                    <span>Saved Items</span>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Mobile Search -->
        <div class="md:hidden px-4 pb-3">
            <div class="relative">
                <input type="text" placeholder="Search..." class="w-full pl-10 pr-4 py-2 bg-gray-100 rounded-full text-sm">
                <i class="fas fa-search absolute left-3 top-2.5 text-gray-400"></i>
            </div>
        </div>
    </nav>

    <!-- Main Content Container -->
    <main id="mainContent">
        
        <!-- HOME PAGE -->
        <div id="homePage" class="page-section">
            <!-- Hero Section -->
            <div class="relative bg-gradient-to-br from-brand-600 via-brand-700 to-brand-900 text-white overflow-hidden">
                <div class="absolute inset-0 hero-pattern opacity-20"></div>
                <div class="absolute inset-0 bg-gradient-to-t from-black/30 to-transparent"></div>
                
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 md:py-24 relative z-10">
                    <div class="grid md:grid-cols-2 gap-12 items-center">
                        <div class="space-y-6">
                            <div class="inline-flex items-center space-x-2 bg-white/10 backdrop-blur-sm rounded-full px-4 py-1.5 border border-white/20">
                                <span class="flex h-2 w-2 rounded-full bg-green-400 animate-pulse"></span>
                                <span class="text-sm font-medium">20,000+ items sold this week</span>
                            </div>
                            <h1 class="text-4xl md:text-6xl font-bold leading-tight">
                                Sell what you don't need.<br>
                                <span class="text-brand-200">Find what you do.</span>
                            </h1>
                            <p class="text-lg md:text-xl text-brand-100 max-w-lg">
                                India's fastest growing local marketplace. Buy and sell electronics, cars, fashion, home goods and more in your neighborhood.
                            </p>
                            <div class="flex flex-wrap gap-4">
                                <button onclick="showPage('listings')" class="bg-white text-brand-700 px-8 py-3.5 rounded-full font-bold hover:bg-gray-100 transition-all shadow-lg hover:shadow-xl transform hover:-translate-y-1">
                                    Browse Items
                                </button>
                                <button onclick="showPage('sell')" class="bg-brand-500 text-white px-8 py-3.5 rounded-full font-bold hover:bg-brand-400 transition-all shadow-lg border-2 border-brand-400">
                                    Post Free Ad
                                </button>
                            </div>
                            <div class="flex items-center space-x-6 text-sm text-brand-100 pt-4">
                                <div class="flex items-center space-x-2">
                                    <i class="fas fa-shield-alt"></i>
                                    <span>Verified Users</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <i class="fas fa-bolt"></i>
                                    <span>Instant Chat</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <i class="fas fa-map-marker-alt"></i>
                                    <span>Local Pickup</span>
                                </div>
                            </div>
                        </div>
                        
                        <!-- Hero Image Grid -->
                        <div class="hidden md:grid grid-cols-2 gap-4 animate-float">
                            <div class="space-y-4 mt-8">
                                <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-4 border border-white/20">
                                    <img src="https://images.unsplash.com/photo-1592899677977-9c10ca588bbd?w=300&h=300&fit=crop" class="rounded-xl w-full h-48 object-cover mb-3" alt="iPhone">
                                    <p class="font-semibold">iPhone 14 Pro</p>
                                    <p class="text-brand-200 text-sm">₹65,000 • Mumbai</p>
                                </div>
                                <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-4 border border-white/20">
                                    <img src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?w=300&h=300&fit=crop" class="rounded-xl w-full h-40 object-cover mb-3" alt="Car">
                                    <p class="font-semibold">BMW 3 Series</p>
                                    <p class="text-brand-200 text-sm">₹25,00,000 • Delhi</p>
                                </div>
                            </div>
                            <div class="space-y-4">
                                <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-4 border border-white/20">
                                    <img src="https://images.unsplash.com/photo-1555041469-a586c61ea9bc?w=300&h=300&fit=crop" class="rounded-xl w-full h-40 object-cover mb-3" alt="Furniture">
                                    <p class="font-semibold">Designer Sofa</p>
                                    <p class="text-brand-200 text-sm">₹15,000 • Bangalore</p>
                                </div>
                                <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-4 border border-white/20">
                                    <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=300&h=300&fit=crop" class="rounded-xl w-full h-48 object-cover mb-3" alt="Shoes">
                                    <p class="font-semibold">Nike Air Max</p>
                                    <p class="text-brand-200 text-sm">₹4,500 • Pune</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Categories Section -->
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 -mt-8 relative z-20">
                <div class="bg-white rounded-3xl shadow-xl p-6 md:p-8">
                    <div class="flex justify-between items-center mb-6">
                        <h2 class="text-2xl font-bold text-gray-900">Browse Categories</h2>
                        <button onclick="showAllCategories()" class="text-brand-600 font-semibold hover:text-brand-700 text-sm">View All</button>
                    </div>
                    
                    <div class="grid grid-cols-4 md:grid-cols-8 gap-4">
                        <div class="category-card cursor-pointer group" onclick="filterByCategory('cars')">
                            <div class="category-icon w-16 h-16 mx-auto bg-blue-50 rounded-2xl flex items-center justify-center text-blue-600 text-2xl mb-2 transition-transform duration-300">
                                <i class="fas fa-car"></i>
                            </div>
                            <p class="text-center text-sm font-medium text-gray-700 group-hover:text-brand-600">Cars</p>
                        </div>
                        <div class="category-card cursor-pointer group" onclick="filterByCategory('mobiles')">
                            <div class="category-icon w-16 h-16 mx-auto bg-purple-50 rounded-2xl flex items-center justify-center text-purple-600 text-2xl mb-2 transition-transform duration-300">
                                <i class="fas fa-mobile-alt"></i>
                            </div>
                            <p class="text-center text-sm font-medium text-gray-700 group-hover:text-brand-600">Mobiles</p>
                        </div>
                        <div class="category-card cursor-pointer group" onclick="filterByCategory('electronics')">
                            <div class="category-icon w-16 h-16 mx-auto bg-green-50 rounded-2xl flex items-center justify-center text-green-600 text-2xl mb-2 transition-transform duration-300">
                                <i class="fas fa-laptop"></i>
                            </div>
                            <p class="text-center text-sm font-medium text-gray-700 group-hover:text-brand-600">Electronics</p>
                        </div>
                        <div class="category-card cursor-pointer group" onclick="filterByCategory('furniture')">
                            <div class="category-icon w-16 h-16 mx-auto bg-orange-50 rounded-2xl flex items-center justify-center text-orange-600 text-2xl mb-2 transition-transform duration-300">
                                <i class="fas fa-couch"></i>
                            </div>
                            <p class="text-center text-sm font-medium text-gray-700 group-hover:text-brand-600">Furniture</p>
                        </div>
                        <div class="category-card cursor-pointer group" onclick="filterByCategory('fashion')">
                            <div class="category-icon w-16 h-16 mx-auto bg-pink-50 rounded-2xl flex items-center justify-center text-pink-600 text-2xl mb-2 transition-transform duration-300">
                                <i class="fas fa-tshirt"></i>
                            </div>
                            <p class="text-center text-sm font-medium text-gray-700 group-hover:text-brand-600">Fashion</p>
                        </div>
                        <div class="category-card cursor-pointer group" onclick="filterByCategory('sports')">
                            <div class="category-icon w-16 h-16 mx-auto bg-red-50 rounded-2xl flex items-center justify-center text-red-600 text-2xl mb-2 transition-transform duration-300">
                                <i class="fas fa-bicycle"></i>
                            </div>
                            <p class="text-center text-sm font-medium text-gray-700 group-hover:text-brand-600">Sports</p>
                        </div>
                        <div class="category-card cursor-pointer group" onclick="filterByCategory('books')">
                            <div class="category-icon w-16 h-16 mx-auto bg-yellow-50 rounded-2xl flex items-center justify-center text-yellow-600 text-2xl mb-2 transition-transform duration-300">
                                <i class="fas fa-book"></i>
                            </div>
                            <p class="text-center text-sm font-medium text-gray-700 group-hover:text-brand-600">Books</p>
                        </div>
                        <div class="category-card cursor-pointer group" onclick="filterByCategory('pets')">
                            <div class="category-icon w-16 h-16 mx-auto bg-teal-50 rounded-2xl flex items-center justify-center text-teal-600 text-2xl mb-2 transition-transform duration-300">
                                <i class="fas fa-paw"></i>
                            </div>
                            <p class="text-center text-sm font-medium text-gray-700 group-hover:text-brand-600">Pets</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Fresh Recommendations -->
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
                <div class="flex justify-between items-end mb-6">
                    <div>
                        <h2 class="text-2xl md:text-3xl font-bold text-gray-900">Fresh Recommendations</h2>
                        <p class="text-gray-500 mt-1">Based on your location • Mumbai</p>
                    </div>
                    <div class="flex space-x-2">
                        <button onclick="scrollListings('left')" class="w-10 h-10 rounded-full border border-gray-300 flex items-center justify-center hover:bg-gray-50 transition-colors">
                            <i class="fas fa-chevron-left text-gray-600"></i>
                        </button>
                        <button onclick="scrollListings('right')" class="w-10 h-10 rounded-full border border-gray-300 flex items-center justify-center hover:bg-gray-50 transition-colors">
                            <i class="fas fa-chevron-right text-gray-600"></i>
                        </button>
                    </div>
                </div>

                <div id="listingsContainer" class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-6">
                    <!-- Listings injected by JS -->
                </div>

                <div class="mt-8 text-center">
                    <button onclick="loadMoreListings()" class="bg-white border-2 border-gray-300 text-gray-700 px-8 py-3 rounded-full font-semibold hover:border-brand-500 hover:text-brand-600 transition-all">
                        Load More
                    </button>
                </div>
            </div>

            <!-- How It Works -->
            <div class="bg-gray-100 py-16">
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                    <div class="text-center mb-12">
                        <h2 class="text-3xl font-bold text-gray-900">How Nikal Do Works</h2>
                        <p class="text-gray-600 mt-2">Sell your items in 3 simple steps</p>
                    </div>
                    
                    <div class="grid md:grid-cols-3 gap-8">
                        <div class="bg-white rounded-2xl p-8 text-center shadow-sm hover:shadow-md transition-shadow">
                            <div class="w-20 h-20 bg-brand-100 rounded-full flex items-center justify-center text-brand-600 text-3xl mx-auto mb-4">
                                <i class="fas fa-camera"></i>
                            </div>
                            <h3 class="text-xl font-bold text-gray-900 mb-2">1. Take Photos</h3>
                            <p class="text-gray-600">Snap clear photos of your item from multiple angles. Good photos sell faster!</p>
                        </div>
                        <div class="bg-white rounded-2xl p-8 text-center shadow-sm hover:shadow-md transition-shadow">
                            <div class="w-20 h-20 bg-brand-100 rounded-full flex items-center justify-center text-brand-600 text-3xl mx-auto mb-4">
                                <i class="fas fa-edit"></i>
                            </div>
                            <h3 class="text-xl font-bold text-gray-900 mb-2">2. Post for Free</h3>
                            <p class="text-gray-600">Create your listing in under 2 minutes. Set your price and add details.</p>
                        </div>
                        <div class="bg-white rounded-2xl p-8 text-center shadow-sm hover:shadow-md transition-shadow">
                            <div class="w-20 h-20 bg-brand-100 rounded-full flex items-center justify-center text-brand-600 text-3xl mx-auto mb-4">
                                <i class="fas fa-handshake"></i>
                            </div>
                            <h3 class="text-xl font-bold text-gray-900 mb-2">3. Deal Locally</h3>
                            <p class="text-gray-600">Chat with buyers, negotiate and meet locally to complete the sale.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- LISTINGS PAGE -->
        <div id="listingsPage" class="page-section hidden">
            <div class="bg-white border-b border-gray-200">
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
                    <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
                        <h1 class="text-2xl font-bold text-gray-900">All Listings</h1>
                        
                        <!-- Filters -->
                        <div class="flex flex-wrap gap-2">
                            <select id="categoryFilter" onchange="applyFilters()" class="px-4 py-2 border border-gray-300 rounded-lg text-sm focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                                <option value="">All Categories</option>
                                <option value="cars">Cars</option>
                                <option value="mobiles">Mobiles</option>
                                <option value="electronics">Electronics</option>
                                <option value="furniture">Furniture</option>
                                <option value="fashion">Fashion</option>
                            </select>
                            
                            <select id="priceFilter" onchange="applyFilters()" class="px-4 py-2 border border-gray-300 rounded-lg text-sm focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                                <option value="">Price Range</option>
                                <option value="0-1000">Under ₹1,000</option>
                                <option value="1000-5000">₹1,000 - ₹5,000</option>
                                <option value="5000-20000">₹5,000 - ₹20,000</option>
                                <option value="20000-100000">₹20,000 - ₹1,00,000</option>
                                <option value="100000+">Above ₹1,00,000</option>
                            </select>
                            
                            <select id="locationFilter" onchange="applyFilters()" class="px-4 py-2 border border-gray-300 rounded-lg text-sm focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                                <option value="">All Locations</option>
                                <option value="mumbai">Mumbai</option>
                                <option value="delhi">Delhi</option>
                                <option value="bangalore">Bangalore</option>
                                <option value="pune">Pune</option>
                                <option value="hyderabad">Hyderabad</option>
                            </select>
                            
                            <select id="sortFilter" onchange="applyFilters()" class="px-4 py-2 border border-gray-300 rounded-lg text-sm focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                                <option value="newest">Newest First</option>
                                <option value="price-low">Price: Low to High</option>
                                <option value="price-high">Price: High to Low</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6">
                <div id="filteredListings" class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-6">
                    <!-- Filtered listings injected here -->
                </div>
            </div>
        </div>

        <!-- PRODUCT DETAIL PAGE -->
        <div id="productPage" class="page-section hidden bg-gray-50 min-h-screen pb-12">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6">
                <button onclick="showPage('home')" class="mb-4 flex items-center text-gray-600 hover:text-gray-900">
                    <i class="fas fa-arrow-left mr-2"></i> Back to listings
                </button>
                
                <div class="grid md:grid-cols-3 gap-6">
                    <!-- Image Gallery -->
                    <div class="md:col-span-2 space-y-4">
                        <div class="bg-white rounded-2xl overflow-hidden shadow-sm">
                            <img id="productMainImage" src="" alt="Product" class="w-full h-96 object-cover">
                        </div>
                        <div class="flex space-x-2 overflow-x-auto scroll-hidden" id="productThumbnails">
                            <!-- Thumbnails injected here -->
                        </div>
                    </div>
                    
                    <!-- Product Info -->
                    <div class="space-y-4">
                        <div class="bg-white rounded-2xl p-6 shadow-sm">
                            <div class="flex justify-between items-start mb-2">
                                <h1 id="productTitle" class="text-2xl font-bold text-gray-900"></h1>
                                <button onclick="toggleSaveItem()" class="text-gray-400 hover:text-red-500 transition-colors">
                                    <i class="far fa-heart text-2xl" id="saveIcon"></i>
                                </button>
                            </div>
                            <p id="productPrice" class="text-3xl font-bold text-brand-600 mb-4"></p>
                            
                            <div class="flex items-center text-sm text-gray-500 mb-6 space-x-4">
                                <span class="flex items-center"><i class="fas fa-map-marker-alt mr-1"></i> <span id="productLocation"></span></span>
                                <span class="flex items-center"><i class="far fa-clock mr-1"></i> <span id="productTime"></span></span>
                            </div>
                            
                            <div class="space-y-3">
                                <button onclick="showChatModal()" class="w-full bg-brand-600 text-white py-3 rounded-xl font-semibold hover:bg-brand-700 transition-colors flex items-center justify-center space-x-2">
                                    <i class="fas fa-comment-dots"></i>
                                    <span>Chat with Seller</span>
                                </button>
                                <button onclick="makeOffer()" class="w-full bg-white border-2 border-brand-600 text-brand-600 py-3 rounded-xl font-semibold hover:bg-brand-50 transition-colors">
                                    Make Offer
                                </button>
                            </div>
                            
                            <div class="mt-6 pt-6 border-t border-gray-100">
                                <div class="flex items-center space-x-3">
                                    <div class="w-12 h-12 bg-gray-200 rounded-full flex items-center justify-center text-gray-600">
                                        <i class="fas fa-user text-xl"></i>
                                    </div>
                                    <div>
                                        <p class="font-semibold text-gray-900">Verified Seller</p>
                                        <p class="text-sm text-gray-500">Member since 2023 • 12 ads</p>
                                    </div>
                                    <button class="ml-auto text-brand-600 text-sm font-semibold">View Profile</button>
                                </div>
                            </div>
                        </div>
                        
                        <div class="bg-white rounded-2xl p-6 shadow-sm">
                            <h3 class="font-bold text-gray-900 mb-3">Details</h3>
                            <div class="space-y-2 text-sm" id="productDetails">
                                <!-- Details injected here -->
                            </div>
                        </div>
                        
                        <div class="bg-white rounded-2xl p-6 shadow-sm">
                            <h3 class="font-bold text-gray-900 mb-3">Description</h3>
                            <p id="productDescription" class="text-gray-600 text-sm leading-relaxed"></p>
                        </div>
                        
                        <div class="bg-yellow-50 border border-yellow-200 rounded-2xl p-4 flex items-start space-x-3">
                            <i class="fas fa-shield-alt text-yellow-600 mt-1"></i>
                            <div>
                                <p class="text-sm font-semibold text-yellow-800">Safety Tips</p>
                                <p class="text-xs text-yellow-700 mt-1">• Meet in public places<br>• Check item before paying<br>• Never pay in advance</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- SELL PAGE -->
        <div id="sellPage" class="page-section hidden bg-gray-50 min-h-screen py-8">
            <div class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="bg-white rounded-3xl shadow-lg p-6 md:p-10">
                    <div class="text-center mb-8">
                        <h1 class="text-3xl font-bold text-gray-900">Post Your Ad</h1>
                        <p class="text-gray-500 mt-2">Reach thousands of buyers in your area</p>
                    </div>
                    
                    <form id="sellForm" onsubmit="handlePostAd(event)" class="space-y-6">
                        <div>
                            <label class="block text-sm font-semibold text-gray-700 mb-2">Ad Title *</label>
                            <input type="text" required placeholder="What are you selling?" class="w-full px-4 py-3 rounded-xl border border-gray-300 focus:border-brand-500 focus:ring-2 focus:ring-brand-200 transition-all">
                        </div>
                        
                        <div class="grid md:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-sm font-semibold text-gray-700 mb-2">Category *</label>
                                <select required class="w-full px-4 py-3 rounded-xl border border-gray-300 focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                                    <option value="">Select Category</option>
                                    <option>Cars</option>
                                    <option>Mobiles</option>
                                    <option>Electronics</option>
                                    <option>Furniture</option>
                                    <option>Fashion</option>
                                    <option>Sports</option>
                                    <option>Books</option>
                                    <option>Pets</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-sm font-semibold text-gray-700 mb-2">Price (₹) *</label>
                                <input type="number" required placeholder="Enter price" class="w-full px-4 py-3 rounded-xl border border-gray-300 focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                            </div>
                        </div>
                        
                        <div>
                            <label class="block text-sm font-semibold text-gray-700 mb-2">Description *</label>
                            <textarea required rows="4" placeholder="Describe your item in detail..." class="w-full px-4 py-3 rounded-xl border border-gray-300 focus:border-brand-500 focus:ring-2 focus:ring-brand-200"></textarea>
                            <p class="text-xs text-gray-500 mt-1">Include condition, features, and reason for selling</p>
                        </div>
                        
                        <div>
                            <label class="block text-sm font-semibold text-gray-700 mb-2">Photos</label>
                            <div class="border-2 border-dashed border-gray-300 rounded-xl p-8 text-center hover:border-brand-500 transition-colors cursor-pointer" onclick="document.getElementById('photoInput').click()">
                                <i class="fas fa-cloud-upload-alt text-4xl text-gray-400 mb-3"></i>
                                <p class="text-gray-600 font-medium">Click to upload photos</p>
                                <p class="text-sm text-gray-400 mt-1">or drag and drop</p>
                                <input type="file" id="photoInput" multiple accept="image/*" class="hidden" onchange="handlePhotoUpload(this)">
                            </div>
                            <div id="photoPreview" class="flex gap-2 mt-4 flex-wrap"></div>
                        </div>
                        
                        <div class="grid md:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-sm font-semibold text-gray-700 mb-2">Location *</label>
                                <input type="text" required placeholder="City, Area" class="w-full px-4 py-3 rounded-xl border border-gray-300 focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                            </div>
                            <div>
                                <label class="block text-sm font-semibold text-gray-700 mb-2">Your Name *</label>
                                <input type="text" required placeholder="Full name" class="w-full px-4 py-3 rounded-xl border border-gray-300 focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                            </div>
                        </div>
                        
                        <div>
                            <label class="block text-sm font-semibold text-gray-700 mb-2">Phone Number *</label>
                            <input type="tel" required placeholder="10-digit mobile number" class="w-full px-4 py-3 rounded-xl border border-gray-300 focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                        </div>
                        
                        <div class="pt-4">
                            <button type="submit" class="w-full bg-brand-600 text-white py-4 rounded-xl font-bold text-lg hover:bg-brand-700 transition-all shadow-lg hover:shadow-xl transform hover:-translate-y-0.5">
                                Post Ad Now
                            </button>
                            <p class="text-center text-sm text-gray-500 mt-4">By posting, you agree to our Terms of Use and Privacy Policy</p>
                        </div>
                    </form>
                </div>
            </div>
        </div>

        <!-- CHAT PAGE -->
        <div id="chatPage" class="page-section hidden bg-gray-50 min-h-screen">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-6 h-[calc(100vh-80px)]">
                <div class="bg-white rounded-2xl shadow-lg h-full overflow-hidden flex">
                    <!-- Chat List -->
                    <div class="w-full md:w-1/3 border-r border-gray-200 flex flex-col">
                        <div class="p-4 border-b border-gray-200">
                            <h2 class="text-xl font-bold text-gray-900">Messages</h2>
                        </div>
                        <div class="flex-1 overflow-y-auto" id="chatList">
                            <!-- Chat list items injected here -->
                        </div>
                    </div>
                    
                    <!-- Chat Window -->
                    <div class="hidden md:flex md:w-2/3 flex-col" id="chatWindow">
                        <div class="p-4 border-b border-gray-200 flex items-center justify-between bg-gray-50">
                            <div class="flex items-center space-x-3">
                                <div class="w-10 h-10 bg-brand-100 rounded-full flex items-center justify-center text-brand-600">
                                    <i class="fas fa-user"></i>
                                </div>
                                <div>
                                    <p class="font-semibold text-gray-900">Rahul Sharma</p>
                                    <p class="text-xs text-green-600">Online</p>
                                </div>
                            </div>
                            <div class="flex items-center space-x-2">
                                <button class="p-2 text-gray-500 hover:text-gray-700"><i class="fas fa-phone"></i></button>
                                <button class="p-2 text-gray-500 hover:text-gray-700"><i class="fas fa-ellipsis-v"></i></button>
                            </div>
                        </div>
                        
                        <div class="flex-1 overflow-y-auto p-4 space-y-4 bg-gray-50" id="messageContainer">
                            <!-- Messages injected here -->
                        </div>
                        
                        <div class="p-4 border-t border-gray-200 bg-white">
                            <form onsubmit="sendMessage(event)" class="flex space-x-2">
                                <input type="text" id="messageInput" placeholder="Type a message..." class="flex-1 px-4 py-2 border border-gray-300 rounded-full focus:border-brand-500 focus:ring-2 focus:ring-brand-200">
                                <button type="submit" class="w-10 h-10 bg-brand-600 text-white rounded-full flex items-center justify-center hover:bg-brand-700 transition-colors">
                                    <i class="fas fa-paper-plane"></i>
                                </button>
                            </form>
                        </div>
                    </div>
                    
                    <!-- Empty State -->
                    <div class="hidden md:flex md:w-2/3 items-center justify-center bg-gray-50" id="emptyChat">
                        <div class="text-center">
                            <div class="w-20 h-20 bg-gray-200 rounded-full flex items-center justify-center text-gray-400 text-3xl mx-auto mb-4">
                                <i class="fas fa-comment-dots"></i>
                            </div>
                            <p class="text-gray-500">Select a conversation to start chatting</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </main>

    <!-- Auth Modal -->
    <div id="authModal" class="hidden fixed inset-0 bg-black/50 backdrop-blur-sm z-50 flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-md w-full p-8 relative animate-float">
            <button onclick="closeAuthModal()" class="absolute top-4 right-4 text-gray-400 hover:text-gray-600">
                <i class="fas fa-times text-xl"></i>
            </button>
            
            <div class="text-center mb-6">
                <div class="w-16 h-16 bg-brand-100 rounded-2xl flex items-center justify-center text-brand-600 text-2xl mx-auto mb-4">
                    <i class="fas fa-hand-holding-usd"></i>
                </div>
                <h2 id="authTitle" class="text-2xl font-bold text-gray-900">Welcome Back</h2>
                <p class="text-gray-500 text-sm mt-1">Sign in to continue to Nikal Do</p>
            </div>
            
            <form id="authForm" class="space-y-4">
                <div id="nameField" class="hidden">
                    <input type="text" placeholder="Full Name" class
