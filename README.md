# Gigflow Money App

## Project Description
Gigflow Money App is a financial management application designed to help gig workers manage their income, expenses, and overall financial health effectively. The application provides tools for tracking earnings, managing expenses, and generating reports to gain insights into financial performance.

## Features
- **Income Tracking**: Easily log your gig earnings.
- **Expense Management**: Keep track of all your expenses.
- **Reports**: Generate financial reports to see your earnings vs. expenditures.
- **User-friendly Interface**: Designed for ease of use, making it accessible for everyone.
- **Secure Data Handling**: Your financial data is handled with utmost security.

## Live Demo
Check out the live demo of Gigflow Money App at [G<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GigFlow AI — Money Machine</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * { font-family: 'Inter', sans-serif; }
        h1, h2, h3, .brand { font-family: 'Space Grotesk', sans-serif; }
        
        .glass {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }
        
        .glow {
            box-shadow: 0 0 40px rgba(99, 102, 241, 0.3);
        }
        
        .money-gradient {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        
        .gold-gradient {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }
        
        .animate-pulse-slow {
            animation: pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }
        
        .typing-cursor::after {
            content: '|';
            animation: blink 1s infinite;
        }
        
        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }
        
        .slide-up {
            animation: slideUp 0.6s ease-out forwards;
        }
        
        @keyframes slideUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .count-up {
            font-variant-numeric: tabular-nums;
        }
        
        .tab-active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }
        
        .hover-lift {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .hover-lift:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }
        
        .progress-ring {
            transform: rotate(-90deg);
        }
        
        .progress-ring-circle {
            transition: stroke-dashoffset 0.35s;
        }
    </style>
