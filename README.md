<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Best Ad Offers For This Season</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #0b0f19;
            color: #ffffff;
            overflow-x: hidden;
            height: 100vh;
        }

        /* Left Floating Speed Scroll Buttons (2x Speed) */
        .floating-speed-controls {
            position: fixed;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            gap: 15px;
            z-index: 1000;
        }

        .speed-btn {
            background: linear-gradient(135deg, #3b82f6, #1d4ed8);
            color: white;
            border: none;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(59, 130, 246, 0.4);
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .speed-btn:hover {
            transform: scale(1.1);
            background: linear-gradient(135deg, #60a5fa, #2563eb);
            box-shadow: 0 6px 20px rgba(59, 130, 246, 0.6);
        }

        /* Header Layout */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px 20px 90px; /* Offset for left buttons */
            background: rgba(17, 24, 39, 0.95);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            position: sticky;
            top: 0;
            z-index: 900;
            backdrop-filter: blur(10px);
        }

        .header-title-area {
            display: flex;
            align-items: center;
            gap: 30px;
        }

        h1 {
            font-size: 24px;
            font-weight: 700;
            background: linear-gradient(90deg, #60a5fa, #34d399);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: 0.5px;
        }

        /* Pagination Controls (Right & Left Arrows) */
        .pagination-bar {
            display: flex;
            align-items: center;
            gap: 15px;
            background: rgba(31, 41, 55, 0.8);
            padding: 8px 16px;
            border-radius: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .page-arrow {
            background: #2563eb;
            color: white;
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background 0.2s, transform 0.2s;
        }

        .page-arrow:hover {
            background: #1d4ed8;
            transform: scale(1.05);
        }

        .page-indicator {
            font-size: 15px;
            font-weight: 600;
            color: #9ca3af;
            min-width: 110px;
            text-align: center;
        }

        .page-indicator span {
            color: #34d399;
        }

        /* Horizontal Long Content Track */
        .main-container {
            padding: 40px;
            margin-left: 70px; /* Space for floating controls */
        }

        .offers-horizontal-track {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
            max-width: 1400px;
            margin: 0 auto;
        }

        /* Professional Ad Offer Card Design */
        .ad-card {
            background: linear-gradient(145deg, #1e293b, #0f172a);
            border: 1px solid rgba(255, 255, 255, 0.08);
            border-radius: 16px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease, border-color 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .ad-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background: #3b82f6;
        }

        .ad-card:hover {
            transform: translateY(-5px);
            border-color: #3b82f6;
        }

        .badge {
            display: inline-block;
            background: rgba(59, 130, 246, 0.15);
            color: #60a5fa;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
            margin-bottom: 15px;
            text-transform: uppercase;
        }

        .ad-title {
            font-size: 20px;
            font-weight: 700;
            margin-bottom: 12px;
            color: #f3f4f6;
        }

        .ad-description {
            font-size: 14px;
            color: #9ca3af;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .ad-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            padding-top: 15px;
        }

        .price-tag {
            font-size: 18px;
            font-weight: 700;
            color: #34d399;
        }

        .claim-btn {
            background: #2563eb;
            color: white;
            border: none;
            padding: 8px 18px;
            border-radius: 8px;
            font-size: 13px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.2s;
        }

        .claim-btn:hover {
            background: #1d4ed8;
        }

        /* Responsive adjustments */
        @media (max-width: 1024px) {
            .offers-horizontal-track {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            header {
                flex-direction: column;
                gap: 15px;
                padding: 15px;
            }
            .header-title-area {
                flex-direction: column;
                gap: 10px;
            }
            .main-container {
                margin-left: 0;
                padding: 20px;
            }
            .floating-speed-controls {
                left: 10px;
            }
            .offers-horizontal-track {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <!-- Left Floating 2x Scroll Speed Controls -->
    <div class="floating-speed-controls">
        <button class="speed-btn" id="scrollUpBtn" title="Scroll Up 2x Speed">⬆</button>
        <button class="speed-btn" id="scrollDownBtn" title="Scroll Down 2x Speed">⬇</button>
    </div>

    <!-- Header containing Title and Pagination Arrows -->
    <header>
        <div class="header-title-area">
            <h1>Best Ad Offers For This Season</h1>
            <div class="pagination-bar">
                <!-- Left Arrow (Previous Page) -->
                <button class="page-arrow" id="prevPageBtn">◀</button>
                <div class="page-indicator">Page <span id="currentPageNum">0</span> / 1000</div>
                <!-- Right Arrow (Next Page / Loop to 0 at 1000) -->
                <button class="page-arrow" id="nextPageBtn">▶</button>
            </div>
        </div>
    </header>

    <!-- Main Content Area representing 1000 Pages of Offers -->
    <main class="main-container">
        <div class="offers-horizontal-track" id="offersGrid">
            <!-- Dynamic Professional Offers Injected Here -->
        </div>
    </main>

    <script>
        // Professional High-End Ad Campaign Templates (No Test/Dummy Data)
        const campaignTemplates = [
            { category: "Global Social Takeover", title: "Meta Advantage+ Enterprise Scaling Suite", desc: "Automated multi-placement ad distribution optimized for high-conversion Tier 1 global e-commerce markets.", price: "$4,999 /mo" },
            { category: "Short-Form Video Surge", title: "TikTok Spark Ads Global Creator Accelerator", desc: "Leverage top-performing creator content amplified directly into high-intent FYP feeds with algorithmic priority.", price: "$3,499 /mo" },
            { category: "Search Dominance", title: "Google Performance Max Omnichannel Growth", desc: "AI-driven inventory bidding across Search, YouTube, Gmail, and Discover to capture ready-to-buy traffic.", price: "$5,800 /mo" },
            { category: "B2B Lead Generation", title: "LinkedIn Account-Based Marketing Surge", desc: "Precision enterprise targeting focusing on C-level decision-makers and key stakeholders in tech & finance.", price: "$6,200 /mo" },
            { category: "Connected TV & OTT", title: "Programmatic Cinematic Streaming Package", desc: "High-impact non-skippable video spots delivered across premium connected television streaming networks.", price: "$8,500 /mo" },
            { category: "Programmatic Retargeting", title: "Cross-Device Visitor Recovery Engine", desc: "Advanced pixel tracking and dynamic product remarketing across high-traffic publisher networks worldwide.", price: "$2,750 /mo" }
        ];

        let currentPage = 0;
        const maxPages = 1000;

        const currentPageNumEl = document.getElementById('currentPageNum');
        const offersGridEl = document.getElementById('offersGrid');
        const nextPageBtn = document.getElementById('nextPageBtn');
        const prevPageBtn = document.getElementById('prevPageBtn');
        const scrollUpBtn = document.getElementById('scrollUpBtn');
        const scrollDownBtn = document.getElementById('scrollDownBtn');

        // Function to render offers for the current page index (0 to 1000)
        function renderPage(pageIndex) {
            currentPageNumEl.textContent = pageIndex;
            offersGridEl.innerHTML = '';

            // Generate 3 unique professional offers per page dynamically based on page index
            for (let i = 1; i <= 3; i++) {
                const templateIndex = (pageIndex + i) % campaignTemplates.length;
                const baseOffer = campaignTemplates[templateIndex];
                
                const card = document.createElement('div');
                card.className = 'ad-card';
                card.innerHTML = `
                    <div class="badge">${baseOffer.category} - Batch #${pageIndex * 3 + i}</div>
                    <div class="ad-title">${baseOffer.title}</div>
                    <div class="ad-description">${baseOffer.desc} Optimized for maximum ROI, high viewability standards, and robust conversion tracking for the current season.</div>
                    <div class="ad-footer">
                        <span class="price-tag">${baseOffer.price}</span>
                        <button class="claim-btn" onclick="alert('Campaign #${pageIndex * 3 + i} Selected Successfully!')">Claim Offer</button>
                    </div>
                `;
                offersGridEl.appendChild(card);
            }
        }

        // Right Arrow Click: Increment page, loop back to 0 when exceeding 1000
        nextPageBtn.addEventListener('click', () => {
            if (currentPage >= maxPages) {
                currentPage = 0;
            } else {
                currentPage++;
            }
            renderPage(currentPage);
            window.scrollTo({ top: 0, behavior: 'smooth' });
        });

        // Left Arrow Click: Decrement page, loop to 1000 if below 0
        prevPageBtn.addEventListener('click', () => {
            if (currentPage <= 0) {
                currentPage = maxPages;
            } else {
                currentPage--;
            }
            renderPage(currentPage);
            window.scrollTo({ top: 0, behavior: 'smooth' });
        });

        // 2x Speed Scroll Up Button
        scrollUpBtn.addEventListener('click', () => {
            window.scrollBy({
                top: -window.innerHeight * 2,
                behavior: 'smooth'
            });
        });

        // 2x Speed Scroll Down Button
        scrollDownBtn.addEventListener('click', () => {
            window.scrollBy({
                top: window.innerHeight * 2,
                behavior: 'smooth'
            });
        });

        // Initialize first page on load
        renderPage(currentPage);
    </script>
</body>
</html>
