<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Fragrance Guy - Premium Perfumes & Colognes</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Helvetica Neue', Arial, sans-serif;
        }
        
        body {
            background-color: #f9f5f0;
            color: #333;
        }
        
        /* Header Styles */
        header {
            background-color: #fff;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .store-heading {
            text-align: center;
            padding: 20px 0;
        }
        
        .store-heading h1 {
            font-size: 2.5rem;
            color: #5d4037;
            letter-spacing: 2px;
            font-weight: 300;
        }
        
        /* Menu Styles */
        .menu-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 30px;
        }
        
        .menu-icon {
            font-size: 1.5rem;
            cursor: pointer;
            color: #5d4037;
        }
        
        .menu-content {
            display: none;
            position: absolute;
            background-color: #fff;
            min-width: 250px;
            box-shadow: 0 8px 16px rgba(0,0,0,0.1);
            z-index: 1;
            left: 30px;
            top: 100px;
        }
        
        .menu-content a {
            color: #5d4037;
            padding: 12px 16px;
            text-decoration: none;
            display: block;
            border-bottom: 1px solid #f1f1f1;
            transition: background-color 0.3s;
        }
        
        .menu-content a:hover {
            background-color: #f9f5f0;
        }
        
        .show-menu {
            display: block;
        }
        
        /* Navigation Bar */
        .nav-bar {
            display: flex;
            justify-content: center;
            border-top: 1px solid #e0e0e0;
            border-bottom: 1px solid #e0e0e0;
            padding: 15px 0;
            margin: 0 30px;
        }
        
        .nav-item {
            margin: 0 15px;
            cursor: pointer;
            color: #5d4037;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav-item:hover {
            color: #d4a373;
        }
        
        /* Account Section */
        .account-section {
            position: absolute;
            right: 30px;
            top: 100px;
            text-align: right;
        }
        
        .account-icon {
            font-size: 1.5rem;
            color: #5d4037;
            cursor: pointer;
        }
        
        .account-actions {
            display: flex;
            flex-direction: column;
            margin-top: 10px;
        }
        
        .account-action {
            display: flex;
            align-items: center;
            margin: 5px 0;
            color: #5d4037;
            cursor: pointer;
        }
        
        .account-action i {
            margin-right: 8px;
        }
        
        /* Main Content */
        .main-content {
            padding: 30px;
        }
        
        .featured-fragrance {
            text-align: center;
            margin-top: 30px;
        }
        
        .featured-title {
            font-size: 1.8rem;
            color: #5d4037;
            margin-bottom: 20px;
            font-weight: 300;
        }
        
        .featured-container {
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #fff;
            padding: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border-radius: 8px;
        }
        
        .featured-image {
            flex: 1;
            max-width: 400px;
        }
        
        .featured-image img {
            width: 100%;
            height: auto;
            border-radius: 4px;
        }
        
        .featured-details {
            flex: 1;
            padding: 0 30px;
            text-align: left;
        }
        
        .featured-name {
            font-size: 2rem;
            color: #5d4037;
            margin-bottom: 15px;
        }
        
        .featured-description {
            color: #666;
            line-height: 1.6;
            margin-bottom: 20px;
        }
        
        .featured-price {
            font-size: 1.5rem;
            color: #d4a373;
            margin-bottom: 25px;
        }
        
        .featured-buttons {
            display: flex;
            gap: 15px;
        }
        
        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
        }
        
        .btn-primary {
            background-color: #d4a373;
            color: white;
        }
        
        .btn-primary:hover {
            background-color: #c08a5d;
        }
        
        .btn-secondary {
            background-color: transparent;
            border: 1px solid #d4a373;
            color: #d4a373;
        }
        
        .btn-secondary:hover {
            background-color: #f9f5f0;
        }
        
        /* Products Grid */
        .products-grid {
            display: none;
            grid-template-columns: repeat(4, 1fr);
            gap: 25px;
            margin-top: 30px;
        }
        
        .product-card {
            background-color: #fff;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
            transition: transform 0.3s, box-shadow 0.3s;
            position: relative;
        }
        
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
        }
        
        .product-image {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }
        
        .product-info {
            padding: 15px;
        }
        
        .product-name {
            font-size: 1.1rem;
            color: #5d4037;
            margin-bottom: 8px;
        }
        
        .product-description {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 10px;
            line-height: 1.4;
        }
        
        .product-price {
            color: #d4a373;
            font-weight: 600;
            font-size: 1.1rem;
        }
        
        .product-hover-actions {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(255,255,255,0.9);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s;
        }
        
        .product-card:hover .product-hover-actions {
            opacity: 1;
        }
        
        .hover-btn {
            margin: 8px 0;
            padding: 8px 15px;
            width: 70%;
            text-align: center;
            background-color: #d4a373;
            color: white;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .hover-btn:hover {
            background-color: #c08a5d;
        }
        
        .wishlist-btn {
            background-color: transparent;
            border: 1px solid #d4a373;
            color: #d4a373;
        }
        
        .wishlist-btn:hover {
            background-color: #f9f5f0;
        }
        
        /* Pagination */
        .pagination {
            display: none;
            justify-content: center;
            margin-top: 30px;
            gap: 10px;
        }
        
        .page-btn {
            padding: 8px 15px;
            border: 1px solid #e0e0e0;
            background-color: white;
            color: #5d4037;
            cursor: pointer;
            border-radius: 4px;
            transition: all 0.3s;
        }
        
        .page-btn:hover {
            background-color: #f9f5f0;
            border-color: #d4a373;
        }
        
        .page-btn.active {
            background-color: #d4a373;
            color: white;
            border-color: #d4a373;
        }
        
        /* Footer */
        footer {
            background-color: #5d4037;
            color: white;
            padding: 30px;
            text-align: center;
            margin-top: 50px;
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .footer-link {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-link:hover {
            color: #d4a373;
        }
        
        .copyright {
            font-size: 0.9rem;
            color: rgba(255,255,255,0.7);
        }
    </style>
</head>
<body>
    <header>
        <div class="menu-container">
            <div class="menu-section">
                <div class="menu-icon" id="menuIcon">
                    <i class="fas fa-bars"></i> MENU
                </div>
                <div class="menu-content" id="menuContent">
                    <a href="#" data-category="top-sellers">Top Sellers</a>
                    <a href="#" data-category="womens-perfume">Women's Perfume</a>
                    <a href="#" data-category="mens-cologne">Men's Cologne</a>
                    <a href="#" data-category="brands">Brands</a>
                    <a href="#" data-category="winter-scents">Winter Scents</a>
                    <a href="#" data-category="summer-scents">Summer Scents</a>
                    <a href="#" data-category="fragrance-pairing">Fragrance Pairing</a>
                    <a href="#" data-category="gift-sets">Gift Sets</a>
                    <a href="#" data-category="body-sprays">Body Sprays</a>
                    <a href="#" data-category="scented-lotions">Scented Lotions</a>
                    <a href="#" data-category="contact-us">Contact Us</a>
                </div>
            </div>
            
            <div class="store-heading">
                <h1>THE FRAGRANCE GUY</h1>
            </div>
            
            <div class="account-section">
                <div class="account-icon">
                    <i class="fas fa-user"></i>
                </div>
                <div class="account-actions">
                    <div class="account-action">
                        <i class="fas fa-search"></i> Search
                    </div>
                    <div class="account-action">
                        <i class="fas fa-heart"></i> Wishlist
                    </div>
                    <div class="account-action">
                        <i class="fas fa-shopping-cart"></i> Cart
                    </div>
                </div>
            </div>
        </div>
        
        <div class="nav-bar">
            <div class="nav-item" data-category="top-sellers">Top Sellers</div>
            <div class="nav-item" data-category="womens-perfume">Women's Perfume</div>
            <div class="nav-item" data-category="mens-cologne">Men's Cologne</div>
            <div class="nav-item" data-category="brands">Brands</div>
            <div class="nav-item" data-category="winter-scents">Winter Scents</div>
            <div class="nav-item" data-category="summer-scents">Summer Scents</div>
            <div class="nav-item" data-category="fragrance-pairing">Fragrance Pairing</div>
            <div class="nav-item" data-category="gift-sets">Gift Sets</div>
            <div class="nav-item" data-category="body-sprays">Body Sprays</div>
            <div class="nav-item" data-category="scented-lotions">Scented Lotions</div>
        </div>
    </header>
    
    <main class="main-content">
        <div class="featured-fragrance" id="featuredFragrance">
            <h2 class="featured-title">Fragrance of the Month</h2>
            <div class="featured-container">
                <div class="featured-image">
                    <img src="https://via.placeholder.com/400x500" alt="Featured Fragrance">
                </div>
                <div class="featured-details">
                    <h3 class="featured-name">Noir Élégance</h3>
                    <p class="featured-description">
                        A captivating blend of dark spices, rich woods, and a hint of vanilla. 
                        Noir Élégance is our signature winter fragrance that evokes sophistication 
                        and mystery. Perfect for evening wear, this unisex scent develops 
                        beautifully over time, leaving a memorable trail.
                    </p>
                    <div class="featured-price">$89.99</div>
                    <div class="featured-buttons">
                        <button class="btn btn-primary">Add to Cart</button>
                        <button class="btn btn-secondary">Add to Wishlist</button>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="products-grid" id="productsGrid"></div>
        
        <div class="pagination" id="pagination">
            <button class="page-btn">Previous</button>
            <button class="page-btn active">1</button>
            <button class="page-btn">2</button>
            <button class="page-btn">3</button>
            <button class="page-btn">Next</button>
        </div>
    </main>
    
    <footer>
        <div class="footer-links">
            <a href="#" class="footer-link">About Us</a>
            <a href="#" class="footer-link">Shipping Policy</a>
            <a href="#" class="footer-link">Return Policy</a>
            <a href="#" class="footer-link">Privacy Policy</a>
            <a href="#" class="footer-link">Terms of Service</a>
            <a href="#" class="footer-link" data-category="contact-us">Contact Us</a>
        </div>
        <div class="copyright">
            &copy; 2023 The Fragrance Guy. All rights reserved.
        </div>
    </footer>
    
    <script>
        // Sample product data
        const products = {
            "top-sellers": [
                {
                    id: 1,
                    name: "Midnight Oud",
                    description: "A luxurious blend of oud wood, amber, and spices with a hint of citrus.",
                    price: "$95.00",
                    image: "https://via.placeholder.com/300x400?text=Midnight+Oud"
                },
                {
                    id: 2,
                    name: "Floral Bloom",
                    description: "Fresh floral bouquet with notes of jasmine, rose, and peony.",
                    price: "$78.00",
                    image: "https://via.placeholder.com/300x400?text=Floral+Bloom"
                },
                {
                    id: 3,
                    name: "Ocean Breeze",
                    description: "Crisp aquatic fragrance with marine notes and a touch of citrus.",
                    price: "$65.00",
                    image: "https://via.placeholder.com/300x400?text=Ocean+Breeze"
                },
                {
                    id: 4,
                    name: "Vanilla Dream",
                    description: "Warm and sweet vanilla with hints of caramel and tonka bean.",
                    price: "$72.00",
                    image: "https://via.placeholder.com/300x400?text=Vanilla+Dream"
                },
                {
                    id: 5,
                    name: "Tobacco Leaf",
                    description: "Rich tobacco blended with vanilla, honey, and woody notes.",
                    price: "$88.00",
                    image: "https://via.placeholder.com/300x400?text=Tobacco+Leaf"
                },
                {
                    id: 6,
                    name: "Citrus Splash",
                    description: "Zesty citrus fragrance with bergamot, lemon, and orange blossom.",
                    price: "$60.00",
                    image: "https://via.placeholder.com/300x400?text=Citrus+Splash"
                },
                {
                    id: 7,
                    name: "Musk Noir",
                    description: "Sensual musk with dark amber and a hint of patchouli.",
                    price: "$82.00",
                    image: "https://via.placeholder.com/300x400?text=Musk+Noir"
                },
                {
                    id: 8,
                    name: "Gardenia Petals",
                    description: "Creamy gardenia with white flowers and a touch of green leaves.",
                    price: "$75.00",
                    image: "https://via.placeholder.com/300x400?text=Gardenia+Petals"
                }
            ],
            "womens-perfume": [
                {
                    id: 9,
                    name: "Rose Elixir",
                    description: "Luxurious rose fragrance with peony and a hint of musk.",
                    price: "$85.00",
                    image: "https://via.placeholder.com/300x400?text=Rose+Elixir"
                },
                {
                    id: 10,
                    name: "Jasmine Nights",
                    description: "Intoxicating jasmine with orange blossom and vanilla.",
                    price: "$79.00",
                    image: "https://via.placeholder.com/300x400?text=Jasmine+Nights"
                }
            ],
            "mens-cologne": [
                {
                    id: 11,
                    name: "Leather & Spice",
                    description: "Bold leather accord with black pepper and vetiver.",
                    price: "$92.00",
                    image: "https://via.placeholder.com/300x400?text=Leather+%26+Spice"
                },
                {
                    id: 12,
                    name: "Blue Cedar",
                    description: "Fresh cedarwood with marine notes and bergamot.",
                    price: "$75.00",
                    image: "https://via.placeholder.com/300x400?text=Blue+Cedar"
                }
            ]
            // Other categories would follow the same pattern
        };
        
        // DOM Elements
        const menuIcon = document.getElementById('menuIcon');
        const menuContent = document.getElementById('menuContent');
        const featuredFragrance = document.getElementById('featuredFragrance');
        const productsGrid = document.getElementById('productsGrid');
        const pagination = document.getElementById('pagination');
        const navItems = document.querySelectorAll('.nav-item');
        const menuLinks = document.querySelectorAll('.menu-content a');
        
        // Toggle menu
        menuIcon.addEventListener('click', () => {
            menuContent.classList.toggle('show-menu');
        });
        
        // Close menu when clicking outside
        document.addEventListener('click', (e) => {
            if (!menuIcon.contains(e.target) && !menuContent.contains(e.target)) {
                menuContent.classList.remove('show-menu');
            }
        });
        
        // Function to display products
        function displayProducts(category) {
            const categoryProducts = products[category] || [];
            
            // Hide featured fragrance and show products grid
            featuredFragrance.style.display = 'none';
            productsGrid.style.display = 'grid';
            pagination.style.display = 'flex';
            
            // Clear existing products
            productsGrid.innerHTML = '';
            
            // Add products to grid
            categoryProducts.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    <img src="${product.image}" alt="${product.name}" class="product-image">
                    <div class="product-info">
                        <h3 class="product-name">${product.name}</h3>
                        <p class="product-description">${product.description}</p>
                        <div class="product-price">${product.price}</div>
                    </div>
                    <div class="product-hover-actions">
                        <div class="hover-btn">Add to Cart</div>
                        <div class="hover-btn wishlist-btn">Add to Wishlist</div>
                    </div>
                `;
                productsGrid.appendChild(productCard);
            });
        }
        
        // Function to show featured fragrance
        function showFeaturedFragrance() {
            featuredFragrance.style.display = 'block';
            productsGrid.style.display = 'none';
            pagination.style.display = 'none';
        }
        
        // Add event listeners to navigation items
        navItems.forEach(item => {
            item.addEventListener('click', () => {
                const category = item.getAttribute('data-category');
                if (category === 'contact-us') {
                    // Handle contact us page
                    alert('Contact Us page would open here');
                } else {
                    displayProducts(category);
                }
            });
        });
        
        // Add event listeners to menu links
        menuLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const category = link.getAttribute('data-category');
                if (category === 'contact-us') {
                    // Handle contact us page
                    alert('Contact Us page would open here');
                } else {
                    displayProducts(category);
                }
                menuContent.classList.remove('show-menu');
            });
        });
        
        // Initialize with featured fragrance
        showFeaturedFragrance();
    </script>
</body>
</html>