</head>
<body class="bg-slate-950 text-white min-h-screen overflow-x-hidden">

    <!-- Navigation -->
    <nav class="fixed top-0 w-full z-50 glass border-b border-white/10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex items-center space-x-3">
                    <div class="w-10 h-10 money-gradient rounded-xl flex items-center justify-center glow">
                        <i class="fas fa-bolt text-white text-xl"></i>
                    </div>
                    <span class="brand text-2xl font-bold bg-gradient-to-r from-indigo-400 to-purple-400 bg-clip-text text-transparent">
                        GigFlow AI
                    </span>
                </div>
                
                <div class="hidden md:flex items-center space-x-6">
                    <div class="flex items-center space-x-2 px-4 py-2 glass rounded-full">
                        <div class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></div>
                        <span class="text-sm text-gray-300">Live Earnings: <span class="text-green-400 font-bold">$<span id="live-earnings">0.00</span></span></span>
                    </div>
                    <button onclick="showWithdraw()" class="px-6 py-2 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-full font-medium hover:shadow-lg hover:shadow-indigo-500/30 transition-all">
                        Withdraw
                    </button>
                    <div class="w-10 h-10 rounded-full bg-gradient-to-br from-pink-500 to-orange-400 flex items-center justify-center cursor-pointer hover:scale-110 transition-transform">
                        <i class="fas fa-user text-white"></i>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <!-- Main Content -->
    <main class="pt-24 pb-12 px-4 sm:px-6 lg:px-8 max-w-7xl mx-auto">
        
        <!-- Hero Stats -->
        <div class="grid grid-cols-1 md:grid-cols-4 gap-6 mb-8 slide-up">
            <div class="glass rounded-2xl p-6 hover-lift relative overflow-hidden">
                <div class="absolute top-0 right-0 w-32 h-32 bg-indigo-500/20 rounded-full blur-3xl -mr-16 -mt-16"></div>
                <p class="text-gray-400 text-sm mb-1">Today's Earnings</p>
                <h3 class="text-3xl font-bold text-white mb-2">$<span class="count-up" data-target="847">0</span></h3>
                <div class="flex items-center text-green-400 text-sm">
                    <i class="fas fa-arrow-up mr-1"></i>
                    <span>+23% from yesterday</span>
                </div>
            </div>
            
            <div class="glass rounded-2xl p-6 hover-lift relative overflow-hidden">
                <div class="absolute top-0 right-0 w-32 h-32 bg-purple-500/20 rounded-full blur-3xl -mr-16 -mt-16"></div>
                <p class="text-gray-400 text-sm mb-1">Active Projects</p>
                <h3 class="text-3xl font-bold text-white mb-2"><span class="count-up" data-target="12">0</span></h3>
                <div class="flex items-center text-indigo-400 text-sm">
                    <i class="fas fa-clock mr-1"></i>
                    <span>4 due today</span>
                </div>
            </div>
            
            <div class="glass rounded-2xl p-6 hover-lift relative overflow-hidden">
                <div class="absolute top-0 right-0 w-32 h-32 bg-pink-500/20 rounded-full blur-3xl -mr-16 -mt-16"></div>
                <p class="text-gray-400 text-sm mb-1">AI Proposals Sent</p>
                <h3 class="text-3xl font-bold text-white mb-2"><span class="count-up" data-target="48">0</span></h3>
                <div class="flex items-center text-green-400 text-sm">
                    <i class="fas fa-check mr-1"></i>
                    <span>8 accepted (17%)</span>
                </div>
            </div>
            
            <div class="glass rounded-2xl p-6 hover-lift relative overflow-hidden cursor-pointer" onclick="showUpgrade()">
                <div class="absolute top-0 right-0 w-32 h-32 bg-yellow-500/20 rounded-full blur-3xl -mr-16 -mt-16"></div>
                <p class="text-gray-400 text-sm mb-1">Current Tier</p>
                <h3 class="text-3xl font-bold bg-gradient-to-r from-yellow-400 to-orange-400 bg-clip-text text-transparent mb-2">Pro</h3>
                <div class="flex items-center text-yellow-400 text-sm">
                    <i class="fas fa-crown mr-1"></i>
                    <span>Upgrade to Max</span>
                </div>
            </div>
        </div>

        <!-- Main Dashboard Grid -->
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
            
            <!-- Left Column: AI Tools -->
            <div class="lg:col-span-2 space-y-6">
                
                <!-- AI Proposal Generator -->
                <div class="glass rounded-2xl p-6 slide-up" style="animation-delay: 0.1s">
                    <div class="flex justify-between items-center mb-6">
                        <div>
                            <h2 class="text-xl font-bold mb-1">AI Proposal Generator</h2>
                            <p class="text-gray-400 text-sm">Land clients on autopilot</p>
                        </div>
                        <div class="flex space-x-2">
                            <button onclick="setProposalType('upwork')" class="px-4 py-2 rounded-lg bg-white/5 hover:bg-white/10 text-sm transition-colors border border-white/10">Upwork</button>
                            <button onclick="setProposalType('fiverr')" class="px-4 py-2 rounded-lg bg-white/5 hover:bg-white/10 text-sm transition-colors border border-white/10">Fiverr</button>
                            <button onclick="setProposalType('cold')" class="px-4 py-2 rounded-lg bg-indigo-600 text-sm transition-colors">Cold Email</button>
                        </div>
                    </div>
                    
                    <div class="space-y-4">
                        <div>
                            <label class="block text-sm text-gray-400 mb-2">Job Description / Client Needs</label>
                            <textarea id="job-input" rows="3" class="w-full bg-slate-900/50 border border-white/10 rounded-xl p-4 text-white placeholder-gray-500 focus:outline-none focus:border-indigo-500 transition-colors resize-none" placeholder="Paste job description here... Need a React developer for e-commerce site..."></textarea>
                        </div>
                        
                        <div class="grid grid-cols-2 gap-4">
                            <div>
                                <label class="block text-sm text-gray-400 mb-2">Your Rate ($)</label>
                                <input type="number" id="rate-input" class="w-full bg-slate-900/50 border border-white/10 rounded-xl p-3 text-white focus:outline-none focus:border-indigo-500" placeholder="75">
                            </div>
                            <div>
                                <label class="block text-sm text-gray-400 mb-2">Tone</label>
                                <select id="tone-select" class="w-full bg-slate-900/50 border border-white/10 rounded-xl p-3 text-white focus:outline-none focus:border-indigo-500">
                                    <option>Professional</option>
                                    <option>Casual</option>
                                    <option>Enthusiastic</option>
                                    <option>Authority</option>
                                </select>
                            </div>
                        </div>
                        
                        <button onclick="generateProposal()" class="w-full py-4 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-xl font-semibold text-lg hover:shadow-lg hover:shadow-indigo-500/30 transition-all flex items-center justify-center space-x-2 group">
                            <i class="fas fa-magic group-hover:rotate-12 transition-transform"></i>
                            <span>Generate Winning Proposal</span>
                        </button>
                    </div>
                    
                    <!-- Generated Output -->
                    <div id="proposal-output" class="mt-6 hidden">
                        <div class="bg-slate-900/50 border border-green-500/30 rounded-xl p-4 relative">
                            <button onclick="copyProposal()" class="absolute top-4 right-4 text-gray-400 hover:text-white transition-colors">
                                <i class="fas fa-copy"></i>
                            </button>
                            <div id="proposal-text" class="text-gray-300 leading-relaxed typing-cursor"></div>
                        </div>
                        <div class="flex space-x-3 mt-4">
                            <button onclick="sendProposal()" class="flex-1 py-3 bg-green-600/20 border border-green-500/50 rounded-lg text-green-400 hover:bg-green-600/30 transition-colors">
                                <i class="fas fa-paper-plane mr-2"></i>Send Now
                            </button>
                            <button onclick="saveTemplate()" class="flex-1 py-3 bg-white/5 border border-white/10 rounded-lg text-gray-300 hover:bg-white/10 transition-colors">
                                <i class="fas fa-save mr-2"></i>Save Template
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Project Pipeline -->
                <div class="glass rounded-2xl p-6 slide-up" style="animation-delay: 0.2s">
                    <div class="flex justify-between items-center mb-6">
                        <h2 class="text-xl font-bold">Project Pipeline</h2>
                        <button onclick="addProject()" class="px-4 py-2 bg-white/5 hover:bg-white/10 rounded-lg text-sm transition-colors border border-white/10">
                            <i class="fas fa-plus mr-2"></i>New Project
                        </button>
                    </div>
                    
                    <div class="space-y-3" id="project-list">
                        <div class="bg-slate-900/30 border border-white/5 rounded-xl p-4 flex items-center justify-between group hover:border-indigo-500/30 transition-colors cursor-pointer">
                            <div class="flex items-center space-x-4">
                                <div class="w-12 h-12 rounded-lg bg-gradient-to-br from-blue-500 to-cyan-400 flex items-center justify-center">
                                    <i class="fas fa-code text-white"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">E-commerce Redesign</h4>
                                    <p class="text-sm text-gray-400">Due in 2 days • $2,400</p>
                                </div>
                            </div>
                            <div class="flex items-center space-x-3">
                                <div class="w-32 h-2 bg-slate-700 rounded-full overflow-hidden">
                                    <div class="h-full bg-gradient-to-r from-blue-500 to-cyan-400 w-3/4"></div>
                                </div>
                                <span class="text-sm text-gray-400">75%</span>
                            </div>
                        </div>
                        
                        <div class="bg-slate-900/30 border border-white/5 rounded-xl p-4 flex items-center justify-between group hover:border-purple-500/30 transition-colors cursor-pointer">
                            <div class="flex items-center space-x-4">
                                <div class="w-12 h-12 rounded-lg bg-gradient-to-br from-purple-500 to-pink-400 flex items-center justify-center">
                                    <i class="fas fa-paint-brush text-white"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Brand Identity System</h4>
                                    <p class="text-sm text-gray-400">Due in 5 days • $3,600</p>
                                </div>
                            </div>
                            <div class="flex items-center space-x-3">
                                <div class="w-32 h-2 bg-slate-700 rounded-full overflow-hidden">
                                    <div class="h-full bg-gradient-to-r from-purple-500 to-pink-400 w-1/3"></div>
                                </div>
                                <span class="text-sm text-gray-400">33%</span>
                            </div>
                        </div>
                        
                        <div class="bg-slate-900/30 border border-white/5 rounded-xl p-4 flex items-center justify-between group hover:border-green-500/30 transition-colors cursor-pointer">
                            <div class="flex items-center space-x-4">
                                <div class="w-12 h-12 rounded-lg bg-gradient-to-br from-green-500 to-emerald-400 flex items-center justify-center">
                                    <i class="fas fa-mobile-alt text-white"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Mobile App UI</h4>
                                    <p class="text-sm text-gray-400">Due tomorrow • $1,800</p>
                                </div>
                            </div>
                            <div class="flex items-center space-x-3">
                                <div class="w-32 h-2 bg-slate-700 rounded-full overflow-hidden">
                                    <div class="h-full bg-gradient-to-r from-green-500 to-emerald-400 w-11/12"></div>
                                </div>
                                <span class="text-sm text-gray-400">92%</span>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Smart Invoicing -->
                <div class="glass rounded-2xl p-6 slide-up" style="animation-delay: 0.3s">
                    <div class="flex justify-between items-center mb-6">
                        <h2 class="text-xl font-bold">Smart Invoicing</h2>
                        <div class="flex space-x-2">
                            <button class="px-3 py-1 rounded-lg bg-green-600/20 text-green-400 text-sm">Paid: $12.4k</button>
                            <button class="px-3 py-1 rounded-lg bg-yellow-600/20 text-yellow-400 text-sm">Pending: $8.2k</button>
                        </div>
                    </div>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div class="bg-slate-900/30 border border-white/5 rounded-xl p-4">
                            <div class="flex justify-between items-start mb-3">
                                <div>
                                    <p class="text-sm text-gray-400">Invoice #00124</p>
                                    <h4 class="font-semibold">TechStart Inc.</h4>
                                </div>
                                <span class="px-3 py-1 rounded-full bg-yellow-500/20 text-yellow-400 text-xs">Pending</span>
                            </div>
                            <p class="text-2xl font-bold mb-3">$4,500</p>
                            <button onclick="sendReminder()" class="w-full py-2 bg-white/5 hover:bg-white/10 rounded-lg text-sm transition-colors">
                                Send Reminder
                            </button>
                        </div>
                        
                        <div class="bg-slate-900/30 border border-white/5 rounded-xl p-4 border-dashed border-2 flex items-center justify-center cursor-pointer hover:bg-white/5 transition-colors" onclick="createInvoice()">
                            <div class="text-center">
                                <i class="fas fa-plus text-3xl text-gray-500 mb-2"></i>
                                <p class="text-gray-400">Create New Invoice</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Right Column: Income Streams & Tools -->
            <div class="space-y-6">
                
                <!-- Quick Actions -->
                <div class="glass rounded-2xl p-6 slide-up" style="animation-delay: 0.1s">
                    <h3 class="font-bold mb-4">Quick Money Actions</h3>
                    <div class="grid grid-cols-2 gap-3">
                        <button onclick="scanGigs()" class="p-4 bg-gradient-to-br from-indigo-600/20 to-purple-600/20 border border-indigo-500/30 rounded-xl hover:scale-105 transition-transform text-center group">
                            <i class="fas fa-search-dollar text-2xl text-indigo-400 mb-2 group-hover:scale-110 transition-transform block"></i>
                            <span class="text-sm font-medium">Scan Gigs</span>
                        </button>
                        <button onclick="priceProject()" class="p-4 bg-gradient-to-br from-pink-600/20 to-rose-600/20 border border-pink-500/30 rounded-xl hover:scale-105 transition-transform text-center group">
                            <i class="fas fa-calculator text-2xl text-pink-400 mb-2 group-hover:scale-110 transition-transform block"></i>
                            <span class="text-sm font-medium">Price Project</span>
                        </button>
                        <button onclick="clientFinder()" class="p-4 bg-gradient-to-br from-green-600/20 to-emerald-600/20 border border-green-500/30 rounded-xl hover:scale-105 transition-transform text-center group">
                            <i class="fas fa-user-plus text-2xl text-green-400 mb-2 group-hover:scale-110 transition-transform block"></i>
                            <span class="text-sm font-medium">Find Clients</span>
                        </button>
                        <button onclick="skillCash()" class="p-4 bg-gradient-to-br from-orange-600/20 to-amber-600/20 border border-orange-500/30 rounded-xl hover:scale-105 transition-transform text-center group">
                            <i class="fas fa-graduation-cap text-2xl text-orange-400 mb-2 group-hover:scale-110 transition-transform block"></i>
                            <span class="text-sm font-medium">Skill Cash</span>
                        </button>
                    </div>
                </div>

                <!-- Income Breakdown -->
                <div class="glass rounded-2xl p-6 slide-up" style="animation-delay: 0.2s">
                    <h3 class="font-bold mb-4">Income Streams</h3>
                    <div class="space-y-4">
                        <div class="flex items-center justify-between">
                            <div class="flex items-center space-x-3">
                                <div class="w-10 h-10 rounded-lg bg-blue-500/20 flex items-center justify-center">
                                    <i class="fas fa-laptop-code text-blue-400"></i>
                                </div>
                                <div>
                                    <p class="font-medium">Development</p>
                                    <p class="text-xs text-gray-400">45% of income</p>
                                </div>
                            </div>
                            <span class="font-bold">$5,400</span>
                        </div>
                        
                        <div class="flex items-center justify-between">
                            <div class="flex items-center space-x-3">
                                <div class="w-10 h-10 rounded-lg bg-purple-500/20 flex items-center justify-center">
                                    <i class="fas fa-palette text-purple-400"></i>
                                </div>
                                <div>
                                    <p class="font-medium">Design</p>
                                    <p class="text-xs text-gray-400">30% of income</p>
                                </div>
                            </div>
                            <span class="font-bold">$3,600</span>
                        </div>
                        
                        <div class="flex items-center justify-between">
                            <div class="flex items-center space-x-3">
                                <div class="w-10 h-10 rounded-lg bg-green-500/20 flex items-center justify-center">
                                    <i class="fas fa-robot text-green-400"></i>
                                </div>
                                <div>
                                    <p class="font-medium">AI Automation</p>
                                    <p class="text-xs text-gray-400">15% of income</p>
                                </div>
                            </div>
                            <span class="font-bold">$1,800</span>
                        </div>
                        
                        <div class="flex items-center justify-between">
                            <div class="flex items-center space-x-3">
                                <div class="w-10 h-10 rounded-lg bg-yellow-500/20 flex items-center justify-center">
                                    <i class="fas fa-book text-yellow-400"></i>
                                </div>
                                <div>
                                    <p class="font-medium">Digital Products</p>
                                    <p class="text-xs text-gray-400">10% of income</p>
                                </div>
                            </div>
                            <span class="font-bold">$1,200</span>
                        </div>
                    </div>
                    
                    <button onclick="diversifyIncome()" class="w-full mt-6 py-3 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-xl font-medium hover:shadow-lg transition-all">
                        Diversify Income
                    </button>
                </div>

                <!-- AI Assistant -->
                <div class="glass rounded-2xl p-6 slide-up relative overflow-hidden" style="animation-delay: 0.3s">
                    <div class="absolute top-0 right-0 w-40 h-40 bg-indigo-500/20 rounded-full blur-3xl -mr-20 -mt-20"></div>
                    <div class="flex items-center space-x-3 mb-4">
                        <div class="w-10 h-10 rounded-full bg-gradient-to-r from-indigo-500 to-purple-500 flex items-center justify-center animate-pulse-slow">
                            <i class="fas fa-robot text-white"></i>
                        </div>
                        <div>
                            <h3 class="font-bold">GigBot AI</h3>
                            <p class="text-xs text-green-400">● Online</p>
                        </div>
                    </div>
                    
                    <div class="bg-slate-900/50 rounded-xl p-4 mb-4 h-48 overflow-y-auto space-y-3 text-sm" id="chat-messages">
                        <div class="flex space-x-2">
                            <div class="w-6 h-6 rounded-full bg-indigo-600 flex-shrink-0 flex items-center justify-center text-xs">AI</div>
                            <div class="bg-white/5 rounded-lg p-2 rounded-tl-none">
                                <p>Hey! I found 3 high-paying gigs matching your skills. Want me to apply?</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="flex space-x-2">
                        <input type="text" id="chat-input" placeholder="Ask me anything..." class="flex-1 bg-slate-900/50 border border-white/10 rounded-lg px-4 py-2 text-sm focus:outline-none focus:border-indigo-500">
                        <button onclick="sendMessage()" class="px-4 py-2 bg-indigo-600 rounded-lg hover:bg-indigo-700 transition-colors">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </div>
                </div>

                <!-- Daily Goal -->
                <div class="glass rounded-2xl p-6 slide-up" style="animation-delay: 0.4s">
                    <div class="flex justify-between items-center mb-4">
                        <h3 class="font-bold">Daily Goal</h3>
                        <span class="text-sm text-green-400">85% Complete</span>
                    </div>
                    
                    <div class="relative w-32 h-32 mx-auto mb-4">
                        <svg class="w-full h-full transform -rotate-90">
                            <circle cx="64" cy="64" r="56" stroke="rgba(255,255,255,0.1)" stroke-width="8" fill="none"></circle>
                            <circle cx="64" cy="64" r="56" stroke="url(#gradient)" stroke-width="8" fill="none" stroke-dasharray="351.86" stroke-dashoffset="52.78" stroke-linecap="round"></circle>
                            <defs>
                                <linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="0%">
                                    <stop offset="0%" stop-color="#667eea"></stop>
                                    <stop offset="100%" stop-color="#764ba2"></stop>
                                </linearGradient>
                            </defs>
                        </svg>
                        <div class="absolute inset-0 flex items-center justify-center flex-col">
                            <span class="text-2xl font-bold">$425</span>
                            <span class="text-xs text-gray-400">of $500</span>
                        </div>
                    </div>
                    
                    <div class="space-y-2">
                        <div class="flex items-center space-x-2 text-sm">
                            <i class="fas fa-check-circle text-green-400"></i>
                            <span class="text-gray-300 line-through">Send 5 proposals</span>
                        </div>
                        <div class="flex items-center space-x-2 text-sm">
                            <i class="fas fa-check-circle text-green-400"></i>
                            <span class="text-gray-300 line-through">Complete 2 deliverables</span>
                        </div>
                        <div class="flex items-center space-x-2 text-sm">
                            <i class="fas fa-circle text-gray-600"></i>
                            <span class="text-gray-300">Follow up with 3 clients</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <!-- Modals -->
    <div id="modal" class="fixed inset-0 z-50 hidden items-center justify-center bg-black/80 backdrop-blur-sm p-4">
        <div class="glass rounded-2xl p-6 max-w-md w-full transform scale-95 opacity-0 transition-all duration-300" id="modal-content">
            <div class="flex justify-between items-center mb-4">
                <h3 class="text-xl font-bold" id="modal-title">Title</h3>
                <button onclick="closeModal()" class="text-gray-400 hover:text-white">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            <div id="modal-body"></div>
        </div>
    </div>

    <script>
        // Live earnings counter
        let liveEarnings = 0;
        setInterval(() => {
            liveEarnings += Math.random() * 2;
            document.getElementById('live-earnings').textContent = liveEarnings.toFixed(2);
        }, 3000);

        // Count up animation
        const counters = document.querySelectorAll('.count-up');
        counters.forEach(counter => {
            const target = +counter.getAttribute('data-target');
            const increment = target / 100;
            let current = 0;
            
            const updateCounter = () => {
                if (current < target) {
                    current += increment;
                    counter.innerText = Math.ceil(current);
                    setTimeout(updateCounter, 20);
                } else {
                    counter.innerText = target;
                }
            };
            updateCounter();
        });

        // Proposal Generator
        let proposalType = 'cold';
        
        function setProposalType(type) {
            proposalType = type;
            document.querySelectorAll('[onclick^="setProposalType"]').forEach(btn => {
                btn.classList.remove('bg-indigo-600');
                btn.classList.add('bg-white/5');
            });
            event.target.classList.remove('bg-white/5');
            event.target.classList.add('bg-indigo-600');
        }

        function generateProposal() {
            const jobInput = document.getElementById('job-input').value;
            const rate = document.getElementById('rate-input').value || '75';
            const tone = document.getElementById('tone-select').value;
            
            if (!jobInput) {
                alert('Please enter a job description first!');
                return;
            }
            
            const output = document.getElementById('proposal-output');
            const text = document.getElementById('proposal-text');
            output.classList.remove('hidden');
            
            const proposals = {
                professional: `Hi there,\n\nI noticed you're looking for a skilled professional to handle this project. With 5+ years of experience delivering similar results, I'm confident I can exceed your expectations.\n\n**Why me?**\n✓ 100% client satisfaction rate\n✓ Specialized in delivering on time\n✓ Clear communication throughout\n\n**Investment:** $${rate}/hour\n**Timeline:** As discussed\n\nI'd love to discuss how we can make this project a success. Ready to start immediately.\n\nBest regards,\n[Your Name]`,
                
                casual: `Hey! 👋\n\nSaw your post and got excited - this is exactly the kind of work I love doing! I've helped similar clients achieve awesome results.\n\n**What you get:**\n• Quality work without the agency markup\n• Direct communication (no middlemen)\n• Fast turnaround\n\n**Rate:** $${rate}/hour (flexible for long-term)\n\nWant to hop on a quick call to chat about it? Coffee's on me! ☕\n\nCheers,\n[Your Name]`,
                
                authority: `Re: Project Opportunity\n\nI've reviewed your requirements and identified three critical success factors for this initiative:\n\n1. **Technical Excellence** — Delivering robust, scalable solutions\n2. **Strategic Alignment** — Ensuring business objectives are met\n3. **Risk Mitigation** — Proactive problem-solving\n\n**My track record:**\n• $2M+ in client revenue generated\n• 50+ successful projects delivered\n• Zero missed deadlines in 3 years\n\n**Investment:** $${rate}/hour\n**Availability:** Immediate\n\nI invite you to review my portfolio and schedule a consultation to discuss strategy.\n\nProfessional regards,\n[Your Name]`
            };
            
            const selectedProposal = tone === 'Casual' ? proposals.casual : tone === 'Authority' ? proposals.authority : proposals.professional;
            
            let i = 0;
            text.textContent = '';
            const typeWriter = () => {
                if (i < selectedProposal.length) {
                    text.textContent += selectedProposal.charAt(i);
                    i++;
                    setTimeout(typeWriter, 20);
                }
            };
            typeWriter();
        }

        function copyProposal() {
            const text = document.getElementById('proposal-text').textContent;
            navigator.clipboard.writeText(text);
            showNotification('Proposal copied to clipboard!');
        }

        function sendProposal() {
            showNotification('Proposal sent successfully! +$150 potential value');
            incrementEarnings(150);
        }

        function saveTemplate() {
            showNotification('Template saved for future use!');
        }

        // Chat functionality
        function sendMessage() {
            const input = document.getElementById('chat-input');
            const message = input.value.trim();
            if (!message) return;
            
            const chatMessages = document.getElementById('chat-messages');
            
            // User message
            chatMessages.innerHTML += `
                <div class="flex space-x-2 justify-end">
                    <div class="bg-indigo-600 rounded-lg p-2 rounded-tr-none max-w-[80%]">
                        <p>${message}</p>
                    </div>
                </div>
            `;
            
            input.value = '';
            chatMessages.scrollTop = chatMessages.scrollHeight;
            
            // AI response simulation
            setTimeout(() => {
                const responses = [
                    "I've analyzed your portfolio. I recommend targeting SaaS companies - they pay 40% above market rate.",
                    "Great question! Based on current trends, adding AI automation skills could increase your rates by 60%.",
                    "I found 2 urgent gigs matching your expertise. Shall I draft proposals?",
                    "Pro tip: Raise your rates by 20%. Your conversion rate suggests you're undervaluing your work."
                ];
                const randomResponse = responses[Math.floor(Math.random() * responses.length)];
                
                chatMessages.innerHTML += `
                    <div class="flex space-x-2">
                        <div class="w-6 h-6 rounded-full bg-indigo-600 flex-shrink-0 flex items-center justify-center text-xs">AI</div>
                        <div class="bg-white/5 rounded-lg p-2 rounded-tl-none max-w-[80%]">
                            <p>${randomResponse}</p>
                        </div>
                    </div>
                `;
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }, 1000);
        }

        // Quick Actions
        function scanGigs() {
            showModal('Gig Scanner', `
                <div class="space-y-4">
                    <div class="bg-slate-900/50 p-4 rounded-lg border border-green-500/30">
                        <div class="flex justify-between items-start mb-2">
                            <h4 class="font-semibold text-green-400">React Developer Needed</h4>
                            <span class="text-xs bg-green-500/20 text-green-400 px-2 py-1 rounded">$120/hr</span>
                        </div>
                        <p class="text-sm text-gray-400 mb-3">Enterprise dashboard project • Remote • Start Monday</p>
                        <button class="w-full py-2 bg-green-600/20 border border-green-500/50 rounded text-green-400 hover:bg-green-600/30 transition-colors">Apply with AI</button>
                    </div>
                    <div class="bg-slate-900/50 p-4 rounded-lg border border-indigo-500/30">
                        <div class="flex justify-between items-start mb-2">
                            <h4 class="font-semibold text-indigo-400">UI/UX Designer</h4>
                            <span class="text-xs bg-indigo-500/20 text-indigo-400 px-2 py-1 rounded">$95/hr</span>
                        </div>
                        <p class="text-sm text-gray-400 mb-3">Mobile app redesign • 2 week sprint</p>
                        <button class="w-full py-2 bg-indigo-600/20 border border-indigo-500/50 rounded text-indigo-400 hover:bg-indigo-600/30 transition-colors">Apply with AI</button>
                    </div>
                </div>
            `);
        }

        function priceProject() {
            showModal('Project Pricing Calculator', `
                <div class="space-y-4">
                    <div>
                        <label class="block text-sm text-gray-400 mb-2">Project Type</label>
                        <select class="w-full bg-slate-900/50 border border-white/10 rounded-lg p-3 text-white mb-4">
                            <option>Web Development</option>
                            <option>Mobile App</option>
                            <option>UI/UX Design</option>
                            <option>Consulting</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-sm text-gray-400 mb-2">Estimated Hours</label>
                        <input type="number" class="w-full bg-slate-900/50 border border-white/10 rounded-lg p-3 text-white mb-4" placeholder="40">
                    </div>
                    <div>
                        <label class="block text-sm text-gray-400 mb-2">Complexity</label>
                        <div class="flex space-x-2">
                            <button class="flex-1 py-2 bg-white/5 rounded-lg text-sm hover:bg-white/10">Simple</button>
                            <button class="flex-1 py-2 bg-indigo-600 rounded-lg text-sm">Medium</button>
                            <button class="flex-1 py-2 bg-white/5 rounded-lg text-sm hover:bg-white/10">Complex</button>
                        </div>
                    </div>
                    <div class="bg-gradient-to-r from-indigo-600/20 to-purple-600/20 p-4 rounded-lg border border-indigo-500/30 mt-4">
                        <p class="text-sm text-gray-400">Recommended Price</p>
                        <p class="text-3xl font-bold text-white">$4,800 - $6,400</p>
                        <p class="text-xs text-gray-500 mt-1">Based on market rates + your experience level</p>
                    </div>
                </div>
            `);
        }

        function clientFinder() {
            showModal('AI Client Finder', `
                <div class="space-y-4">
                    <p class="text-sm text-gray-400">Scanning LinkedIn, Twitter, and job boards for high-intent prospects...</p>
                    <div class="space-y-3">
                        <div class="flex items-center space-x-3 p-3 bg-slate-900/50 rounded-lg">
                            <div class="w-10 h-10 rounded-full bg-blue-500 flex items-center justify-center">JD</div>
                            <div class="flex-1">
                                <p class="font-medium">John Doe</p>
                                <p class="text-xs text-gray-400">CTO at TechStart • Posted "Looking for devs"</p>
                            </div>
                            <button class="px-3 py-1 bg-indigo-600 rounded text-sm">Connect</button>
                        </div>
                        <div class="flex items-center space-x-3 p-3 bg-slate-900/50 rounded-lg">
                            <div class="w-10 h-10 rounded-full bg-purple-500 flex items-center justify-center">AS</div>
                            <div class="flex-1">
                                <p class="font-medium">Alice Smith</p>
                                <p class="text-xs text-gray-400">Founder • Just raised Series A</p>
                            </div>
                            <button class="px-3 py-1 bg-indigo-600 rounded text-sm">Connect</button>
                        </div>
                    </div>
                </div>
            `);
        }

        function skillCash() {
            showModal('Monetize Your Skills', `
                <div class="grid grid-cols-2 gap-3">
                    <div class="p-4 bg-slate-900/50 rounded-lg border border-white/10 hover:border-indigo-500/50 cursor-pointer transition-colors">
                        <i class="fas fa-video text-2xl text-red-400 mb-2"></i>
                        <p class="font-medium text-sm">Create Course</p>
                        <p class="text-xs text-gray-400">Passive income</p>
                    </div>
                    <div class="p-4 bg-slate-900/50 rounded-lg border border-white/10 hover:border-indigo-500/50 cursor-pointer transition-colors">
                        <i class="fas fa-book text-2xl text-blue-400 mb-2"></i>
                        <p class="font-medium text-sm">Write E-book</p>
                        <p class="text-xs text-gray-400">$20-50/sale</p>
                    </div>
                    <div class="p-4 bg-slate-900/50 rounded-lg border border-white/10 hover:border-indigo-500/50 cursor-pointer transition-colors">
                        <i class="fas fa-users text-2xl text-green-400 mb-2"></i>
                        <p class="font-medium text-sm">Group Coaching</p>
                        <p class="text-xs text-gray-400">$500/session</p>
                    </div>
                    <div class="p-4 bg-slate-900/50 rounded-lg border border-white/10 hover:border-indigo-500/50 cursor-pointer transition-colors">
                        <i class="fas fa-code text-2xl text-yellow-400 mb-2"></i>
                        <p class="font-medium text-sm">Sell Templates</p>
                        <p class="text-xs text-gray-400">Marketplace</p>
                    </div>
                </div>
            `);
        }

        function showWithdraw() {
            showModal('Withdraw Earnings', `
                <div class="space-y-4">
                    <div class="text-center p-6 bg-gradient-to-br from-green-600/20 to-emerald-600/20 rounded-xl border border-green-500/30">
                        <p class="text-gray-400 mb-1">Available Balance</p>
                        <p class="text-4xl font-bold text-white mb-2">$12,847.00</p>
                        <p class="text-xs text-green-400">Ready to withdraw</p>
                    </div>
                    <div class="space-y-2">
                        <button class="w-full p-4 bg-slate-900/50 rounded-lg flex items-center justify-between hover:bg-white/5 transition-colors">
                            <div class="flex items-center space-x-3">
                                <i class="fas fa-university text-xl text-gray-400"></i>
                                <span>Bank Transfer</span>
                            </div>
                            <span class="text-sm text-gray-400">1-2 days</span>
                        </button>
                        <button class="w-full p-4 bg-slate-900/50 rounded-lg flex items-center justify-between hover:bg-white/5 transition-colors">
                            <div class="flex items-center space-x-3">
                                <i class="fab fa-paypal text-xl text-blue-400"></i>
                                <span>PayPal</span>
                            </div>
                            <span class="text-sm text-gray-400">Instant</span>
                        </button>
                        <button class="w-full p-4 bg-slate-900/50 rounded-lg flex items-center justify-between hover:bg-white/5 transition-colors">
                            <div class="flex items-center space-x-3">
                                <i class="fab fa-bitcoin text-xl text-orange-400"></i>
                                <span>Crypto</span>
                            </div>
                            <span class="text-sm text-gray-400">10 min</span>
                        </button>
                    </div>
                </div>
            `);
        }

        function showUpgrade() {
            showModal('Upgrade to GigFlow Max', `
                <div class="space-y-4">
                    <div class="bg-gradient-to-r from-yellow-600/20 to-orange-600/20 p-4 rounded-xl border border-yellow-500/30 text-center">
                        <i class="fas fa-crown text-4xl text-yellow-400 mb-2"></i>
                        <h4 class="text-xl font-bold mb-1">Max Tier</h4>
                        <p class="text-2xl font-bold text-white">$49/month</p>
                    </div>
                    <ul class="space-y-2 text-sm">
                        <li class="flex items-center space-x-2"><i class="fas fa-check text-green-400"></i><span>Unlimited AI proposals</span></li>
                        <li class="flex items-center space-x-2"><i class="fas fa-check text-green-400"></i><span>Auto-apply to gigs</span></li>
                        <li class="flex items-center space-x-2"><i class="fas fa-check text-green-400"></i><span>Client CRM & pipeline</span></li>
                        <li class="flex items-center space-x-2"><i class="fas fa-check text-green-400"></i><span>Priority support</span></li>
                        <li class="flex items-center space-x-2"><i class="fas fa-check text-green-400"></i><span>0% platform fees</span></li>
                    </ul>
                    <button class="w-full py-3 bg-gradient-to-r from-yellow-600 to-orange-600 rounded-xl font-bold hover:shadow-lg transition-all">
                        Upgrade Now
                    </button>
                </div>
            `);
        }

        function sendReminder() {
            showNotification('Reminder sent to client!');
        }

        function createInvoice() {
            showNotification('New invoice created!');
        }

        function addProject() {
            showNotification('New project added to pipeline!');
        }

        function diversifyIncome() {
            showNotification('Opening income diversification guide...');
        }

        // Utility functions
        function showModal(title, content) {
            document.getElementById('modal-title').textContent = title;
            document.getElementById('modal-body').innerHTML = content;
            const modal = document.getElementById('modal');
            const modalContent = document.getElementById('modal-content');
            modal.classList.remove('hidden');
            modal.classList.add('flex');
            setTimeout(() => {
                modalContent.classList.remove('scale-95', 'opacity-0');
                modalContent.classList.add('scale-100', 'opacity-100');
            }, 10);
        }

        function closeModal() {
            const modal = document.getElementById('modal');
            const modalContent = document.getElementById('modal-content');
            modalContent.classList.remove('scale-100', 'opacity-100');
            modalContent.classList.add('scale-95', 'opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
                modal.classList.remove('flex');
            }, 300);
        }

        function showNotification(message) {
            const notif = document.createElement('div');
            notif.className = 'fixed bottom-4 right-4 bg-indigo-600 text-white px-6 py-3 rounded-xl shadow-lg transform translate-y-10 opacity-0 transition-all duration-300 z-50';
            notif.textContent = message;
            document.body.appendChild(notif);
            setTimeout(() => {
                notif.classList.remove('translate-y-10', 'opacity-0');
            }, 10);
            setTimeout(() => {
                notif.classList.add('translate-y-10', 'opacity-0');
                setTimeout(() => notif.remove(), 300);
            }, 3000);
        }

        function incrementEarnings(amount) {
            const counter = document.querySelector('[data-target="847"]');
            let current = parseInt(counter.textContent);
            counter.textContent = current + amount;
        }

        // Close modal on outside click
        document.getElementById('modal').addEventListener('click', (e) => {
            if (e.target.id === 'modal') closeModal();
        });

        // Enter key for chat
        document.getElementById('chat-input').addEventListener('keypress', (e) => {
            if (e.key === 'Enter') sendMessage();
        });
    </script>
</body>
</html>
igflow Demo](http://example.com/live-demo).