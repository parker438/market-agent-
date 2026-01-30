<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="AI Marketing Automation Platform - Deploy autonomous agents to manage your social media presence 24/7">
    <meta property="og:title" content="AgentX - AI Marketing Agent Platform">
    <meta property="og:description" content="Autonomous AI agents for social media management">
    <meta property="og:type" content="website">
    <title>AgentX - AI Marketing Automation Platform</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://cdnjs.cloudflare.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        *,*::before,*::after{box-sizing:border-box}
        html,body{margin:0;padding:0}
        body{font-family:'Inter',sans-serif;background:#020617;color:#e2e8f0;overflow-x:hidden;line-height:1.6}
        .font-display{font-family:'Space Grotesk',sans-serif}
        .glass{background:rgba(15,23,42,0.6);backdrop-filter:blur(12px);border:1px solid rgba(99,102,241,0.2)}
        .glass-strong{background:rgba(15,23,42,0.8);backdrop-filter:blur(20px);border:1px solid rgba(99,102,241,0.3)}
        .gradient-text{background:linear-gradient(135deg,#6366f1 0%,#ec4899 50%,#06b6d4 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
        .grid-pattern{background-image:radial-gradient(rgba(99,102,241,0.1) 1px,transparent 1px);background-size:30px 30px}
        @keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-20px)}}
        @keyframes orbit{from{transform:rotate(0deg) translateX(100px) rotate(0deg)}to{transform:rotate(360deg) translateX(100px) rotate(-360deg)}}
        @keyframes pulse-ring{0%{transform:scale(0.8);box-shadow:0 0 0 0 rgba(34,197,94,0.7)}70%{transform:scale(1);box-shadow:0 0 0 10px rgba(34,197,94,0)}100%{transform:scale(0.8);box-shadow:0 0 0 0 rgba(34,197,94,0)}}
        @keyframes marquee{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
        .animate-float{animation:float 6s ease-in-out infinite}
        .animate-orbit{animation:orbit 20s linear infinite}
        .status-dot{animation:pulse-ring 2s cubic-bezier(0.215,0.61,0.355,1) infinite}
        .animate-marquee{animation:marquee 30s linear infinite}
        .typing-cursor::after{content:'|';animation:blink 1s infinite}
        @keyframes blink{0%,50%{opacity:1}51%,100%{opacity:0}}
        #canvas-container{position:fixed;top:0;left:0;width:100%;height:100%;z-index:-1;pointer-events:none}
        .platform-card{transition:all 0.3s ease}
        .platform-card:hover{transform:translateY(-5px);box-shadow:0 20px 40px -10px rgba(99,102,241,0.3)}
        .scrollbar-hide::-webkit-scrollbar{display:none}
        .scrollbar-hide{-ms-overflow-style:none;scrollbar-width:none}
        .sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border-width:0}
    </style>
