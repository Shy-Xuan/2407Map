<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>武汉理工大学校园导航系统</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" />
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="https://unpkg.com/leaflet-routing-machine@3.2.12/dist/leaflet-routing-machine.css" />
</head>

<body>
    <!-- 头部区域 -->
    <header class="main-header">
        <div class="header-logo">
            <img src="1.png" alt="校徽" class="logo-img">
            <h1 class="school-name">武汉理工大学校园导航系统</h1>
        </div>

        <!-- 导航菜单 -->
        <nav class="nav-menu">
            <ul class="menu-list">

                <li><a href="#campus-info">校史昭彰</a></li>
                <li><a href="#attractions">校园地标</a></li>
                <li><a href="#map-container" class="nav-link">地图展示</a></li>
            </ul>
        </nav>

        <!-- 搜索功能区 -->
        <div class="search-container">
            <div class="search-box">
                <input type="text" id="searchInput" placeholder="搜索地点或建筑..." autofocus autocomplete="off">
                <div class="search-controls">



                    <button id="searchButton" aria-label="搜索">
                        <svg class="search-icon" viewBox="0 0 24 24">
                            <path
                                d="M15.5 14h-.79l-.28-.27A6.47 6.47 0 0 0 16 9.5 6.5 6.5 0 1 0 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z" />
                        </svg>
                    </button>
                </div>
                <div id="searchSuggestions" class="suggestions-box">
                    <div class="loading-indicator"></div>
                </div>
            </div>
        </div>

        <!-- 用户面板 -->
        <div class="user-panel">
            <div class="user-info" id="userInfo">
                <img src="1.png" alt="用户头像" class="user-avatar">
                <span class="username">游客</span>
                <div class="dropdown-icon">▼</div>
            </div>
            <div class="dropdown-menu" id="dropdownMenu">
                <a href="#login" class="dropdown-item">登录/注册</a>
                <a href="#profile" class="dropdown-item">个人中心</a>
                <a href="#logout" class="dropdown-item">退出登录</a>
            </div>
        </div>
    </header>


    <section id="campus-info" class="info-section">
        <div class="section-header">
            <div class="section-tabs">
                <button class="tab-btn active" data-tab="overview">学校概况</button>
                <button class="tab-btn" data-tab="history">历史沿革</button>
                <button class="tab-btn" data-tab="features">特色优势</button>
            </div>
        </div>

        <!-- 各内容区块 -->
        <div class="tab-content active" id="overview">
            <img src="images/campus-aerial.jpg" alt="武汉理工大学全景航拍" class="info-image" loading="lazy">
            <div class="text-content">
                <div class="collapsible">
                    <p class="content-text">

                        武汉理工大学是教育部直属全国重点大学，首批“211工程”和“双一流”建设高校，由武汉工业大学等三校合并而成，办学历史可追溯到1898年。学校占地4000余亩，设25个学院等教学科研单位，涵盖工、理、经等多学科，材料学科优势突出，毕业生就业广泛，在行业内影响力大。

                    </p>
                    <p class="full-content">
                    <p>（完整详细内容）学校由原武汉工业大学、武汉交通科技大学、武汉汽车工业大学于2000年合并组建...</p>
                    <ul class="highlight-list">
                        <li>📌 国家级一流本科专业建设点42个</li>
                        <li>🏅 材料科学与工程学科在第四轮学科评估中获A+</li>
                        <li>🌐 与哈佛大学等200余所海外高校建立合作关系</li>
                    </ul>
                    <div class="full-content">
                        <h3>关键数据</h3>
                        <ul class="data-grid">
                            <li>
                                <span class="data-label">校区面积</span>
                                <span class="data-value">4000+ 亩</span>
                            </li>
                            <li>
                                <span class="data-label">在校生</span>
                                <span class="data-value">5.4万余人</span>
                            </li>
                            <li>
                                <span class="data-label">ESI全球前1‰学科</span>
                                <span class="data-value">3个</span>
                            </li>
                        </ul>

                        <div class="campus-map">
                            <img src="images/campus-map.svg" alt="校区分布示意图" class="responsive-map">
                            <p>三大校区：马房山主校区、余家头校区、南湖校区</p>
                        </div>
                    </div>

                </div>
                <button class="expand-btn">展开全部 ▼</button>
            </div>
        </div>

        <div class="tab-content" id="history">
            <div class="text-content">
                <div class="collapsible">
                    <p class="content-text">学校办学历史起源于1898年...</p>
                    <p class="full-content">完整历史沿革内容（约800字）...</p>
                    <p>（完整详细内容）学校由原武汉工业大学、武汉交通科技大学、武汉汽车工业大学于2000年合并组建...</p>
                    <ul class="highlight-list">
                        <li>📌 国家级一流本科专业建设点42个</li>
                        <li>🏅 材料科学与工程学科在第四轮学科评估中获A+</li>
                        <li>🌐 与哈佛大学等200余所海外高校建立合作关系</li>
                    </ul>
                </div>
                <button class="expand-btn">展开全部 ▼</button>
            </div>
        </div>
    
        <!-- 特色优势 -->
        <div class="tab-content" id="features">
            <div class="text-content">
                <div class="collapsible">
                    <p class="content-text">学校已形成以工学为主...</p>
                    <p class="full-content">完整特色优势内容（约600字）...</p>
                </div>
                <button class="expand-btn">展开全部 ▼</button>
            </div>
        </div>
    </section>

    <!-- 校园景点区 -->
    <section id="attractions" class="info-section">
        <h2 class="section-title">校园地标</h2>
        <div class="main-carousel">
            <div class="main-track">
                <!-- 动态生成五个地点卡片 -->
            </div>
            <button class="main-prev">❮</button>
            <button class="main-next">❯</button>
        </div>
    </section>

    <!-- 景点详情弹窗 -->
    <div id="attraction-modal" class="modal">
        <div class="modal-content">
            <span class="close-btn">&times;</span>
            <div id="modal-content"></div>
        </div>
    </div>

    <!-- 地图展示区 -->
    <main id="map-container">
        <!-- 筛选栏 -->
        <div class="filter-bar">
            <div class="filter-group">
                <div class="filter-title">地点类型</div>
                <div class="filter-options" id="typeFilters">
                    <button class="filter-btn active" data-type="all">全部</button>
                    <button class="filter-btn" data-type="teaching">教学楼</button>
                    <button class="filter-btn" data-type="dorm">宿舍</button>
                    <button class="filter-btn" data-type="dining">食堂</button>
                </div>
            </div>
            <div class="filter-group">
                <div class="filter-title">其他筛选</div>
                <div class="filter-options">
                    <select class="filter-select" id="timeFilter">
                        <option value="all">所有时间</option>
                        <option value="open">当前开放</option>
                        <option value="morning">上午开放</option>
                    </select>
                    <select class="filter-select" id="crowdFilter">
                        <option value="all">人流量</option>
                        <option value="low">空闲</option>
                        <option value="medium">适中</option>
                    </select>
                </div>
            </div>
        </div>
        <!-- 路线规划面板 -->
        <div id="routePanel" class="route-panel">
            <div class="route-header">
                <h3>路线规划</h3>
                <button id="closeRoutePanel" class="icon-btn">×</button>
            </div>
            <div class="route-controls">
                <div class="input-group">
                    <input type="text" id="startInput" placeholder="起点" list="locationList">
                    <input type="text" id="endInput" placeholder="终点" list="locationList">
                </div>
                <div class="mode-selectors">
                    <button class="mode-btn active" data-mode="walking">步行</button>
                    <button class="mode-btn" data-mode="cycling">骑行</button>
                    <button class="mode-btn" data-mode="driving">驾车</button>
                </div>
                <button id="startNavigation" class="primary-btn">
                    开始导航
                </button>
            </div>
            <div id="routeSummary" class="route-summary">
                <div class="summary-item">
                    <span>距离</span>
                    <strong id="distanceValue">-</strong>
                </div>
                <div class="summary-item">
                    <span>时间</span>
                    <strong id="durationValue">-</strong>
                </div>
            </div>
            <div id="routeSteps" class="route-steps"></div>
        </div>

        <datalist id="locationList">
            <!-- 自动完成建议 -->
        </datalist>
        <div id="campus-map"></div>
    </main>
    <footer class="main-footer">
        <div class="footer-content">
            <!-- 版权信息 -->
            <div class="footer-section">
                <h4>某某大学</h4>
                <p>地址：XX省XX市XX路123号</p>
                <p>电话：(012) 345-6789</p>
                <p>&copy; 2022-<span id="currentYear"></span> 版权所有</p>
            </div>

            <!-- 友情链接 -->
            <div class="footer-section">
                <h4>快速链接</h4>
                <ul class="footer-links">
                    <li><a href="https://www.xxxx.edu.cn" target="_blank">学校官网</a></li>
                    <li><a href="#map-container">校园导航</a></li>
                    <li><a href="https://library.xxxx.edu.cn" target="_blank">数字图书馆</a></li>
                    <li><a href="https://jw.xxxx.edu.cn" target="_blank">教务系统</a></li>
                </ul>
            </div>

            <!-- 反馈帮助 -->
            <div class="footer-section">
                <h4>支持与帮助</h4>
                <ul class="footer-links">
                    <li><a href="mailto:support@xxxx.edu.cn">意见反馈</a></li>
                    <li><a href="/help">帮助中心</a></li>
                    <li><a href="/privacy">隐私政策</a></li>
                    <li><a href="/sitemap">网站地图</a></li>
                </ul>
            </div>
        </div>
    </footer>
    <script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js"></script>
    <script src="https://unpkg.com/leaflet-routing-machine@3.2.12/dist/leaflet-routing-machine.js"></script>
    <script src="script.js"></script>
</body>

</html>
