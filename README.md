<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2026年度设计部工作规划看板</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        /* Chart Container Styling as per requirements */
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px;
            }
        }
        
        /* Custom Scrollbar for task lists */
        .task-scroll::-webkit-scrollbar {
            width: 6px;
        }
        .task-scroll::-webkit-scrollbar-track {
            background: #f1f1f1; 
            border-radius: 4px;
        }
        .task-scroll::-webkit-scrollbar-thumb {
            background: #cbd5e1; 
            border-radius: 4px;
        }
        .task-scroll::-webkit-scrollbar-thumb:hover {
            background: #94a3b8; 
        }

        /* Transition effects */
        .fade-in {
            animation: fadeIn 0.5s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .tab-active {
            background-color: #3b82f6;
            color: white;
            border-bottom: 2px solid #1d4ed8;
        }
        .tab-inactive {
            background-color: #e2e8f0;
            color: #64748b;
            border-bottom: 2px solid transparent;
        }
        .tab-inactive:hover {
            background-color: #cbd5e1;
        }
    </style>
    <!-- Chosen Palette: Warm Neutrals with Professional Blue Accents -->
    <!-- 
         Application Structure Plan:
         1. Header: High-level summary showing the 4 main pillars (Exhibitions, Routine, Holidays, Core Projects).
         2. Main Layout (Grid): 
            - Left Column (Interactive Timeline): A tabbed interface for Q1-Q4 allowing users to drill down into specific monthly tasks. This is the primary navigation method.
            - Right Column (Analytics): Visualizing workload intensity and task distribution to help with resource planning.
         3. Exhibition Deep Dive: A horizontal flow section specifically for the 5 major exhibitions to visualize the "Early" vs "Late" stage workflow described in the report.
         4. Strategy Section: Visual cards presenting the management suggestions (Asset Library, Buffer Time, etc.).
         
         Why this structure? The report is chronological but dense. Splitting it into "Quarterly Views" prevents cognitive overload. The "Analytics" help justify the "Management Suggestions" (e.g., showing peak months).
    -->
    <!-- 
         Visualization & Content Choices:
         1. Workload Intensity Chart (Bar Chart): Shows estimated task volume per month. Goal: Inform/Compare. Helps visualize the "Busy Season".
         2. Task Type Distribution (Doughnut Chart): Shows ratio of Exhibitions vs Routine. Goal: Inform.
         3. Interactive Timeline (HTML/JS): Custom tabbed lists. Goal: Organize/Change. Allows exploring the textual content without scrolling endlessly.
         4. Status/Process Flow (HTML Grid): Visualizing the Exhibition Lifecycle. Goal: Inform.
         
         CONFIRMATION: NO SVG graphics used. NO Mermaid JS used.
    -->
</head>
<body class="bg-slate-50 text-slate-800 font-sans selection:bg-blue-100">

    <!-- App Container -->
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">

        <!-- Header Section -->
        <header class="mb-10 text-center">
            <h1 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4">2026年度设计部工作规划 📅</h1>
            <p class="text-lg text-slate-600 max-w-3xl mx-auto">
                本交互式看板旨在通过可视化手段，梳理2026年全年的设计工作重点、时间节点及资源分配。
                涵盖常规迭代、五大展会、节日营销及年度核心项目。
            </p>
        </header>

        <!-- Key Metrics Cards -->
        <section class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-10">
            <div class="bg-white p-6 rounded-xl shadow-sm border-l-4 border-blue-500 hover:shadow-md transition-shadow">
                <div class="text-sm font-medium text-slate-500 uppercase tracking-wider">重点展会</div>
                <div class="mt-2 flex items-baseline">
                    <span class="text-4xl font-bold text-slate-900">5</span>
                    <span class="ml-2 text-sm text-slate-500">场次 (中/美/澳)</span>
                </div>
                <div class="mt-2 text-xs text-blue-600 font-semibold">4月, 6月, 8月, 9月, 10月</div>
            </div>
            
            <div class="bg-white p-6 rounded-xl shadow-sm border-l-4 border-indigo-500 hover:shadow-md transition-shadow">
                <div class="text-sm font-medium text-slate-500 uppercase tracking-wider">节日营销</div>
                <div class="mt-2 flex items-baseline">
                    <span class="text-4xl font-bold text-slate-900">8+</span>
                    <span class="ml-2 text-sm text-slate-500">节点 (欧美为主)</span>
                </div>
                <div class="mt-2 text-xs text-indigo-600 font-semibold">需提前1个月出图</div>
            </div>

            <div class="bg-white p-6 rounded-xl shadow-sm border-l-4 border-emerald-500 hover:shadow-md transition-shadow">
                <div class="text-sm font-medium text-slate-500 uppercase tracking-wider">常规迭代</div>
                <div class="mt-2 flex items-baseline">
                    <span class="text-4xl font-bold text-slate-900">4</span>
                    <span class="ml-2 text-sm text-slate-500">次 (HD复盘/优化)</span>
                </div>
                <div class="mt-2 text-xs text-emerald-600 font-semibold">官网同步更新</div>
            </div>

            <div class="bg-white p-6 rounded-xl shadow-sm border-l-4 border-amber-500 hover:shadow-md transition-shadow">
                <div class="text-sm font-medium text-slate-500 uppercase tracking-wider">核心项目</div>
                <div class="mt-2 flex items-baseline">
                    <span class="text-4xl font-bold text-slate-900">Q4</span>
                    <span class="ml-2 text-sm text-slate-500">重点</span>
                </div>
                <div class="mt-2 text-xs text-amber-600 font-semibold">2027年新品PPT</div>
            </div>
        </section>

        <!-- Main Content Layout -->
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
            
            <!-- Left Column: Interactive Timeline (Spans 2 cols) -->
            <div class="lg:col-span-2 space-y-8">
                
                <!-- Introduction to Timeline -->
                <div class="bg-white p-6 rounded-xl shadow-sm">
                    <h2 class="text-xl font-bold text-slate-800 mb-2">🗓️ 年度工作节奏概览</h2>
                    <p class="text-slate-600 text-sm mb-4">
                        点击下方季度标签，查看详细的月度工作安排。此部分将展会、节日与常规工作整合在同一时间轴上，便于识别工作重叠期。
                    </p>

                    <!-- Quarterly Navigation -->
                    <div class="flex space-x-2 border-b border-slate-200 mb-6" id="quarterTabs">
                        <button onclick="updateQuarter('q1')" id="tab-q1" class="tab-active flex-1 py-3 px-4 text-center font-medium rounded-t-lg transition-colors focus:outline-none">第一季度 (Q1)</button>
                        <button onclick="updateQuarter('q2')" id="tab-q2" class="tab-inactive flex-1 py-3 px-4 text-center font-medium rounded-t-lg transition-colors focus:outline-none">第二季度 (Q2)</button>
                        <button onclick="updateQuarter('q3')" id="tab-q3" class="tab-inactive flex-1 py-3 px-4 text-center font-medium rounded-t-lg transition-colors focus:outline-none">第三季度 (Q3)</button>
                        <button onclick="updateQuarter('q4')" id="tab-q4" class="tab-inactive flex-1 py-3 px-4 text-center font-medium rounded-t-lg transition-colors focus:outline-none">第四季度 (Q4)</button>
                    </div>

                    <!-- Dynamic Content Area -->
                    <div id="quarterContent" class="fade-in space-y-6">
                        <!-- Content will be injected by JS -->
                    </div>
                </div>

                <!-- Exhibition Deep Dive -->
                <div class="bg-white p-6 rounded-xl shadow-sm">
                    <h2 class="text-xl font-bold text-slate-800 mb-2">🎪 展会工作流可视化</h2>
                    <p class="text-slate-600 text-sm mb-6">
                        针对全年的五大展会，我们采用了标准化的“两段式”工作流。此处展示了各展会的关键交付节点。
                    </p>
                    
                    <div class="space-y-6">
                        <!-- Exhibition Logic Visualization -->
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="border border-slate-200 rounded-lg p-4 bg-blue-50">
                                <h3 class="font-bold text-blue-800 mb-2">前期：空间规划</h3>
                                <ul class="list-disc list-inside text-sm text-blue-700 space-y-1">
                                    <li>展架尺寸图</li>
                                    <li>布局效果图</li>
                                    <li><span class="font-semibold">时间点：</span>展前 2-3 个月</li>
                                </ul>
                            </div>
                            <div class="border border-slate-200 rounded-lg p-4 bg-indigo-50">
                                <h3 class="font-bold text-indigo-800 mb-2">后期：平面视觉</h3>
                                <ul class="list-disc list-inside text-sm text-indigo-700 space-y-1">
                                    <li>小样册排版 & 打样</li>
                                    <li>邀请函设计 & 发放</li>
                                    <li>招贴画定稿 & 下厂</li>
                                    <li><span class="font-semibold">时间点：</span>展前 1-1.5 个月</li>
                                </ul>
                            </div>
                        </div>

                        <!-- Simple Gantt-like list -->
                        <div class="mt-6">
                            <h3 class="text-sm font-semibold text-slate-500 uppercase tracking-wider mb-3">2026 展会排期表</h3>
                            <div class="space-y-3" id="exhibitionList">
                                <!-- JS Populated -->
                            </div>
                        </div>
                    </div>
                </div>

            </div>

            <!-- Right Column: Analytics & Strategy (Spans 1 col) -->
            <div class="space-y-8">
                
                <!-- Workload Chart -->
                <div class="bg-white p-6 rounded-xl shadow-sm">
                    <h2 class="text-xl font-bold text-slate-800 mb-2">📊 工作负荷分析</h2>
                    <p class="text-slate-600 text-sm mb-4">
                        基于任务数量与紧急程度的月度负荷估算。请注意4月、6月及8-10月的峰值。
                    </p>
                    <div class="chart-container">
                        <canvas id="workloadChart"></canvas>
                    </div>
                    <div class="mt-4 text-xs text-slate-500 text-center">
                        *分数基于任务复杂度估算 (1-5分)
                    </div>
                </div>

                <!-- Management Suggestions -->
                <div class="bg-slate-800 text-white p-6 rounded-xl shadow-lg">
                    <h2 class="text-xl font-bold mb-4 text-amber-400">💡 总监管理建议</h2>
                    <p class="text-slate-300 text-sm mb-6">
                        为确保高效交付，建议执行以下三大策略：
                    </p>
                    
                    <div class="space-y-5">
                        <div class="flex items-start">
                            <div class="flex-shrink-0 bg-slate-700 p-2 rounded text-xl">🧩</div>
                            <div class="ml-3">
                                <h3 class="font-bold text-sm text-white">工作拆解法则</h3>
                                <p class="text-xs text-slate-400 mt-1">
                                    将“空间设计”与“平面物料”拆分给不同设计师，或严格区隔时间段，避免临展撞车。
                                </p>
                            </div>
                        </div>

                        <div class="flex items-start">
                            <div class="flex-shrink-0 bg-slate-700 p-2 rounded text-xl">📂</div>
                            <div class="ml-3">
                                <h3 class="font-bold text-sm text-white">素材复用池 (Asset Library)</h3>
                                <p class="text-xs text-slate-400 mt-1">
                                    年初建立标准展架库与通用样册模板。仅替换主KV，可节省 30% 工作量。
                                </p>
                            </div>
                        </div>

                        <div class="flex items-start">
                            <div class="flex-shrink-0 bg-slate-700 p-2 rounded text-xl">⏳</div>
                            <div class="ml-3">
                                <h3 class="font-bold text-sm text-white">机动时间 (Buffer Time)</h3>
                                <p class="text-xs text-slate-400 mt-1">
                                    2月春节、10月国庆需重点关注。广交会物料下厂需比日常提前 15 天。
                                </p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Holiday Quick List -->
                <div class="bg-white p-6 rounded-xl shadow-sm">
                    <h2 class="text-lg font-bold text-slate-800 mb-3">🎉 节日贺卡待办</h2>
                    <div class="h-48 overflow-y-auto task-scroll pr-2">
                        <ul class="space-y-3" id="holidayList">
                            <!-- JS Populated -->
                        </ul>
                    </div>
                </div>

            </div>
        </div>

        <footer class="mt-12 text-center text-slate-400 text-sm">
            <p>© 2026 Design Department Work Plan Dashboard. Generated for internal planning.</p>
        </footer>

    </div>

    <!-- Data & Logic -->
    <script>
        // --- DATA STORAGE ---
        // Storing the structured data from the source report
        const quarterData = {
            q1: {
                title: "第一季度：新年开局与春展筹备",
                summary: "包含2月美国展的紧急筹备与开展，以及4月春季广交会的前期规划。春节假期叠加美国展，进度极度紧张。",
                months: [
                    {
                        name: "1月",
                        tags: ["常规", "节日", "展会前期"],
                        tasks: [
                            { text: "Q4(25年) HD复盘 & Q1 HD优化方案启动", type: "routine" },
                            { text: "官网新年视觉更新", type: "routine" },
                            { text: "情人节（2.14）贺卡及配图设计", type: "holiday" },
                            { text: "4月广交会：展架尺寸图、布局效果图初稿", type: "expo_early" },
                            { text: "美国展（2月）：小样册、招贴画、邀请函冲刺", type: "expo_late" }
                        ]
                    },
                    {
                        name: "2月",
                        tags: ["春节", "美国展"],
                        tasks: [
                            { text: "🔥 2月美国展开展", type: "event" },
                            { text: "4月广交会：邀请函设计并发放", type: "expo_late" },
                            { text: "4月广交会：小样册排版、招贴画构思", type: "expo_late" },
                            { text: "圣帕特里克节（3.17）贺卡设计（选做）", type: "holiday" },
                            { text: "⚠️ 重点：春节假期叠加美国展开展，需极度前置工作", type: "alert" }
                        ]
                    },
                    {
                        name: "3月",
                        tags: ["收尾", "验收"],
                        tasks: [
                            { text: "Q1 HD优化验收与数据复盘", type: "routine" },
                            { text: "4月广交会：小样册定稿打样、招贴画定稿", type: "expo_late" },
                            { text: "4月广交会：所有印刷品下厂发货", type: "expo_late" },
                            { text: "复活节（4.5）贺卡设计", type: "holiday" }
                        ]
                    }
                ]
            },
            q2: {
                title: "第二季度：连轴多展与年中极限挑战",
                summary: "全年最繁忙时段！4月广交会后，6月迎来上海展与澳洲展的双线作战，需高度统筹资源并复用素材。",
                months: [
                    {
                        name: "4月",
                        tags: ["广交会开展", "双展前期"],
                        tasks: [
                            { text: "🔥 4月春季广交会开展", type: "event" },
                            { text: "官网更新（同步上线广交会春季新品）", type: "routine" },
                            { text: "6月上海展：展架尺寸图确认、布局效果图", type: "expo_early" },
                            { text: "6月澳洲展：展架尺寸图确认、布局效果图", type: "expo_early" },
                            { text: "母亲节（5.10）贺卡设计", type: "holiday" }
                        ]
                    },
                    {
                        name: "5月",
                        tags: ["双展冲刺"],
                        tasks: [
                            { text: "6月上海展：邀请函、小样册打样、招贴画定稿", type: "expo_late" },
                            { text: "6月澳洲展：邀请函、小样册打样、招贴画定稿", type: "expo_late" },
                            { text: "父亲节（6.21）贺卡设计", type: "holiday" },
                            { text: "⚠️ 重点：双展物料齐发，必须采用素材复用池策略", type: "alert" }
                        ]
                    },
                    {
                        name: "6月",
                        tags: ["双展开展", "年中复盘"],
                        tasks: [
                            { text: "🔥 6月上海展开展", type: "event" },
                            { text: "🔥 6月澳洲展开展", type: "event" },
                            { text: "Q2 HD复盘 & Q3 HD优化方案启动", type: "routine" },
                            { text: "官网年中更新", type: "routine" }
                        ]
                    }
                ]
            },
            q3: {
                title: "第三季度：双展复盘与秋季蓄水",
                summary: "上半年高强度展会告一段落，Q3重点在于视觉资产沉淀与10月秋季广交会筹备。",
                months: [
                    {
                        name: "7月",
                        tags: ["资产归档", "常规迭代"],
                        tasks: [
                            { text: "Q2 极限双展（上海/澳洲）设计物料复盘与归档", type: "routine" },
                            { text: "官网更新（同步上线双展新品）", type: "routine" }
                        ]
                    },
                    {
                        name: "8月",
                        tags: ["广交会前期"],
                        tasks: [
                            { text: "10月广交会：展架尺寸图、布局效果图", type: "expo_early" },
                            { text: "新品PPT前期素材初步收集", type: "routine" }
                        ]
                    },
                    {
                        name: "9月",
                        tags: ["广交会后期"],
                        tasks: [
                            { text: "Q3 HD复盘 & Q4 HD优化方案启动", type: "routine" },
                            { text: "10月广交会：邀请函发放、秋季版小样册更新", type: "expo_late" },
                            { text: "万圣节（10.31）贺卡设计", type: "holiday" }
                        ]
                    }
                ]
            },
            q4: {
                title: "第四季度：秋季收官与来年规划",
                summary: "秋季广交会后，重点转向2027年新品PPT的制作及年度总结。",
                months: [
                    {
                        name: "10月",
                        tags: ["广交会开展"],
                        tasks: [
                            { text: "🔥 10月秋季广交会开展", type: "event" },
                            { text: "官网更新（同步上线秋季新品）", type: "routine" },
                            { text: "感恩节（11.26）贺卡设计", type: "holiday" }
                        ]
                    },
                    {
                        name: "11月",
                        tags: ["核心项目启动"],
                        tasks: [
                            { text: "🌟 2027年新品PPT：启动期（资料/框架/KV）", type: "core" },
                            { text: "圣诞节（12.25）及新年贺卡、电子贺卡筹备", type: "holiday" }
                        ]
                    },
                    {
                        name: "12月",
                        tags: ["核心项目交付", "年终总结"],
                        tasks: [
                            { text: "🌟 2027年新品PPT：交付期（动效/渲染/定稿）", type: "core" },
                            { text: "Q4 HD复盘 & 2026年度工作年终总结", type: "routine" },
                            { text: "官网年终维护与清理", type: "routine" }
                        ]
                    }
                ]
            }
        };

        const exhibitionList = [
            { name: "春季广交会", month: "4月", status: "国内", color: "bg-blue-100 text-blue-800" },
            { name: "上海展", month: "6月", status: "国内", color: "bg-indigo-100 text-indigo-800" },
            { name: "澳洲展", month: "6月", status: "海外", color: "bg-emerald-100 text-emerald-800" },
            { name: "美国展", month: "2月", status: "海外", color: "bg-violet-100 text-violet-800" },
            { name: "秋季广交会", month: "10月", status: "国内", color: "bg-blue-100 text-blue-800" }
        ];

        const holidays = [
            { name: "情人节", date: "2月14日" },
            { name: "圣帕特里克节", date: "3月17日" },
            { name: "复活节", date: "4月5日" },
            { name: "母亲节", date: "5月10日" },
            { name: "父亲节", date: "6月21日" },
            { name: "万圣节", date: "10月31日" },
            { name: "感恩节", date: "11月26日" },
            { name: "圣诞节", date: "12月25日" }
        ];

        // --- HELPER FUNCTIONS ---
        
        // Returns CSS classes based on task type
        function getTaskStyle(type) {
            switch(type) {
                case 'event': return 'border-l-4 border-red-500 bg-red-50 text-red-700 font-bold';
                case 'core': return 'border-l-4 border-amber-500 bg-amber-50 text-amber-800 font-bold';
                case 'expo_early': return 'border-l-4 border-blue-400 bg-white';
                case 'expo_late': return 'border-l-4 border-indigo-400 bg-white';
                case 'holiday': return 'border-l-4 border-pink-400 bg-pink-50';
                case 'alert': return 'border-l-4 border-orange-500 bg-orange-100 text-orange-800 font-bold';
                default: return 'border-l-4 border-slate-300 bg-white';
            }
        }

        // Renders the Quarter Content
        function renderQuarter(qId) {
            const data = quarterData[qId];
            const container = document.getElementById('quarterContent');
            
            // Fade out
            container.style.opacity = '0';
            
            setTimeout(() => {
                let html = `
                    <div class="mb-4">
                        <h3 class="text-lg font-bold text-slate-700">${data.title}</h3>
                        <p class="text-sm text-slate-500">${data.summary}</p>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                `;

                data.months.forEach(month => {
                    html += `
                        <div class="bg-slate-50 rounded-lg p-4 border border-slate-200 flex flex-col h-full">
                            <div class="flex justify-between items-center mb-3">
                                <h4 class="text-xl font-bold text-slate-800">${month.name}</h4>
                                <div class="flex flex-wrap gap-1 justify-end">
                                    ${month.tags.map(tag => `<span class="px-2 py-0.5 bg-slate-200 text-slate-600 text-[10px] rounded-full">${tag}</span>`).join('')}
                                </div>
                            </div>
                            <ul class="space-y-2 flex-grow">
                                ${month.tasks.map(task => `
                                    <li class="text-xs p-2 rounded shadow-sm ${getTaskStyle(task.type)}">
                                        ${task.text}
                                    </li>
                                `).join('')}
                            </ul>
                        </div>
                    `;
                });

                html += `</div>`;
                container.innerHTML = html;
                
                // Fade in
                container.style.opacity = '1';
                container.style.transform = 'translateY(0)';
            }, 150); // Short delay for transition
        }

        // Tab Switching Logic
        function updateQuarter(qId) {
            // Reset tabs
            ['q1', 'q2', 'q3', 'q4'].forEach(id => {
                const btn = document.getElementById(`tab-${id}`);
                if (id === qId) {
                    btn.classList.remove('tab-inactive');
                    btn.classList.add('tab-active');
                } else {
                    btn.classList.remove('tab-active');
                    btn.classList.add('tab-inactive');
                }
            });

            // Render content
            renderQuarter(qId);
        }

        // Render Side Lists
        function renderSideLists() {
            // Exhibitions
            const expoContainer = document.getElementById('exhibitionList');
            exhibitionList.forEach(expo => {
                expoContainer.innerHTML += `
                    <div class="flex items-center justify-between p-3 bg-white rounded border border-slate-100 shadow-sm">
                        <div>
                            <span class="font-bold text-slate-700 text-sm">${expo.name}</span>
                            <span class="text-xs text-slate-400 block">${expo.status}</span>
                        </div>
                        <span class="px-2 py-1 rounded text-xs font-semibold ${expo.color}">${expo.month}</span>
                    </div>
                `;
            });

            // Holidays
            const holidayContainer = document.getElementById('holidayList');
            holidays.forEach(h => {
                holidayContainer.innerHTML += `
                    <li class="flex justify-between items-center text-sm border-b border-slate-100 pb-2 last:border-0">
                        <span class="text-slate-600">${h.name}</span>
                        <span class="text-slate-400 font-mono text-xs">${h.date}</span>
                    </li>
                `;
            });
        }

        // --- CHART INITIALIZATION ---
        function initCharts() {
            const ctx = document.getElementById('workloadChart').getContext('2d');
            
            // Workload Estimation logic derived from task density in MD
            // Jan: 4 (US prep), Feb: 4.5 (CNY + US), Mar: 3, Apr: 5 (Expo), May: 5 (2x Expo), Jun: 6 (2x Expo), 
            // Jul: 2, Aug: 2.5, Sep: 3.5, Oct: 5 (Expo), Nov: 3.5, Dec: 4 (PPT)
            const workloadData = [4, 4.5, 3, 5, 5, 6, 2, 2.5, 3.5, 5, 3.5, 4];

            new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: ['1月', '2月', '3月', '4月', '5月', '6月', '7月', '8月', '9月', '10月', '11月', '12月'],
                    datasets: [{
                        label: '预估工作负荷指数',
                        data: workloadData,
                        backgroundColor: (ctx) => {
                            const val = ctx.raw;
                            // High workload = Red/Orange, Med = Blue, Low = Green
                            if (val >= 4.5) return 'rgba(239, 68, 68, 0.7)'; // Red-500
                            if (val >= 3.5) return 'rgba(245, 158, 11, 0.7)'; // Amber-500
                            return 'rgba(59, 130, 246, 0.7)'; // Blue-500
                        },
                        borderRadius: 4,
                        borderWidth: 0
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { display: false },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    return `负荷指数: ${context.raw} / 5`;
                                },
                                afterLabel: function(context) {
                                    const highMonths = [0, 1, 3, 4, 5, 9]; // indices: Jan, Feb, Apr, May, Jun, Oct
                                    if (highMonths.includes(context.dataIndex)) {
                                        return "展会/项目密集期";
                                    }
                                    return "";
                                }
                            }
                        }
                    },
                    scales: {
                        y: {
                            beginAtZero: true,
                            max: 6,
                            ticks: { display: false },
                            grid: { display: false }
                        },
                        x: {
                            grid: { display: false }
                        }
                    }
                }
            });
        }

        // --- INITIALIZE APP ---
        document.addEventListener('DOMContentLoaded', () => {
            renderQuarter('q1'); // Default to Q1
            renderSideLists();
            initCharts();
        });

    </script>
</body>
</html>
