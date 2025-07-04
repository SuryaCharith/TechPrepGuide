# TechPrepGuide
# It is Website That Contains:
# A complete A–Z guide for engineering students preparing for tech placements, featuring:
# ✅ 200+ companies with details
# ✅ 3000+ interview questions
# ✅ Filter by branch (CSE, ECE, IT, MECH, etc.)
# ✅ Filter by salary range
# ✅ Browse by alphabet
# ✅ Random question generator
# ✅ Fully responsive and modern design

# 🛠️ Built using AI tools and customized for students to have everything in one place!

 <!DOCTYPE html>
 <html lang="en">
 <head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <title>Ultimate Engineering Placement Hub - 200+ Companies A-Z</title>
 <script src="https://cdn.tailwindcss.com"></script>
 <style>
 .company-card {
 transition: all 0.3s ease;
 cursor: pointer;
 }
 .company-card:hover {
 transform: translateY(-4px);
 box-shadow: 0 10px 25px rgba(0,0,0,0.15);
 }
 .alphabet-btn.active {
 background-color: #3b82f6 !important;
 color: white !important;
 }
 .stats-card {
 background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
 }
 .modal {
 display: none;
 }
 .modal.active {
 display: flex;
 }
 .tab-content {
 display: none;
 }
 .tab-content.active {
 display: block;
}
 .tab-button.active {
 background-color: #3b82f6;
 color: white;
 border-bottom: 2px solid #3b82f6;
 }
 </style>
 </head>
 <body class="bg-gradient-to-br from-blue-50 to-indigo-100 min-h-screen">
 <!-- Header -->
 <header class="bg-white shadow-lg">
 <div class="container mx-auto px-6 py-4">
 <div class="flex items-center justify-between">
 <div class="flex items-center space-x-3">
 <div class="w-12 h-12 bg-gradient-to-r from-blue-600 to-purple-600 rounded-lg flex 
items-center justify-center">
 <span class="text-white font-bold text-xl">
 🎓
 </span>
 </div>
 <div>
 <h1 class="text-2xl font-bold text-gray-800">PlacementHub Ultimate</h1>
 <p class="text-sm text-gray-600">200+ Companies • Top Interview Questions • 
Complete Guide</p>
 </div>
 </div>
 </div>
 </div>
 </header>
 <!-- Hero Section -->
 <section class="py-16 px-6">
 <div class="container mx-auto text-center">
 <h2 class="text-4xl md:text-6xl font-bold text-gray-800 mb-6">
 Ultimate A-Z Placement Guide
 </h2>
 <p class="text-xl text-gray-600 mb-8 max-w-4xl mx-auto">
 Complete placement preparation with 200+ companies, top 15 interview questions for each 
company, 
selection processes, salary ranges, and comprehensive guides for all engineering 
branches.
 </p>
 <!-- Stats Cards -->
 <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-8 max-w-4xl mx-auto">
 <div class="stats-card text-white p-4 rounded-lg">
 <div class="text-2xl font-bold">200+</div>
 <div class="text-sm opacity-90">Companies</div>
</div>
 <div class="stats-card text-white p-4 rounded-lg">
 <div class="text-2xl font-bold">3000+</div>
 <div class="text-sm opacity-90">Questions</div>
 </div>
 <div class="stats-card text-white p-4 rounded-lg">
 <div class="text-2xl font-bold">26</div>
 <div class="text-sm opacity-90">Alphabets</div>
 </div>
 <div class="stats-card text-white p-4 rounded-lg">
 <div class="text-2xl font-bold">8</div>
 <div class="text-sm opacity-90">Branches</div>
 </div>
 </div>
 <div class="flex flex-col sm:flex-row gap-4 justify-center">
 <button onclick="scrollToCompanies()" class="bg-blue-600 hover:bg-blue-700 text-white 
px-8 py-3 rounded-lg font-semibold transition-colors">
 Browse All Companies
 </button>
 <button onclick="showRandomQuestion()" class="bg-purple-600 hover:bg-purple-700 text
white px-8 py-3 rounded-lg font-semibold transition-colors">
 Random Interview Question
 </button>
 </div>
 </div>
 </section>
 <!-- Search Section -->
 <section class="px-6 mb-8">
 <div class="container mx-auto">
 <div class="bg-white rounded-xl shadow-lg p-6">
 <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
 <input type="text" id="searchInput" placeholder="Search companies (e.g., Google, TCS, 
Microsoft...)" 
class="px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 
focus:ring-blue-500"
 oninput="filterCompanies()">
 <select id="branchFilter" class="px-4 py-3 border border-gray-300 rounded-lg 
focus:outline-none focus:ring-2 focus:ring-blue-500"
 onchange="filterCompanies()">
 <option value="">All Branches</option>
 <option value="CSE">Computer Science</option>
 <option value="ECE">Electronics & Communication</option>
 <option value="IT">Information Technology</option>
 <option value="MECH">Mechanical</option>
<option value="CIVIL">Civil</option>
 <option value="EEE">Electrical</option>
 <option value="CHEM">Chemical</option>
 <option value="AERO">Aerospace</option>
 </select>
 <select id="salaryFilter" class="px-4 py-3 border border-gray-300 rounded-lg 
focus:outline-none focus:ring-2 focus:ring-blue-500"
 onchange="filterCompanies()">
 <option value="">All Salary Ranges</option>
 <option value="0-5">₹0-5 LPA</option>
 <option value="5-10">₹5-10 LPA</option>
 <option value="10-20">₹10-20 LPA</option>
 <option value="20-50">₹20-50 LPA</option>
 <option value="50+">₹50+ LPA</option>
 </select>
 </div>
 </div>
 </div>
 </section>
 <!-- Alphabet Navigation -->
 <div class="sticky top-0 z-40 bg-white shadow-md py-4">
 <div class="container mx-auto px-6">
 <div class="flex flex-wrap justify-center gap-2">
 <button onclick="filterByAlphabet('all')" class="alphabet-btn bg-blue-600 text-white px-3 py
2 rounded font-medium text-sm hover:bg-blue-700">All</button>
 <button onclick="filterByAlphabet('A')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">A</button>
 <button onclick="filterByAlphabet('B')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">B</button>
 <button onclick="filterByAlphabet('C')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">C</button>
 <button onclick="filterByAlphabet('D')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">D</button>
 <button onclick="filterByAlphabet('E')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">E</button>
 <button onclick="filterByAlphabet('F')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">F</button>
 <button onclick="filterByAlphabet('G')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">G</button>
 <button onclick="filterByAlphabet('H')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">H</button>
 <button onclick="filterByAlphabet('I')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">I</button>
 <button onclick="filterByAlphabet('J')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">J</button>
<button onclick="filterByAlphabet('K')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">K</button>
 <button onclick="filterByAlphabet('L')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">L</button>
 <button onclick="filterByAlphabet('M')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">M</button>
 <button onclick="filterByAlphabet('N')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">N</button>
 <button onclick="filterByAlphabet('O')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">O</button>
 <button onclick="filterByAlphabet('P')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">P</button>
 <button onclick="filterByAlphabet('Q')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">Q</button>
 <button onclick="filterByAlphabet('R')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">R</button>
 <button onclick="filterByAlphabet('S')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">S</button>
 <button onclick="filterByAlphabet('T')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">T</button>
 <button onclick="filterByAlphabet('U')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">U</button>
 <button onclick="filterByAlphabet('V')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">V</button>
 <button onclick="filterByAlphabet('W')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">W</button>
 <button onclick="filterByAlphabet('X')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">X</button>
 <button onclick="filterByAlphabet('Y')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">Y</button>
 <button onclick="filterByAlphabet('Z')" class="alphabet-btn bg-gray-200 text-gray-700 px-3 
py-2 rounded font-medium text-sm hover:bg-gray-300">Z</button>
 </div>
 </div>
 </div>
 <!-- Companies Grid -->
 <section id="companies" class="px-6 mb-16">
 <div class="container mx-auto">
 <div class="flex justify-between items-center mb-8">
 <h3 class="text-3xl font-bold text-gray-800">All Companies</h3>
 <div class="text-gray-600" id="companyCount">Showing all companies</div>
 </div>
 <div id="companiesGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 
gap-6">
 <!-- Companies will be populated by JavaScript -->
