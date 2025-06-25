<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人自我介绍</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#4F46E5',
                        secondary: '#10B981',
                        accent: '#F59E0B',
                        dark: '#1E293B',
                        light: '#F8FAFC'
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <style type="text/tailwindcss">
        @layer utilities {
            .content-auto {
                content-visibility: auto;
            }
            .text-shadow {
                text-shadow: 0 2px 4px rgba(0,0,0,0.1);
            }
            .text-gradient {
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
                background-image: linear-gradient(to right, #4F46E5, #10B981);
            }
            .bg-pattern {
                background-image: 
                    radial-gradient(rgba(79, 70, 229, 0.05) 1px, transparent 1px),
                    radial-gradient(rgba(79, 70, 229, 0.05) 1px, transparent 1px);
                background-size: 40px 40px;
                background-position: 0 0, 20px 20px;
            }
            .animate-float {
                animation: float 6s ease-in-out infinite;
            }
            .animate-type {
                animation: typing 2s steps(30) forwards, blink 1s steps(30) infinite;
            }
            .animate-fade-in {
                animation: fadeIn 1.5s ease-in forwards;
            }
            .animate-slide-up {
                animation: slideUp 1s ease-out forwards;
            }
            .animate-pulse-slow {
                animation: pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite;
            }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink {
            from, to { border-color: transparent }
            50% { border-color: #4F46E5 }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .cursor {
            border-right: 2px solid #4F46E5;
            display: inline-block;
            margin-left: 5px;
            animation: blink 1s step-end infinite;
        }
    </style>
</head>
<body class="bg-light text-dark font-sans bg-pattern min-h-screen">
    <!-- 导航栏 -->
    <nav class="fixed w-full top-0 z-50 transition-all duration-300" id="navbar">
        <div class="container mx-auto px-4 py-3 flex justify-between items-center">
            <a href="#" class="text-2xl font-bold text-gradient">自我介绍</a>
            <div class="hidden md:flex space-x-8">
                <a href="#about" class="text-dark hover:text-primary transition-colors">关于我</a>
                <a href="#skills" class="text-dark hover:text-primary transition-colors">技能</a>
                <a href="#experience" class="text-dark hover:text-primary transition-colors">经历</a>
                <a href="#contact" class="text-dark hover:text-primary transition-colors">联系我</a>
            </div>
            <button class="md:hidden text-dark focus:outline-none" id="menuBtn">
                <i class="fa fa-bars text-2xl"></i>
            </button>
        </div>
        <!-- 移动端菜单 -->
        <div class="md:hidden hidden bg-white shadow-lg absolute w-full" id="mobileMenu">
            <div class="container mx-auto px-4 py-3 flex flex-col space-y-4">
                <a href="#about" class="text-dark hover:text-primary transition-colors py-2">关于我</a>
                <a href="#skills" class="text-dark hover:text-primary transition-colors py-2">技能</a>
                <a href="#experience" class="text-dark hover:text-primary transition-colors py-2">经历</a>
                <a href="#contact" class="text-dark hover:text-primary transition-colors py-2">联系我</a>
            </div>
        </div>
    </nav>

    <!-- 英雄区域 -->
    <section class="pt-32 pb-20 md:pt-40 md:pb-32 container mx-auto px-4 flex flex-col md:flex-row items-center">
        <div class="md:w-1/2 mb-10 md:mb-0">
            <h1 class="text-[clamp(2.5rem,5vw,4rem)] font-bold leading-tight text-shadow mb-4 animate-fade-in" style="animation-delay: 0.2s">
                你好，我是 <span class="text-gradient">张三</span>
            </h1>
            <p class="text-[clamp(1rem,2vw,1.25rem)] text-gray-600 mb-8 max-w-lg animate-fade-in" style="animation-delay: 0.4s">
                一个充满热情的前端开发者，致力于创造美观、交互友好的网页体验
            </p>
            <div class="flex flex-wrap gap-4 animate-fade-in" style="animation-delay: 0.6s">
                <a href="#contact" class="bg-primary hover:bg-primary/90 text-white px-6 py-3 rounded-full font-medium transition-all transform hover:scale-105 shadow-lg hover:shadow-primary/20">
                    联系我 <i class="fa fa-arrow-right ml-2"></i>
                </a>
                <a href="#about" class="bg-white hover:bg-gray-100 text-dark border border-primary px-6 py-3 rounded-full font-medium transition-all transform hover:scale-105 shadow-md">
                    了解更多
                </a>
            </div>
        </div>
        <div class="md:w-1/2 flex justify-center animate-float">
            <div class="relative">
                <!-- 主图片 -->
                <div class="w-64 h-64 md:w-80 md:h-80 rounded-full overflow-hidden border-8 border-white shadow-2xl relative z-10">
                    <img src="https://picsum.photos/seed/portrait/800/800" alt="个人照片" class="w-full h-full object-cover transition-transform hover:scale-110 duration-700">
                </div>
                <!-- 装饰圆环 -->
                <div class="w-72 h-72 md:w-88 md:h-88 rounded-full border-4 border-primary/30 absolute -top-4 -left-4 animate-pulse-slow"></div>
                <div class="w-80 h-80 md:w-96 md:h-96 rounded-full border-2 border-secondary/20 absolute -top-8 -left-8"></div>
            </div>
        </div>
    </section>

    <!-- 关于我 -->
    <section id="about" class="py-20 bg-white/50 backdrop-blur-sm container mx-auto px-4">
        <div class="text-center mb-16">
            <h2 class="text-[clamp(1.8rem,3vw,2.5rem)] font-bold mb-4 text-dark">关于我</h2>
            <div class="w-20 h-1 bg-primary mx-auto rounded-full"></div>
        </div>

        <div class="grid md:grid-cols-2 gap-12 items-center">
            <div class="order-2 md:order-1">
                <h3 class="text-2xl font-bold mb-6 text-dark">我是一个充满激情的开发者</h3>
                <p class="text-gray-600 mb-6 leading-relaxed">
                    从大学期间接触编程开始，我就深深爱上了创造数字体验的过程。至今已有3年的前端开发经验，专注于打造美观、易用且性能优异的网页应用。
                </p>
                <p class="text-gray-600 mb-8 leading-relaxed">
                    我相信优秀的设计不仅要好看，还要能解决实际问题。因此，我始终关注用户体验和交互设计，致力于将复杂的功能转化为简洁直观的界面。
                </p>
                
                <div class="grid grid-cols-2 gap-6 mb-8">
                    <div class="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow">
                        <div class="text-primary text-3xl mb-3"><i class="fa fa-code"></i></div>
                        <h4 class="font-bold text-lg mb-2">开发经验</h4>
                        <p class="text-gray-500">3+ 年</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow">
                        <div class="text-secondary text-3xl mb-3"><i class="fa fa-trophy"></i></div>
                        <h4 class="font-bold text-lg mb-2">完成项目</h4>
                        <p class="text-gray-500">20+ 个</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow">
                        <div class="text-accent text-3xl mb-3"><i class="fa fa-users"></i></div>
                        <h4 class="font-bold text-lg mb-2">合作客户</h4>
                        <p class="text-gray-500">15+ 家</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow">
                        <div class="text-primary text-3xl mb-3"><i class="fa fa-coffee"></i></div>
                        <h4 class="font-bold text-lg mb-2">每日咖啡</h4>
                        <p class="text-gray-500">2+ 杯</p>
                    </div>
                </div>
                
                <a href="#contact" class="inline-flex items-center text-primary font-medium hover:underline">
                    想了解更多我的故事 <i class="fa fa-long-arrow-right ml-2 transition-transform hover:translate-x-1"></i>
                </a>
            </div>
            
            <div class="order-1 md:order-2 relative">
                <!-- 个人照片与装饰元素 -->
                <div class="relative z-10 rounded-xl overflow-hidden shadow-2xl">
                    <img src="https://picsum.photos/seed/work/600/800" alt="工作中的我" class="w-full h-auto">
                </div>
                <!-- 装饰元素 -->
                <div class="absolute -bottom-6 -right-6 w-40 h-40 bg-primary/10 rounded-lg -z-10"></div>
                <div class="absolute -top-6 -left-6 w-32 h-32 bg-secondary/10 rounded-lg -z-10"></div>
            </div>
        </div>
    </section>

    <!-- 技能 -->
    <section id="skills" class="py-20 container mx-auto px-4">
        <div class="text-center mb-16">
            <h2 class="text-[clamp(1.8rem,3vw,2.5rem)] font-bold mb-4 text-dark">我的技能</h2>
            <div class="w-20 h-1 bg-primary mx-auto rounded-full"></div>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- 技能卡片 1 -->
            <div class="bg-white rounded-xl shadow-md p-8 hover:shadow-xl transition-all duration-300 transform hover:-translate-y-2">
                <div class="w-16 h-16 bg-primary/10 rounded-full flex items-center justify-center mb-6 text-primary text-2xl">
                    <i class="fa fa-code"></i>
                </div>
                <h3 class="text-xl font-bold mb-4">前端开发</h3>
                <p class="text-gray-600 mb-6">
                    精通HTML5、CSS3和JavaScript，熟悉现代前端框架如React和Vue，能够构建响应式、交互性强的网页应用。
                </p>
                <div class="space-y-4">
                    <div>
                        <div class="flex justify-between mb-1">
                            <span class="text-sm font-medium">HTML/CSS</span>
                            <span class="text-sm font-medium">95%</span>
                        </div>
                        <div class="w-full bg-gray-200 rounded-full h-2">
                            <div class="bg-primary h-2 rounded-full" style="width: 95%"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between mb-1">
                            <span class="text-sm font-medium">JavaScript</span>
                            <span class="text-sm font-medium">90%</span>
                        </div>
                        <div class="w-full bg-gray-200 rounded-full h-2">
                            <div class="bg-primary h-2 rounded-full" style="width: 90%"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between mb-1">
                            <span class="text-sm font-medium">React</span>
                            <span class="text-sm font-medium">85%</span>
                        </div>
                        <div class="w-full bg-gray-200 rounded-full h-2">
                            <div class="bg-primary h-2 rounded-full" style="width: 85%"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- 技能卡片 2 -->
            <div class="bg-white rounded-xl shadow-md p-8 hover:shadow-xl transition-all duration-300 transform hover:-translate-y-2">
                <div class="w-16 h-16 bg-secondary/10 rounded-full flex items-center justify-center mb-6 text-secondary text-2xl">
                    <i class="fa fa-mobile"></i>
                </div>
                <h3 class="text-xl font-bold mb-4">响应式设计</h3>
                <p class="text-gray-600 mb-6">
                    擅长创建在各种设备上都能良好显示的网页，精通响应式设计原则和技术，确保用户在手机、平板和桌面端都有最佳体验。
                </p>
                <div class="space-y-4">
                    <div>
                        <div class="flex justify-between mb-1">
                            <span class="text-sm font-medium">响应式布局</span>
                            <span class="text-sm font-medium">90%</span>
                        </div>
                        <div class="w-full bg-gray-200 rounded-full h-2">
                            <div class="bg-secondary h-2 rounded-full" style="width: 90%"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between mb-1">
                            <span class="text-sm font-medium">移动优先设计</span>
                            <span class="text-sm font-medium">85%</span>
                        </div>
                        <div class="w-full bg-gray-200 rounded-full h-2">
                            <div class="bg-secondary h-2 rounded-full" style="width: 85%"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between mb-1">
                            <span class="text-sm font-medium">性能优化</span>
                            <span class="text-sm font-medium">80%</span>
                        </div>
                        <div class="w-full bg-gray-200 rounded-full h-2">
                            <div class="bg-secondary h-2 rounded-full" style="width: 80%"></div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- 技能卡片 3 -->
            <div class="bg-white rounded-xl shadow-md p-8 hover:shadow-xl transition-all duration-300 transform hover:-translate-y-2">
                <div class="w-16 h-16 bg-accent/10 rounded-full flex items-center justify-center mb-6 text-accent text-2xl">
                    <i class="fa fa-paint-brush"></i>
                </div>
                <h3 class="text-xl font-bold mb-4">UI/UX设计</h3>
                <p class="text-gray-600 mb-6">
                    具备良好的设计审美和用户体验意识，能够将设计稿转化为高质量的前端实现，并在过程中提出优化建议。
                </p>
                <div class="space-y-4">
                    <div>
                        <div class="flex justify-between mb-1">
                            <span class="text-sm font-medium">设计理解</span>
                            <span class="text-sm font-medium">85%</span>
                        </div>
                        <div class="w-full bg-gray-200 rounded-full h-2">
                            <div class="bg-accent h-2 rounded-full" style="width: 85%"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between mb-1">
                            <span class="text-sm font-medium">交互设计</span>
                            <span class="text-sm font-medium">80%</span>
                        </div>
                        <div class="w-full bg-gray-200 rounded-full h-2">
                            <div class="bg-accent h-2 rounded-full" style="width: 80%"></div>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between mb-1">
                            <span class="text-sm font-medium">设计系统</span>
                            <span class="text-sm font-medium">75%</span>
                        </div>
                        <div class="w-full bg-gray-200 rounded-full h-2">
                            <div class="bg-accent h-2 rounded-full" style="width: 75%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- 技能图标展示 -->
        <div class="mt-16 grid grid-cols-4 md:grid-cols-6 gap-8 justify-items-center">
            <div class="text-center p-4 hover:scale-110 transition-transform">
                <div class="w-16 h-16 bg-primary/10 rounded-full flex items-center justify-center mx-auto mb-3 text-primary text-2xl">
                    <i class="fa fa-html5"></i>
                </div>
                <p class="text-sm">HTML5</p>
            </div>
            <div class="text-center p-4 hover:scale-110 transition-transform">
                <div class="w-16 h-16 bg-primary/10 rounded-full flex items-center justify-center mx-auto mb-3 text-primary text-2xl">
                    <i class="fa fa-css3"></i>
                </div>
                <p class="text-sm">CSS3</p>
            </div>
            <div class="text-center p-4 hover:scale-110 transition-transform">
                <div class="w-16 h-16 bg-yellow-500/10 rounded-full flex items-center justify-center mx-auto mb-3 text-yellow-500 text-2xl">
                    <i class="fa fa-code"></i>
                </div>
                <p class="text-sm">JavaScript</p>
            </div>
            <div class="text-center p-4 hover:scale-110 transition-transform">
                <div class="w-16 h-16 bg-blue-500/10 rounded-full flex items-center justify-center mx-auto mb-3 text-blue-500 text-2xl">
                    <i class="fa fa-react"></i>
                </div>
                <p class="text-sm">React</p>
            </div>
            <div class="text-center p-4 hover:scale-110 transition-transform">
                <div class="w-16 h-16 bg-green-500/10 rounded-full flex items-center justify-center mx-auto mb-3 text-green-500 text-2xl">
                    <i class="fa fa-vuejs"></i>
                </div>
                <p class="text-sm">Vue</p>
            </div>
            <div class="text-center p-4 hover:scale-110 transition-transform">
                <div class="w-16 h-16 bg-purple-500/10 rounded-full flex items-center justify-center mx-auto mb-3 text-purple-500 text-2xl">
                    <i class="fa fa-node-js"></i>
                </div>
                <p class="text-sm">Node.js</p>
            </div>
        </div>
    </section>

    <!-- 经历 -->
    <section id="experience" class="py-20 bg-white/50 backdrop-blur-sm container mx-auto px-4">
        <div class="text-center mb-16">
            <h2 class="text-[clamp(1.8rem,3vw,2.5rem)] font-bold mb-4 text-dark">我的经历</h2>
            <div class="w-20 h-1 bg-primary mx-auto rounded-full"></div>
        </div>

        <div class="relative">
            <!-- 时间线 -->
            <div class="absolute left-1/2 transform -translate-x-1/2 h-full w-1 bg-primary/20 md:w-2"></div>
            
            <!-- 经历项目 1 -->
            <div class="relative mb-16 flex flex-col md:flex-row items-center">
                <div class="md:w-1/2 md:pr-12 md:text-right order-2 md:order-1">
                    <h3 class="text-xl font-bold mb-2">高级前端开发者</h3>
                    <p class="text-gray-600 mb-4">ABC科技有限公司</p>
                    <p class="text-primary font-medium">2022年6月 - 至今</p>
                    <p class="text-gray-600 mt-4">
                        负责公司核心产品的前端架构设计与开发，主导响应式设计重构，使移动端访问量提升40%。带领3人前端团队，制定开发规范和技术选型。
                    </p>
                </div>
                <div class="absolute left-1/2 transform -translate-x-1/2 w-6 h-6 bg-primary rounded-full border-4 border-white z-10 md:mt-0"></div>
                <div class="md:w-1/2 md:pl-12 order-1 md:order-2">
                    <div class="bg-white p-6 rounded-xl shadow-md">
                        <h4 class="font-semibold mb-2">主要成就</h4>
                        <ul class="list-disc pl-5 text-gray-600 space-y-2">
                            <li>重构前端架构，使页面加载速度提升50%</li>
                            <li>引入组件化开发模式，提高开发效率30%</li>
                            <li>优化移动端体验，用户留存率提高25%</li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <!-- 经历项目 2 -->
            <div class="relative mb-16 flex flex-col md:flex-row items-center">
                <div class="md:w-1/2 md:pr-12 md:text-right order-2 md:order-1">
                    <h3 class="text-xl font-bold mb-2">前端开发者</h3>
                    <p class="text-gray-600 mb-4">XYZ网络科技</p>
                    <p class="text-primary font-medium">2020年3月 - 2022年5月</p>
                    <p class="text-gray-600 mt-4">
                        负责多个客户项目的前端开发，包括电商平台、企业官网和管理系统。与设计师和后端开发人员紧密合作，确保项目高质量交付。
                    </p>
                </div>
                <div class="absolute left-1/2 transform -translate-x-1/2 w-6 h-6 bg-primary rounded-full border-4 border-white z-10 md:mt-0"></div>
                <div class="md:w-1/2 md:pl-12 order-1 md:order-2">
                    <div class="bg-white p-6 rounded-xl shadow-md">
                        <h4 class="font-semibold mb-2">主要项目</h4>
                        <ul class="list-disc pl-5 text-gray-600 space-y-2">
                            <li>开发某知名电商平台移动端页面，日活用户超10万</li>
                            <li>重构企业管理系统前端，提升用户操作效率40%</li>
                            <li>实现多个交互动画和微交互，提升产品用户体验</li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <!-- 经历项目 3 -->
            <div class="relative flex flex-col md:flex-row items-center">
                <div class="md:w-1/2 md:pr-12 md:text-right order-2 md:order-1">
                    <h3 class="text-xl font-bold mb-2">前端开发实习生</h3>
                    <p class="text-gray-600 mb-4">创新科技工作室</p>
                    <p class="text-primary font-medium">2019年7月 - 2020年2月</p>
                    <p class="text-gray-600 mt-4">
                        参与多个小型项目的前端开发，学习并实践了现代前端开发流程和最佳实践，积累了宝贵的项目经验。
                    </p>
                </div>
                <div class="absolute left-1/2 transform -translate-x-1/2 w-6 h-6 bg-primary rounded-full border-4 border-white z-10 md:mt-0"></div>
                <div class="md:w-1/2 md:pl-12 order-1 md:order-2">
                    <div class="bg-white p-6 rounded-xl shadow-md">
                        <h4 class="font-semibold mb-2">学习与成长</h4>
                        <ul class="list-disc pl-5 text-gray-600 space-y-2">
                            <li>掌握了React框架的核心概念和实践</li>
                            <li>学习了响应式设计和移动优先开发原则</li>
                            <li>参与代码审查和团队协作，提升了开发技能</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 联系我 -->
    <section id="contact" class="py-20 container mx-auto px-4">
        <div class="text-center mb-16">
            <h2 class="text-[clamp(1.8rem,3vw,2.5rem)] font-bold mb-4 text-dark">联系我</h2>
            <div class="w-20 h-1 bg-primary mx-auto rounded-full"></div>
            <p class="text-gray-600 mt-4 max-w-2xl mx-auto">
                如果你有任何问题或合作机会，欢迎随时联系我。我很乐意听到你的想法！
            </p>
        </div>

        <div class="grid md:grid-cols-2 gap-12 items-start">
            <div>
                <div class="bg-white p-8 rounded-xl shadow-md mb-8">
                    <h3 class="text-xl font-bold mb-6">发送消息</h3>
                    <form id="contactForm">
                        <div class="mb-4">
                            <label for="name" class="block text-gray-700 font-medium mb-2">姓名</label>
                            <input type="text" id="name" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary/50 focus:border-primary" placeholder="你的名字">
                        </div>
                        <div class="mb-4">
                            <label for="email" class="block text-gray-700 font-medium mb-2">邮箱</label>
                            <input type="email" id="email" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary/50 focus:border-primary" placeholder="你的邮箱">
                        </div>
                        <div class="mb-6">
                            <label for="message" class="block text-gray-700 font-medium mb-2">消息</label>
                            <textarea id="message" rows="5" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary/50 focus:border-primary" placeholder="请输入你的消息..."></textarea>
                        </div>
                        <button type="submit" class="w-full bg-primary hover:bg-primary/90 text-white px-6 py-3 rounded-lg font-medium transition-all transform hover:scale-[1.02]">
                            发送消息 <i class="fa fa-paper-plane ml-2"></i>
                        </button>
                    </form>
                </div>

                <div class="bg-white p-8 rounded-xl shadow-md">
                    <h3 class="text-xl font-bold mb-6">联系方式</h3>
                    <div class="space-y-4">
                        <div class="flex items-start">
                            <div class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center mr-4 mt-1">
                                <i class="fa fa-envelope text-primary"></i>
                            </div>
                            <div>
                                <h4 class="font-medium mb-1">邮箱</h4>
                                <p class="text-gray-600">zhangsan@example.com</p>
                            </div>
                        </div>
                        <div class="flex items-start">
                            <div class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center mr-4 mt-1">
                                <i class="fa fa-phone text-primary"></i>
                            </div>
                            <div>
                                <h4 class="font-medium mb-1">电话</h4>
                                <p class="text-gray-600">+86 138 **** 5678</p>
                            </div>
                        </div>
                        <div class="flex items-start">
                            <div class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center mr-4 mt-1">
                                <i class="fa fa-map-marker text-primary"></i>
                            </div>
                            <div>
                                <h4 class="font-medium mb-1">地址</h4>
                                <p class="text-gray-600">上海市浦东新区张江高科技园区</p>
                            </div>
                        </div>
                    </div>

                    <div class="mt-8">
                        <h4 class="font-medium mb-4">社交媒体</h4>
                        <div class="flex space-x-4">
                            <a href="#" class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-colors">
                                <i class="fa fa-github"></i>
                            </a>
                            <a href="#" class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-colors">
                                <i class="fa fa-linkedin"></i>
                            </a>
                            <a href="#" class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-colors">
                                <i class="fa fa-weixin"></i>
                            </a>
                            <a href="#" class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center text-primary hover:bg-primary hover:text-white transition-colors">
                                <i class="fa fa-weibo"></i>
                            </a>
                        </div>
                    </div>
                </div>
            </div>

            <div>
                <div class="bg-white p-8 rounded-xl shadow-md h-full">
                    <h3 class="text-xl font-bold mb-6">关于我</h3>
                    <p class="text-gray-600 mb-6 leading-relaxed">
                        我是一个充满热情的前端开发者，喜欢创造美丽而实用的网页体验。除了编码，我还喜欢阅读技术文章、参加开源项目和探索新的前端技术。
                    </p>
                    <p class="text-gray-600 mb-8 leading-relaxed">
                        在业余时间，我喜欢旅行、摄影和学习新的语言。我相信生活中的各种经历都能为我的工作带来新的灵感和视角。
                    </p>
                    
                    <!-- 兴趣标签 -->
                    <div class="mb-8">
                        <h4 class="font-medium mb-4">我的兴趣</h4>
                        <div class="flex flex-wrap gap-2">
                            <span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">前端开发</span>
                            <span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">UI设计</span>
                            <span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">摄影</span>
                            <span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">旅行</span>
                            <span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">阅读</span>
                            <span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">音乐</span>
                            <span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">咖啡</span>
                            <span class="px-3 py-1 bg-primary/10 text-primary rounded-full text-sm">开源项目</span>
                        </div>
                    </div>
                    
                    <!-- 签名图片 -->
                    <div class="border-t border-gray-200 pt-6">
                        <h4 class="font-medium mb-4">我的签名</h4>
                        <div class="bg-light p-4 rounded-lg text-center">
                            <img src="https://picsum.photos/seed/signature/300/100" alt="签名" class="mx-auto">
                            <p class="mt-4 text-gray-500">张三</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer class="bg-dark text-white py-12">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-4 gap-8 mb-8">
                <div>
                    <h3 class="text-xl font-bold mb-4 text-gradient">自我介绍</h3>
                    <p class="text-gray-400 mb-4">
                        一个充满热情的前端开发者，致力于创造美观、交互友好的网页体验。
                    </p>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fa fa-github"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fa fa-linkedin"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fa fa-weixin"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-colors">
                            <i class="fa fa-weibo"></i>
                        </a>
                    </div>
                </div>
                <div>
                    <h4 class="font-bold text-lg mb-4">快速链接</h4>
                    <ul class="space-y-2">
                        <li><a href="#about" class="text-gray-400 hover:text-white transition-colors">关于我</a></li>
                        <li><a href="#skills" class="text-gray-400 hover:text-white transition-colors">我的技能</a></li>
                        <li><a href="#experience" class="text-gray-400 hover:text-white transition-colors">我的经历</a></li>
                        <li><a href="#contact" class="text-gray-400 hover:text-white transition-colors">联系我</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold text-lg mb-4">技能</h4>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-gray-400 hover:text-white transition-colors">HTML5 / CSS3</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-colors">JavaScript</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-colors">React / Vue</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-colors">响应式设计</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold text-lg mb-4">联系信息</h4>
                    <ul class="space-y-2">
                        <li class="flex items-start">
                            <i class="fa fa-envelope text-primary mt-1 mr-2"></i>
                            <span class="text-gray-400">zhangsan@example.com</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-phone text-primary mt-1 mr-2"></i>
                            <span class="text-gray-400">+86 138 **** 5678</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-map-marker text-primary mt-1 mr-2"></i>
                            <span class="text-gray-400">上海市浦东新区</span>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-gray-800 pt-8 text-center text-gray-500 text-sm">
                <p>&copy; 2025 张三. 保留所有权利.</p>
            </div>
        </div>
    </footer>

    <!-- 返回顶部按钮 -->
    <button id="backToTop" class="fixed bottom-8 right-8 w-12 h-12 bg-primary text-white rounded-full flex items-center justify-center shadow-lg opacity-0 invisible transition-all z-50">
        <i class="fa fa-arrow-up"></i>
    </button>

    <script>
        // 导航栏滚动效果
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('bg-white', 'shadow-md');
                navbar.classList.remove('bg-transparent');
            } else {
                navbar.classList.remove('bg-white', 'shadow-md');
            }
        });

        // 移动端菜单
        const menuBtn = document.getElementById('menuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        menuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
            if (mobileMenu.classList.contains('hidden')) {
                menuBtn.innerHTML = '<i class="fa fa-bars text-2xl"></i>';
            } else {
                menuBtn.innerHTML = '<i class="fa fa-times text-2xl"></i>';
            }
        });

        // 平滑滚动
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                // 关闭移动端菜单
                mobileMenu.classList.add('hidden');
                menuBtn.innerHTML = '<i class="fa fa-bars text-2xl"></i>';
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // 返回顶部按钮
        const backToTopBtn = document.getElementById('backToTop');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 300) {
                backToTopBtn.classList.remove('opacity-0', 'invisible');
                backToTopBtn.classList.add('opacity-100', 'visible');
            } else {
                backToTopBtn.classList.add('opacity-0', 'invisible');
                backToTopBtn.classList.remove('opacity-100', 'visible');
            }
        });

        backToTopBtn.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });

        // 联系表单提交
        const contactForm = document.getElementById('contactForm');
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // 这里可以添加表单验证和提交逻辑
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;
            
            // 简单验证
            if (!name || !email || !message) {
                alert('请填写所有字段');
                return;
            }
            
            // 模拟表单提交
            alert('消息已成功发送！我会尽快回复你。');
            contactForm.reset();
        });

        // 滚动动画
        const animateOnScroll = () => {
            const elements = document.querySelectorAll('.animate-fade-in, .animate-slide-up');
            
            elements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                
                if (elementTop < window.innerHeight - elementVisible) {
                    element.style.opacity = 1;
                    element.style.transform = 'translateY(0)';
                }
            });
        };

        // 初始化动画样式
        document.querySelectorAll('.animate-fade-in, .animate-slide-up').forEach(element => {
            element.style.opacity = 0;
            if (element.classList.contains('animate-slide-up')) {
                element.style.transform = 'translateY(50px)';
            }
            element.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
        });

        // 页面加载和滚动时触发动画
        window.addEventListener('load', animateOnScroll);
        window.addEventListener('scroll', animateOnScroll);
    </script>
</body>
</html>