</head>
<body>
    <div id="canvas-container" aria-hidden="true"></div>
    
    <a href="#main-content" class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 focus:z-50 focus:bg-primary focus:text-white focus:px-4 focus:py-2 focus:rounded-lg">Skip to main content</a>

    <nav class="fixed w-full z-50 glass-strong border-b border-white/10" role="navigation" aria-label="Main navigation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center space-x-2">
                    <div class="w-8 h-8 bg-gradient-to-br from-indigo-500 to-pink-500 rounded-lg flex items-center justify-center" aria-hidden="true">
                        <i class="fas fa-robot text-white text-sm"></i>
                    </div>
                    <span class="font-display font-bold text-xl tracking-tight">Agent<span class="text-indigo-400">X</span></span>
                </div>
                
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#features" class="text-sm font-medium text-gray-300 hover:text-white transition-colors">Features</a>
                    <a href="#platforms" class="text-sm font-medium text-gray-300 hover:text-white transition-colors">Platforms</a>
                    <a href="#dashboard" class="text-sm font-medium text-gray-300 hover:text-white transition-colors">Dashboard</a>
                    <a href="#pricing" class="text-sm font-medium text-gray-300 hover:text-white transition-colors">Pricing</a>
                </div>
                
                <div class="flex items-center space-x-4">
                    <button class="hidden md:block text-sm font-medium text-gray-300 hover:text-white" onclick="alert('Sign in coming soon')">Sign In</button>
                    <button class="bg-indigo-500 hover:bg-indigo-600 text-white px-5 py-2 rounded-full text-sm font-medium transition-all hover:scale-105 hover:shadow-lg hover:shadow-indigo-500/25" onclick="alert('Welcome! Deployment starts here.')">
                        Get Started
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <main id="main-content">
        <section class="relative min-h-screen flex items-center justify-center pt-16 overflow-hidden" aria-label="Hero">
            <div class="absolute inset-0 grid-pattern opacity-30" aria-hidden="true"></div>
            
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="grid lg:grid-cols-2 gap-12 items-center">
                    <div class="space-y-8">
                        <div class="inline-flex items-center space-x-2 px-4 py-2 rounded-full glass border border-indigo-500/30">
                            <span class="w-2 h-2 bg-green-400 rounded-full status-dot" aria-hidden="true"></span>
                            <span class="text-xs font-medium text-indigo-400">AI Agent v2.0 Now Live</span>
                        </div>
                        
                        <h1 class="font-display text-5xl md:text-7xl font-bold leading-tight">
                            Your <span class="gradient-text">AI Marketing</span> Agent That Never Sleeps
                        </h1>
                        
                        <p class="text-lg text-gray-400 max-w-lg leading-relaxed">
                            Deploy autonomous AI agents to create, schedule, and optimize content across all social platforms. Connect once, automate forever.
                        </p>
                        
                        <div class="flex flex-col sm:flex-row gap-4">
                            <button class="group bg-gradient-to-r from-indigo-500 to-pink-500 px-8 py-4 rounded-full font-semibold text-white flex items-center justify-center space-x-2 hover:shadow-2xl hover:shadow-indigo-500/25 transition-all hover:scale-105" onclick="document.getElementById('dashboard').scrollIntoView({behavior:'smooth'})">
                                <span>Deploy Your Agent</span>
                                <i class="fas fa-arrow-right group-hover:translate-x-1 transition-transform" aria-hidden="true"></i>
                            </button>
                            <button class="px-8 py-4 rounded-full font-semibold text-white border border-white/20 hover:bg-white/5 transition-all flex items-center justify-center space-x-2" onclick="alert('Demo video modal would open here')">
                                <i class="fas fa-play text-xs" aria-hidden="true"></i>
                                <span>Watch Demo</span>
                            </button>
                        </div>
                        
                        <div class="flex items-center space-x-6 text-sm text-gray-500">
                            <div class="flex -space-x-2" aria-hidden="true">
                                <div class="w-8 h-8 rounded-full bg-gray-700 border-2 border-slate-950 flex items-center justify-center text-xs">JD</div>
                                <div class="w-8 h-8 rounded-full bg-gray-600 border-2 border-slate-950 flex items-center justify-center text-xs">MK</div>
                                <div class="w-8 h-8 rounded-full bg-gray-500 border-2 border-slate-950 flex items-center justify-center text-xs">+2k</div>
                            </div>
                            <span>Trusted by 2,000+ marketers</span>
                        </div>
                    </div>
                    
                    <div class="relative" aria-hidden="true">
                        <div class="relative w-full aspect-square max-w-md mx-auto">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-64 h-64 border border-indigo-500/20 rounded-full animate-spin" style="animation-duration:30s"></div>
                                <div class="absolute w-48 h-48 border border-pink-500/20 rounded-full animate-spin" style="animation-duration:20s;animation-direction:reverse"></div>
                                <div class="absolute w-32 h-32 border border-cyan-500/20 rounded-full animate-spin" style="animation-duration:15s"></div>
                            </div>
                            
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-32 h-32 bg-gradient-to-br from-indigo-500/20 to-pink-500/20 rounded-2xl backdrop-blur-xl border border-white/10 flex items-center justify-center animate-float shadow-2xl shadow-indigo-500/20">
                                    <i class="fas fa-brain text-4xl gradient-text"></i>
                                </div>
                            </div>
                            
                            <div class="absolute top-0 left-1/2 -translate-x-1/2 animate-orbit" style="animation-delay:0s">
                                <div class="w-12 h-12 bg-[#1DA1F2]/20 backdrop-blur-md rounded-xl flex items-center justify-center border border-[#1DA1F2]/30">
                                    <i class="fab fa-twitter text-[#1DA1F2]"></i>
                                </div>
                            </div>
                            <div class="absolute top-1/2 right-0 translate-x-1/2 animate-orbit" style="animation-delay:-5s">
                                <div class="w-12 h-12 bg-[#E1306C]/20 backdrop-blur-md rounded-xl flex items-center justify-center border border-[#E1306C]/30">
                                    <i class="fab fa-instagram text-[#E1306C]"></i>
                                </div>
                            </div>
                            <div class="absolute bottom-0 left-1/2 -translate-x-1/2 animate-orbit" style="animation-delay:-10s">
                                <div class="w-12 h-12 bg-[#0A66C2]/20 backdrop-blur-md rounded-xl flex items-center justify-center border border-[#0A66C2]/30">
                                    <i class="fab fa-linkedin text-[#0A66C2]"></i>
                                </div>
                            </div>
                            <div class="absolute top-1/2 left-0 -translate-x-1/2 animate-orbit" style="animation-delay:-15s">
                                <div class="w-12 h-12 bg-[#FF0000]/20 backdrop-blur-md rounded-xl flex items-center justify-center border border-[#FF0000]/30">
                                    <i class="fab fa-youtube text-[#FF0000]"></i>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <div class="border-y border-white/5 bg-black/20 backdrop-blur-sm overflow-hidden" aria-label="Live activity ticker">
            <div class="flex animate-marquee whitespace-nowrap py-4">
                <div class="flex items-center space-x-8 mx-4 text-sm">
                    <span class="flex items-center space-x-2 text-green-400"><i class="fas fa-check-circle" aria-hidden="true"></i><span>Agent posted on Twitter for @techcorp</span></span>
                    <span class="flex items-center space-x-2 text-blue-400"><i class="fas fa-sync fa-spin" aria-hidden="true"></i><span>Analyzing engagement metrics...</span></span>
                    <span class="flex items-center space-x-2 text-purple-400"><i class="fas fa-robot" aria-hidden="true"></i><span>AI generating Instagram carousel for @fashionbrand</span></span>
                    <span class="flex items-center space-x-2 text-pink-400"><i class="fas fa-heart" aria-hidden="true"></i><span>Auto-replied to 47 comments on LinkedIn</span></span>
                    <span class="flex items-center space-x-2 text-yellow-400"><i class="fas fa-chart-line" aria-hidden="true"></i><span>Campaign ROI increased by 34%</span></span>
                </div>
                <div class="flex items-center space-x-8 mx-4 text-sm" aria-hidden="true">
                    <span class="flex items-center space-x-2 text-green-400"><i class="fas fa-check-circle"></i><span>Agent posted on Twitter for @techcorp</span></span>
                    <span class="flex items-center space-x-2 text-blue-400"><i class="fas fa-sync fa-spin"></i><span>Analyzing engagement metrics...</span></span>
                    <span class="flex items-center space-x-2 text-purple-400"><i class="fas fa-robot"></i><span>AI generating Instagram carousel for @fashionbrand</span></span>
                    <span class="flex items-center space-x-2 text-pink-400"><i class="fas fa-heart"></i><span>Auto-replied to 47 comments on LinkedIn</span></span>
                </div>
            </div>
        </div>

        <section id="platforms" class="py-24 relative" aria-labelledby="platforms-heading">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 id="platforms-heading" class="font-display text-4xl font-bold mb-4">Connect <span class="gradient-text">Everything</span></h2>
                    <p class="text-gray-400 max-w-2xl mx-auto">One AI agent to manage them all. Native integrations with every major platform.</p>
                </div>
                
                <div class="grid grid-cols-2 md:grid-cols-4 gap-6" role="list">
                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#1DA1F2]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-twitter text-2xl text-[#1DA1F2]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle Twitter connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">Twitter/X</h3>
                        <p class="text-xs text-gray-500">Auto-post threads & replies</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#E1306C]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-instagram text-2xl text-[#E1306C]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle Instagram connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">Instagram</h3>
                        <p class="text-xs text-gray-500">Stories, Reels & Posts</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#0A66C2]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-linkedin text-2xl text-[#0A66C2]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle LinkedIn connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">LinkedIn</h3>
                        <p class="text-xs text-gray-500">Professional network posts</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#FF0000]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-youtube text-2xl text-[#FF0000]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle YouTube connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">YouTube</h3>
                        <p class="text-xs text-gray-500">Video & Shorts automation</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#5865F2]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-discord text-2xl text-[#5865F2]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle Discord connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">Discord</h3>
                        <p class="text-xs text-gray-500">Community management</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#25D366]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-whatsapp text-2xl text-[#25D366]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle WhatsApp connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">WhatsApp</h3>
                        <p class="text-xs text-gray-500">Business API integration</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-black border border-white/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-tiktok text-2xl text-white"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle TikTok connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">TikTok</h3>
                        <p class="text-xs text-gray-500">Viral content automation</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#FF4500]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-reddit text-2xl text-[#FF4500]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle Reddit connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">Reddit</h3>
                        <p class="text-xs text-gray-500">Subreddit monitoring</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>
                </div>
            </div>
        </section>

        <section id="dashboard" class="py-24 relative overflow-hidden" aria-labelledby="dashboard-heading">
            <div class="absolute inset-0 bg-gradient-to-b from-indigo-500/5 to-transparent" aria-hidden="true"></div>
            
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="text-center mb-12">
                    <h2 id="dashboard-heading" class="font-display text-4xl font-bold mb-4">Command <span class="gradient-text">Center</span></h2>
                    <p class="text-gray-400">Real-time control over your AI marketing workforce</p>
                </div>

                <div class="glass-strong rounded-3xl border border-white/10 overflow-hidden shadow-2xl shadow-indigo-500/10">
                    <div class="border-b border-white/10 px-6 py-4 flex items-center justify-between bg-white/5">
                        <div class="flex items-center space-x-4">
                            <div class="flex space-x-2" aria-hidden="true">
                                <div class="w-3 h-3 rounded-full bg-red-500"></div>
                                <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
                                <div class="w-3 h-3 rounded-full bg-green-500"></div>
                            </div>
                            <span class="text-sm font-medium text-gray-400">AgentX Dashboard</span>
                        </div>
                        <div class="flex items-center space-x-4">
                            <button class="text-xs bg-indigo-500/20 text-indigo-400 px-3 py-1 rounded-full border border-indigo-500/30">
                                <i class="fas fa-circle text-[8px] mr-1 animate-pulse" aria-hidden="true"></i>
                                Live
                            </button>
                            <i class="fas fa-bell text-gray-400 hover:text-white cursor-pointer" aria-hidden="true"></i>
                            <div class="w-8 h-8 rounded-full bg-gradient-to-br from-indigo-500 to-pink-500" aria-hidden="true"></div>
                        </div>
                    </div>

                    <div class="grid lg:grid-cols-4 min-h-[600px]">
                        <nav class="hidden lg:block border-r border-white/10 p-6 space-y-6 bg-black/20" aria-label="Dashboard navigation">
                            <div class="space-y-2">
                                <button class="w-full text-left px-4 py-3 rounded-xl bg-indigo-500/20 text-indigo-400 border border-indigo-500/30 flex items-center space-x-3" aria-current="page">
                                    <i class="fas fa-home" aria-hidden="true"></i>
                                    <span>Overview</span>
                                </button>
                                <button class="w-full text-left px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 flex items-center space-x-3 transition-colors">
                                    <i class="fas fa-robot" aria-hidden="true"></i>
                                    <span>AI Agents</span>
                                </button>
                                <button class="w-full text-left px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 flex items-center space-x-3 transition-colors">
                                    <i class="fas fa-calendar" aria-hidden="true"></i>
                                    <span>Schedule</span>
                                </button>
                                <button class="w-full text-left px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 flex items-center space-x-3 transition-colors">
                                    <i class="fas fa-chart-bar" aria-hidden="true"></i>
                                    <span>Analytics</span>
                                </button>
                            </div>

                            <div class="pt-6 border-t border-white/10">
                                <h4 class="text-xs font-semibold text-gray-500 uppercase tracking-wider mb-4">Active Agents</h4>
                                <div class="space-y-3">
                                    <div class="flex items-center space-x-3 p-2 rounded-lg bg-white/5">
                                        <div class="w-2 h-2 bg-green-400 rounded-full animate-pulse" aria-hidden="true"></div>
                                        <div class="flex-1">
                                            <div class="text-sm font-medium">Content Creator</div>
                                            <div class="text-xs text-gray-500">Posting to Instagram...</div>
                                        </div>
                                    </div>
                                    <div class="flex items-center space-x-3 p-2 rounded-lg bg-white/5">
                                        <div class="w-2 h-2 bg-blue-400 rounded-full animate-pulse" aria-hidden="true"></div>
                                        <div class="flex-1">
                                            <div class="text-sm font-medium">Engagement Bot</div>
                                            <div class="text-xs text-gray-500">Replying to comments</div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </nav>

                        <div class="lg:col-span-3 p-6 space-y-6">
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                <div class="glass rounded-2xl p-6 border border-white/5">
                                    <div class="flex items-center justify-between mb-2">
                                        <span class="text-gray-400 text-sm">Total Reach</span>
                                        <span class="text-green-400 text-xs">+24.5%</span>
                                    </div>
                                    <div class="text-3xl font-bold font-display">2.4M</div>
                                    <div class="mt-2 h-1 bg-gray-700 rounded-full overflow-hidden" aria-hidden="true">
                                        <div class="h-full bg-indigo-500 w-3/4 rounded-full"></div>
                                    </div>
                                </div>
                                <div class="glass rounded-2xl p-6 border border-white/5">
                                    <div class="flex items-center justify-between mb-2">
                                        <span class="text-gray-400 text-sm">Engagement</span>
                                        <span class="text-green-400 text-xs">+12.3%</span>
                                    </div>
                                    <div class="text-3xl font-bold font-display">89.2K</div>
                                    <div class="mt-2 h-1 bg-gray-700 rounded-full overflow-hidden" aria-hidden="true">
                                        <div class="h-full bg-pink-500 w-1/2 rounded-full"></div>
                                    </div>
                                </div>
                                <div class="glass rounded-2xl p-6 border border-white/5">
                                    <div class="flex items-center justify-between mb-2">
                                        <span class="text-gray-400 text-sm">Posts Scheduled</span>
                                        <span class="text-blue-400 text-xs">This week</span>
                                    </div>
                                    <div class="text-3xl font-bold font-display">47</div>
                                    <div class="mt-2 h-1 bg-gray-700 rounded-full overflow-hidden" aria-hidden="true">
                                        <div class="h-full bg-cyan-500 w-2/3 rounded-full"></div>
                                    </div>
                                </div>
                            </div>

                            <div class="glass rounded-2xl p-6 border border-white/10">
                                <div class="flex items-center justify-between mb-4">
                                    <h3 class="font-semibold flex items-center space-x-2">
                                        <i class="fas fa-magic text-indigo-400" aria-hidden="true"></i>
                                        <span>AI Content Composer</span>
                                    </h3>
                                    <div class="flex space-x-2">
                                        <button class="px-3 py-1 rounded-lg bg-white/5 text-xs hover:bg-white/10 transition-colors" onclick="generateContent('twitter')">Twitter</button>
                                        <button class="px-3 py-1 rounded-lg bg-white/5 text-xs hover:bg-white/10 transition-colors" onclick="generateContent('linkedin')">LinkedIn</button>
                                        <button class="px-3 py-1 rounded-lg bg-white/5 text-xs hover:bg-white/10 transition-colors" onclick="generateContent('instagram')">Instagram</button>
                                    </div>
                                </div>
                                
                                <div class="space-y-4">
                                    <div class="relative">
                                        <textarea id="ai-input" class="w-full bg-black/30 border border-white/10 rounded-xl p-4 text-sm focus:outline-none focus:border-indigo-500/50 transition-colors resize-none h-24" placeholder="Describe what you want to post about..."></textarea>
                                        <button onclick="generateContent()" class="absolute bottom-3 right-3 w-8 h-8 bg-indigo-500 rounded-lg flex items-center justify-center hover:bg-indigo-600 transition-colors" aria-label="Generate content">
                                            <i class="fas fa-wand-magic-sparkles text-xs" aria-hidden="true"></i>
                                        </button>
                                    </div>
                                    
                                    <div id="generated-content" class="hidden bg-black/20 rounded-xl p-4 border border-indigo-500/20">
                                        <div class="flex items-start space-x-3">
                                            <div class="w-8 h-8 rounded-full bg-gradient-to-br from-indigo-500 to-pink-500 flex items-center justify-center flex-shrink-0" aria-hidden="true">
                                                <i class="fas fa-robot text-xs"></i>
                                            </div>
                                            <div class="flex-1">
                                                <p class="text-sm text-gray-300 typing-cursor" id="typing-text"></p>
                                                <div class="mt-3 flex items-center space-x-2">
                                                    <button class="text-xs bg-indigo-500/20 text-indigo-400 px-3 py-1.5 rounded-lg border border-indigo-500/30 hover:bg-indigo-500/30 transition-colors" onclick="alert('Posted successfully!')">
                                                        <i class="fas fa-paper-plane mr-1" aria-hidden="true"></i> Post Now
                                                    </button>
                                                    <button class="text-xs bg-white/5 text-gray-300 px-3 py-1.5 rounded-lg hover:bg-white/10 transition-colors">
                                                        <i class="fas fa-clock mr-1" aria-hidden="true"></i> Schedule
                                                    </button>
                                                    <button class="text-xs bg-white/5 text-gray-300 px-3 py-1.5 rounded-lg hover:bg-white/10 transition-colors">
                                                        <i class="fas fa-edit mr-1" aria-hidden="true"></i> Edit
                                                    </button>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <div class="glass rounded-2xl p-6 border border-white/10">
                                <h3 class="font-semibold mb-4">Recent Agent Activity</h3>
                                <div class="space-y-3" id="activity-feed" aria-live="polite" aria-atomic="false">
                                    <div class="flex items-center space-x-4 p-3 rounded-xl bg-white/5 border border-white/5">
                                        <div class="w-10 h-10 rounded-full bg-[#1DA1F2]/20 flex items-center justify-center" aria-hidden="true">
                                            <i class="fab fa-twitter text-[#1DA1F2]"></i>
                                        </div>
                                        <div class="flex-1">
                                            <div class="flex items-center justify-between">
                                                <span class="font-medium text-sm">Posted thread on Twitter</span>
                                                <span class="text-xs text-gray-500">2m ago</span>
                                            </div>
                                            <p class="text-xs text-gray-400 mt-1">"5 AI trends that will change marketing in 2026..."</p>
                                        </div>
                                        <div class="flex items-center space-x-2 text-xs text-gray-500">
                                            <span><i class="fas fa-heart text-red-400" aria-hidden="true"></i> 234</span>
                                            <span><i class="fas fa-retweet text-green-400" aria-hidden="true"></i> 89</span>
                                        </div>
                                    </div>

                                    <div class="flex items-center space-x-4 p-3 rounded-xl bg-white/5 border border-white/5">
                                        <div class="w-10 h-10 rounded-full bg-[#E1306C]/20 flex items-center justify-center" aria-hidden="true">
                                            <i class="fab fa-instagram text-[#E1306C]"></i>
                                        </div>
                                        <div class="flex-1">
                                            <div class="flex items-center justify-between">
                                                <span class="font-medium text-sm">Generated carousel</span>
                                                <span class="text-xs text-gray-500">15m ago</span>
                                            </div>
                                            <p class="text-xs text-gray-400 mt-1">Product showcase for @brandname with AI captions</p>
                                        </div>
                                        <span class="text-xs bg-green-500/20 text-green-400 px-2 py-1 rounded">Published</span>
                                    </div>

                                    <div class="flex items-center space-x-4 p-3 rounded-xl bg-white/5 border border-white/5 opacity-50">
                                        <div class="w-10 h-10 rounded-full bg-[#0A66C2]/20 flex items-center justify-center" aria-hidden="true">
                                            <i class="fab fa-linkedin text-[#0A66C2]"></i>
                                        </div>
                                        <div class="flex-1">
                                            <div class="flex items-center justify-between">
                                                <span class="font-medium text-sm">Scheduled post</span>
                                                <span class="text-xs text-gray-500">Tomorrow 9:00 AM</span>
                                            </div>
                                            <p class="text-xs text-gray-400 mt-1">Industry insights article share</p>
                                        </div>
                                        <span class="text-xs bg-yellow-500/20 text-yellow-400 px-2 py-1 rounded">Pending</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="features" class="py-24 relative" aria-labelledby="features-heading">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 id="features-heading" class="sr-only">Features</h2>
                <div class="grid md:grid-cols-3 gap-8">
                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-indigo-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-indigo-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-brain text-2xl text-indigo-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Autonomous Content</h3>
                        <p class="text-gray-400 leading-relaxed">AI agents that research trends, write copy, and generate visuals without human intervention. Set your brand voice once, let it run 24/7.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-pink-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-pink-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-network-wired text-2xl text-pink-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Cross-Platform Sync</h3>
                        <p class="text-gray-400 leading-relaxed">One content piece automatically adapted for each platform's format and audience. Native posting to 15+ social networks simultaneously.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-cyan-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-cyan-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-comments text-2xl text-cyan-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Smart Engagement</h3>
                        <p class="text-gray-400 leading-relaxed">Auto-reply to comments, DMs, and mentions with context-aware responses. Maintain authentic conversations at scale.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-indigo-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-indigo-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-chart-pie text-2xl text-indigo-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Predictive Analytics</h3>
                        <p class="text-gray-400 leading-relaxed">ML models predict optimal posting times, content performance, and trending topics before they peak.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-pink-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-pink-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-shield-alt text-2xl text-pink-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Brand Safety</h3>
                        <p class="text-gray-400 leading-relaxed">Advanced content filtering ensures every post aligns with your brand guidelines and compliance requirements.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-cyan-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-cyan-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-users text-2xl text-cyan-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Team Collaboration</h3>
                        <p class="text-gray-400 leading-relaxed">Multi-agent workflows with approval chains, role-based access, and collaborative campaign management.</p>
                    </article>
                </div>
            </div>
        </section>

        <section id="pricing" class="py-24 relative" aria-labelledby="pricing-heading">
            <div class="absolute inset-0 bg-gradient-to-t from-indigo-500/5 to-transparent" aria-hidden="true"></div>
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="text-center mb-16">
                    <h2 id="pricing-heading" class="font-display text-4xl font-bold mb-4">Simple <span class="gradient-text">Pricing</span></h2>
                    <p class="text-gray-400">Scale your AI marketing team without scaling your headcount</p>
                </div>

                <div class="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">
                    <article class="glass rounded-3xl p-8 border border-white/10 hover:border-white/20 transition-all">
                        <h3 class="text-lg font-semibold text-gray-300 mb-2">Starter</h3>
                        <div class="flex items-baseline mb-6">
                            <span class="text-4xl font-bold font-display">$29</span>
                            <span class="text-gray-500 ml-2">/month</span>
                        </div>
                        <ul class="space-y-4 mb-8">
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>1 AI Agent</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>3 Social Platforms</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>50 Posts/month</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Basic Analytics</span></li>
                        </ul>
                        <button class="w-full py-3 rounded-xl border border-white/20 text-white font-medium hover:bg-white/5 transition-colors" onclick="alert('Starter plan selected')">Get Started</button>
                    </article>

                    <article class="glass rounded-3xl p-8 border border-indigo-500/50 relative transform md:-translate-y-4 shadow-2xl shadow-indigo-500/20">
                        <div class="absolute -top-4 left-1/2 -translate-x-1/2 bg-gradient-to-r from-indigo-500 to-pink-500 px-4 py-1 rounded-full text-xs font-bold text-white">MOST POPULAR</div>
                        <h3 class="text-lg font-semibold text-gray-300 mb-2">Professional</h3>
                        <div class="flex items-baseline mb-6">
                            <span class="text-4xl font-bold font-display gradient-text">$99</span>
                            <span class="text-gray-500 ml-2">/month</span>
                        </div>
                        <ul class="space-y-4 mb-8">
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>5 AI Agents</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Unlimited Platforms</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Unlimited Posts</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Advanced Analytics</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>AI Image Generation</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Priority Support</span></li>
                        </ul>
                        <button class="w-full py-3 rounded-xl bg-gradient-to-r from-indigo-500 to-pink-500 text-white font-medium hover:shadow-lg hover:shadow-indigo-500/25 transition-all hover:scale-105" onclick="alert('Pro trial started!')">Start Free Trial</button>
                    </article>

                    <article class="glass rounded-3xl p-8 border border-white/10 hover:border-white/20 transition-all">
                        <h3 class="text-lg font-semibold text-gray-300 mb-2">Enterprise</h3>
                        <div class="flex items-baseline mb-6">
                            <span class="text-4xl font-bold font-display">Custom</span>
                        </div>
                        <ul class="space-y-4 mb-8">
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Unlimited AI Agents</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Custom Integrations</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Dedicated Infrastructure</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>SLA & 24/7 Support</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Custom AI Training</span></li>
                        </ul>
                        <button class="w-full py-3 rounded-xl border border-white/20 text-white font-medium hover:bg-white/5 transition-colors" onclick="alert('Contact form would open')">Contact Sales</button>
                    </article>
                </div>
            </div>
        </section>

        <section class="py-24 relative overflow-hidden" aria-label="Call to action">
            <div class="absolute inset-0 bg-gradient-to-r from-indigo-500/20 via-pink-500/20 to-cyan-500/20 opacity-30" aria-hidden="true"></div>
            <div class="max-w-4xl mx-auto px-4 text-center relative z-10">
                <h2 class="font-display text-5xl font-bold mb-6">Ready to Deploy Your <span class="gradient-text">AI Workforce?</span></h2>
                <p class="text-xl text-gray-300 mb-8">Join thousands of marketers automating their social presence with intelligent agents.</p>
                <div class="flex flex-col sm:flex-row gap-4 justify-center">
                    <button class="px-8 py-4 rounded-full bg-white text-slate-950 font-bold hover:scale-105 transition-transform" onclick="alert('Trial started! Check your email.')">Start Free 14-Day Trial</button>
                    <button class="px-8 py-4 rounded-full border border-white/30 text-white font-medium hover:bg-white/10 transition-colors" onclick="alert('Demo scheduling modal')">Schedule Demo</button>
                </div>
                <p class="mt-6 text-sm text-gray-500">No credit card required • Cancel anytime</p>
            </div>
        </section>
    </main>

    <footer class="border-t border-white/10 bg-black/40 backdrop-blur-lg" role="contentinfo">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mb-8">
                <div>
                    <h4 class="font-bold mb-4">Product</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#features" class="hover:text-white transition-colors">Features</a></li>
                        <li><a href="#platforms" class="hover:text-white transition-colors">Integrations</a></li>
                        <li><a href="#pricing" class="hover:text-white transition-colors">Pricing</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Changelog</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold mb-4">Company</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#" class="hover:text-white transition-colors">About</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Blog</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Careers</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Press</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold mb-4">Resources</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#" class="hover:text-white transition-colors">Documentation</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Help Center</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Community</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">API Reference</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold mb-4">Legal</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#" class="hover:text-white transition-colors">Privacy</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Terms</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Security</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Cookies</a></li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-white/10 pt-8 flex flex-col md:flex-row items-center justify-between">
                <div class="flex items-center space-x-2 mb-4 md:mb-0">
                    <div class="w-6 h-6 bg-gradient-to-br from-indigo-500 to-pink-500 rounded flex items-center justify-center" aria-hidden="true">
                        <i class="fas fa-robot text-white text-xs"></i>
                    </div>
                    <span class="font-display font-bold">AgentX</span>
                </div>
                <div class="flex space-x-6 text-gray-400">
                    <a href="#" class="hover:text-white transition-colors" aria-label="Twitter"><i class="fab fa-twitter" aria-hidden="true"></i></a>
                    <a href="#" class="hover:text-white transition-colors" aria-label="GitHub"><i class="fab fa-github" aria-hidden="true"></i></a>
                    <a href="#" class="hover:text-white transition-colors" aria-label="Discord"><i class="fab fa-discord" aria-hidden="true"></i></a>
                    <a href="#" class="hover:text-white transition-colors" aria-label="LinkedIn"><i class="fab fa-linkedin" aria-hidden="true"></i></a>
                </div>
                <p class="text-sm text-gray-500 mt-4 md:mt-0">© 2026 AgentX. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Three.js Background
        const scene=new THREE.Scene();
        const camera=new THREE.PerspectiveCamera(75,window.innerWidth/window.innerHeight,0.1,1000);
        const renderer=new THREE.WebGLRenderer({alpha:true,antialias:true});
        renderer.setSize(window.innerWidth,window.innerHeight);
        document.getElementById('canvas-container').appendChild(renderer.domElement);

        const particlesGeometry=new THREE.BufferGeometry();
        const particlesCount=1500;
        const posArray=new Float32Array(particlesCount*3);

        for(let i=0;i<particlesCount*3;i++){
            posArray[i]=(Math.random()-0.5)*50;
        }

        particlesGeometry.setAttribute('position',new THREE.BufferAttribute(posArray,3));
        
        const particlesMaterial=new THREE.PointsMaterial({
            size:0.02,
            color:0x6366f1,
            transparent:true,
            opacity:0.6,
            blending:THREE.AdditiveBlending
        });

        const particlesMesh=new THREE.Points(particlesGeometry,particlesMaterial);
        scene.add(particlesMesh);
        camera.position.z=5;

        let mouseX=0,mouseY=0;
        document.addEventListener('mousemove',(e)=>{
            mouseX=e.clientX/window.innerWidth-0.5;
            mouseY=e.clientY/window.innerHeight-0.5;
        });

        function animate(){
            requestAnimationFrame(animate);
            particlesMesh.rotation.y+=0.001;
            particlesMesh.rotation.x+=0.001;
            particlesMesh.rotation.x+=mouseY*0.05;
            particlesMesh.rotation.y+=mouseX*0.05;
            renderer.render(scene,camera);
        }
        animate();

        window.addEventListener('resize',()=>{
            camera.aspect=window.innerWidth/window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth,window.innerHeight);
        });

        // Platform Toggle
        function togglePlatform(element){
            const toggle=element.querySelector('.platform-toggle');
            const badge=element.querySelector('.connected-badge');
            const isActive=toggle.classList.contains('bg-green-500');
            
            if(!isActive){
                toggle.classList.remove('bg-gray-700');
                toggle.classList.add('bg-green-500');
                toggle.querySelector('div').classList.add('translate-x-4');
                toggle.setAttribute('aria-checked','true');
                badge.classList.remove('opacity-0');
                element.classList.add('border-green-500/50');
            }else{
                toggle.classList.add('bg-gray-700');
                toggle.classList.remove('bg-green-500');
                toggle.querySelector('div').classList.remove('translate-x-4');
                toggle.setAttribute('aria-checked','false');
                badge.classList.add('opacity-0');
                element.classList.remove('border-green-500/50');
            }
        }

        // AI Content Generation
        const sampleContents={
            twitter:"🚀 Just dropped: Our AI agent now supports predictive analytics! Know which content will go viral before you post. Thread below 👇 #AIMarketing #SocialMedia",
            linkedin:"Excited to announce that our latest AI marketing automation features are now live. After 6 months of development, we've achieved 40% higher engagement rates through predictive content optimization.",
            instagram:"✨ Behind the scenes: How our AI creates the perfect carousel posts\n\n1️⃣ Analyzes trending visuals\n2️⃣ Generates cohesive color palettes\n3️⃣ Writes engaging captions\n4️⃣ Optimizes for your audience\n\nSave this for later! 🔖"
        };

        let typingInterval;

        function generateContent(platform){
            const container=document.getElementById('generated-content');
            const textElement=document.getElementById('typing-text');
            const input=document.getElementById('ai-input');
            
            if(typingInterval)clearInterval(typingInterval);
            container.classList.remove('hidden');
            
            let content;
            if(platform&&sampleContents[platform]){
                content=sampleContents[platform];
            }else if(input.value.trim()){
                content=`Generated post about: "${input.value}"\n\nHere's an engaging caption optimized for maximum reach based on current trending topics...`;
            }else{
                const keys=Object.keys(sampleContents);
                content=sampleContents[keys[Math.floor(Math.random()*keys.length)]];
            }
            
            textElement.textContent='';
            let i=0;
            typingInterval=setInterval(()=>{
                if(i<content.length){
                    textElement.textContent+=content.charAt(i);
                    i++;
                }else{
                    clearInterval(typingInterval);
                }
            },30);
        }

        // Activity Feed Updates
        const activities=[
            {platform:'twitter',icon:'fab fa-twitter',color:'#1DA1F2',text:'Analyzed trending hashtags for optimal reach'},
            {platform:'instagram',icon:'fab fa-instagram',color:'#E1306C',text:'Generated visual content for Stories'},
            {platform:'linkedin',icon:'fab fa-linkedin',color:'#0A66C2',text:'Scheduled thought leadership article'}
        ];

        setInterval(()=>{
            const feed=document.getElementById('activity-feed');
            const randomActivity=activities[Math.floor(Math.random()*activities.length)];
            
            const newItem=document.createElement('div');
            newItem.className='flex items-center space-x-4 p-3 rounded-xl bg-white/5 border border-white/5 animate-pulse';
            newItem.innerHTML=`
                <div class="w-10 h-10 rounded-full flex items-center justify-center" style="background:${randomActivity.color}20">
                    <i class="${randomActivity.icon}" style="color:${randomActivity.color}"></i>
                </div>
                <div class="flex-1">
                    <div class="flex items-center justify-between">
                        <span class="font-medium text-sm">AI Agent Action</span>
                        <span class="text-xs text-gray-500">Just now</span>
                    </div>
                    <p class="text-xs text-gray-400 mt-1">${randomActivity.text}</p>
                </div>
            `;
            
            feed.insertBefore(newItem,feed.firstChild);
            if(feed.children.length>5)feed.removeChild(feed.lastChild);
            setTimeout(()=>newItem.classList.remove('animate-pulse'),1000);
        },8000);

        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor=>{
            anchor.addEventListener('click',function(e){
                e.preventDefault();
                const target=document.querySelector(this.getAttribute('href'));
                if(target)target.scrollIntoView({behavior:'smooth',block:'start'});
            });
        });

        // Intersection Observer
        const observer=new IntersectionObserver((entries)=>{
            entries.forEach(entry=>{
                if(entry.isIntersecting){
                    entry.target.style.opacity='1';
                    entry.target.style.transform='translateY(0)';
                }
            });
        },{threshold:0.1,rootMargin:'0px 0px -50px 0px'});

        document.querySelectorAll('.glass, .platform-card').forEach((el,index)=>{
            el.style.opacity='0';
            el.style.transform='translateY(20px)';
            el.style.transition=`all 0.6s ease ${index*0.1}s`;
            observer.observe(el);
        });
    </script>
