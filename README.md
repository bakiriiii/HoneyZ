# HoneyZ
Create website where i can sell honey
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Honey Haven - Premium Honey Products</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CSS will be placed here for simplicity */
        :root {
            --golden: #FFD700;
            --honey: #F4A460;
            --dark-honey: #D2691E;
            --light-honey: #FFE4B5;
            --black: #1A1A1A;
            --white: #FFF8DC;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--white);
            color: var(--black);
            background-image: url('data:image/svg+xml;utf8,<svg width="100" height="100" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><path d="M50 0 L100 25 L100 75 L50 100 L0 75 L0 25 Z" fill="none" stroke="%23FFD700" stroke-width="0.5" opacity="0.2"/></svg>');
        }

        header {
            background-color: var(--black);
            color: var(--golden);
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .logo i {
            font-size: 2rem;
            color: var(--golden);
        }

        .logo h1 {
            font-size: 1.8rem;
            background: linear-gradient(to right, var(--golden), var(--honey));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: var(--golden);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            padding: 0.5rem 1rem;
            border-radius: 5px;
        }

        nav a:hover {
            background-color: var(--golden);
            color: var(--black);
        }

        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1587049352851-8d4e89133924?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            height: 60vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: var(--white);
            padding: 0 2rem;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--golden);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin-bottom: 2rem;
        }

        .btn {
            background-color: var(--golden);
            color: var(--black);
            padding: 0.8rem 2rem;
            border: none;
            border-radius: 50px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .btn:hover {
            background-color: var(--honey);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .products-section {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--dark-honey);
            display: inline-block;
            background-color: var(--white);
            padding: 0 2rem;
            position: relative;
            z-index: 1;
        }

        .section-title::after {
            content: "";
            position: absolute;
            top: 50%;
            left: 0;
            right: 0;
            height: 2px;
            background-color: var(--golden);
            z-index: 0;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s;
            border: 1px solid var(--light-honey);
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        .product-image {
            height: 200px;
            background-color: var(--light-honey);
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .product-image img {
            max-width: 80%;
            max-height: 80%;
            object-fit: contain;
            transition: transform 0.3s;
        }

        .product-card:hover .product-image img {
            transform: scale(1.1);
        }

        .product-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--golden);
            color: var(--black);
            padding: 0.3rem 0.8rem;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-info h3 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: var(--dark-honey);
        }

        .product-info p {
            color: #666;
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }

        .product-price {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 1rem;
        }

        .price {
            font-size: 1.3rem;
            font-weight: bold;
            color: var(--dark-honey);
        }

        .add-to-cart {
            background-color: var(--golden);
            color: var(--black);
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .add-to-cart:hover {
            background-color: var(--honey);
        }

        .add-product-form {
            background-color: white;
            max-width: 600px;
            margin: 4rem auto;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            border: 1px solid var(--light-honey);
        }

        .add-product-form h2 {
            text-align: center;
            margin-bottom: 2rem;
            color: var(--dark-honey);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--dark-honey);
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid var(--light-honey);
            border-radius: 5px;
            font-size: 1rem;
        }

        .form-group textarea {
            min-height: 100px;
            resize: vertical;
        }

        .form-actions {
            display: flex;
            justify-content: center;
            margin-top: 2rem;
        }

        footer {
            background-color: var(--black);
            color: var(--golden);
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: left;
        }

        .footer-column h3 {
            margin-bottom: 1rem;
            color: var(--golden);
            font-size: 1.2rem;
        }

        .footer-column p, .footer-column a {
            color: var(--light-honey);
            margin-bottom: 0.5rem;
            display: block;
            text-decoration: none;
        }

        .footer-column a:hover {
            color: var(--golden);
        }

        .social-icons {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-icons a {
            color: var(--golden);
            font-size: 1.5rem;
        }

        .copyright {
            margin-top: 2rem;
            padding-top: 1rem;
            border-top: 1px solid var(--dark-honey);
        }

        /* Modal styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            max-width: 500px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
        }

        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-honey);
        }

        /* Responsive styles */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                padding: 1rem;
            }

            nav ul {
                margin-top: 1rem;
                gap: 1rem;
            }

            .hero h2 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .products-grid {
                grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            }
        }

        @media (max-width: 480px) {
            nav ul {
                flex-direction: column;
                align-items: center;
                gap: 0.5rem;
            }

            .hero {
                height: 50vh;
            }

            .hero h2 {
                font-size: 1.8rem;
            }

            .products-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="logo">
            <i class="fas fa-honey-pot"></i>
            <h1>Honey Haven</h1>
        </div>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#add-product">Add Product</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <h2>Nature's Golden Elixir</h2>
        <p>Discover our premium selection of raw, organic honey products straight from the hive to your table.</p>
        <a href="#products" class="btn">Explore Our Hive</a>
    </section>

    <!-- Products Section -->
    <section class="products-section" id="products">
        <div class="section-title">
            <h2>Our Honey Collection</h2>
        </div>
        <div class="products-grid" id="products-container">
            <!-- Products will be dynamically added here -->
        </div>
    </section>

    <!-- Add Product Form -->
    <section class="add-product-form" id="add-product">
        <h2>Add New Honey Product</h2>
        <form id="product-form">
            <div class="form-group">
                <label for="product-name">Product Name</label>
                <input type="text" id="product-name" required>
            </div>
            <div class="form-group">
                <label for="product-description">Description</label>
                <textarea id="product-description" required></textarea>
            </div>
            <div class="form-group">
                <label for="product-price">Price ($)</label>
                <input type="number" id="product-price" step="0.01" required>
            </div>
            <div class="form-group">
                <label for="product-image">Image URL</label>
                <input type="url" id="product-image" required>
            </div>
            <div class="form-group">
                <label for="product-category">Category</label>
                <select id="product-category" required>
                    <option value="">Select a category</option>
                    <option value="raw-honey">Raw Honey</option>
                    <option value="infused-honey">Infused Honey</option>
                    <option value="honey-comb">Honey Comb</option>
                    <option value="honey-products">Honey Products</option>
                </select>
            </div>
            <div class="form-actions">
                <button type="submit" class="btn">Add Product</button>
            </div>
        </form>
    </section>

    <!-- About Section -->
    <section class="products-section" id="about">
        <div class="section-title">
            <h2>Our Story</h2>
        </div>
        <div style="text-align: center; max-width: 800px; margin: 0 auto;">
            <p style="font-size: 1.1rem; line-height: 1.6; margin-bottom: 2rem;">
                Honey Haven was founded in 2010 with a simple mission: to bring the purest, most delicious honey from sustainable beekeepers to honey lovers everywhere. 
                We work directly with small-scale beekeepers who practice ethical beekeeping, ensuring the health of the bees and the quality of the honey.
            </p>
            <p style="font-size: 1.1rem; line-height: 1.6;">
                Our honey is never heated or processed, preserving all the natural enzymes, antioxidants, and flavors that make raw honey so special. 
                From our hive to your home, we're committed to delivering nature's golden elixir in its most authentic form.
            </p>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="products-section" id="contact">
        <div class="section-title">
            <h2>Contact Us</h2>
        </div>
        <div style="text-align: center; max-width: 800px; margin: 0 auto;">
            <p style="font-size: 1.1rem; line-height: 1.6; margin-bottom: 2rem;">
                Have questions about our products or beekeeping practices? We'd love to hear from you!
            </p>
            <div style="display: flex; justify-content: center; gap: 2rem; flex-wrap: wrap;">
                <div style="text-align: left;">
                    <h3 style="color: var(--dark-honey); margin-bottom: 1rem;"><i class="fas fa-map-marker-alt"></i> Visit Us</h3>
                    <p>123 Honeycomb Lane</p>
                    <p>Beetown, CA 90210</p>
                </div>
                <div style="text-align: left;">
                    <h3 style="color: var(--dark-honey); margin-bottom: 1rem;"><i class="fas fa-phone"></i> Call Us</h3>
                    <p>(555) 123-4567</p>
                    <p>Mon-Fri: 9am-5pm</p>
                </div>
                <div style="text-align: left;">
                    <h3 style="color: var(--dark-honey); margin-bottom: 1rem;"><i class="fas fa-envelope"></i> Email Us</h3>
                    <p>info@honeyhaven.com</p>
                    <p>orders@honeyhaven.com</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-column">
                <h3>Honey Haven</h3>
                <p>Providing premium honey products since 2010. Pure, raw, and delicious honey straight from sustainable beekeepers.</p>
                <div class="social-icons">
                    <a href="#"><i class="fab fa-facebook"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-pinterest"></i></a>
                </div>
            </div>
            <div class="footer-column">
                <h3>Quick Links</h3>
                <a href="#home">Home</a>
                <a href="#products">Products</a>
                <a href="#add-product">Add Product</a>
                <a href="#about">About Us</a>
                <a href="#contact">Contact</a>
            </div>
            <div class="footer-column">
                <h3>Customer Service</h3>
                <a href="#">Shipping Policy</a>
                <a href="#">Returns & Refunds</a>
                <a href="#">FAQ</a>
                <a href="#">Privacy Policy</a>
                <a href="#">Terms of Service</a>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2023 Honey Haven. All rights reserved.</p>
        </div>
    </footer>

    <!-- Product Detail Modal -->
    <div class="modal" id="product-modal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <div id="modal-content">
                <!-- Modal content will be dynamically added here -->
            </div>
        </div>
    </div>

    <script>
        // JavaScript for the product management
        document.addEventListener('DOMContentLoaded', function() {
            // Sample initial products
            const initialProducts = [
                {
                    id: 1,
                    name: "Wildflower Raw Honey",
                    description: "Pure, unfiltered wildflower honey with a rich, complex flavor profile. Collected from diverse floral sources.",
                    price: 12.99,
                    image: "https://images.unsplash.com/photo-1587049288093-2cbe98f0a91b?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                    category: "raw-honey"
                },
                {
                    id: 2,
                    name: "Manuka Honey",
                    description: "Premium New Zealand Manuka honey with UMF 15+ rating. Known for its unique antibacterial properties.",
                    price: 29.99,
                    image: "https://images.unsplash.com/photo-1558645836-e44122a743ee?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                    category: "raw-honey"
                },
                {
                    id: 3,
                    name: "Lavender Infused Honey",
                    description: "Delicate raw honey infused with organic lavender flowers. Perfect for tea and desserts.",
                    price: 14.99,
                    image: "https://images.unsplash.com/photo-1587049352851-8d4e89133924?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                    category: "infused-honey"
                },
                {
                    id: 4,
                    name: "Honey Comb",
                    description: "Pure honeycomb sections with raw honey still in the wax. A true delicacy straight from the hive.",
                    price: 19.99,
                    image: "https://images.unsplash.com/photo-1587049352851-8d4e89133924?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80",
                    category: "honey-comb"
                }
            ];

            // Get DOM elements
            const productsContainer = document.getElementById('products-container');
            const productForm = document.getElementById('product-form');
            const productModal = document.getElementById('product-modal');
            const modalContent = document.getElementById('modal-content');
            const closeModal = document.querySelector('.close-modal');

            // Load products from localStorage or use initial products
            let products = JSON.parse(localStorage.getItem('honeyProducts')) || initialProducts;

            // Display all products
            function displayProducts() {
                productsContainer.innerHTML = '';
                products.forEach(product => {
                    const productCard = document.createElement('div');
                    productCard.className = 'product-card';
                    productCard.innerHTML = `
                        <div class="product-image">
                            <img src="${product.image}" alt="${product.name}">
                            <span class="product-badge">${getCategoryName(product.category)}</span>
                        </div>
                        <div class="product-info">
                            <h3>${product.name}</h3>
                            <p>${product.description}</p>
                            <div class="product-price">
                                <span class="price">$${product.price.toFixed(2)}</span>
                                <button class="add-to-cart" data-id="${product.id}">Add to Cart</button>
                            </div>
                        </div>
                    `;
                    productsContainer.appendChild(productCard);
                });

                // Add event listeners to "Add to Cart" buttons
                document.querySelectorAll('.add-to-cart').forEach(button => {
                    button.addEventListener('click', function() {
                        const productId = parseInt(this.getAttribute('data-id'));
                        const product = products.find(p => p.id === productId);
                        showProductModal(product);
                    });
                });
            }

            // Show product details in modal
            function showProductModal(product) {
                modalContent.innerHTML = `
                    <div style="display: flex; flex-direction: column; gap: 1.5rem;">
                        <div style="display: flex; gap: 2rem; flex-wrap: wrap;">
                            <div style="flex: 1; min-width: 200px;">
                                <div class="product-image" style="height: 300px;">
                                    <img src="${product.image}" alt="${product.name}" style="max-width: 100%; max-height: 100%;">
                                </div>
                            </div>
                            <div style="flex: 1; min-width: 200px;">
                                <h2 style="color: var(--dark-honey); margin-bottom: 1rem;">${product.name}</h2>
                                <p style="margin-bottom: 1rem;"><strong>Category:</strong> ${getCategoryName(product.category)}</p>
                                <p style="font-size: 1.5rem; color: var(--dark-honey); margin-bottom: 1.5rem;">$${product.price.toFixed(2)}</p>
                                <p style="margin-bottom: 1.5rem;">${product.description}</p>
                                <div style="display: flex; gap: 1rem;">
                                    <input type="number" value="1" min="1" style="width: 60px; padding: 0.5rem; border: 1px solid var(--light-honey); border-radius: 5px;">
                                    <button class="btn" style="flex: 1;">Add to Cart</button>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
                productModal.style.display = 'flex';
            }

            // Get category name for display
            function getCategoryName(category) {
                const categories = {
                    'raw-honey': 'Raw Honey',
                    'infused-honey': 'Infused',
                    'honey-comb': 'Honey Comb',
                    'honey-products': 'Honey Product'
                };
                return categories[category] || 'Honey';
            }

            // Handle form submission
            productForm.addEventListener('submit', function(e) {
                e.preventDefault();
                
                const newProduct = {
                    id: products.length > 0 ? Math.max(...products.map(p => p.id)) + 1 : 1,
                    name: document.getElementById('product-name').value,
                    description: document.getElementById('product-description').value,
                    price: parseFloat(document.getElementById('product-price').value),
                    image: document.getElementById('product-image').value,
                    category: document.getElementById('product-category').value
                };

                products.push(newProduct);
                localStorage.setItem('honeyProducts', JSON.stringify(products));
                displayProducts();
                productForm.reset();
                
                // Scroll to products section
                document.getElementById('products').scrollIntoView({ behavior: 'smooth' });
            });

            // Close modal
            closeModal.addEventListener('click', function() {
                productModal.style.display = 'none';
            });

            // Close modal when clicking outside
            window.addEventListener('click', function(e) {
                if (e.target === productModal) {
                    productModal.style.display = 'none';
                }
            });

            // Smooth scrolling for navigation links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });

            // Initialize the page
            displayProducts();
        });
    </script>
</body>
</html>
