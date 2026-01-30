<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Luvigo - Timeless Elegance from Sweden</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- 自定义配置 -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        luvigo: {
                            cream: '#F8F4E9',
                            espresso: '#3A2E24',
                            gold: '#D4B98C',
                            white: '#FFFFFF',
                            overlay: 'rgba(0,0,0,0.4)'
                        }
                    },
                    fontFamily: {
                        serif: ['Playfair Display', 'serif'],
                        sans: ['Inter', 'system-ui', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <!-- 自定义样式 -->
    <style type="text/tailwindcss">
        @layer utilities {
            .fade-in {
                animation: fadeIn 1.5s ease-in-out forwards;
            }
            .slide-up {
                transition: all 1s ease-out;
                opacity: 0;
                transform: translateY(30px);
            }
            .slide-up.active {
                opacity: 1;
                transform: translateY(0);
            }
            @keyframes fadeIn {
                0% { opacity: 0; }
                100% { opacity: 1; }
            }
        }
    </style>
    <!-- 谷歌字体 -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">
</head>
<body class="bg-luvigo-cream min-h-screen font-sans text-luvigo-espresso">
    <!-- 主视觉区域 -->
    <section class="relative h-screen w-full overflow-hidden">
        <!-- 背景图（手工制包高级感图片） -->
        <div class="absolute inset-0 z-0">
            <img src="brandintro.png" class="w-full h-full object-cover">
            <div class="absolute inset-0 bg-luvigo-overlay"></div>
        </div>

        <!-- 品牌名称（页面加载淡入） -->
        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-10 text-center">
            <h1 class="font-serif text-[clamp(4rem,10vw,7rem)] font-bold text-luvigo-white fade-in opacity-0">
                Luvigo
            </h1>
            
            <!-- 品牌介绍（滚轮滑动出现） -->
            <p class="mt-6 text-[clamp(1rem,3vw,1.5rem)] text-luvigo-white/90 slide-up max-w-2xl mx-auto">
                from Sweden, with elegance and timeless sophistication, renowned for modern design and refined aesthetic.
            </p>
        </div>

        <!-- 滚动提示 -->
        <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 text-luvigo-white animate-bounce z-10">
            <i class="fa-solid fa-chevron-down text-xl"></i>
            <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
        </div>
    </section>

    <!-- Bestseller 展示区域 -->
    <section class="py-20 px-4 md:px-8 container mx-auto">
        <h2 class="font-serif text-[clamp(2rem,5vw,3rem)] font-semibold text-center mb-12">Bestseller</h2>
        
        <!-- 本地图片展示（design.png） -->
        <div class="max-w-3xl mx-auto shadow-xl rounded-sm overflow-hidden">
            <img src="design.png" alt="Luvigo bestseller bag" class="w-full h-auto object-cover">
        </div>
    </section>

    <!-- 简单页脚 -->
    <footer class="py-8 bg-luvigo-espresso text-luvigo-white/80 text-center">
        <p>© 2026 Luvigo - All Rights Reserved</p>
    </footer>

    <!-- 交互脚本 -->
    <script>
        // 监听滚轮，触发品牌介绍文字显示
        const brandText = document.querySelector('.slide-up');
        
        function checkScroll() {
            const scrollPosition = window.scrollY;
            // 滚动超过100px时显示品牌介绍文字
            if (scrollPosition > 100) {
                brandText.classList.add('active');
            }
        }

        // 初始检查 + 滚动监听
        window.addEventListener('load', checkScroll);
        window.addEventListener('scroll', checkScroll);
    </script>
</body>
</html>