</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="AI Marketing Automation Platform - Deploy autonomous agents to manage your social media presence 24/7">
    <meta property="og:title" content="AgentX - AI Marketing Agent Platform">
    <meta property="og:description" content="Autonomous AI agents for social media management">
    <meta property="og:type" content="website">
    <title>AgentX - AI Marketing Automation Platform</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://cdnjs.cloudflare.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        *,*::before,*::after{box-sizing:border-box}
        html,body{margin:0;padding:0}
        body{font-family:'Inter',sans-serif;background:#020617;color:#e2e8f0;overflow-x:hidden;line-height:1.6}
        .font-display{font-family:'Space Grotesk',sans-serif}
        .glass{background:rgba(15,23,42,0.6);backdrop-filter:blur(12px);border:1px solid rgba(99,102,241,0.2)}
        .glass-strong{background:rgba(15,23,42,0.8);backdrop-filter:blur(20px);border:1px solid rgba(99,102,241,0.3)}
        .gradient-text{background:linear-gradient(135deg,#6366f1 0%,#ec4899 50%,#06b6d4 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
        .grid-pattern{background-image:radial-gradient(rgba(99,102,241,0.1) 1px,transparent 1px);background-size:30px 30px}
        @keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-20px)}}
        @keyframes orbit{from{transform:rotate(0deg) translateX(100px) rotate(0deg)}to{transform:rotate(360deg) translateX(100px) rotate(-360deg)}}
        @keyframes pulse-ring{0%{transform:scale(0.8);box-shadow:0 0 0 0 rgba(34,197,94,0.7)}70%{transform:scale(1);box-shadow:0 0 0 10px rgba(34,197,94,0)}100%{transform:scale(0.8);box-shadow:0 0 0 0 rgba(34,197,94,0)}}
        @keyframes marquee{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
        .animate-float{animation:float 6s ease-in-out infinite}
        .animate-orbit{animation:orbit 20s linear infinite}
        .status-dot{animation:pulse-ring 2s cubic-bezier(0.215,0.61,0.355,1) infinite}
        .animate-marquee{animation:marquee 30s linear infinite}
        .typing-cursor::after{content:'|';animation:blink 1s infinite}
        @keyframes blink{0%,50%{opacity:1}51%,100%{opacity:0}}
        #canvas-container{position:fixed;top:0;left:0;width:100%;height:100%;z-index:-1;pointer-events:none}
        .platform-card{transition:all 0.3s ease}
        .platform-card:hover{transform:translateY(-5px);box-shadow:0 20px 40px -10px rgba(99,102,241,0.3)}
        .scrollbar-hide::-webkit-scrollbar{display:none}
        .scrollbar-hide{-ms-overflow-style:none;scrollbar-width:none}
        .sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border-width:0}
    </style>