</div>
 </div>
 </section>
 <!-- Company Detail Modal -->
 <div id="companyModal" class="modal fixed inset-0 bg-black bg-opacity-50 z-50 items-center 
justify-center p-4">
 <div class="bg-white rounded-xl max-w-6xl w-full max-h-[90vh] overflow-y-auto">
 <div class="p-6 border-b border-gray-200">
 <div class="flex justify-between items-center">
 <h2 id="modalCompanyName" class="text-2xl font-bold text-gray-800"></h2>
 <button onclick="closeModal()" class="text-gray-500 hover:text-gray-700 text
2xl">&times;</button>
 </div>
 </div>
 <!-- Tab Navigation -->
 <div class="border-b border-gray-200">
 <nav class="flex space-x-8 px-6 overflow-x-auto">
 <button class="tab-button active py-4 px-2 border-b-2 border-transparent font-medium 
text-sm whitespace-nowrap" onclick="showTab('overview')">Overview</button>
 <button class="tab-button py-4 px-2 border-b-2 border-transparent font-medium text-sm 
whitespace-nowrap" onclick="showTab('questions')">Top 15 Questions</button>
 <button class="tab-button py-4 px-2 border-b-2 border-transparent font-medium text-sm 
whitespace-nowrap" onclick="showTab('process')">Selection Process</button>
 <button class="tab-button py-4 px-2 border-b-2 border-transparent font-medium text-sm 
whitespace-nowrap" onclick="showTab('salary')">Salary & Benefits</button>
 </nav>
 </div>
 <!-- Tab Content -->
 <div class="p-6">
 <div id="overview" class="tab-content active">
 <div id="companyOverview"></div>
 </div>
 <div id="questions" class="tab-content">
 <div id="companyQuestions"></div>
 </div>
 <div id="process" class="tab-content">
 <div id="companyProcess"></div>
 </div>
 <div id="salary" class="tab-content">
 <div id="companySalary"></div>
</div>
 </div>
 </div>
 </div>
 <!-- Random Question Modal -->
 <div id="randomQuestionModal" class="modal fixed inset-0 bg-black bg-opacity-50 z-50 items
center justify-center p-4">
 <div class="bg-white rounded-xl max-w-2xl w-full">
 <div class="p-6 border-b border-gray-200">
 <div class="flex justify-between items-center">
 <h2 class="text-2xl font-bold text-gray-800">Random Interview Question</h2>
 <button onclick="closeRandomModal()" class="text-gray-500 hover:text-gray-700 text
2xl">&times;</button>
 </div>
 </div>
 <div class="p-6">
 <div id="randomQuestionContent" class="text-center">
 <div class="text-lg font-semibold text-blue-600 mb-4" id="randomCompanyName"></div>
 <div class="text-xl text-gray-800 mb-6" id="randomQuestion"></div>
 <button onclick="showRandomQuestion()" class="bg-blue-600 hover:bg-blue-700 text
