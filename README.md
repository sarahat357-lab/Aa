<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>جمل لاكجري | Jammal Luxury</title>
    <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@700&family=Tajawal:wght@300;500;800&display=swap" rel="stylesheet">
    <style>
        /* تعريف الألوان الملكية */
        :root {
            --oud-dark: #4A0404; /* لون عودي غامق */
            --gold: #D4AF37;     /* لون ذهبي ملكي */
            --black: #111111;
            --white: #ffffff;
        }

        body {
            margin: 0;
            font-family: 'Tajawal', sans-serif;
            background-color: var(--white);
            color: var(--black);
        }

        /* شريط الماركات المتحرك */
        .brand-ticker {
            background: var(--black);
            color: var(--gold);
            padding: 10px 0;
            border-bottom: 2px solid var(--gold);
            overflow: hidden;
            white-space: nowrap;
        }

        .brand-ticker marquee {
            font-weight: 800;
            font-size: 1.2rem;
            letter-spacing: 2px;
        }

        /* الهيدر (الرأس) */
        header {
            background: var(--oud-dark);
            padding: 20px;
            text-align: center;
            border-bottom: 3px solid var(--gold);
        }

        .logo {
            font-family: 'Amiri', serif;
            font-size: 3rem;
            color: var(--gold);
            text-decoration: none;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        /* قسم الترحيب الفخم */
        .hero {
            height: 70vh;
            background: linear-gradient(rgba(0,0,0,0.6), rgba(74,4,4,0.6)), 
                        url('https://images.unsplash.com/photo-1550955295-58dcdb21695c?auto=format&fit=crop&w=1500&q=80');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--gold);
        }

        .hero-content h2 {
            font-size: 4rem;
            margin-bottom: 10px;
        }

        /* شبكة المنتجات (الخوادم) */
        .container {
            padding: 50px 5%;
        }

        .section-title {
            text-align: center;
            color: var(--oud-dark);
            font-size: 2.5rem;
            margin-bottom: 40px;
            position: relative;
        }

        .section-title::after {
            content: '';
            width: 100px;
            height: 3px;
            background: var(--gold);
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }

        .product-card {
            border: 1px solid #eee;
            padding: 15px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
            border-radius: 10px;
            position: relative;
            overflow: hidden;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            border-color: var(--gold);
        }

        .product-card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            border-radius: 8px;
        }

        .product-card h3 {
            color: var(--oud-dark);
            margin: 15px 0 5px;
        }

        .product-card .brand-name {
            color: #888;
            font-size: 0.9rem;
            text-transform: uppercase;
        }

        .product-card .price {
            color: var(--gold);
            font-weight: 800;
            font-size: 1.2rem;
            margin: 10px 0;
        }

        .btn-buy {
            background: var(--oud-dark);
            color: var(--gold);
            border: 1px solid var(--gold);
            padding: 10px 25px;
            cursor: pointer;
            width: 100%;
            border-radius: 5px;
            font-weight: bold;
        }

        .btn-buy:hover {
            background: var(--gold);
            color: var(--oud-dark);
        }
    </style>
</head>
<body>

    <div class="brand-ticker">
        <marquee scrollamount="8">
            ROLEX ★ ROLLS ROYCE ★ MERCEDES-BENZ ★ GUCCI ★ CHANEL ★ BENTLEY ★ PRADA ★ LOUIS VUITTON ★ LAMBORGHINI ★ HERMÈS
        </marquee>
    </div>

    <header>
        <a href="#" class="logo">جمل لاكجري</a>
    </header>

    <section class="hero">
        <div class="hero-content">
            <h2>مجموعة النخبة 2026</h2>
            <p>حيث تلتقي الأصالة بالفخامة العالمية</p>
        </div>
    </section>

    <div class="container">
        <h2 class="section-title">أحدث المقتنيات العالمية</h2>
        
        <div class="product-grid" id="productContainer">
            </div>
    </div>

    <script>
        // مصفوفة البراندات والصور لتوليد 100 منتج متنوع
        const brands = ["Rolex", "Gucci", "Mercedes", "Rolls Royce", "Chanel", "Prada", "Patek Philippe"];
        const categories = ["ساعة", "حقيبة", "إكسسوار", "سيارة", "أثاث"];
        
        const container = document.getElementById('productContainer');

        for (let i = 1; i <= 100; i++) {
            const randomBrand = brands[Math.floor(Math.random() * brands.length)];
            const randomCat = categories[Math.floor(Math.random() * categories.length)];
            
            container.innerHTML += `
                <div class="product-card">
                    <img src="https://picsum.photos/400/400?random=${i}" alt="منتج فخم">
                    <div class="brand-name">${randomBrand}</div>
                    <h3>${randomCat} إصدار ملكي خاص</h3>
                    <div class="price">${(Math.random() * 50000 + 5000).toLocaleString()} ر.س</div>
                    <button class="btn-buy">إضافة للمقتنيات</button>
                </div>
            `;
        }
    </script>

</body>
</html>
# Aa