</head>
<body>
    <div id="canvas-container" aria-hidden="true"></div>
    
    <a href="#main-content" class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 focus:z-50 focus:bg-primary focus:text-white focus:px-4 focus:py-2 focus:rounded-lg">Skip to main content</a>

    <nav class="fixed w-full z-50 glass-strong border-b border-white/10" role="navigation" aria-label="Main navigation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center space-x-2">
                    <div class="w-8 h-8 bg-gradient-to-br from-indigo-500 to-pink-500 rounded-lg flex items-center justify-center" aria-hidden="true">
                        <i class="fas fa-robot text-white text-sm"></i>
                    </div>
                    <span class="font-display font-bold text-xl tracking-tight">Agent<span class="text-indigo-400">X</span></span>
                </div>
                
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#features" class="text-sm font-medium text-gray-300 hover:text-white transition-colors">Features</a>
                    <a href="#platforms" class="text-sm font-medium text-gray-300 hover:text-white transition-colors">Platforms</a>
                    <a href="#dashboard" class="text-sm font-medium text-gray-300 hover:text-white transition-colors">Dashboard</a>
                    <a href="#pricing" class="text-sm font-medium text-gray-300 hover:text-white transition-colors">Pricing</a>
                </div>
                
                <div class="flex items-center space-x-4">
                    <button class="hidden md:block text-sm font-medium text-gray-300 hover:text-white" onclick="alert('Sign in coming soon')">Sign In</button>
                    <button class="bg-indigo-500 hover:bg-indigo-600 text-white px-5 py-2 rounded-full text-sm font-medium transition-all hover:scale-105 hover:shadow-lg hover:shadow-indigo-500/25" onclick="alert('Welcome! Deployment starts here.')">
                        Get Started
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <main id="main-content">
        <section class="relative min-h-screen flex items-center justify-center pt-16 overflow-hidden" aria-label="Hero">
            <div class="absolute inset-0 grid-pattern opacity-30" aria-hidden="true"></div>
            
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="grid lg:grid-cols-2 gap-12 items-center">
                    <div class="space-y-8">
                        <div class="inline-flex items-center space-x-2 px-4 py-2 rounded-full glass border border-indigo-500/30">
                            <span class="w-2 h-2 bg-green-400 rounded-full status-dot" aria-hidden="true"></span>
                            <span class="text-xs font-medium text-indigo-400">AI Agent v2.0 Now Live</span>
                        </div>
                        
                        <h1 class="font-display text-5xl md:text-7xl font-bold leading-tight">
                            Your <span class="gradient-text">AI Marketing</span> Agent That Never Sleeps
                        </h1>
                        
                        <p class="text-lg text-gray-400 max-w-lg leading-relaxed">
                            Deploy autonomous AI agents to create, schedule, and optimize content across all social platforms. Connect once, automate forever.
                        </p>
                        
                        <div class="flex flex-col sm:flex-row gap-4">
                            <button class="group bg-gradient-to-r from-indigo-500 to-pink-500 px-8 py-4 rounded-full font-semibold text-white flex items-center justify-center space-x-2 hover:shadow-2xl hover:shadow-indigo-500/25 transition-all hover:scale-105" onclick="document.getElementById('dashboard').scrollIntoView({behavior:'smooth'})">
                                <span>Deploy Your Agent</span>
                                <i class="fas fa-arrow-right group-hover:translate-x-1 transition-transform" aria-hidden="true"></i>
                            </button>
                            <button class="px-8 py-4 rounded-full font-semibold text-white border border-white/20 hover:bg-white/5 transition-all flex items-center justify-center space-x-2" onclick="alert('Demo video modal would open here')">
                                <i class="fas fa-play text-xs" aria-hidden="true"></i>
                                <span>Watch Demo</span>
                            </button>
                        </div>
                        
                        <div class="flex items-center space-x-6 text-sm text-gray-500">
                            <div class="flex -space-x-2" aria-hidden="true">
                                <div class="w-8 h-8 rounded-full bg-gray-700 border-2 border-slate-950 flex items-center justify-center text-xs">JD</div>
                                <div class="w-8 h-8 rounded-full bg-gray-600 border-2 border-slate-950 flex items-center justify-center text-xs">MK</div>
                                <div class="w-8 h-8 rounded-full bg-gray-500 border-2 border-slate-950 flex items-center justify-center text-xs">+2k</div>
                            </div>
                            <span>Trusted by 2,000+ marketers</span>
                        </div>
                    </div>
                    
                    <div class="relative" aria-hidden="true">
                        <div class="relative w-full aspect-square max-w-md mx-auto">
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-64 h-64 border border-indigo-500/20 rounded-full animate-spin" style="animation-duration:30s"></div>
                                <div class="absolute w-48 h-48 border border-pink-500/20 rounded-full animate-spin" style="animation-duration:20s;animation-direction:reverse"></div>
                                <div class="absolute w-32 h-32 border border-cyan-500/20 rounded-full animate-spin" style="animation-duration:15s"></div>
                            </div>
                            
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-32 h-32 bg-gradient-to-br from-indigo-500/20 to-pink-500/20 rounded-2xl backdrop-blur-xl border border-white/10 flex items-center justify-center animate-float shadow-2xl shadow-indigo-500/20">
                                    <i class="fas fa-brain text-4xl gradient-text"></i>
                                </div>
                            </div>
                            
                            <div class="absolute top-0 left-1/2 -translate-x-1/2 animate-orbit" style="animation-delay:0s">
                                <div class="w-12 h-12 bg-[#1DA1F2]/20 backdrop-blur-md rounded-xl flex items-center justify-center border border-[#1DA1F2]/30">
                                    <i class="fab fa-twitter text-[#1DA1F2]"></i>
                                </div>
                            </div>
                            <div class="absolute top-1/2 right-0 translate-x-1/2 animate-orbit" style="animation-delay:-5s">
                                <div class="w-12 h-12 bg-[#E1306C]/20 backdrop-blur-md rounded-xl flex items-center justify-center border border-[#E1306C]/30">
                                    <i class="fab fa-instagram text-[#E1306C]"></i>
                                </div>
                            </div>
                            <div class="absolute bottom-0 left-1/2 -translate-x-1/2 animate-orbit" style="animation-delay:-10s">
                                <div class="w-12 h-12 bg-[#0A66C2]/20 backdrop-blur-md rounded-xl flex items-center justify-center border border-[#0A66C2]/30">
                                    <i class="fab fa-linkedin text-[#0A66C2]"></i>
                                </div>
                            </div>
                            <div class="absolute top-1/2 left-0 -translate-x-1/2 animate-orbit" style="animation-delay:-15s">
                                <div class="w-12 h-12 bg-[#FF0000]/20 backdrop-blur-md rounded-xl flex items-center justify-center border border-[#FF0000]/30">
                                    <i class="fab fa-youtube text-[#FF0000]"></i>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <div class="border-y border-white/5 bg-black/20 backdrop-blur-sm overflow-hidden" aria-label="Live activity ticker">
            <div class="flex animate-marquee whitespace-nowrap py-4">
                <div class="flex items-center space-x-8 mx-4 text-sm">
                    <span class="flex items-center space-x-2 text-green-400"><i class="fas fa-check-circle" aria-hidden="true"></i><span>Agent posted on Twitter for @techcorp</span></span>
                    <span class="flex items-center space-x-2 text-blue-400"><i class="fas fa-sync fa-spin" aria-hidden="true"></i><span>Analyzing engagement metrics...</span></span>
                    <span class="flex items-center space-x-2 text-purple-400"><i class="fas fa-robot" aria-hidden="true"></i><span>AI generating Instagram carousel for @fashionbrand</span></span>
                    <span class="flex items-center space-x-2 text-pink-400"><i class="fas fa-heart" aria-hidden="true"></i><span>Auto-replied to 47 comments on LinkedIn</span></span>
                    <span class="flex items-center space-x-2 text-yellow-400"><i class="fas fa-chart-line" aria-hidden="true"></i><span>Campaign ROI increased by 34%</span></span>
                </div>
                <div class="flex items-center space-x-8 mx-4 text-sm" aria-hidden="true">
                    <span class="flex items-center space-x-2 text-green-400"><i class="fas fa-check-circle"></i><span>Agent posted on Twitter for @techcorp</span></span>
                    <span class="flex items-center space-x-2 text-blue-400"><i class="fas fa-sync fa-spin"></i><span>Analyzing engagement metrics...</span></span>
                    <span class="flex items-center space-x-2 text-purple-400"><i class="fas fa-robot"></i><span>AI generating Instagram carousel for @fashionbrand</span></span>
                    <span class="flex items-center space-x-2 text-pink-400"><i class="fas fa-heart"></i><span>Auto-replied to 47 comments on LinkedIn</span></span>
                </div>
            </div>
        </div>

        <section id="platforms" class="py-24 relative" aria-labelledby="platforms-heading">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 id="platforms-heading" class="font-display text-4xl font-bold mb-4">Connect <span class="gradient-text">Everything</span></h2>
                    <p class="text-gray-400 max-w-2xl mx-auto">One AI agent to manage them all. Native integrations with every major platform.</p>
                </div>
                
                <div class="grid grid-cols-2 md:grid-cols-4 gap-6" role="list">
                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#1DA1F2]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-twitter text-2xl text-[#1DA1F2]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle Twitter connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">Twitter/X</h3>
                        <p class="text-xs text-gray-500">Auto-post threads & replies</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#E1306C]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-instagram text-2xl text-[#E1306C]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle Instagram connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">Instagram</h3>
                        <p class="text-xs text-gray-500">Stories, Reels & Posts</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#0A66C2]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-linkedin text-2xl text-[#0A66C2]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle LinkedIn connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">LinkedIn</h3>
                        <p class="text-xs text-gray-500">Professional network posts</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#FF0000]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-youtube text-2xl text-[#FF0000]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle YouTube connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">YouTube</h3>
                        <p class="text-xs text-gray-500">Video & Shorts automation</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#5865F2]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-discord text-2xl text-[#5865F2]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle Discord connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">Discord</h3>
                        <p class="text-xs text-gray-500">Community management</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#25D366]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-whatsapp text-2xl text-[#25D366]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle WhatsApp connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">WhatsApp</h3>
                        <p class="text-xs text-gray-500">Business API integration</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-black border border-white/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-tiktok text-2xl text-white"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle TikTok connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">TikTok</h3>
                        <p class="text-xs text-gray-500">Viral content automation</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>

                    <article class="platform-card glass rounded-2xl p-6 cursor-pointer group" onclick="togglePlatform(this)" role="listitem" tabindex="0" onkeypress="if(event.key==='Enter')togglePlatform(this)">
                        <div class="flex items-center justify-between mb-4">
                            <div class="w-12 h-12 rounded-xl bg-[#FF4500]/10 flex items-center justify-center group-hover:scale-110 transition-transform" aria-hidden="true">
                                <i class="fab fa-reddit text-2xl text-[#FF4500]"></i>
                            </div>
                            <div class="platform-toggle w-10 h-6 rounded-full bg-gray-700 relative transition-colors" role="switch" aria-checked="false" aria-label="Toggle Reddit connection">
                                <div class="absolute top-1 left-1 w-4 h-4 rounded-full bg-white transition-transform"></div>
                            </div>
                        </div>
                        <h3 class="font-semibold mb-1">Reddit</h3>
                        <p class="text-xs text-gray-500">Subreddit monitoring</p>
                        <div class="mt-4 flex items-center space-x-2 text-xs text-green-400 opacity-0 transition-opacity connected-badge">
                            <i class="fas fa-check" aria-hidden="true"></i>
                            <span>Connected</span>
                        </div>
                    </article>
                </div>
            </div>
        </section>

        <section id="dashboard" class="py-24 relative overflow-hidden" aria-labelledby="dashboard-heading">
            <div class="absolute inset-0 bg-gradient-to-b from-indigo-500/5 to-transparent" aria-hidden="true"></div>
            
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="text-center mb-12">
                    <h2 id="dashboard-heading" class="font-display text-4xl font-bold mb-4">Command <span class="gradient-text">Center</span></h2>
                    <p class="text-gray-400">Real-time control over your AI marketing workforce</p>
                </div>

                <div class="glass-strong rounded-3xl border border-white/10 overflow-hidden shadow-2xl shadow-indigo-500/10">
                    <div class="border-b border-white/10 px-6 py-4 flex items-center justify-between bg-white/5">
                        <div class="flex items-center space-x-4">
                            <div class="flex space-x-2" aria-hidden="true">
                                <div class="w-3 h-3 rounded-full bg-red-500"></div>
                                <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
                                <div class="w-3 h-3 rounded-full bg-green-500"></div>
                            </div>
                            <span class="text-sm font-medium text-gray-400">AgentX Dashboard</span>
                        </div>
                        <div class="flex items-center space-x-4">
                            <button class="text-xs bg-indigo-500/20 text-indigo-400 px-3 py-1 rounded-full border border-indigo-500/30">
                                <i class="fas fa-circle text-[8px] mr-1 animate-pulse" aria-hidden="true"></i>
                                Live
                            </button>
                            <i class="fas fa-bell text-gray-400 hover:text-white cursor-pointer" aria-hidden="true"></i>
                            <div class="w-8 h-8 rounded-full bg-gradient-to-br from-indigo-500 to-pink-500" aria-hidden="true"></div>
                        </div>
                    </div>

                    <div class="grid lg:grid-cols-4 min-h-[600px]">
                        <nav class="hidden lg:block border-r border-white/10 p-6 space-y-6 bg-black/20" aria-label="Dashboard navigation">
                            <div class="space-y-2">
                                <button class="w-full text-left px-4 py-3 rounded-xl bg-indigo-500/20 text-indigo-400 border border-indigo-500/30 flex items-center space-x-3" aria-current="page">
                                    <i class="fas fa-home" aria-hidden="true"></i>
                                    <span>Overview</span>
                                </button>
                                <button class="w-full text-left px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 flex items-center space-x-3 transition-colors">
                                    <i class="fas fa-robot" aria-hidden="true"></i>
                                    <span>AI Agents</span>
                                </button>
                                <button class="w-full text-left px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 flex items-center space-x-3 transition-colors">
                                    <i class="fas fa-calendar" aria-hidden="true"></i>
                                    <span>Schedule</span>
                                </button>
                                <button class="w-full text-left px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 flex items-center space-x-3 transition-colors">
                                    <i class="fas fa-chart-bar" aria-hidden="true"></i>
                                    <span>Analytics</span>
                                </button>
                            </div>

                            <div class="pt-6 border-t border-white/10">
                                <h4 class="text-xs font-semibold text-gray-500 uppercase tracking-wider mb-4">Active Agents</h4>
                                <div class="space-y-3">
                                    <div class="flex items-center space-x-3 p-2 rounded-lg bg-white/5">
                                        <div class="w-2 h-2 bg-green-400 rounded-full animate-pulse" aria-hidden="true"></div>
                                        <div class="flex-1">
                                            <div class="text-sm font-medium">Content Creator</div>
                                            <div class="text-xs text-gray-500">Posting to Instagram...</div>
                                        </div>
                                    </div>
                                    <div class="flex items-center space-x-3 p-2 rounded-lg bg-white/5">
                                        <div class="w-2 h-2 bg-blue-400 rounded-full animate-pulse" aria-hidden="true"></div>
                                        <div class="flex-1">
                                            <div class="text-sm font-medium">Engagement Bot</div>
                                            <div class="text-xs text-gray-500">Replying to comments</div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </nav>

                        <div class="lg:col-span-3 p-6 space-y-6">
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                <div class="glass rounded-2xl p-6 border border-white/5">
                                    <div class="flex items-center justify-between mb-2">
                                        <span class="text-gray-400 text-sm">Total Reach</span>
                                        <span class="text-green-400 text-xs">+24.5%</span>
                                    </div>
                                    <div class="text-3xl font-bold font-display">2.4M</div>
                                    <div class="mt-2 h-1 bg-gray-700 rounded-full overflow-hidden" aria-hidden="true">
                                        <div class="h-full bg-indigo-500 w-3/4 rounded-full"></div>
                                    </div>
                                </div>
                                <div class="glass rounded-2xl p-6 border border-white/5">
                                    <div class="flex items-center justify-between mb-2">
                                        <span class="text-gray-400 text-sm">Engagement</span>
                                        <span class="text-green-400 text-xs">+12.3%</span>
                                    </div>
                                    <div class="text-3xl font-bold font-display">89.2K</div>
                                    <div class="mt-2 h-1 bg-gray-700 rounded-full overflow-hidden" aria-hidden="true">
                                        <div class="h-full bg-pink-500 w-1/2 rounded-full"></div>
                                    </div>
                                </div>
                                <div class="glass rounded-2xl p-6 border border-white/5">
                                    <div class="flex items-center justify-between mb-2">
                                        <span class="text-gray-400 text-sm">Posts Scheduled</span>
                                        <span class="text-blue-400 text-xs">This week</span>
                                    </div>
                                    <div class="text-3xl font-bold font-display">47</div>
                                    <div class="mt-2 h-1 bg-gray-700 rounded-full overflow-hidden" aria-hidden="true">
                                        <div class="h-full bg-cyan-500 w-2/3 rounded-full"></div>
                                    </div>
                                </div>
                            </div>

                            <div class="glass rounded-2xl p-6 border border-white/10">
                                <div class="flex items-center justify-between mb-4">
                                    <h3 class="font-semibold flex items-center space-x-2">
                                        <i class="fas fa-magic text-indigo-400" aria-hidden="true"></i>
                                        <span>AI Content Composer</span>
                                    </h3>
                                    <div class="flex space-x-2">
                                        <button class="px-3 py-1 rounded-lg bg-white/5 text-xs hover:bg-white/10 transition-colors" onclick="generateContent('twitter')">Twitter</button>
                                        <button class="px-3 py-1 rounded-lg bg-white/5 text-xs hover:bg-white/10 transition-colors" onclick="generateContent('linkedin')">LinkedIn</button>
                                        <button class="px-3 py-1 rounded-lg bg-white/5 text-xs hover:bg-white/10 transition-colors" onclick="generateContent('instagram')">Instagram</button>
                                    </div>
                                </div>
                                
                                <div class="space-y-4">
                                    <div class="relative">
                                        <textarea id="ai-input" class="w-full bg-black/30 border border-white/10 rounded-xl p-4 text-sm focus:outline-none focus:border-indigo-500/50 transition-colors resize-none h-24" placeholder="Describe what you want to post about..."></textarea>
                                        <button onclick="generateContent()" class="absolute bottom-3 right-3 w-8 h-8 bg-indigo-500 rounded-lg flex items-center justify-center hover:bg-indigo-600 transition-colors" aria-label="Generate content">
                                            <i class="fas fa-wand-magic-sparkles text-xs" aria-hidden="true"></i>
                                        </button>
                                    </div>
                                    
                                    <div id="generated-content" class="hidden bg-black/20 rounded-xl p-4 border border-indigo-500/20">
                                        <div class="flex items-start space-x-3">
                                            <div class="w-8 h-8 rounded-full bg-gradient-to-br from-indigo-500 to-pink-500 flex items-center justify-center flex-shrink-0" aria-hidden="true">
                                                <i class="fas fa-robot text-xs"></i>
                                            </div>
                                            <div class="flex-1">
                                                <p class="text-sm text-gray-300 typing-cursor" id="typing-text"></p>
                                                <div class="mt-3 flex items-center space-x-2">
                                                    <button class="text-xs bg-indigo-500/20 text-indigo-400 px-3 py-1.5 rounded-lg border border-indigo-500/30 hover:bg-indigo-500/30 transition-colors" onclick="alert('Posted successfully!')">
                                                        <i class="fas fa-paper-plane mr-1" aria-hidden="true"></i> Post Now
                                                    </button>
                                                    <button class="text-xs bg-white/5 text-gray-300 px-3 py-1.5 rounded-lg hover:bg-white/10 transition-colors">
                                                        <i class="fas fa-clock mr-1" aria-hidden="true"></i> Schedule
                                                    </button>
                                                    <button class="text-xs bg-white/5 text-gray-300 px-3 py-1.5 rounded-lg hover:bg-white/10 transition-colors">
                                                        <i class="fas fa-edit mr-1" aria-hidden="true"></i> Edit
                                                    </button>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <div class="glass rounded-2xl p-6 border border-white/10">
                                <h3 class="font-semibold mb-4">Recent Agent Activity</h3>
                                <div class="space-y-3" id="activity-feed" aria-live="polite" aria-atomic="false">
                                    <div class="flex items-center space-x-4 p-3 rounded-xl bg-white/5 border border-white/5">
                                        <div class="w-10 h-10 rounded-full bg-[#1DA1F2]/20 flex items-center justify-center" aria-hidden="true">
                                            <i class="fab fa-twitter text-[#1DA1F2]"></i>
                                        </div>
                                        <div class="flex-1">
                                            <div class="flex items-center justify-between">
                                                <span class="font-medium text-sm">Posted thread on Twitter</span>
                                                <span class="text-xs text-gray-500">2m ago</span>
                                            </div>
                                            <p class="text-xs text-gray-400 mt-1">"5 AI trends that will change marketing in 2026..."</p>
                                        </div>
                                        <div class="flex items-center space-x-2 text-xs text-gray-500">
                                            <span><i class="fas fa-heart text-red-400" aria-hidden="true"></i> 234</span>
                                            <span><i class="fas fa-retweet text-green-400" aria-hidden="true"></i> 89</span>
                                        </div>
                                    </div>

                                    <div class="flex items-center space-x-4 p-3 rounded-xl bg-white/5 border border-white/5">
                                        <div class="w-10 h-10 rounded-full bg-[#E1306C]/20 flex items-center justify-center" aria-hidden="true">
                                            <i class="fab fa-instagram text-[#E1306C]"></i>
                                        </div>
                                        <div class="flex-1">
                                            <div class="flex items-center justify-between">
                                                <span class="font-medium text-sm">Generated carousel</span>
                                                <span class="text-xs text-gray-500">15m ago</span>
                                            </div>
                                            <p class="text-xs text-gray-400 mt-1">Product showcase for @brandname with AI captions</p>
                                        </div>
                                        <span class="text-xs bg-green-500/20 text-green-400 px-2 py-1 rounded">Published</span>
                                    </div>

                                    <div class="flex items-center space-x-4 p-3 rounded-xl bg-white/5 border border-white/5 opacity-50">
                                        <div class="w-10 h-10 rounded-full bg-[#0A66C2]/20 flex items-center justify-center" aria-hidden="true">
                                            <i class="fab fa-linkedin text-[#0A66C2]"></i>
                                        </div>
                                        <div class="flex-1">
                                            <div class="flex items-center justify-between">
                                                <span class="font-medium text-sm">Scheduled post</span>
                                                <span class="text-xs text-gray-500">Tomorrow 9:00 AM</span>
                                            </div>
                                            <p class="text-xs text-gray-400 mt-1">Industry insights article share</p>
                                        </div>
                                        <span class="text-xs bg-yellow-500/20 text-yellow-400 px-2 py-1 rounded">Pending</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="features" class="py-24 relative" aria-labelledby="features-heading">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 id="features-heading" class="sr-only">Features</h2>
                <div class="grid md:grid-cols-3 gap-8">
                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-indigo-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-indigo-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-brain text-2xl text-indigo-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Autonomous Content</h3>
                        <p class="text-gray-400 leading-relaxed">AI agents that research trends, write copy, and generate visuals without human intervention. Set your brand voice once, let it run 24/7.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-pink-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-pink-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-network-wired text-2xl text-pink-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Cross-Platform Sync</h3>
                        <p class="text-gray-400 leading-relaxed">One content piece automatically adapted for each platform's format and audience. Native posting to 15+ social networks simultaneously.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-cyan-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-cyan-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-comments text-2xl text-cyan-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Smart Engagement</h3>
                        <p class="text-gray-400 leading-relaxed">Auto-reply to comments, DMs, and mentions with context-aware responses. Maintain authentic conversations at scale.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-indigo-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-indigo-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-chart-pie text-2xl text-indigo-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Predictive Analytics</h3>
                        <p class="text-gray-400 leading-relaxed">ML models predict optimal posting times, content performance, and trending topics before they peak.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-pink-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-pink-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-shield-alt text-2xl text-pink-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Brand Safety</h3>
                        <p class="text-gray-400 leading-relaxed">Advanced content filtering ensures every post aligns with your brand guidelines and compliance requirements.</p>
                    </article>

                    <article class="glass rounded-2xl p-8 border border-white/10 hover:border-cyan-500/30 transition-colors group">
                        <div class="w-14 h-14 rounded-2xl bg-cyan-500/10 flex items-center justify-center mb-6 group-hover:scale-110 transition-transform" aria-hidden="true">
                            <i class="fas fa-users text-2xl text-cyan-500"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-3 font-display">Team Collaboration</h3>
                        <p class="text-gray-400 leading-relaxed">Multi-agent workflows with approval chains, role-based access, and collaborative campaign management.</p>
                    </article>
                </div>
            </div>
        </section>

        <section id="pricing" class="py-24 relative" aria-labelledby="pricing-heading">
            <div class="absolute inset-0 bg-gradient-to-t from-indigo-500/5 to-transparent" aria-hidden="true"></div>
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="text-center mb-16">
                    <h2 id="pricing-heading" class="font-display text-4xl font-bold mb-4">Simple <span class="gradient-text">Pricing</span></h2>
                    <p class="text-gray-400">Scale your AI marketing team without scaling your headcount</p>
                </div>

                <div class="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">
                    <article class="glass rounded-3xl p-8 border border-white/10 hover:border-white/20 transition-all">
                        <h3 class="text-lg font-semibold text-gray-300 mb-2">Starter</h3>
                        <div class="flex items-baseline mb-6">
                            <span class="text-4xl font-bold font-display">$29</span>
                            <span class="text-gray-500 ml-2">/month</span>
                        </div>
                        <ul class="space-y-4 mb-8">
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>1 AI Agent</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>3 Social Platforms</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>50 Posts/month</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Basic Analytics</span></li>
                        </ul>
                        <button class="w-full py-3 rounded-xl border border-white/20 text-white font-medium hover:bg-white/5 transition-colors" onclick="alert('Starter plan selected')">Get Started</button>
                    </article>

                    <article class="glass rounded-3xl p-8 border border-indigo-500/50 relative transform md:-translate-y-4 shadow-2xl shadow-indigo-500/20">
                        <div class="absolute -top-4 left-1/2 -translate-x-1/2 bg-gradient-to-r from-indigo-500 to-pink-500 px-4 py-1 rounded-full text-xs font-bold text-white">MOST POPULAR</div>
                        <h3 class="text-lg font-semibold text-gray-300 mb-2">Professional</h3>
                        <div class="flex items-baseline mb-6">
                            <span class="text-4xl font-bold font-display gradient-text">$99</span>
                            <span class="text-gray-500 ml-2">/month</span>
                        </div>
                        <ul class="space-y-4 mb-8">
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>5 AI Agents</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Unlimited Platforms</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Unlimited Posts</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Advanced Analytics</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>AI Image Generation</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Priority Support</span></li>
                        </ul>
                        <button class="w-full py-3 rounded-xl bg-gradient-to-r from-indigo-500 to-pink-500 text-white font-medium hover:shadow-lg hover:shadow-indigo-500/25 transition-all hover:scale-105" onclick="alert('Pro trial started!')">Start Free Trial</button>
                    </article>

                    <article class="glass rounded-3xl p-8 border border-white/10 hover:border-white/20 transition-all">
                        <h3 class="text-lg font-semibold text-gray-300 mb-2">Enterprise</h3>
                        <div class="flex items-baseline mb-6">
                            <span class="text-4xl font-bold font-display">Custom</span>
                        </div>
                        <ul class="space-y-4 mb-8">
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Unlimited AI Agents</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Custom Integrations</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Dedicated Infrastructure</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>SLA & 24/7 Support</span></li>
                            <li class="flex items-center space-x-3 text-sm text-gray-300"><i class="fas fa-check text-indigo-500" aria-hidden="true"></i><span>Custom AI Training</span></li>
                        </ul>
                        <button class="w-full py-3 rounded-xl border border-white/20 text-white font-medium hover:bg-white/5 transition-colors" onclick="alert('Contact form would open')">Contact Sales</button>
                    </article>
                </div>
            </div>
        </section>

        <section class="py-24 relative overflow-hidden" aria-label="Call to action">
            <div class="absolute inset-0 bg-gradient-to-r from-indigo-500/20 via-pink-500/20 to-cyan-500/20 opacity-30" aria-hidden="true"></div>
            <div class="max-w-4xl mx-auto px-4 text-center relative z-10">
                <h2 class="font-display text-5xl font-bold mb-6">Ready to Deploy Your <span class="gradient-text">AI Workforce?</span></h2>
                <p class="text-xl text-gray-300 mb-8">Join thousands of marketers automating their social presence with intelligent agents.</p>
                <div class="flex flex-col sm:flex-row gap-4 justify-center">
                    <button class="px-8 py-4 rounded-full bg-white text-slate-950 font-bold hover:scale-105 transition-transform" onclick="alert('Trial started! Check your email.')">Start Free 14-Day Trial</button>
                    <button class="px-8 py-4 rounded-full border border-white/30 text-white font-medium hover:bg-white/10 transition-colors" onclick="alert('Demo scheduling modal')">Schedule Demo</button>
                </div>
                <p class="mt-6 text-sm text-gray-500">No credit card required • Cancel anytime</p>
            </div>
        </section>
    </main>

    <footer class="border-t border-white/10 bg-black/40 backdrop-blur-lg" role="contentinfo">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mb-8">
                <div>
                    <h4 class="font-bold mb-4">Product</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#features" class="hover:text-white transition-colors">Features</a></li>
                        <li><a href="#platforms" class="hover:text-white transition-colors">Integrations</a></li>
                        <li><a href="#pricing" class="hover:text-white transition-colors">Pricing</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Changelog</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold mb-4">Company</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#" class="hover:text-white transition-colors">About</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Blog</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Careers</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Press</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold mb-4">Resources</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#" class="hover:text-white transition-colors">Documentation</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Help Center</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Community</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">API Reference</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold mb-4">Legal</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#" class="hover:text-white transition-colors">Privacy</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Terms</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Security</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Cookies</a></li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-white/10 pt-8 flex flex-col md:flex-row items-center justify-between">
                <div class="flex items-center space-x-2 mb-4 md:mb-0">
                    <div class="w-6 h-6 bg-gradient-to-br from-indigo-500 to-pink-500 rounded flex items-center justify-center" aria-hidden="true">
                        <i class="fas fa-robot text-white text-xs"></i>
                    </div>
                    <span class="font-display font-bold">AgentX</span>
                </div>
                <div class="flex space-x-6 text-gray-400">
                    <a href="#" class="hover:text-white transition-colors" aria-label="Twitter"><i class="fab fa-twitter" aria-hidden="true"></i></a>
                    <a href="#" class="hover:text-white transition-colors" aria-label="GitHub"><i class="fab fa-github" aria-hidden="true"></i></a>
                    <a href="#" class="hover:text-white transition-colors" aria-label="Discord"><i class="fab fa-discord" aria-hidden="true"></i></a>
                    <a href="#" class="hover:text-white transition-colors" aria-label="LinkedIn"><i class="fab fa-linkedin" aria-hidden="true"></i></a>
                </div>
                <p class="text-sm text-gray-500 mt-4 md:mt-0">© 2026 AgentX. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Three.js Background
        const scene=new THREE.Scene();
        const camera=new THREE.PerspectiveCamera(75,window.innerWidth/window.innerHeight,0.1,1000);
        const renderer=new THREE.WebGLRenderer({alpha:true,antialias:true});
        renderer.setSize(window.innerWidth,window.innerHeight);
        document.getElementById('canvas-container').appendChild(renderer.domElement);

        const particlesGeometry=new THREE.BufferGeometry();
        const particlesCount=1500;
        const posArray=new Float32Array(particlesCount*3);

        for(let i=0;i<particlesCount*3;i++){
            posArray[i]=(Math.random()-0.5)*50;
        }

        particlesGeometry.setAttribute('position',new THREE.BufferAttribute(posArray,3));
        
        const particlesMaterial=new THREE.PointsMaterial({
            size:0.02,
            color:0x6366f1,
            transparent:true,
            opacity:0.6,
            blending:THREE.AdditiveBlending
        });

        const particlesMesh=new THREE.Points(particlesGeometry,particlesMaterial);
        scene.add(particlesMesh);
        camera.position.z=5;

        let mouseX=0,mouseY=0;
        document.addEventListener('mousemove',(e)=>{
            mouseX=e.clientX/window.innerWidth-0.5;
            mouseY=e.clientY/window.innerHeight-0.5;
        });

        function animate(){
            requestAnimationFrame(animate);
            particlesMesh.rotation.y+=0.001;
            particlesMesh.rotation.x+=0.001;
            particlesMesh.rotation.x+=mouseY*0.05;
            particlesMesh.rotation.y+=mouseX*0.05;
            renderer.render(scene,camera);
        }
        animate();

        window.addEventListener('resize',()=>{
            camera.aspect=window.innerWidth/window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth,window.innerHeight);
        });

        // Platform Toggle
        function togglePlatform(element){
            const toggle=element.querySelector('.platform-toggle');
            const badge=element.querySelector('.connected-badge');
            const isActive=toggle.classList.contains('bg-green-500');
            
            if(!isActive){
                toggle.classList.remove('bg-gray-700');
                toggle.classList.add('bg-green-500');
                toggle.querySelector('div').classList.add('translate-x-4');
                toggle.setAttribute('aria-checked','true');
                badge.classList.remove('opacity-0');
                element.classList.add('border-green-500/50');
            }else{
                toggle.classList.add('bg-gray-700');
                toggle.classList.remove('bg-green-500');
                toggle.querySelector('div').classList.remove('translate-x-4');
                toggle.setAttribute('aria-checked','false');
                badge.classList.add('opacity-0');
                element.classList.remove('border-green-500/50');
            }
        }

        // AI Content Generation
        const sampleContents={
            twitter:"🚀 Just dropped: Our AI agent now supports predictive analytics! Know which content will go viral before you post. Thread below 👇 #AIMarketing #SocialMedia",
            linkedin:"Excited to announce that our latest AI marketing automation features are now live. After 6 months of development, we've achieved 40% higher engagement rates through predictive content optimization.",
            instagram:"✨ Behind the scenes: How our AI creates the perfect carousel posts\n\n1️⃣ Analyzes trending visuals\n2️⃣ Generates cohesive color palettes\n3️⃣ Writes engaging captions\n4️⃣ Optimizes for your audience\n\nSave this for later! 🔖"
        };

        let typingInterval;

        function generateContent(platform){
            const container=document.getElementById('generated-content');
            const textElement=document.getElementById('typing-text');
            const input=document.getElementById('ai-input');
            
            if(typingInterval)clearInterval(typingInterval);
            container.classList.remove('hidden');
            
            let content;
            if(platform&&sampleContents[platform]){
                content=sampleContents[platform];
            }else if(input.value.trim()){
                content=`Generated post about: "${input.value}"\n\nHere's an engaging caption optimized for maximum reach based on current trending topics...`;
            }else{
                const keys=Object.keys(sampleContents);
                content=sampleContents[keys[Math.floor(Math.random()*keys.length)]];
            }
            
            textElement.textContent='';
            let i=0;
            typingInterval=setInterval(()=>{
                if(i<content.length){
                    textElement.textContent+=content.charAt(i);
                    i++;
                }else{
                    clearInterval(typingInterval);
                }
            },30);
        }

        // Activity Feed Updates
        const activities=[
            {platform:'twitter',icon:'fab fa-twitter',color:'#1DA1F2',text:'Analyzed trending hashtags for optimal reach'},
            {platform:'instagram',icon:'fab fa-instagram',color:'#E1306C',text:'Generated visual content for Stories'},
            {platform:'linkedin',icon:'fab fa-linkedin',color:'#0A66C2',text:'Scheduled thought leadership article'}
        ];

        setInterval(()=>{
            const feed=document.getElementById('activity-feed');
            const randomActivity=activities[Math.floor(Math.random()*activities.length)];
            
            const newItem=document.createElement('div');
            newItem.className='flex items-center space-x-4 p-3 rounded-xl bg-white/5 border border-white/5 animate-pulse';
            newItem.innerHTML=`
                <div class="w-10 h-10 rounded-full flex items-center justify-center" style="background:${randomActivity.color}20">
                    <i class="${randomActivity.icon}" style="color:${randomActivity.color}"></i>
                </div>
                <div class="flex-1">
                    <div class="flex items-center justify-between">
                        <span class="font-medium text-sm">AI Agent Action</span>
                        <span class="text-xs text-gray-500">Just now</span>
                    </div>
                    <p class="text-xs text-gray-400 mt-1">${randomActivity.text}</p>
                </div>
            `;
            
            feed.insertBefore(newItem,feed.firstChild);
            if(feed.children.length>5)feed.removeChild(feed.lastChild);
            setTimeout(()=>newItem.classList.remove('animate-pulse'),1000);
        },8000);

        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor=>{
            anchor.addEventListener('click',function(e){
                e.preventDefault();
                const target=document.querySelector(this.getAttribute('href'));
                if(target)target.scrollIntoView({behavior:'smooth',block:'start'});
            });
        });

        // Intersection Observer
        const observer=new IntersectionObserver((entries)=>{
            entries.forEach(entry=>{
                if(entry.isIntersecting){
                    entry.target.style.opacity='1';
                    entry.target.style.transform='translateY(0)';
                }
            });
        },{threshold:0.1,rootMargin:'0px 0px -50px 0px'});

        document.querySelectorAll('.glass, .platform-card').forEach((el,index)=>{
            el.style.opacity='0';
            el.style.transform='translateY(20px)';
            el.style.transition=`all 0.6s ease ${index*0.1}s`;
            observer.observe(el);
        });
    </script>
</body>
</html>