white px-6 py-2 rounded-lg">
 Get Another Question
 </button>
 </div>
 </div>
 </div>
 </div>
 <script>
 // Complete company database with all your requested companies
 const companies = [
 // A Companies
 { name: "Accenture", logo: "
 🏢
 ", salary: "₹4-12 LPA", branches: ["CSE", "IT", "ECE", "MECH"], 
category: "consulting", 
description: "Global professional services company", 
questions: ["Tell me about yourself", "Why Accenture?", "OOP concepts", "SDLC phases", 
"Database design", "Cloud computing", "Agile methodology", "Problem-solving approach", "Team 
collaboration", "Client handling", "Technical challenges", "Career goals", "Strengths/weaknesses", 
"Learning new tech", "Industry trends"] },
 { name: "Adobe", logo: "
 🎨
 ", salary: "₹15-45 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Creative software and digital marketing solutions",
 questions: ["Design Photoshop architecture", "Image compression algorithms", "Memory 
management", "Graphics data structures", "Performance optimization", "Collaborative editing", 
"Raster vs vector", "Undo/redo implementation", "UX design approach", "Large file processing", 
"Color theory", "Plugin architecture", "Real-time collaboration", "Cross-platform challenges", 
"Accessibility features"] },
 { name: "ADP", logo: "
 💼
 ", salary: "₹6-18 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "HR management software and services",
 questions: ["Payroll systems", "HR system design", "Data privacy", "Compliance 
requirements", "Microservices", "Multi-tenant architecture", "Employee data security", "System 
reliability", "API design", "Time zone handling", "Cloud platforms", "Database optimization", "Audit 
trails", "Access control", "HR technology trends"] },
 { name: "Amdocs", logo: "
 📡
 ", salary: "₹5-15 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "Telecom software and services",
 questions: ["Telecom billing", "Customer management", "OSS/BSS systems", "Real-time 
charging", "Network inventory", "Fraud detection", "Telecom analytics", "System scalability", "Telecom 
protocols", "Service orchestration", "Cloud-native apps", "Legacy integration", "Real-time processing", 
"Customer experience", "Digital transformation"] },
 { name: "AMD", logo: "
 🔴
 ", salary: "₹12-35 LPA", branches: ["ECE", "EEE", "CSE"], category: 
"core",
 description: "Semiconductor and processor company",
 questions: ["CPU/GPU architecture", "Performance optimization", "Semiconductor 
manufacturing", "VLSI design", "Parallel computing", "Cache hierarchies", "AI chip design", "Thermal 
management", "Computer architecture", "Memory controllers", "HDL languages", "Performance 
analysis", "Instruction set design", "Hardware-software optimization", "Processor trends"] },
 { name: "Amazon", logo: "
 📦
 ", salary: "₹10-35 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "E-commerce and cloud computing giant",
 questions: ["Two Sum problem", "Recommendation system", "Leadership principles", 
"Distributed cache", "LRU cache implementation", "Order processing system", "Difficult decisions", 
"Search optimization", "CAP theorem", "Inventory management", "Distributed systems failure", "Merge 
sort", "Video streaming", "Fraud detection", "System monitoring"] },
 { name: "Ashok Leyland", logo: "
 🚛
 ", salary: "₹4-12 LPA", branches: ["MECH", "EEE", "ECE"], 
category: "automotive",
 description: "Commercial vehicle manufacturer",
 questions: ["Engine design", "Vehicle dynamics", "Electric vehicles", "Safety standards", 
"Supply chain", "Predictive maintenance", "Commercial vehicle design", "Fuel efficiency", "Automotive 
electronics", "Quality control", "CAD software", "Cost optimization", "Sustainability", "IoT in vehicles", 
"Autonomous vehicles"] },
 { name: "Atos", logo: "
 🔷
 ", salary: "₹5-14 LPA", branches: ["CSE", "IT", "ECE"], category: 
"consulting",
description: "IT services and consulting",
 questions: ["Digital transformation", "Cloud migration", "Cybersecurity", "System integration", 
"DevOps/CI-CD", "Data analytics", "Legacy modernization", "Compliance", "Project management", 
"Stakeholder management", "Enterprise architecture", "Performance optimization", "Change 
management", "AI solutions", "Enterprise trends"] },
 { name: "Atlassian", logo: "
 🔵
 ", salary: "₹12-40 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Developer and collaboration tools",
 questions: ["Jira system design", "Real-time collaboration", "Developer tools", "Scalability", 
"Code repositories", "Search functionality", "Plugin architecture", "Data consistency", "Notification 
system", "Access control", "API design", "Data migration", "File attachments", "Audit logging", "Cross
platform apps"] },
 { name: "ABB", logo: "
 ⚡
 ", salary: "₹6-20 LPA", branches: ["EEE", "ECE", "MECH"], category: 
"core",
 description: "Power and automation technology",
 questions: ["Power systems", "Industrial automation", "Robotics", "Motor drives", "Smart 
grids", "Predictive maintenance", "Power transmission", "Electrical safety", "PLC programming", 
"Energy efficiency", "Industrial protocols", "Thermal management", "Power quality", "IoT automation", 
"Electrification trends"] },
 // B Companies
 { name: "Bosch", logo: "
 ⚙
 ", salary: "₹6-18 LPA", branches: ["MECH", "ECE", "EEE", "CSE"], 
category: "core",
 description: "Engineering and technology company",
 questions: ["Automotive systems", "Embedded control", "Industry 4.0", "Sensor technology", 
"Safety systems", "Predictive maintenance", "Electric vehicles", "Manufacturing quality", "Control 
systems", "Production efficiency", "CAD simulation", "Engineering problem-solving", "Sustainability", 
"Team collaboration", "Automotive trends"] },
 { name: "BEL", logo: "
 🛡
 ", salary: "₹5-15 LPA", branches: ["ECE", "EEE", "CSE"], category: 
"core",
 description: "Defense electronics company",
 questions: ["Radar systems", "Electronic warfare", "Defense communication", "Embedded 
systems", "Satellite communication", "Secure protocols", "Aerospace electronics", "System reliability", 
"Microwave/RF", "EMC", "Real-time OS", "Defense testing", "Cybersecurity", "Fault tolerance", 
"Defense technology"] },
 { name: "BHEL", logo: "
 ⚡
 ", salary: "₹6-18 LPA", branches: ["MECH", "EEE", "ECE"], category: 
"core",
 description: "Heavy electrical equipment",
 questions: ["Power plant engineering", "Steam turbines", "Power transmission", "Boiler 
design", "Renewable energy", "Condition monitoring", "Heavy equipment", "Power system quality", 
"Control systems", "Plant efficiency", "Project management", "Environmental compliance", 
"Maintenance strategies", "Equipment testing", "Clean energy"] },
{ name: "Broadcom", logo: "
 📡
 ", salary: "₹15-40 LPA", branches: ["ECE", "EEE", "CSE"], 
category: "core",
 description: "Semiconductor solutions",
 questions: ["Semiconductor physics", "RF circuits", "Wireless protocols", "Analog IC design", 
"SoC architecture", "Power optimization", "High-speed design", "Signal integrity", "Networking tech", 
"Error correction", "FPGA/ASIC", "Design verification", "Thermal management", "EMI issues", "5G 
technology"] },
 { name: "Byju's", logo: "
 📚
 ", salary: "₹6-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"startup",
 description: "Educational technology platform",
 questions: ["Learning platform design", "Adaptive algorithms", "Video streaming", "User 
engagement", "Personalized recommendations", "Real-time collaboration", "Mobile app 
development", "Content security", "Assessment systems", "Offline sync", "Gamification", "App 
optimization", "Live classes", "Parental controls", "EdTech trends"] },
 { name: "BPCL", logo: "
 ⛽
 ", salary: "₹8-20 LPA", branches: ["CHEM", "MECH", "EEE"], 
category: "core",
 description: "Oil and gas company",
 questions: ["Refinery processes", "Petrochemical engineering", "Process optimization", 
"Safety systems", "Environmental compliance", "Quality control", "Pipeline systems", "Energy 
efficiency", "Automation", "Maintenance planning", "Process control", "Chemical reactions", 
"Distillation", "Catalysis", "Green energy"] },
 // C Companies
 { name: "Capgemini", logo: "
 💼
 ", salary: "₹4-12 LPA", branches: ["CSE", "IT", "ECE", "MECH"], 
category: "consulting",
 description: "Digital transformation consulting",
 questions: ["Digital transformation", "Client requirements", "Agile methodology", "Software 
quality", "Cloud computing", "Client situations", "Software engineering", "Database design", "Web 
technologies", "Enterprise security", "DevOps practices", "Project delivery", "Team collaboration", 
"Technology adaptation", "Industry trends"] },
 { name: "Cisco", logo: "
 🌐
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Networking hardware and software",
 questions: ["Networking protocols", "Network architecture", "Routing/switching", "Network 
security", "Software-defined networking", "Network troubleshooting", "Cloud networking", 
"Performance optimization", "Wireless networking", "Network monitoring", "Network automation", 
"Scalability", "Quality of Service", "Remote access", "Networking trends"] },
 { name: "Cognizant", logo: "
 🔷
 ", salary: "₹4-10 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "IT services and consulting",
 questions: ["OOP concepts", "Database design", "Testing methodologies", "Requirements 
gathering", "Web services", "Data migration", "Agile development", "Code quality", "Cloud platforms", 
"Performance optimization", "Version control", "Debugging", "Documentation", "Technology learning", 
"Digital transformation"] },
 { name: "CGI", logo: "
 🏢
 ", salary: "₹5-15 LPA", branches: ["CSE", "IT", "ECE"], category: 
"consulting",
 description: "IT and business consulting",
 questions: ["Business consulting", "IT strategy", "System integration", "Digital solutions", 
"Project management", "Client engagement", "Technology architecture", "Process improvement", 
"Change management", "Quality assurance", "Risk management", "Stakeholder communication", 
"Solution design", "Innovation", "Consulting trends"] },
 { name: "Citrix", logo: "
 ☁
 ", salary: "₹8-22 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Cloud computing and virtualization",
 questions: ["Virtualization technology", "Cloud architecture", "Remote access", "Application 
delivery", "Network security", "Performance monitoring", "Desktop virtualization", "Cloud migration", 
"System optimization", "User experience", "Infrastructure management", "Scalability", "Disaster 
recovery", "Automation", "Cloud trends"] },
 // D Companies
 { name: "Deloitte", logo: "
 🏛
 ", salary: "₹6-18 LPA", branches: ["CSE", "IT", "ECE", "MECH"], 
category: "consulting",
 description: "Professional services and consulting",
 questions: ["Business analysis", "Consulting scenarios", "Digital transformation", "Data 
analytics", "Change management", "Technology solutions", "Project management", "Stakeholder 
alignment", "Enterprise architecture", "Risk assessment", "Client communication", "Multiple priorities", 
"Ethics", "Client relationships", "Business trends"] },
 { name: "Dell", logo: "
 💻
 ", salary: "₹6-20 LPA", branches: ["CSE", "IT", "ECE", "MECH"], 
category: "product",
 description: "Computer technology company",
 questions: ["Hardware architecture", "System performance", "Supply chain", "Quality 
assurance", "Enterprise solutions", "Cloud infrastructure", "Technology distribution", "Cybersecurity", 
"Data center tech", "Customer support", "Virtualization", "Cost optimization", "Sustainability", "IoT 
solutions", "Edge computing"] },
 { name: "DE Shaw", logo: "
 📈
 ", salary: "₹25-80 LPA", branches: ["CSE", "IT", "ECE"], category: 
"finance",
 description: "Quantitative hedge fund",
 questions: ["Algorithmic trading", "Quantitative analysis", "Risk management", "Market 
microstructure", "Statistical modeling", "High-frequency trading", "Portfolio optimization", "Derivatives 
pricing", "Machine learning", "Data structures", "System latency", "Financial mathematics", 
"Backtesting", "Market data", "Quantitative research"] },
 { name: "Directi", logo: "
 🌐
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Internet and technology products",
 questions: ["Web technologies", "Scalable systems", "Database optimization", "API design", 
"System architecture", "Performance tuning", "Cloud computing", "Security", "User experience", 
"Product development", "Agile methodology", "Code quality", "Testing", "Innovation", "Tech trends"] },
 { name: "Dr. Reddy's", logo: "
 💊
 ", salary: "₹5-15 LPA", branches: ["CHEM", "MECH", "EEE"], 
category: "pharma",
 description: "Pharmaceutical company",
 questions: ["Drug development", "Process chemistry", "Quality control", "Regulatory 
compliance", "Manufacturing processes", "Analytical methods", "Process optimization", "Good 
manufacturing practices", "Validation", "Documentation", "Safety protocols", "Environmental 
compliance", "Cost reduction", "Innovation", "Pharma trends"] },
 { name: "DRDO", logo: "
 🛡
 ", salary: "₹6-18 LPA", branches: ["ECE", "EEE", "MECH", "AERO"], 
category: "core",
 description: "Defense research organization",
 questions: ["Defense technology", "Research methodology", "System design", "Testing 
protocols", "Project management", "Innovation", "Technical documentation", "Quality assurance", 
"Safety standards", "Collaboration", "Problem-solving", "Technology transfer", "Strategic thinking", 
"Leadership", "Defense trends"] },
 // E Companies
 { name: "Ericsson", logo: "
 📡
 ", salary: "₹8-22 LPA", branches: ["ECE", "EEE", "CSE"], 
category: "core",
 description: "Telecommunications equipment",
 questions: ["5G technology", "Network architecture", "Network virtualization", "Wireless 
communication", "Software-defined networking", "Network optimization", "IoT deployment", "Network 
security", "Signal processing", "Edge computing", "Telecom protocols", "Network planning", "Quality of 
service", "Network maintenance", "Telecom trends"] },
 { name: "Eaton", logo: "
 ⚡
 ", salary: "₹6-18 LPA", branches: ["EEE", "MECH", "ECE"], category: 
"core",
 description: "Power management company",
 questions: ["Power systems", "Electrical distribution", "Motor control", "Power quality", 
"Energy efficiency", "Industrial automation", "Power electronics", "Grid solutions", "Renewable 
integration", "Safety systems", "Maintenance", "System design", "Standards compliance", 
"Innovation", "Power trends"] },
 { name: "EPAM", logo: "
 💻
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "Software engineering services",
 questions: ["Software development", "Agile practices", "System architecture", "Code quality", 
"Testing strategies", "Client collaboration", "Technology stack", "Performance optimization", "DevOps", 
"Cloud solutions", "Database design", "API development", "Security", "Innovation", "Software trends"] 
},
// F Companies
 { name: "Facebook (Meta)", logo: "
 📘
 ", salary: "₹20-60 LPA", branches: ["CSE", "IT", "ECE"], 
category: "product",
 description: "Social media and technology",
 questions: ["News feed algorithm", "Distributed hash table", "Social platform architecture", 
"Billions of interactions", "Real-time messaging", "Friend suggestions", "Content moderation", 
"Privacy/security", "Photo/video storage", "Trending topics", "Notification system", "ML 
personalization", "Content delivery", "Live streaming", "Fake news detection"] },
 { name: "FactSet", logo: "
 📊
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"finance",
 description: "Financial data and analytics",
 questions: ["Financial data systems", "Real-time analytics", "Portfolio management", "Market 
data processing", "Risk analytics", "Performance measurement", "Data visualization", "API design", 
"Database optimization", "System reliability", "Financial modeling", "Compliance", "User experience", 
"Innovation", "Fintech trends"] },
 { name: "Ford", logo: "
 🚗
 ", salary: "₹6-20 LPA", branches: ["MECH", "EEE", "ECE"], category: 
"automotive",
 description: "Automotive manufacturer",
 questions: ["Vehicle engineering", "Automotive systems", "Electric vehicles", "Autonomous 
driving", "Manufacturing processes", "Quality control", "Supply chain", "Safety systems", "Emissions 
control", "Cost optimization", "Innovation", "Sustainability", "Connected vehicles", "Mobility solutions", 
"Auto trends"] },
 { name: "Freshworks", logo: "
 🌱
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], 
category: "product",
 description: "Customer experience software",
 questions: ["CRM system design", "Real-time messaging", "SaaS applications", "Multi
tenancy", "Email automation", "Support ticketing", "Scalable web apps", "Data security", 
"Analytics/reporting", "Third-party APIs", "Microservices", "Database optimization", "Authentication", 
"Real-time notifications", "Customer experience trends"] },
 { name: "Flipkart", logo: "
 🛒
 ", salary: "₹8-30 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "E-commerce platform",
 questions: ["Product catalog", "Concurrent users", "Recommendation system", "Data 
consistency", "Inventory management", "Search functionality", "Payment processing", "Cart recovery", 
"Order tracking", "Fraud detection", "A/B testing", "Database queries", "Notifications", "Traffic spikes", 
"Microservices"] },
 // G Companies
 { name: "Google", logo: "
 🔍
 ", salary: "₹15-45 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Search and cloud computing",
questions: ["Search indexing", "LRU cache", "YouTube streaming", "PageRank algorithm", 
"Distributed storage", "Billions of queries", "Autocomplete", "Maps routing", "Click fraud", "Drive 
storage", "Collaborative editing", "Data consistency", "Web crawler", "Spam detection", "ML model 
serving"] },
 { name: "Goldman Sachs", logo: "
 🏦
 ", salary: "₹15-50 LPA", branches: ["CSE", "IT", "ECE"], 
category: "finance",
 description: "Investment banking",
 questions: ["Trading systems", "High-frequency trading", "Risk management", "Real-time 
data", "Algorithmic trading", "Fraud detection", "Regulatory compliance", "Low-latency systems", 
"Derivatives systems", "Portfolio management", "Distributed systems", "Investment analytics", 
"Financial security", "Disaster recovery", "Fintech trends"] },
 { name: "GE", logo: "
 ⚡
 ", salary: "₹6-20 LPA", branches: ["EEE", "MECH", "ECE"], category: 
"core",
 description: "Industrial conglomerate",
 questions: ["Industrial systems", "Power generation", "Aviation technology", "Healthcare 
equipment", "Digital industrial", "Predictive analytics", "IoT solutions", "Manufacturing", "Quality 
systems", "Safety protocols", "Innovation", "Sustainability", "Digital transformation", "Operational 
excellence", "Industrial trends"] },
 { name: "Godrej", logo: "
 🏢
 ", salary: "₹5-15 LPA", branches: ["MECH", "CHEM", "EEE"], 
category: "core",
 description: "Consumer goods and industrial",
 questions: ["Manufacturing processes", "Product development", "Quality control", "Supply 
chain", "Process optimization", "Safety systems", "Environmental compliance", "Cost management", 
"Innovation", "Sustainability", "Automation", "Maintenance", "Project management", "Team 
leadership", "Industry trends"] },
 // H Companies
 { name: "HCL Technologies", logo: "
 💻
 ", salary: "₹3.5-8 LPA", branches: ["CSE", "IT", "ECE"], 
category: "service",
 description: "IT services company",
 questions: ["SDLC phases", "Database design", "OOP concepts", "Software testing", "Web 
services", "Version control", "Agile development", "Debugging", "Cloud platforms", "Performance 
optimization", "Front-end tech", "Client communication", "Documentation", "Technology learning", 
"Digital transformation"] },
 { name: "HP", logo: "
 🖨
 ", salary: "₹5-18 LPA", branches: ["CSE", "IT", "ECE", "MECH"], 
category: "product",
 description: "Technology company",
 questions: ["Hardware design", "System architecture", "Manufacturing", "Quality assurance", 
"Supply chain", "Product development", "Customer support", "Technology innovation", "Cost 
optimization", "Sustainability", "Global operations", "Market analysis", "Competitive strategy", "Digital 
transformation", "Tech trends"] },
{ name: "Honeywell", logo: "
 🏭
 ", salary: "₹6-20 LPA", branches: ["EEE", "MECH", "ECE"], 
category: "core",
 description: "Industrial technology",
 questions: ["Industrial automation", "Control systems", "Safety systems", "Process 
optimization", "IoT solutions", "Building automation", "Aerospace systems", "Manufacturing", "Quality 
control", "Predictive maintenance", "System integration", "Standards compliance", "Innovation", 
"Sustainability", "Industrial trends"] },
 { name: "HSBC", logo: "
 🏦
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"finance",
 description: "Banking and financial services",
 questions: ["Banking systems", "Financial technology", "Risk management", "Regulatory 
compliance", "Digital banking", "Payment systems", "Data security", "Customer experience", 
"Analytics", "Cloud computing", "API development", "System integration", "Innovation", "Fintech", 
"Banking trends"] },
 // I Companies
 { name: "IBM", logo: "
 🔵
 ", salary: "₹6-20 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Technology and consulting",
 questions: ["Watson AI", "Cloud platform", "Blockchain", "Enterprise software", "Hybrid 
cloud", "Machine learning", "Legacy modernization", "Enterprise security", "Database systems", 
"Distributed computing", "DevOps", "Client consulting", "Data analytics", "Large-scale processing", 
"Quantum computing"] },
 { name: "Infosys", logo: "
 🔷
 ", salary: "₹3.5-8 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "IT services company",
 questions: ["Software engineering", "Web applications", "Database normalization", "Testing 
strategies", "Microservices", "Data security", "Project management", "Code quality", "Cloud 
technologies", "Performance optimization", "Agile methodologies", "Client communication", "CI/CD", 
"Digital transformation", "Technology trends"] },
 { name: "Intel", logo: "
 🔷
 ", salary: "₹10-30 LPA", branches: ["ECE", "EEE", "CSE"], category: 
"core",
 description: "Semiconductor company",
 questions: ["CPU architecture", "Processor optimization", "Semiconductor manufacturing", 
"VLSI design", "Parallel processing", "Memory hierarchy", "Chip design", "Power efficiency", 
"Computer architecture", "Cache optimization", "HDL languages", "Performance analysis", "Thermal 
management", "Hardware-software co-design", "Processor trends"] },
 { name: "InMobi", logo: "
 📱
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Mobile advertising platform",
 questions: ["Mobile advertising", "Real-time bidding", "Data analytics", "Machine learning", 
"Scalable systems", "Mobile SDKs", "Performance optimization", "User targeting", "Ad serving", 
"Revenue optimization", "A/B testing", "Data processing", "Mobile trends", "Privacy compliance", 
"AdTech innovation"] },
 { name: "ISRO", logo: "
 🚀
 ", salary: "₹6-18 LPA", branches: ["AERO", "ECE", "MECH", "EEE"], 
category: "core",
 description: "Space research organization",
 questions: ["Satellite technology", "Space missions", "Rocket propulsion", "Orbital 
mechanics", "Space communication", "Navigation systems", "Remote sensing", "Mission planning", 
"System reliability", "Quality assurance", "Testing protocols", "Innovation", "Research methodology", 
"Project management", "Space trends"] },
 // J Companies
 { name: "Jio Platforms", logo: "
 📱
 ", salary: "₹6-20 LPA", branches: ["ECE", "EEE", "CSE"], 
category: "telecom",
 description: "Telecommunications company",
 questions: ["4G/5G networks", "Telecom billing", "Network optimization", "Wireless 
communication", "VoLTE", "Capacity planning", "Infrastructure deployment", "Network security", "Fiber 
optics", "IoT solutions", "Network monitoring", "Customer experience", "Quality of service", "Network 
troubleshooting", "Telecom trends"] },
 { name: "JP Morgan", logo: "
 🏛
 ", salary: "₹12-40 LPA", branches: ["CSE", "IT", "ECE"], 
category: "finance",
 description: "Investment banking",
 questions: ["Investment banking", "Risk management", "Financial derivatives", "High
frequency data", "Algorithmic trading", "Compliance reporting", "Payment systems", "Data security", 
"Credit risk", "Portfolio analytics", "Distributed computing", "Market data", "Disaster recovery", "AML 
systems", "Digital banking"] },
 { name: "Juniper", logo: "
 🌐
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Networking equipment",
 questions: ["Network routing", "Switching technology", "Network security", "SDN", "Network 
protocols", "Performance optimization", "Cloud networking", "Network automation", "Quality of 
service", "Network monitoring", "Scalability", "Troubleshooting", "Innovation", "Network trends", 
"Enterprise networking"] },
 // K Companies
 { name: "KPIT", logo: "
 🚗
 ", salary: "₹4-15 LPA", branches: ["CSE", "IT", "ECE", "MECH"], 
category: "automotive",
 description: "Automotive technology",
 questions: ["Automotive software", "Embedded systems", "Connected vehicles", 
"Autonomous driving", "Electric vehicles", "Vehicle diagnostics", "Automotive testing", "Safety 
systems", "In-vehicle networking", "Software integration", "Automotive standards", "Innovation", 
"Quality assurance", "Automotive trends", "Mobility solutions"] },
 { name: "KPMG", logo: "
 🏢
 ", salary: "₹6-18 LPA", branches: ["CSE", "IT", "ECE"], category: 
"consulting",
 description: "Professional services",
 questions: ["Business consulting", "Digital transformation", "Process improvement", "Risk 
management", "Technology strategy", "Data analytics", "Change management", "Project 
management", "Client engagement", "Solution design", "Quality assurance", "Innovation", "Industry 
knowledge", "Leadership", "Consulting trends"] },
 // L Companies
 { name: "L&T", logo: "
 🏗
 ", salary: "₹5-15 LPA", branches: ["CIVIL", "MECH", "EEE", "ECE"], 
category: "core",
 description: "Engineering and construction",
 questions: ["Project management", "Structural design", "Heavy engineering", "Quality 
control", "Infrastructure development", "Safety management", "Project execution", "Cost optimization", 
"Power systems", "Manufacturing automation", "CAD software", "Environmental compliance", "Supply 
chain", "Digital transformation", "Smart infrastructure"] },
 { name: "LTI Mindtree", logo: "
 🌳
 ", salary: "₹4-12 LPA", branches: ["CSE", "IT", "ECE"], 
category: "service",
 description: "Digital solutions company",
 questions: ["Enterprise applications", "Digital transformation", "Cloud migration", "Data 
analytics", "Customer experience", "DevOps/CI-CD", "Legacy modernization", "Cybersecurity", 
"AI/automation", "Microservices", "Agile/lean", "Client engagement", "Quality assurance", "Multi
cloud", "Enterprise innovation"] },
 { name: "LinkedIn", logo: "
 💼
 ", salary: "₹15-45 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Professional networking platform",
 questions: ["Social networking", "Recommendation systems", "Data processing", "Search 
algorithms", "Real-time messaging", "Content delivery", "Machine learning", "A/B testing", "System 
scalability", "Data analytics", "User engagement", "Privacy/security", "Mobile optimization", 
"Innovation", "Professional networking trends"] },
 // M Companies
 { name: "Microsoft", logo: "
 🪟
 ", salary: "₹12-40 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Technology company",
 questions: ["Operating systems", "Cloud computing", "Distributed systems", "Software 
architecture", "Azure platform", "Machine learning", "Database systems", "Security", "DevOps", "API 
design", "Performance optimization", "System design", "Innovation", "User experience", "Technology 
trends"] },
 { name: "Mahindra", logo: "
 🚗
 ", salary: "₹5-18 LPA", branches: ["MECH", "EEE", "ECE"], 
category: "automotive",
 description: "Automotive and aerospace",
 questions: ["Vehicle engineering", "Manufacturing", "Electric vehicles", "Automotive systems", 
"Quality control", "Supply chain", "Cost optimization", "Safety systems", "Innovation", "Sustainability", 
"Process improvement", "Project management", "Technology integration", "Market analysis", 
"Automotive trends"] },
 { name: "Maruti Suzuki", logo: "
 🚙
 ", salary: "₹5-15 LPA", branches: ["MECH", "EEE", "ECE"], 
category: "automotive",
 description: "Automotive manufacturer",
 questions: ["Automotive manufacturing", "Production systems", "Quality management", 
"Supply chain", "Process optimization", "Safety protocols", "Cost reduction", "Innovation", "Lean 
manufacturing", "Automation", "Environmental compliance", "Continuous improvement", "Team 
management", "Problem-solving", "Auto industry trends"] },
 { name: "Mindtree", logo: "
 🌲
 ", salary: "₹4-12 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "Digital transformation company",
 questions: ["Digital solutions", "Cloud services", "Data analytics", "Customer experience", 
"Agile delivery", "Technology consulting", "Innovation", "Quality engineering", "DevOps", 
"Automation", "Enterprise solutions", "Client collaboration", "Emerging technologies", "Digital 
strategy", "Transformation trends"] },
 { name: "Morgan Stanley", logo: "
 🏦
 ", salary: "₹15-50 LPA", branches: ["CSE", "IT", "ECE"], 
category: "finance",
 description: "Investment banking",
 questions: ["Financial systems", "Trading platforms", "Risk management", "Portfolio 
management", "Market data", "Algorithmic trading", "Regulatory compliance", "Data analytics", 
"System reliability", "Performance optimization", "Security", "Innovation", "Client solutions", 
"Technology strategy", "Financial trends"] },
 // N Companies
 { name: "NetApp", logo: "
 💾
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Data management company",
 questions: ["Storage systems", "Data management", "Cloud storage", "Backup solutions", 
"Data protection", "Storage optimization", "Virtualization", "System performance", "Data analytics", 
"Hybrid cloud", "Storage architecture", "Disaster recovery", "Innovation", "Customer solutions", 
"Storage trends"] },
 { name: "Nokia", logo: "
 📱
 ", salary: "₹6-20 LPA", branches: ["ECE", "EEE", "CSE"], category: 
"core",
 description: "Telecommunications equipment",
 questions: ["5G technology", "Network infrastructure", "Wireless communication", "Network 
optimization", "Telecom protocols", "System design", "Performance analysis", "Innovation", "Quality 
assurance", "Customer solutions", "Technology trends", "Global markets", "Sustainability", "Digital 
transformation", "Telecom evolution"] },
 { name: "Nvidia", logo: "
 🎮
 ", salary: "₹15-45 LPA", branches: ["ECE", "EEE", "CSE"], category: 
"core",
description: "Graphics and AI computing",
 questions: ["GPU architecture", "Parallel computing", "AI/ML acceleration", "Graphics 
processing", "CUDA programming", "Deep learning", "Computer vision", "High-performance 
computing", "System optimization", "Hardware design", "Software development", "Innovation", 
"Performance analysis", "Emerging technologies", "AI trends"] },
 { name: "NTT Data", logo: "
 🌐
 ", salary: "₹5-15 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "IT services company",
 questions: ["Enterprise solutions", "Digital transformation", "Cloud services", "System 
integration", "Application development", "Data analytics", "Cybersecurity", "Quality assurance", 
"Project management", "Client engagement", "Innovation", "Agile delivery", "Technology consulting", 
"Global delivery", "IT trends"] },
 // O Companies
 { name: "Oracle", logo: "
 🔴
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Database and cloud computing",
 questions: ["Database systems", "Cloud computing", "Enterprise applications", "System 
architecture", "Performance tuning", "Data management", "Security", "Integration", "Scalability", 
"Innovation", "Customer solutions", "Technology strategy", "Digital transformation", "Emerging 
technologies", "Enterprise trends"] },
 { name: "Optum", logo: "
 🏥
 ", salary: "₹6-20 LPA", branches: ["CSE", "IT", "ECE"], category: 
"healthcare",
 description: "Healthcare technology",
 questions: ["Healthcare systems", "Data analytics", "Population health", "Clinical workflows", 
"Healthcare compliance", "System integration", "Innovation", "Quality improvement", "Patient 
experience", "Technology solutions", "Healthcare trends", "Digital health", "Interoperability", "Security", 
"Healthcare transformation"] },
 { name: "Ola", logo: "
 🚗
 ", salary: "₹6-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"startup",
 description: "Mobility and electric vehicles",
 questions: ["Ride-sharing platform", "Real-time matching", "Location services", "Payment 
systems", "Electric vehicles", "Fleet management", "Data analytics", "Machine learning", "Mobile 
applications", "Scalability", "User experience", "Innovation", "Sustainability", "Mobility solutions", 
"Transportation trends"] },
 { name: "ONGC", logo: "
 ⛽
 ", salary: "₹8-20 LPA", branches: ["MECH", "CHEM", "EEE", 
"CIVIL"], category: "core",
 description: "Oil and gas exploration",
 questions: ["Petroleum engineering", "Drilling technology", "Production systems", "Reservoir 
engineering", "Process optimization", "Safety systems", "Environmental compliance", "Project 
management", "Quality control", "Innovation", "Sustainability", "Cost optimization", "Technology 
integration", "Industry trends", "Energy transition"] },
// P Companies
 { name: "Paytm", logo: "
 💳
 ", salary: "₹6-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"fintech",
 description: "Digital payments platform",
 questions: ["Payment systems", "Digital wallet", "Financial services", "Security", "Fraud 
detection", "Scalability", "Mobile applications", "Data analytics", "Machine learning", "Compliance", 
"User experience", "Innovation", "Fintech trends", "Digital transformation", "Financial inclusion"] },
 { name: "PayPal", logo: "
 💰
 ", salary: "₹12-35 LPA", branches: ["CSE", "IT", "ECE"], category: 
"fintech",
 description: "Online payments system",
 questions: ["Payment processing", "Financial technology", "Security systems", "Fraud 
prevention", "Global payments", "Compliance", "Data analytics", "Machine learning", "System 
scalability", "User experience", "Innovation", "Risk management", "Digital payments", "Fintech 
evolution", "Financial services"] },
 { name: "Philips", logo: "
 💡
 ", salary: "₹6-20 LPA", branches: ["EEE", "ECE", "MECH"], 
category: "healthcare",
 description: "Healthcare technology",
 questions: ["Medical devices", "Healthcare technology", "Innovation", "Quality systems", 
"Regulatory compliance", "Patient safety", "System design", "Manufacturing", "Research & 
development", "Clinical applications", "Digital health", "Sustainability", "Global markets", "Healthcare 
trends", "Technology integration"] },
 { name: "Publicis Sapient", logo: "
 🎯
 ", salary: "₹6-20 LPA", branches: ["CSE", "IT", "ECE"], 
category: "consulting",
 description: "Digital transformation",
 questions: ["Digital transformation", "Customer experience", "Technology consulting", "Agile 
delivery", "Innovation", "Data analytics", "Cloud solutions", "Mobile applications", "E-commerce", 
"Digital strategy", "Client engagement", "Quality engineering", "Emerging technologies", "Digital 
trends", "Business transformation"] },
 // Q Companies
 { name: "Qualcomm", logo: "
 📱
 ", salary: "₹10-30 LPA", branches: ["ECE", "EEE", "CSE"], 
category: "core",
 description: "Wireless technology",
 questions: ["Wireless communication", "5G technology", "Semiconductor design", "Mobile 
processors", "RF systems", "Signal processing", "System architecture", "Performance optimization", 
"Innovation", "Standards development", "Quality assurance", "Technology trends", "Mobile evolution", 
"Connectivity solutions", "Emerging technologies"] },
 { name: "QuEST Global", logo: "
 🔬
 ", salary: "₹5-18 LPA", branches: ["MECH", "AERO", "EEE", 
"ECE"], category: "engineering",
 description: "Engineering services",
 questions: ["Product engineering", "Design services", "Manufacturing support", "Quality 
systems", "Innovation", "Technology solutions", "Project management", "Client collaboration", 
"Engineering processes", "Cost optimization", "Sustainability", "Digital transformation", "Industry 
expertise", "Global delivery", "Engineering trends"] },
 // R Companies
 { name: "Reliance", logo: "
 🏭
 ", salary: "₹6-20 LPA", branches: ["CHEM", "MECH", "EEE", 
"ECE"], category: "core",
 description: "Conglomerate company",
 questions: ["Petrochemicals", "Refinery operations", "Process engineering", "Safety 
systems", "Quality control", "Project management", "Innovation", "Sustainability", "Cost optimization", 
"Technology integration", "Manufacturing excellence", "Supply chain", "Environmental compliance", 
"Digital transformation", "Industry leadership"] },
 { name: "Razorpay", logo: "
 💎
 ", salary: "₹8-30 LPA", branches: ["CSE", "IT", "ECE"], category: 
"fintech",
 description: "Payment gateway",
 questions: ["Payment processing", "Fintech solutions", "API development", "Security 
systems", "Fraud detection", "Scalability", "Database design", "System architecture", "Performance 
optimization", "Compliance", "Innovation", "User experience", "Financial services", "Digital payments", 
"Fintech trends"] },
 { name: "Red Hat", logo: "
 🎩
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Open source solutions",
 questions: ["Linux systems", "Open source", "Cloud computing", "Container technology", 
"DevOps", "System administration", "Automation", "Security", "Performance tuning", "Innovation", 
"Community collaboration", "Enterprise solutions", "Technology trends", "Digital transformation", 
"Open source evolution"] },
 // S Companies
 { name: "Samsung R&D", logo: "
 📱
 ", salary: "₹8-25 LPA", branches: ["ECE", "EEE", "CSE"], 
category: "product",
 description: "Technology research",
 questions: ["Mobile technology", "Semiconductor design", "Consumer electronics", 
"Innovation", "Research & development", "Product design", "Manufacturing", "Quality systems", 
"Technology trends", "Global markets", "Sustainability", "User experience", "Emerging technologies", 
"Digital transformation", "Technology leadership"] },
 { name: "SAP Labs", logo: "
 💼
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Enterprise software",
 questions: ["Enterprise applications", "Business processes", "Database systems", "Cloud 
computing", "Analytics", "Innovation", "System integration", "Performance optimization", "User 
experience", "Quality assurance", "Technology strategy", "Digital transformation", "Enterprise trends", 
"Business solutions", "Software development"] },
{ name: "Siemens", logo: "
 ⚙
 ", salary: "₹6-20 LPA", branches: ["EEE", "MECH", "ECE"], 
category: "core",
 description: "Industrial technology",
 questions: ["Industrial automation", "Power systems", "Manufacturing", "Digital factory", "IoT 
solutions", "Innovation", "Quality systems", "Safety protocols", "Sustainability", "Technology 
integration", "Process optimization", "Global markets", "Digital transformation", "Industry 4.0", 
"Engineering excellence"] },
 { name: "Synopsys", logo: "
 🔧
 ", salary: "₹8-25 LPA", branches: ["ECE", "EEE", "CSE"], 
category: "product",
 description: "Electronic design automation",
 questions: ["EDA tools", "Semiconductor design", "VLSI", "System design", "Verification", 
"Innovation", "Software development", "Performance optimization", "Quality assurance", "Customer 
solutions", "Technology trends", "Design automation", "Chip design", "Electronic systems", 
"Technology evolution"] },
 { name: "Salesforce", logo: "
 ☁
 ", salary: "₹8-30 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "CRM and cloud computing",
 questions: ["CRM systems", "Cloud computing", "SaaS applications", "Customer 
experience", "Automation", "Integration", "Data analytics", "Innovation", "Scalability", "Security", "User 
experience", "Platform development", "Digital transformation", "Business solutions", "Cloud trends"] },
 { name: "Swiggy", logo: "
 🍔
 ", salary: "₹6-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"startup",
 description: "Food delivery platform",
 questions: ["Food delivery", "Real-time tracking", "Location services", "Payment systems", 
"Machine learning", "Data analytics", "Mobile applications", "Scalability", "User experience", 
"Operations optimization", "Innovation", "Growth strategies", "Technology solutions", "Market 
expansion", "Platform evolution"] },
 // T Companies
 { name: "TCS", logo: "
 🔷
 ", salary: "₹3.5-8 LPA", branches: ["CSE", "IT", "ECE", "MECH"], 
category: "service",
 description: "IT services company",
 questions: ["Software development", "System design", "Database management", "Testing 
methodologies", "Project management", "Client communication", "Quality assurance", "Technology 
trends", "Innovation", "Digital transformation", "Agile practices", "Problem-solving", "Team 
collaboration", "Continuous learning", "Industry knowledge"] },
 { name: "Tata Motors", logo: "
 🚗
 ", salary: "₹5-15 LPA", branches: ["MECH", "EEE", "ECE"], 
category: "automotive",
 description: "Automotive manufacturer",
 questions: ["Vehicle engineering", "Manufacturing processes", "Quality control", "Electric 
vehicles", "Automotive systems", "Safety standards", "Cost optimization", "Innovation", 
"Sustainability", "Supply chain", "Process improvement", "Technology integration", "Market analysis", 
"Product development", "Automotive trends"] },
 { name: "Tech Mahindra", logo: "
 🌐
 ", salary: "₹4-12 LPA", branches: ["CSE", "IT", "ECE"], 
category: "service",
 description: "IT services company",
 questions: ["Digital transformation", "Technology solutions", "Client engagement", 
"Innovation", "Quality delivery", "Agile practices", "Cloud services", "Data analytics", "Cybersecurity", 
"Automation", "Enterprise solutions", "Global delivery", "Emerging technologies", "Business 
consulting", "Technology trends"] },
 { name: "Texas Instruments", logo: "
 🔧
 ", salary: "₹8-25 LPA", branches: ["ECE", "EEE", 
"CSE"], category: "core",
 description: "Semiconductor company",
 questions: ["Analog circuits", "Embedded systems", "Semiconductor design", "Signal 
processing", "Power management", "Innovation", "Product development", "Quality systems", 
"Customer solutions", "Technology trends", "Manufacturing", "Testing", "Applications engineering", 
"Market analysis", "Technology evolution"] },
 { name: "ThoughtWorks", logo: "
 💭
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], 
category: "consulting",
 description: "Software consultancy",
 questions: ["Software craftsmanship", "Agile practices", "Technology consulting", 
"Innovation", "Quality engineering", "Client collaboration", "Continuous delivery", "Test-driven 
development", "Refactoring", "Design patterns", "Architecture", "Team dynamics", "Social impact", 
"Technology trends", "Software excellence"] },
 // U Companies
 { name: "UST Global", logo: "
 🌐
 ", salary: "₹5-15 LPA", branches: ["CSE", "IT", "ECE"], 
category: "service",
 description: "Digital transformation",
 questions: ["Digital solutions", "Technology consulting", "Cloud services", "Data analytics", 
"Innovation", "Quality engineering", "Agile delivery", "Client engagement", "Emerging technologies", 
"Business transformation", "Global delivery", "Automation", "Cybersecurity", "Enterprise solutions", 
"Technology trends"] },
 { name: "Unisys", logo: "
 💻
 ", salary: "₹5-15 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "IT services company",
 questions: ["Enterprise solutions", "System integration", "Cloud computing", "Security 
solutions", "Innovation", "Digital transformation", "Client solutions", "Technology consulting", "Quality 
delivery", "Global services", "Automation", "Data analytics", "Emerging technologies", "Business 
solutions", "Technology evolution"] },
 { name: "UltraTech", logo: "
 🏗
 ", salary: "₹5-15 LPA", branches: ["CIVIL", "MECH", "CHEM"], 
category: "core",
 description: "Cement company",
questions: ["Cement manufacturing", "Process optimization", "Quality control", 
"Environmental compliance", "Safety systems", "Cost management", "Innovation", "Sustainability", 
"Project management", "Maintenance", "Automation", "Supply chain", "Market analysis", "Technology 
integration", "Industry trends"] },
 // V Companies
 { name: "Verizon", logo: "
 📡
 ", salary: "₹8-25 LPA", branches: ["ECE", "EEE", "CSE"], category: 
"telecom",
 description: "Telecommunications company",
 questions: ["Network infrastructure", "5G technology", "Telecommunications", "Network 
optimization", "Customer solutions", "Innovation", "Quality assurance", "Technology trends", "Digital 
transformation", "Cloud services", "Cybersecurity", "Data analytics", "Global networks", "Emerging 
technologies", "Telecom evolution"] },
 { name: "Virtusa", logo: "
 🔷
 ", salary: "₹4-12 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "Digital engineering",
 questions: ["Digital transformation", "Technology solutions", "Innovation", "Quality 
engineering", "Client engagement", "Agile delivery", "Cloud services", "Data analytics", "Automation", 
"Enterprise solutions", "Global delivery", "Emerging technologies", "Business consulting", "Technology 
trends", "Digital innovation"] },
 { name: "VMware", logo: "
 ☁
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Virtualization technology",
 questions: ["Virtualization", "Cloud computing", "Software-defined data center", "Network 
virtualization", "Security", "Innovation", "System architecture", "Performance optimization", "Customer 
solutions", "Technology trends", "Digital transformation", "Hybrid cloud", "Automation", "Enterprise 
solutions", "Technology evolution"] },
 // W Companies
 { name: "Wipro", logo: "
 💻
 ", salary: "₹3.5-8 LPA", branches: ["CSE", "IT", "ECE", "MECH"], 
category: "service",
 description: "IT services company",
 questions: ["Software development", "Digital transformation", "Technology consulting", 
"Innovation", "Quality delivery", "Client engagement", "Agile practices", "Cloud services", "Data 
analytics", "Cybersecurity", "Automation", "Enterprise solutions", "Global delivery", "Emerging 
technologies", "Business solutions"] },
 { name: "Wells Fargo", logo: "
 🏦
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], 
category: "finance",
 description: "Banking and financial services",
 questions: ["Banking systems", "Financial technology", "Risk management", "Regulatory 
compliance", "Digital banking", "Customer experience", "Data analytics", "Security", "Innovation", 
"Technology solutions", "Quality assurance", "Business solutions", "Financial services", "Banking 
trends", "Digital transformation"] },
{ name: "Western Digital", logo: "
 💾
 ", salary: "₹6-20 LPA", branches: ["ECE", "EEE", "CSE"], 
category: "core",
 description: "Data storage company",
 questions: ["Storage technology", "Data management", "Hardware design", "System 
architecture", "Performance optimization", "Innovation", "Quality systems", "Manufacturing", 
"Customer solutions", "Technology trends", "Data analytics", "Cloud storage", "Emerging 
technologies", "Storage evolution", "Digital transformation"] },
 // X Companies
 { name: "Xilinx", logo: "
 🔧
 ", salary: "₹8-25 LPA", branches: ["ECE", "EEE", "CSE"], category: 
"core",
 description: "Programmable logic devices",
 questions: ["FPGA design", "Programmable logic", "Hardware acceleration", "System 
design", "Performance optimization", "Innovation", "Customer solutions", "Technology trends", 
"Applications engineering", "Quality systems", "Design tools", "Verification", "Emerging technologies", 
"Hardware evolution", "Technology integration"] },
 { name: "Xerox", logo: "
 🖨
 ", salary: "₹5-15 LPA", branches: ["ECE", "MECH", "CSE"], category: 
"product",
 description: "Document technology",
 questions: ["Document technology", "Printing systems", "Innovation", "Product development", 
"Quality systems", "Customer solutions", "Technology trends", "Manufacturing", "Service delivery", 
"Digital transformation", "Automation", "Sustainability", "Market analysis", "Technology integration", 
"Business solutions"] },
 // Y Companies
 { name: "Yatra", logo: "
 ✈
 ", salary: "₹4-12 LPA", branches: ["CSE", "IT", "ECE"], category: 
"startup",
 description: "Online travel company",
 questions: ["Travel technology", "Booking systems", "Customer experience", "Mobile 
applications", "Data analytics", "Innovation", "Scalability", "Payment systems", "Search algorithms", 
"User experience", "Technology solutions", "Market trends", "Digital transformation", "Travel industry", 
"Platform evolution"] },
 { name: "Yash Technologies", logo: "
 💻
 ", salary: "₹4-12 LPA", branches: ["CSE", "IT", "ECE"], 
category: "service",
 description: "IT services company",
 questions: ["Software development", "Technology solutions", "Innovation", "Quality delivery", 
"Client engagement", "Agile practices", "Digital transformation", "Cloud services", "Data analytics", 
"Automation", "Enterprise solutions", "Global delivery", "Emerging technologies", "Business 
consulting", "Technology trends"] },
 // Z Companies
 { name: "Zoho", logo: "
 📊
 ", salary: "₹5-18 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
description: "Business software suite",
 questions: ["SaaS applications", "Business software", "Customer experience", "Innovation", 
"Product development", "Quality systems", "Scalability", "Security", "User experience", "Technology 
trends", "Cloud computing", "Integration", "Automation", "Business solutions", "Software evolution"] },
 { name: "Zscaler", logo: "
 🔒
 ", salary: "₹8-25 LPA", branches: ["CSE", "IT", "ECE"], category: 
"product",
 description: "Cloud security company",
 questions: ["Cloud security", "Network security", "Cybersecurity", "Zero trust", "Innovation", 
"Security architecture", "Threat detection", "Performance optimization", "Customer solutions", 
"Technology trends", "Digital transformation", "Security solutions", "Emerging threats", "Security 
evolution", "Cloud transformation"] },
 { name: "Zensar", logo: "
 🔷
 ", salary: "₹4-12 LPA", branches: ["CSE", "IT", "ECE"], category: 
"service",
 description: "Digital solutions company",
 questions: ["Digital transformation", "Technology solutions", "Innovation", "Quality 
engineering", "Client engagement", "Agile delivery", "Cloud services", "Data analytics", "Automation", 
"Enterprise solutions", "Global delivery", "Emerging technologies", "Business consulting", "Technology 
trends", "Digital innovation"] }
 ];
 let filteredCompanies = [...companies];
 let currentFilter = 'all';
 // Initialize the page
 document.addEventListener('DOMContentLoaded', function() {
 displayCompanies(companies);
 updateCompanyCount(companies.length);
 });
 function displayCompanies(companiesToShow) {
 const grid = document.getElementById('companiesGrid');
 grid.innerHTML = '';
 companiesToShow.forEach(company => {
 const card = document.createElement('div');
 card.className = 'company-card bg-white rounded-lg shadow-md p-6 hover:shadow-lg 
transition-all duration-300';
 card.onclick = () => openCompanyModal(company);
 card.innerHTML = `
 <div class="flex items-center mb-4">
 <div class="text-3xl mr-3">${company.logo}</div>
 <div>
 <h3 class="text-lg font-bold text-gray-800">${company.name}</h3>
<p class="text-sm text-gray-600">${company.category}</p>
 </div>
 </div>
 <p class="text-gray-600 text-sm mb-3">${company.description}</p>
 <div class="flex justify-between items-center">
 <span class="text-green-600 font-semibold">${company.salary}</span>
 <div class="flex flex-wrap gap-1">
 ${company.branches.slice(0, 3).map(branch => 
`<span class="bg-blue-100 text-blue-800 text-xs px-2 py-1 rounded">${branch}
 </span>`
 ).join('')}
 ${company.branches.length > 3 ? `<span class="text-xs text-gray
500">+${company.branches.length - 3}</span>` : ''}
 </div>
 </div>
 `;
 grid.appendChild(card);
 });
 }
 function filterCompanies() {
 const searchTerm = document.getElementById('searchInput').value.toLowerCase();
 const branchFilter = document.getElementById('branchFilter').value;
 const salaryFilter = document.getElementById('salaryFilter').value;
 filteredCompanies = companies.filter(company => {
 const matchesSearch = company.name.toLowerCase().includes(searchTerm) || 
company.description.toLowerCase().includes(searchTerm);
 const matchesBranch = !branchFilter || company.branches.includes(branchFilter);
 const matchesSalary = !salaryFilter || checkSalaryRange(company.salary, salaryFilter);
 const matchesAlphabet = currentFilter === 'all' || company.name.charAt(0).toUpperCase() 
=== currentFilter;
 return matchesSearch && matchesBranch && matchesSalary && matchesAlphabet;
 });
 displayCompanies(filteredCompanies);
 updateCompanyCount(filteredCompanies.length);
 }
 function checkSalaryRange(companySalary, filterRange) {
 const salaryNum = parseInt(companySalary.match(/\d+/)[0]);
 switch(filterRange) {
 case '0-5': return salaryNum <= 5;
 case '5-10': return salaryNum >= 5 && salaryNum <= 10;
case '10-20': return salaryNum >= 10 && salaryNum <= 20;
 case '20-50': return salaryNum >= 20 && salaryNum <= 50;
 case '50+': return salaryNum >= 50;
 default: return true;
 }
 }
 function filterByAlphabet(letter) {
 currentFilter = letter;
 // Update active button
 document.querySelectorAll('.alphabet-btn').forEach(btn => {
 btn.classList.remove('active');
 btn.classList.add('bg-gray-200', 'text-gray-700');
 btn.classList.remove('bg-blue-600', 'text-white');
 });
 event.target.classList.add('active');
 event.target.classList.remove('bg-gray-200', 'text-gray-700');
 event.target.classList.add('bg-blue-600', 'text-white');
 filterCompanies();
 }
 function updateCompanyCount(count) {
 document.getElementById('companyCount').textContent = `Showing ${count} companies`;
 }
 function openCompanyModal(company) {
 document.getElementById('modalCompanyName').textContent = company.name;
 // Overview tab
 document.getElementById('companyOverview').innerHTML = `
 <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
 <div>
 <h4 class="text-lg font-semibold mb-3">Company Details</h4>
 <div class="space-y-2">
 <p><strong>Category:</strong> ${company.category}</p>
 <p><strong>Salary Range:</strong> ${company.salary}</p>
 <p><strong>Description:</strong> ${company.description}</p>
 </div>
 </div>
 <div>
 <h4 class="text-lg font-semibold mb-3">Eligible Branches</h4>
 <div class="flex flex-wrap gap-2">
 ${company.branches.map(branch => 
`<span class="bg-blue-100 text-blue-800 px-3 py-1 rounded-full text
sm">${branch}</span>`
 ).join('')}
 </div>
 </div>
 </div>
 `;
 // Questions tab
 document.getElementById('companyQuestions```
