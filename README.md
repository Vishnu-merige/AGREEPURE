<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AgriPure Link - Organic Farming Management</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        /* General body and font styles */
        body {
            background-color: #f9fafb; /* bg-gray-50 */
            font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji"; /* font-sans */
        }
        
        /* Navigation and Header Styles */
        .gradient-bg {
            background: linear-gradient(135deg, #22c55e 0%, #16a34a 100%);
            color: #ffffff; /* text-white */
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05); /* shadow-lg */
            position: sticky;
            top: 0;
            z-index: 50;
        }

        .container-nav {
            max-width: 80rem; /* max-w-7xl */
            margin-left: auto;
            margin-right: auto;
            padding-left: 1rem; /* px-4 */
            padding-right: 1rem;
        }
        @media (min-width: 640px) {
            .container-nav {
                padding-left: 1.5rem; /* sm:px-6 */
                padding-right: 1.5rem;
            }
        }
        @media (min-width: 1024px) {
            .container-nav {
                padding-left: 2rem; /* lg:px-8 */
                padding-right: 2rem;
            }
        }
        
        .flex-items-center {
            display: flex;
            align-items: center;
        }

        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 4rem; /* h-16 */
        }

        .space-x-3 > * + * { margin-left: 0.75rem; }
        .space-x-6 > * + * { margin-left: 1.5rem; }

        .title {
            font-size: 1.25rem; /* text-xl */
            line-height: 1.75rem;
            font-weight: 700; /* font-bold */
        }
        
        .nav-item {
            padding: 0.5rem 0.75rem; /* px-3 py-2 */
            border-radius: 0.375rem; /* rounded-md */
            font-size: 0.875rem; /* text-sm */
            line-height: 1.25rem;
            font-weight: 500; /* font-medium */
            transition: all 0.2s ease;
        }

        .nav-item:hover {
            background-color: rgba(255, 255, 255, 0.1);
        }

        .mobile-menu-btn {
            display: block;
        }
        @media (min-width: 768px) {
            .mobile-menu-btn {
                display: none;
            }
        }

        .desktop-nav {
            display: none;
        }
        @media (min-width: 768px) {
            .desktop-nav {
                display: flex;
            }
        }

        .mobile-menu {
            position: fixed;
            inset: 0 auto 0 0;
            width: 16rem; /* w-64 */
            background-color: #15803d; /* bg-green-700 */
            z-index: 50;
            transform: translateX(-100%);
            transition: transform 0.3s ease;
        }

        .mobile-menu.open {
            transform: translateX(0);
        }

        .mobile-menu .p-4 { padding: 1rem; }
        .mobile-menu .mb-6 { margin-bottom: 1.5rem; }
        .mobile-menu .space-y-2 > * + * { margin-top: 0.5rem; }
        .mobile-menu .w-full { width: 100%; }
        .mobile-menu .text-left { text-align: left; }

        /* Main Content and Section Styles */
        .main-content {
            max-width: 80rem; /* max-w-7xl */
            margin-left: auto;
            margin-right: auto;
            padding: 1.5rem 1rem; /* px-4 sm:px-6 lg:px-8 py-6 */
        }
        @media (min-width: 640px) { .main-content { padding-left: 1.5rem; padding-right: 1.5rem; } }
        @media (min-width: 1024px) { .main-content { padding-left: 2rem; padding-right: 2rem; } }

        .section {
            animation: fadeIn 0.5s ease-in;
        }

        .section.hidden {
            display: none;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Card and Panel Styles */
        .card {
            background-color: #ffffff; /* bg-white */
            border-radius: 0.5rem; /* rounded-lg */
            padding: 1.5rem; /* p-6 */
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06); /* shadow-md */
        }
        .card-hover {
            transition: all 0.3s ease;
        }
        .card-hover:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .grid {
            display: grid;
        }
        .grid-cols-1 { grid-template-columns: repeat(1, minmax(0, 1fr)); }
        @media (min-width: 768px) { .md\:grid-cols-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); } }
        @media (min-width: 1024px) { 
            .lg\:grid-cols-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
            .lg\:grid-cols-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
            .lg\:grid-cols-4 { grid-template-columns: repeat(4, minmax(0, 1fr)); }
            .lg\:col-span-2 { grid-column: span 2 / span 2; }
        }
        .gap-6 { gap: 1.5rem; }
        .mb-6 { margin-bottom: 1.5rem; }
        .mt-4 { margin-top: 1rem; }
        .mt-8 { margin-top: 2rem; }

        /* Welcome banner-specific styles */
        .welcome-banner {
            padding: 1.5rem; /* p-6 */
            margin-bottom: 1.5rem; /* mb-6 */
        }
        .welcome-banner h2 {
            font-size: 1.5rem; /* text-2xl */
            line-height: 2rem;
            font-weight: 700;
            margin-bottom: 0.5rem; /* mb-2 */
        }
        .welcome-banner p {
            color: #d1fae5; /* text-green-100 */
        }

        .welcome-banner-weather {
            margin-top: 1rem;
            text-align: right;
        }
        @media (min-width: 768px) {
            .welcome-banner-weather {
                margin-top: 0;
            }
        }
        
        /* Form, Table, and UI Element Styles */
        .input-field, .select-field, .textarea-field {
            width: 100%;
            padding: 0.5rem 0.75rem; /* px-3 py-2 */
            border: 1px solid #d1d5db;
            border-radius: 0.375rem; /* rounded-md */
        }

        .btn-primary {
            background-color: #16a34a; /* bg-green-600 */
            color: white; /* text-white */
            padding: 0.5rem 1rem; /* px-4 py-2 */
            border-radius: 0.5rem; /* rounded-lg */
            transition: background-color 0.15s ease-in-out;
            cursor: pointer;
        }
        .btn-primary:hover {
            background-color: #166534; /* hover:bg-green-700 */
        }

        .btn-secondary {
            border: 1px solid #16a34a; /* border-green-600 */
            color: #16a34a; /* text-green-600 */
            padding: 0.5rem 1rem;
            border-radius: 0.5rem;
            transition: background-color 0.15s ease-in-out;
            cursor: pointer;
        }
        .btn-secondary:hover {
            background-color: #f0fdf4; /* hover:bg-green-50 */
        }

        .text-green-600 { color: #16a34a; }
        .text-red-600 { color: #dc2626; }
        .text-blue-600 { color: #2563eb; }
        .text-orange-600 { color: #ea580c; }
        .text-yellow-400 { color: #facc15; }

        .table-container {
            overflow-x: auto;
        }

        .table-header {
            background-color: #f9fafb; /* bg-gray-50 */
        }

        .table-row {
            border-bottom: 1px solid #e5e7eb; /* border-b */
        }
        
        .modal {
            position: fixed;
            inset: 0;
            background-color: rgba(0, 0, 0, 0.5); /* bg-black bg-opacity-50 */
            z-index: 50;
            display: none;
            justify-content: center;
            align-items: center;
            padding: 1rem;
        }

        .modal-content {
            background-color: #ffffff;
            border-radius: 0.5rem;
            max-width: 28rem; /* max-w-md */
            width: 100%;
            max-height: 100vh;
            overflow-y: auto;
            padding: 1.5rem;
        }
    </style>
</head>
<body>
    <!-- Navigation Header -->
    <nav class="gradient-bg">
        <div class="container-nav">
            <div class="nav-content">
                <div class="flex-items-center space-x-3">
                    <i class="fas fa-leaf text-2xl"></i>
                    <h1 class="title">AgriPure Link</h1>
                </div>
                
                <!-- Desktop Navigation -->
                <div class="desktop-nav flex-items-center space-x-6">
                    <button onclick="showSection('dashboard')" class="nav-item">
                        <i class="fas fa-home mr-2"></i>Dashboard
                    </button>
                    <button onclick="showSection('marketplace')" class="nav-item">
                        <i class="fas fa-store mr-2"></i>Marketplace
                    </button>
                    <button onclick="showSection('crops')" class="nav-item">
                        <i class="fas fa-seedling mr-2"></i>Crops
                    </button>
                    <button onclick="showSection('advisory')" class="nav-item">
                        <i class="fas fa-chart-line mr-2"></i>Advisory
                    </button>
                    <button onclick="showSection('profile')" class="nav-item">
                        <i class="fas fa-user mr-2"></i>Profile
                    </button>
                    <div style="position: relative;">
                        <select onchange="changeLanguage(this.value)" style="background-color: #16a34a; color: white; padding: 0.25rem 0.75rem; border-radius: 0.375rem; font-size: 0.875rem;">
                            <option value="en">English</option>
                            <option value="hi">हिंदी</option>
                            <option value="te">తెలుగు</option>
                            <option value="ta">தமிழ்</option>
                        </select>
                    </div>
                </div>

                <!-- Mobile menu button -->
                <button onclick="toggleMobileMenu()" class="mobile-menu-btn">
                    <i class="fas fa-bars text-xl"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Navigation -->
        <div id="mobileMenu" class="mobile-menu">
            <div class="p-4">
                <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 1.5rem;">
                    <h2 style="font-size: 1.125rem; font-weight: 700;">Menu</h2>
                    <button onclick="toggleMobileMenu()" style="color: #6b7280;">
                        <i class="fas fa-times text-xl"></i>
                    </button>
                </div>
                <div style="display: flex; flex-direction: column; gap: 0.5rem;">
                    <button onclick="showSection('dashboard'); toggleMobileMenu()" class="nav-item w-full text-left">
                        <i class="fas fa-home mr-2"></i>Dashboard
                    </button>
                    <button onclick="showSection('marketplace'); toggleMobileMenu()" class="nav-item w-full text-left">
                        <i class="fas fa-store mr-2"></i>Marketplace
                    </button>
                    <button onclick="showSection('crops'); toggleMobileMenu()" class="nav-item w-full text-left">
                        <i class="fas fa-seedling mr-2"></i>Crops
                    </button>
                    <button onclick="showSection('advisory'); toggleMobileMenu()" class="nav-item w-full text-left">
                        <i class="fas fa-chart-line mr-2"></i>Advisory
                    </button>
                    <button onclick="showSection('profile'); toggleMobileMenu()" class="nav-item w-full text-left">
                        <i class="fas fa-user mr-2"></i>Profile
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Main Content -->
    <div class="main-content">
        
        <!-- Dashboard Section -->
        <div id="dashboard" class="section">
            <!-- Welcome Banner -->
            <div class="gradient-bg card welcome-banner">
                <div class="flex flex-col md:flex-row justify-between items-start md:items-center">
                    <div>
                        <h2 style="font-size: 1.5rem; font-weight: 700; margin-bottom: 0.5rem;">Welcome back, Farmer Raj!</h2>
                        <p style="color: #d1fae5;">Your organic farm is thriving. Here's your daily overview.</p>
                    </div>
                    <div class="welcome-banner-weather">
                        <div style="font-size: 0.875rem; color: #d1fae5;">Today's Weather</div>
                        <div class="flex-items-center" style="gap: 0.5rem;">
                            <i class="fas fa-sun" style="color: #fcd34d;"></i>
                            <span style="font-size: 1.125rem; font-weight: 600;">28°C</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Quick Stats -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-6">
                <div class="card card-hover">
                    <div class="flex-items-center" style="justify-content: space-between;">
                        <div>
                            <p style="color: #4b5563; font-size: 0.875rem;">Active Crops</p>
                            <p style="font-size: 1.5rem; font-weight: 700; color: #16a34a;">12</p>
                        </div>
                        <i class="fas fa-seedling" style="font-size: 1.875rem; color: #22c55e;"></i>
                    </div>
                </div>
                <div class="card card-hover">
                    <div class="flex-items-center" style="justify-content: space-between;">
                        <div>
                            <p style="color: #4b5563; font-size: 0.875rem;">Monthly Revenue</p>
                            <p style="font-size: 1.5rem; font-weight: 700; color: #2563eb;">₹45,000</p>
                        </div>
                        <i class="fas fa-rupee-sign" style="font-size: 1.875rem; color: #3b82f6;"></i>
                    </div>
                </div>
                <div class="card card-hover">
                    <div class="flex-items-center" style="justify-content: space-between;">
                        <div>
                            <p style="color: #4b5563; font-size: 0.875rem;">Pending Orders</p>
                            <p style="font-size: 1.5rem; font-weight: 700; color: #ea580c;">8</p>
                        </div>
                        <i class="fas fa-shopping-cart" style="font-size: 1.875rem; color: #f97316;"></i>
                    </div>
                </div>
                <div class="card card-hover">
                    <div class="flex-items-center" style="justify-content: space-between;">
                        <div>
                            <p style="color: #4b5563; font-size: 0.875rem;">Certification Status</p>
                            <p style="font-size: 0.875rem; font-weight: 700; color: #16a34a;">Valid</p>
                        </div>
                        <i class="fas fa-certificate" style="font-size: 1.875rem; color: #22c55e;"></i>
                    </div>
                </div>
            </div>

            <!-- Charts and Recent Activity -->
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6 mb-6">
                <div class="card">
                    <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Monthly Sales Trend</h3>
                    <canvas id="salesChart" width="400" height="200" style="width: 100%; height: 200px; border: 1px solid #e5e7eb; border-radius: 0.5rem;"></canvas>
                </div>
                <div class="card">
                    <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Recent Activities</h3>
                    <div style="display: flex; flex-direction: column; gap: 0.75rem;">
                        <div class="flex-items-center space-x-3" style="padding: 0.75rem; background-color: #f0fdf4; border-radius: 0.5rem;">
                            <i class="fas fa-check-circle" style="color: #22c55e;"></i>
                            <div>
                                <p style="font-weight: 500;">Order #1234 completed</p>
                                <p style="font-size: 0.875rem; color: #4b5563;">2 hours ago</p>
                            </div>
                        </div>
                        <div class="flex-items-center space-x-3" style="padding: 0.75rem; background-color: #eff6ff; border-radius: 0.5rem;">
                            <i class="fas fa-bell" style="color: #3b82f6;"></i>
                            <div>
                                <p style="font-weight: 500;">Certification renewal due</p>
                                <p style="font-size: 0.875rem; color: #4b5563;">5 days remaining</p>
                            </div>
                        </div>
                        <div class="flex-items-center space-x-3" style="padding: 0.75rem; background-color: #fffbeb; border-radius: 0.5rem;">
                            <i class="fas fa-cloud-rain" style="color: #facc15;"></i>
                            <div>
                                <p style="font-weight: 500;">Rain expected tomorrow</p>
                                <p style="font-size: 0.875rem; color: #4b5563;">Adjust irrigation</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Live Market Prices -->
            <div class="card">
                <div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-4">
                    <h3 style="font-size: 1.125rem; font-weight: 600;">Live Market Prices</h3>
                    <div class="flex-items-center space-x-2" style="margin-top: 0.5rem;">
                        <select style="padding: 0.25rem 0.75rem; border: 1px solid #d1d5db; border-radius: 0.375rem; font-size: 0.875rem;">
                            <option>All Regions</option>
                            <option>North India</option>
                            <option>South India</option>
                        </select>
                        <select style="padding: 0.25rem 0.75rem; border: 1px solid #d1d5db; border-radius: 0.375rem; font-size: 0.875rem;">
                            <option>All Crops</option>
                            <option>Rice</option>
                            <option>Wheat</option>
                            <option>Vegetables</option>
                        </select>
                    </div>
                </div>
                <div style="overflow-x: auto;">
                    <table style="width: 100%; font-size: 0.875rem; text-align: left;">
                        <thead style="background-color: #f9fafb;">
                            <tr>
                                <th style="padding: 0.5rem 1rem;">Crop</th>
                                <th style="padding: 0.5rem 1rem;">Grade</th>
                                <th style="padding: 0.5rem 1rem;">Price/Kg</th>
                                <th style="padding: 0.5rem 1rem;">Change</th>
                                <th style="padding: 0.5rem 1rem;">Market</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr style="border-bottom: 1px solid #e5e7eb;">
                                <td style="padding: 0.5rem 1rem;">Organic Rice</td>
                                <td style="padding: 0.5rem 1rem;">Grade A</td>
                                <td style="padding: 0.5rem 1rem; font-weight: 600;">₹45</td>
                                <td style="padding: 0.5rem 1rem; color: #16a34a;">+2.5%</td>
                                <td style="padding: 0.5rem 1rem;">Delhi</td>
                            </tr>
                            <tr style="border-bottom: 1px solid #e5e7eb;">
                                <td style="padding: 0.5rem 1rem;">Organic Wheat</td>
                                <td style="padding: 0.5rem 1rem;">Grade A</td>
                                <td style="padding: 0.5rem 1rem; font-weight: 600;">₹38</td>
                                <td style="padding: 0.5rem 1rem; color: #dc2626;">-1.2%</td>
                                <td style="padding: 0.5rem 1rem;">Mumbai</td>
                            </tr>
                            <tr style="border-bottom: 1px solid #e5e7eb;">
                                <td style="padding: 0.5rem 1rem;">Organic Tomato</td>
                                <td style="padding: 0.5rem 1rem;">Grade B</td>
                                <td style="padding: 0.5rem 1rem; font-weight: 600;">₹25</td>
                                <td style="padding: 0.5rem 1rem; color: #16a34a;">+5.8%</td>
                                <td style="padding: 0.5rem 1rem;">Bangalore</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

        <!-- Marketplace Section -->
        <div id="marketplace" class="section hidden">
            <div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-6">
                <h2 style="font-size: 1.5rem; font-weight: 700; color: #1f2937;">Organic Marketplace</h2>
                <button onclick="showAddProductModal()" class="btn-primary" style="margin-top: 0.5rem;">
                    <i class="fas fa-plus mr-2"></i>Add Product
                </button>
            </div>

            <!-- Search and Filters -->
            <div class="card mb-6">
                <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
                    <input type="text" placeholder="Search products..." class="input-field">
                    <select class="select-field">
                        <option>All Categories</option>
                        <option>Seeds</option>
                        <option>Fertilizers</option>
                        <option>Bio-pesticides</option>
                        <option>Compost</option>
                    </select>
                    <select class="select-field">
                        <option>All Locations</option>
                        <option>Within 50km</option>
                        <option>Within 100km</option>
                        <option>Pan India</option>
                    </select>
                    <select class="select-field">
                        <option>Price: Low to High</option>
                        <option>Price: High to Low</option>
                        <option>Newest First</option>
                        <option>Rating</option>
                    </select>
                </div>
            </div>

            <!-- Product Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div class="card card-hover" style="padding: 0; overflow: hidden;">
                    <div style="height: 12rem; background: linear-gradient(to bottom right, #4ade80, #16a34a); display: flex; align-items: center; justify-content: center;">
                        <i class="fas fa-seedling text-6xl text-white"></i>
                    </div>
                    <div style="padding: 1rem;">
                        <h3 style="font-weight: 600; font-size: 1.125rem; margin-bottom: 0.5rem;">Organic Tomato Seeds</h3>
                        <p style="color: #4b5563; font-size: 0.875rem; margin-bottom: 0.5rem;">High yield variety, certified organic</p>
                        <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.75rem;">
                            <span style="font-size: 1.5rem; font-weight: 700; color: #16a34a;">₹150/pack</span>
                            <div class="flex-items-center">
                                <i class="fas fa-star" style="color: #facc15;"></i>
                                <span style="margin-left: 0.25rem; font-size: 0.875rem;">4.8</span>
                            </div>
                        </div>
                        <div class="flex-items-center" style="justify-content: space-between; font-size: 0.875rem; color: #4b5563; margin-bottom: 0.75rem;">
                            <span><i class="fas fa-map-marker-alt mr-1"></i>Pune, MH</span>
                            <span><i class="fas fa-certificate mr-1"></i>Certified</span>
                        </div>
                        <button class="btn-primary" style="width: 100%; padding: 0.5rem;">
                            Add to Cart
                        </button>
                    </div>
                </div>

                <div class="card card-hover" style="padding: 0; overflow: hidden;">
                    <div style="height: 12rem; background: linear-gradient(to bottom right, #a16207, #713f12); display: flex; align-items: center; justify-content: center;">
                        <i class="fas fa-leaf text-6xl text-white"></i>
                    </div>
                    <div style="padding: 1rem;">
                        <h3 style="font-weight: 600; font-size: 1.125rem; margin-bottom: 0.5rem;">Organic Compost</h3>
                        <p style="color: #4b5563; font-size: 0.875rem; margin-bottom: 0.5rem;">Premium quality, nutrient-rich</p>
                        <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.75rem;">
                            <span style="font-size: 1.5rem; font-weight: 700; color: #16a34a;">₹25/kg</span>
                            <div class="flex-items-center">
                                <i class="fas fa-star" style="color: #facc15;"></i>
                                <span style="margin-left: 0.25rem; font-size: 0.875rem;">4.6</span>
                            </div>
                        </div>
                        <div class="flex-items-center" style="justify-content: space-between; font-size: 0.875rem; color: #4b5563; margin-bottom: 0.75rem;">
                            <span><i class="fas fa-map-marker-alt mr-1"></i>Nashik, MH</span>
                            <span><i class="fas fa-certificate mr-1"></i>Certified</span>
                        </div>
                        <button class="btn-primary" style="width: 100%; padding: 0.5rem;">
                            Add to Cart
                        </button>
                    </div>
                </div>

                <div class="card card-hover" style="padding: 0; overflow: hidden;">
                    <div style="height: 12rem; background: linear-gradient(to bottom right, #60a5fa, #2563eb); display: flex; align-items: center; justify-content: center;">
                        <i class="fas fa-spray-can text-6xl text-white"></i>
                    </div>
                    <div style="padding: 1rem;">
                        <h3 style="font-weight: 600; font-size: 1.125rem; margin-bottom: 0.5rem;">Bio-Pesticide</h3>
                        <p style="color: #4b5563; font-size: 0.875rem; margin-bottom: 0.5rem;">Natural pest control solution</p>
                        <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.75rem;">
                            <span style="font-size: 1.5rem; font-weight: 700; color: #16a34a;">₹180/L</span>
                            <div class="flex-items-center">
                                <i class="fas fa-star" style="color: #facc15;"></i>
                                <span style="margin-left: 0.25rem; font-size: 0.875rem;">4.7</span>
                            </div>
                        </div>
                        <div class="flex-items-center" style="justify-content: space-between; font-size: 0.875rem; color: #4b5563; margin-bottom: 0.75rem;">
                            <span><i class="fas fa-map-marker-alt mr-1"></i>Hyderabad, TS</span>
                            <span><i class="fas fa-certificate mr-1"></i>Certified</span>
                        </div>
                        <button class="btn-primary" style="width: 100%; padding: 0.5rem;">
                            Add to Cart
                        </button>
                    </div>
                </div>
            </div>

            <!-- Import/Export Dashboard -->
            <div class="mt-8 card">
                <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Import/Export Dashboard</h3>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 1rem;">
                        <h4 style="font-weight: 500; margin-bottom: 0.5rem;">Export Opportunities</h4>
                        <div style="display: flex; flex-direction: column; gap: 0.5rem;">
                            <div class="flex-items-center" style="justify-content: space-between; font-size: 0.875rem;">
                                <span>USA - Organic Rice</span>
                                <span style="color: #16a34a;">$2.5/kg</span>
                            </div>
                            <div class="flex-items-center" style="justify-content: space-between; font-size: 0.875rem;">
                                <span>EU - Organic Spices</span>
                                <span style="color: #16a34a;">$8.2/kg</span>
                            </div>
                            <div class="flex-items-center" style="justify-content: space-between; font-size: 0.875rem;">
                                <span>Japan - Organic Tea</span>
                                <span style="color: #16a34a;">$12/kg</span>
                            </div>
                        </div>
                    </div>
                    <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 1rem;">
                        <h4 style="font-weight: 500; margin-bottom: 0.5rem;">Shipping Partners</h4>
                        <div style="display: flex; flex-direction: column; gap: 0.5rem;">
                            <div class="flex-items-center space-x-2">
                                <i class="fas fa-ship" style="color: #3b82f6;"></i>
                                <span style="font-size: 0.875rem;">Global Shipping Co.</span>
                            </div>
                            <div class="flex-items-center space-x-2">
                                <i class="fas fa-plane" style="color: #22c55e;"></i>
                                <span style="font-size: 0.875rem;">Air Cargo Express</span>
                            </div>
                            <div class="flex-items-center space-x-2">
                                <i class="fas fa-truck" style="color: #f97316;"></i>
                                <span style="font-size: 0.875rem;">Land Transport Ltd.</span>
                            </div>
                        </div>
                    </div>
                    <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 1rem;">
                        <h4 style="font-weight: 500; margin-bottom: 0.5rem;">Regulations</h4>
                        <div style="display: flex; flex-direction: column; gap: 0.5rem;">
                            <div style="font-size: 0.875rem;">
                                <i class="fas fa-check-circle" style="color: #22c55e; margin-right: 0.5rem;"></i>
                                Organic Certification Valid
                            </div>
                            <div style="font-size: 0.875rem;">
                                <i class="fas fa-clock" style="color: #facc15; margin-right: 0.5rem;"></i>
                                Export License Renewal Due
                            </div>
                            <div style="font-size: 0.875rem;">
                                <i class="fas fa-file-alt" style="color: #3b82f6; margin-right: 0.5rem;"></i>
                                Documentation Complete
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Crops Section -->
        <div id="crops" class="section hidden">
            <div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-6">
                <h2 style="font-size: 1.5rem; font-weight: 700; color: #1f2937;">Organic Crop Catalog</h2>
                <button onclick="showAddCropModal()" class="btn-primary" style="margin-top: 0.5rem;">
                    <i class="fas fa-plus mr-2"></i>Add New Crop
                </button>
            </div>

            <!-- Crop Filters -->
            <div class="card mb-6">
                <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
                    <select class="select-field">
                        <option>All Seasons</option>
                        <option>Kharif</option>
                        <option>Rabi</option>
                        <option>Zaid</option>
                    </select>
                    <select class="select-field">
                        <option>All Types</option>
                        <option>Cereals</option>
                        <option>Vegetables</option>
                        <option>Fruits</option>
                        <option>Spices</option>
                    </select>
                    <select class="select-field">
                        <option>All Yields</option>
                        <option>High Yield</option>
                        <option>Medium Yield</option>
                        <option>Low Yield</option>
                    </select>
                    <input type="text" placeholder="Search crops..." class="input-field">
                </div>
            </div>

            <!-- Crop Cards -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div class="card card-hover" style="padding: 0; overflow: hidden;">
                    <div style="height: 8rem; background: linear-gradient(to bottom right, #facc15, #ca8a04); display: flex; align-items: center; justify-content: center;">
                        <i class="fas fa-wheat" style="font-size: 2.25rem; color: #ffffff;"></i>
                    </div>
                    <div style="padding: 1rem;">
                        <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.5rem;">
                            <h3 style="font-weight: 600; font-size: 1.125rem;">Organic Wheat</h3>
                            <span style="background-color: #f0fdf4; color: #14532d; font-size: 0.75rem; padding: 0.25rem 0.5rem; border-radius: 9999px;">Certified</span>
                        </div>
                        <p style="color: #4b5563; font-size: 0.875rem; margin-bottom: 0.75rem;">Variety: HD-2967 | Season: Rabi</p>
                        <div class="grid grid-cols-2 gap-4" style="font-size: 0.875rem;">
                            <div>
                                <span style="color: #6b7280;">Yield Estimate:</span>
                                <p style="font-weight: 600;">45 quintals/hectare</p>
                            </div>
                            <div>
                                <span style="color: #6b7280;">Duration:</span>
                                <p style="font-weight: 600;">120-130 days</p>
                            </div>
                        </div>
                        <div style="margin-top: 1rem; display: flex; gap: 0.5rem;">
                            <button class="btn-primary" style="flex: 1; font-size: 0.875rem;">
                                View Details
                            </button>
                            <button class="btn-secondary" style="flex: 1; font-size: 0.875rem;">
                                Add to Farm
                            </button>
                        </div>
                    </div>
                </div>

                <div class="card card-hover" style="padding: 0; overflow: hidden;">
                    <div style="height: 8rem; background: linear-gradient(to bottom right, #f87171, #dc2626); display: flex; align-items: center; justify-content: center;">
                        <i class="fas fa-apple-alt" style="font-size: 2.25rem; color: #ffffff;"></i>
                    </div>
                    <div style="padding: 1rem;">
                        <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.5rem;">
                            <h3 style="font-weight: 600; font-size: 1.125rem;">Organic Tomato</h3>
                            <span style="background-color: #f0fdf4; color: #14532d; font-size: 0.75rem; padding: 0.25rem 0.5rem; border-radius: 9999px;">Certified</span>
                        </div>
                        <p style="color: #4b5563; font-size: 0.875rem; margin-bottom: 0.75rem;">Variety: Pusa Ruby | Season: All Year</p>
                        <div class="grid grid-cols-2 gap-4" style="font-size: 0.875rem;">
                            <div>
                                <span style="color: #6b7280;">Yield Estimate:</span>
                                <p style="font-weight: 600;">60 tonnes/hectare</p>
                            </div>
                            <div>
                                <span style="color: #6b7280;">Duration:</span>
                                <p style="font-weight: 600;">90-100 days</p>
                            </div>
                        </div>
                        <div style="margin-top: 1rem; display: flex; gap: 0.5rem;">
                            <button class="btn-primary" style="flex: 1; font-size: 0.875rem;">
                                View Details
                            </button>
                            <button class="btn-secondary" style="flex: 1; font-size: 0.875rem;">
                                Add to Farm
                            </button>
                        </div>
                    </div>
                </div>

                <div class="card card-hover" style="padding: 0; overflow: hidden;">
                    <div style="height: 8rem; background: linear-gradient(to bottom right, #4ade80, #16a34a); display: flex; align-items: center; justify-content: center;">
                        <i class="fas fa-seedling" style="font-size: 2.25rem; color: #ffffff;"></i>
                    </div>
                    <div style="padding: 1rem;">
                        <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.5rem;">
                            <h3 style="font-weight: 600; font-size: 1.125rem;">Organic Rice</h3>
                            <span style="background-color: #f0fdf4; color: #14532d; font-size: 0.75rem; padding: 0.25rem 0.5rem; border-radius: 9999px;">Certified</span>
                        </div>
                        <p style="color: #4b5563; font-size: 0.875rem; margin-bottom: 0.75rem;">Variety: Basmati 370 | Season: Kharif</p>
                        <div class="grid grid-cols-2 gap-4" style="font-size: 0.875rem;">
                            <div>
                                <span style="color: #6b7280;">Yield Estimate:</span>
                                <p style="font-weight: 600;">35 quintals/hectare</p>
                            </div>
                            <div>
                                <span style="color: #6b7280;">Duration:</span>
                                <p style="font-weight: 600;">140-150 days</p>
                            </div>
                        </div>
                        <div style="margin-top: 1rem; display: flex; gap: 0.5rem;">
                            <button class="btn-primary" style="flex: 1; font-size: 0.875rem;">
                                View Details
                            </button>
                            <button class="btn-secondary" style="flex: 1; font-size: 0.875rem;">
                                Add to Farm
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Geo-tagged Farm Tracking -->
            <div class="mt-8 card">
                <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Farm Tracking & Weather</h3>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                    <div>
                        <h4 style="font-weight: 500; margin-bottom: 0.75rem;">Your Farm Locations</h4>
                        <div style="display: flex; flex-direction: column; gap: 0.75rem;">
                            <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 0.75rem;">
                                <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.5rem;">
                                    <h5 style="font-weight: 500;">Farm Plot A</h5>
                                    <span style="background-color: #f0fdf4; color: #14532d; font-size: 0.75rem; padding: 0.25rem 0.5rem; border-radius: 9999px;">Active</span>
                                </div>
                                <p style="font-size: 0.875rem; color: #4b5563; margin-bottom: 0.5rem;">
                                    <i class="fas fa-map-marker-alt mr-1"></i>
                                    Lat: 18.5204, Long: 73.8567
                                </p>
                                <div class="grid grid-cols-2 gap-2" style="font-size: 0.875rem;">
                                    <div>Area: 2.5 hectares</div>
                                    <div>Crop: Organic Wheat</div>
                                </div>
                            </div>
                            <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 0.75rem;">
                                <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.5rem;">
                                    <h5 style="font-weight: 500;">Farm Plot B</h5>
                                    <span style="background-color: #fffbeb; color: #92400e; font-size: 0.75rem; padding: 0.25rem 0.5rem; border-radius: 9999px;">Preparing</span>
                                </div>
                                <p style="font-size: 0.875rem; color: #4b5563; margin-bottom: 0.5rem;">
                                    <i class="fas fa-map-marker-alt mr-1"></i>
                                    Lat: 18.5304, Long: 73.8667
                                </p>
                                <div class="grid grid-cols-2 gap-2" style="font-size: 0.875rem;">
                                    <div>Area: 1.8 hectares</div>
                                    <div>Next Crop: Organic Rice</div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div>
                        <h4 style="font-weight: 500; margin-bottom: 0.75rem;">Weather Forecast</h4>
                        <div style="display: flex; flex-direction: column; gap: 0.75rem;">
                            <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; background-color: #eff6ff; border-radius: 0.5rem;">
                                <div class="flex-items-center space-x-3">
                                    <i class="fas fa-sun" style="color: #facc15; font-size: 1.25rem;"></i>
                                    <div>
                                        <p style="font-weight: 500;">Today</p>
                                        <p style="font-size: 0.875rem; color: #4b5563;">Sunny, 28°C</p>
                                    </div>
                                </div>
                                <div style="text-align: right;">
                                    <p style="font-size: 0.875rem;">Humidity: 65%</p>
                                    <p style="font-size: 0.875rem;">Wind: 12 km/h</p>
                                </div>
                            </div>
                            <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; background-color: #f9fafb; border-radius: 0.5rem;">
                                <div class="flex-items-center space-x-3">
                                    <i class="fas fa-cloud-rain" style="color: #3b82f6; font-size: 1.25rem;"></i>
                                    <div>
                                        <p style="font-weight: 500;">Tomorrow</p>
                                        <p style="font-size: 0.875rem; color: #4b5563;">Light Rain, 24°C</p>
                                    </div>
                                </div>
                                <div style="text-align: right;">
                                    <p style="font-size: 0.875rem;">Humidity: 85%</p>
                                    <p style="font-size: 0.875rem;">Rainfall: 5mm</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Advisory Section -->
        <div id="advisory" class="section hidden">
            <h2 style="font-size: 1.5rem; font-weight: 700; color: #1f2937; margin-bottom: 1.5rem;">Soil Health & Crop Advisory</h2>

            <!-- Soil Health Dashboard -->
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6 mb-6">
                <div class="card">
                    <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Soil Health Analysis</h3>
                    <div style="display: flex; flex-direction: column; gap: 1rem;">
                        <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; border: 1px solid #d1d5db; border-radius: 0.5rem;">
                            <div class="flex-items-center space-x-3">
                                <div style="width: 1rem; height: 1rem; background-color: #22c55e; border-radius: 9999px;"></div>
                                <span>pH Level</span>
                            </div>
                            <div style="text-align: right;">
                                <span style="font-weight: 600;">6.8</span>
                                <span style="font-size: 0.875rem; color: #16a34a; margin-left: 0.5rem;">Good</span>
                            </div>
                        </div>
                        <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; border: 1px solid #d1d5db; border-radius: 0.5rem;">
                            <div class="flex-items-center space-x-3">
                                <div style="width: 1rem; height: 1rem; background-color: #facc15; border-radius: 9999px;"></div>
                                <span>Nitrogen</span>
                            </div>
                            <div style="text-align: right;">
                                <span style="font-weight: 600;">Medium</span>
                                <span style="font-size: 0.875rem; color: #ca8a04; margin-left: 0.5rem;">Needs Attention</span>
                            </div>
                        </div>
                        <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; border: 1px solid #d1d5db; border-radius: 0.5rem;">
                            <div class="flex-items-center space-x-3">
                                <div style="width: 1rem; height: 1rem; background-color: #22c55e; border-radius: 9999px;"></div>
                                <span>Phosphorus</span>
                            </div>
                            <div style="text-align: right;">
                                <span style="font-weight: 600;">High</span>
                                <span style="font-size: 0.875rem; color: #16a34a; margin-left: 0.5rem;">Excellent</span>
                            </div>
                        </div>
                        <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; border: 1px solid #d1d5db; border-radius: 0.5rem;">
                            <div class="flex-items-center space-x-3">
                                <div style="width: 1rem; height: 1rem; background-color: #ef4444; border-radius: 9999px;"></div>
                                <span>Potassium</span>
                            </div>
                            <div style="text-align: right;">
                                <span style="font-weight: 600;">Low</span>
                                <span style="font-size: 0.875rem; color: #dc2626; margin-left: 0.5rem;">Critical</span>
                            </div>
                        </div>
                    </div>
                    <button class="btn-primary" style="width: 100%; margin-top: 1rem;">
                        Schedule Soil Test
                    </button>
                </div>

                <div class="card">
                    <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">AI Crop Recommendations</h3>
                    <div style="display: flex; flex-direction: column; gap: 1rem;">
                        <div style="border-left: 4px solid #22c55e; padding-left: 1rem;">
                            <h4 style="font-weight: 500; color: #14532d;">Highly Recommended</h4>
                            <p style="font-size: 0.875rem; color: #4b5563; margin-bottom: 0.5rem;">Based on your soil conditions and climate</p>
                            <div style="display: flex; flex-direction: column; gap: 0.5rem;">
                                <div class="flex-items-center" style="justify-content: space-between;">
                                    <span style="font-size: 0.875rem;">Organic Tomatoes</span>
                                    <span style="font-size: 0.75rem; background-color: #f0fdf4; color: #14532d; padding: 0.25rem 0.5rem; border-radius: 9999px;">95% match</span>
                                </div>
                                <div class="flex-items-center" style="justify-content: space-between;">
                                    <span style="font-size: 0.875rem;">Organic Spinach</span>
                                    <span style="font-size: 0.75rem; background-color: #f0fdf4; color: #14532d; padding: 0.25rem 0.5rem; border-radius: 9999px;">92% match</span>
                                </div>
                            </div>
                        </div>
                        <div style="border-left: 4px solid #facc15; padding-left: 1rem;">
                            <h4 style="font-weight: 500; color: #92400e;">Consider With Care</h4>
                            <p style="font-size: 0.875rem; color: #4b5563; margin-bottom: 0.5rem;">May require soil amendments</p>
                            <div style="display: flex; flex-direction: column; gap: 0.5rem;">
                                <div class="flex-items-center" style="justify-content: space-between;">
                                    <span style="font-size: 0.875rem;">Organic Wheat</span>
                                    <span style="font-size: 0.75rem; background-color: #fffbeb; color: #92400e; padding: 0.25rem 0.5rem; border-radius: 9999px;">78% match</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Expert Advisory -->
            <div class="card mb-6">
                <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Expert Advisory</h3>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div>
                        <h4 style="font-weight: 500; margin-bottom: 0.75rem;">Recent Advice</h4>
                        <div style="display: flex; flex-direction: column; gap: 0.75rem;">
                            <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 0.75rem;">
                                <div style="display: flex; gap: 0.75rem; align-items: flex-start;">
                                    <div style="width: 2.5rem; height: 2.5rem; background-color: #f0fdf4; border-radius: 9999px; display: flex; align-items: center; justify-content: center;">
                                        <i class="fas fa-user-tie" style="color: #16a34a;"></i>
                                    </div>
                                    <div style="flex: 1;">
                                        <p style="font-weight: 500; font-size: 0.875rem;">Dr. Rajesh Kumar</p>
                                        <p style="font-size: 0.75rem; color: #4b5563; margin-bottom: 0.5rem;">Soil Specialist</p>
                                        <p style="font-size: 0.875rem;">"Consider adding organic compost to improve potassium levels before next planting season."</p>
                                        <p style="font-size: 0.75rem; color: #6b7280; margin-top: 0.5rem;">2 days ago</p>
                                    </div>
                                </div>
                            </div>
                            <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 0.75rem;">
                                <div style="display: flex; gap: 0.75rem; align-items: flex-start;">
                                    <div style="width: 2.5rem; height: 2.5rem; background-color: #eff6ff; border-radius: 9999px; display: flex; align-items: center; justify-content: center;">
                                        <i class="fas fa-user-tie" style="color: #2563eb;"></i>
                                    </div>
                                    <div style="flex: 1;">
                                        <p style="font-weight: 500; font-size: 0.875rem;">Dr. Priya Sharma</p>
                                        <p style="font-size: 0.75rem; color: #4b5563; margin-bottom: 0.5rem;">Crop Advisor</p>
                                        <p style="font-size: 0.875rem;">"Weather forecast shows good conditions for tomato transplanting next week."</p>
                                        <p style="font-size: 0.75rem; color: #6b7280; margin-top: 0.5rem;">5 days ago</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div>
                        <h4 style="font-weight: 500; margin-bottom: 0.75rem;">Ask an Expert</h4>
                        <div style="display: flex; flex-direction: column; gap: 0.75rem;">
                            <textarea placeholder="Describe your farming question or concern..." class="textarea-field" style="height: 6rem; resize: none;"></textarea>
                            <div class="flex-items-center space-x-2">
                                <button class="btn-primary" style="flex: 1;">
                                    Submit Question
                                </button>
                                <button class="btn-secondary" style="padding: 0.5rem 1rem;">
                                    <i class="fas fa-camera"></i>
                                </button>
                            </div>
                        </div>
                        <div style="margin-top: 1rem; padding: 0.75rem; background-color: #eff6ff; border-radius: 0.5rem;">
                            <p style="font-size: 0.875rem; color: #1e40af;">
                                <i class="fas fa-info-circle mr-2"></i>
                                Expert responses typically arrive within 24 hours
                            </p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Notifications -->
            <div class="card">
                <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Important Notifications</h3>
                <div style="display: flex; flex-direction: column; gap: 0.75rem;">
                    <div style="display: flex; gap: 0.75rem; align-items: flex-start; padding: 0.75rem; background-color: #fef2f2; border-left: 4px solid #ef4444; border-radius: 0.5rem;">
                        <i class="fas fa-exclamation-triangle" style="color: #dc2626; margin-top: 0.25rem;"></i>
                        <div>
                            <p style="font-weight: 500; color: #991b1b;">Certification Renewal Due</p>
                            <p style="font-size: 0.875rem; color: #b91c1c;">Your organic certification expires in 15 days. Please renew to continue selling organic products.</p>
                            <button style="margin-top: 0.5rem; font-size: 0.875rem; background-color: #dc2626; color: white; padding: 0.25rem 0.75rem; border-radius: 0.375rem; transition: background-color 0.15s ease-in-out;">
                                Renew Now
                            </button>
                        </div>
                    </div>
                    <div style="display: flex; gap: 0.75rem; align-items: flex-start; padding: 0.75rem; background-color: #eff6ff; border-left: 4px solid #3b82f6; border-radius: 0.5rem;">
                        <i class="fas fa-gift" style="color: #2563eb; margin-top: 0.25rem;"></i>
                        <div>
                            <p style="font-weight: 500; color: #1e40af;">Government Subsidy Available</p>
                            <p style="font-size: 0.875rem; color: #1d4ed8;">New subsidy scheme for organic farming equipment. Apply before March 31st.</p>
                            <button style="margin-top: 0.5rem; font-size: 0.875rem; background-color: #2563eb; color: white; padding: 0.25rem 0.75rem; border-radius: 0.375rem; transition: background-color 0.15s ease-in-out;">
                                Learn More
                            </button>
                        </div>
                    </div>
                    <div style="display: flex; gap: 0.75rem; align-items: flex-start; padding: 0.75rem; background-color: #f0fdf4; border-left: 4px solid #22c55e; border-radius: 0.5rem;">
                        <i class="fas fa-check-circle" style="color: #16a34a; margin-top: 0.25rem;"></i>
                        <div>
                            <p style="font-weight: 500; color: #14532d;">Soil Test Results Ready</p>
                            <p style="font-size: 0.875rem; color: #15803d;">Your recent soil analysis is complete. View detailed recommendations.</p>
                            <button style="margin-top: 0.5rem; font-size: 0.875rem; background-color: #16a34a; color: white; padding: 0.25rem 0.75rem; border-radius: 0.375rem; transition: background-color 0.15s ease-in-out;">
                                View Results
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Profile Section -->
        <div id="profile" class="section hidden">
            <h2 style="font-size: 1.5rem; font-weight: 700; color: #1f2937; margin-bottom: 1.5rem;">Farmer Profile & KYC</h2>

            <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                <!-- Profile Information -->
                <div style="grid-column: span 1 / span 1;">
                    <div style="display: flex; flex-direction: column; gap: 1.5rem;">
                        <div class="card">
                            <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Personal Information</h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div>
                                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Full Name</label>
                                    <input type="text" value="Rajesh Kumar Patel" class="input-field">
                                </div>
                                <div>
                                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Phone Number</label>
                                    <input type="tel" value="+91 9876543210" class="input-field">
                                </div>
                                <div>
                                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Email Address</label>
                                    <input type="email" value="rajesh.patel@email.com" class="input-field">
                                </div>
                                <div>
                                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Date of Birth</label>
                                    <input type="date" value="1985-06-15" class="input-field">
                                </div>
                                <div style="grid-column: span 2 / span 2;">
                                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Address</label>
                                    <textarea class="textarea-field" style="height: 5rem; resize: none;">Village Khandala, Taluka Maval, District Pune, Maharashtra - 410301</textarea>
                                </div>
                            </div>
                        </div>

                        <div class="card">
                            <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Land Details</h3>
                            <div style="display: flex; flex-direction: column; gap: 1rem;">
                                <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 1rem;">
                                    <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.75rem;">
                                        <h4 style="font-weight: 500;">Plot 1 - Main Farm</h4>
                                        <span style="background-color: #f0fdf4; color: #14532d; font-size: 0.75rem; padding: 0.25rem 0.5rem; border-radius: 9999px;">Verified</span>
                                    </div>
                                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4" style="font-size: 0.875rem;">
                                        <div>
                                            <span style="color: #4b5563;">Survey Number:</span>
                                            <p style="font-weight: 500;">123/4A</p>
                                        </div>
                                        <div>
                                            <span style="color: #4b5563;">Area:</span>
                                            <p style="font-weight: 500;">2.5 hectares</p>
                                        </div>
                                        <div>
                                            <span style="color: #4b5563;">Soil Type:</span>
                                            <p style="font-weight: 500;">Black Cotton Soil</p>
                                        </div>
                                        <div>
                                            <span style="color: #4b5563;">Irrigation:</span>
                                            <p style="font-weight: 500;">Drip + Bore Well</p>
                                        </div>
                                    </div>
                                </div>
                                <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 1rem;">
                                    <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.75rem;">
                                        <h4 style="font-weight: 500;">Plot 2 - Secondary Farm</h4>
                                        <span style="background-color: #fffbeb; color: #92400e; font-size: 0.75rem; padding: 0.25rem 0.5rem; border-radius: 9999px;">Pending</span>
                                    </div>
                                    <p style="font-size: 0.875rem; color: #4b5563; margin-bottom: 0.5rem;">
                                        <i class="fas fa-map-marker-alt mr-1"></i>
                                        Lat: 18.5304, Long: 73.8667
                                    </p>
                                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4" style="font-size: 0.875rem;">
                                        <div>
                                            <span style="color: #4b5563;">Survey Number:</span>
                                            <p style="font-weight: 500;">125/2B</p>
                                        </div>
                                        <div>
                                            <span style="color: #4b5563;">Area:</span>
                                            <p style="font-weight: 500;">1.8 hectares</p>
                                        </div>
                                        <div>
                                            <span style="color: #4b5563;">Soil Type:</span>
                                            <p style="font-weight: 500;">Red Soil</p>
                                        </div>
                                        <div>
                                            <span style="color: #4b5563;">Irrigation:</span>
                                            <p style="font-weight: 500;">Rain Fed</p>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <button class="btn-primary" style="margin-top: 1rem;">
                                <i class="fas fa-plus mr-2"></i>Add New Plot
                            </button>
                        </div>

                        <div class="card">
                            <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Bank Details</h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div>
                                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Bank Name</label>
                                    <input type="text" value="State Bank of India" class="input-field">
                                </div>
                                <div>
                                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Account Number</label>
                                    <input type="text" value="1234567890123456" class="input-field">
                                </div>
                                <div>
                                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">IFSC Code</label>
                                    <input type="text" value="SBIN0001234" class="input-field">
                                </div>
                                <div>
                                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">UPI ID</label>
                                    <input type="text" value="rajesh@paytm" class="input-field">
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- KYC Status and Documents -->
                <div style="grid-column: span 1 / span 1;">
                    <div style="display: flex; flex-direction: column; gap: 1.5rem;">
                        <div class="card">
                            <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">KYC Status</h3>
                            <div style="display: flex; flex-direction: column; gap: 0.75rem;">
                                <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; background-color: #f0fdf4; border-radius: 0.5rem;">
                                    <div class="flex-items-center space-x-3">
                                        <i class="fas fa-check-circle" style="color: #22c55e;"></i>
                                        <span style="font-size: 0.875rem;">Aadhaar Card</span>
                                    </div>
                                    <span style="font-size: 0.75rem; background-color: #d1fae5; color: #14532d; padding: 0.25rem 0.5rem; border-radius: 9999px;">Verified</span>
                                </div>
                                <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; background-color: #f0fdf4; border-radius: 0.5rem;">
                                    <div class="flex-items-center space-x-3">
                                        <i class="fas fa-check-circle" style="color: #22c55e;"></i>
                                        <span style="font-size: 0.875rem;">PAN Card</span>
                                    </div>
                                    <span style="font-size: 0.75rem; background-color: #d1fae5; color: #14532d; padding: 0.25rem 0.5rem; border-radius: 9999px;">Verified</span>
                                </div>
                                <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; background-color: #fffbeb; border-radius: 0.5rem;">
                                    <div class="flex-items-center space-x-3">
                                        <i class="fas fa-clock" style="color: #facc15;"></i>
                                        <span style="font-size: 0.875rem;">Land Records</span>
                                    </div>
                                    <span style="font-size: 0.75rem; background-color: #fef9c3; color: #92400e; padding: 0.25rem 0.5rem; border-radius: 9999px;">Pending</span>
                                </div>
                                <div class="flex-items-center" style="justify-content: space-between; padding: 0.75rem; background-color: #f0fdf4; border-radius: 0.5rem;">
                                    <div class="flex-items-center space-x-3">
                                        <i class="fas fa-check-circle" style="color: #22c55e;"></i>
                                        <span style="font-size: 0.875rem;">Bank Account</span>
                                    </div>
                                    <span style="font-size: 0.75rem; background-color: #d1fae5; color: #14532d; padding: 0.25rem 0.5rem; border-radius: 9999px;">Verified</span>
                                </div>
                            </div>
                            <div style="margin-top: 1rem; padding: 0.75rem; background-color: #eff6ff; border-radius: 0.5rem;">
                                <p style="font-size: 0.875rem; color: #1e40af;">
                                    <i class="fas fa-info-circle mr-2"></i>
                                    KYC completion: 85%
                                </p>
                            </div>
                        </div>

                        <div class="card">
                            <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Certifications</h3>
                            <div style="display: flex; flex-direction: column; gap: 0.75rem;">
                                <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 0.75rem;">
                                    <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.5rem;">
                                        <h4 style="font-weight: 500; font-size: 0.875rem;">Organic Certification</h4>
                                        <span style="background-color: #d1fae5; color: #14532d; font-size: 0.75rem; padding: 0.25rem 0.5rem; border-radius: 9999px;">Active</span>
                                    </div>
                                    <p style="font-size: 0.75rem; color: #4b5563; margin-bottom: 0.25rem;">Certificate No: ORG/2023/001234</p>
                                    <p style="font-size: 0.75rem; color: #4b5563; margin-bottom: 0.5rem;">Valid until: March 15, 2024</p>
                                    <button class="btn-primary" style="font-size: 0.75rem; padding: 0.25rem 0.5rem;">
                                        View Certificate
                                    </button>
                                </div>
                                <div style="border: 1px solid #d1d5db; border-radius: 0.5rem; padding: 0.75rem;">
                                    <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 0.5rem;">
                                        <h4 style="font-weight: 500; font-size: 0.875rem;">Export License</h4>
                                        <span style="background-color: #fef9c3; color: #92400e; font-size: 0.75rem; padding: 0.25rem 0.5rem; border-radius: 9999px;">Expiring Soon</span>
                                    </div>
                                    <p style="font-size: 0.75rem; color: #4b5563; margin-bottom: 0.25rem;">License No: EXP/2023/005678</p>
                                    <p style="font-size: 0.75rem; color: #4b5563; margin-bottom: 0.5rem;">Valid until: January 30, 2024</p>
                                    <button style="font-size: 0.75rem; background-color: #ca8a04; color: white; padding: 0.25rem 0.5rem; border-radius: 0.375rem; transition: background-color 0.15s ease-in-out;">
                                        Renew License
                                    </button>
                                </div>
                            </div>
                        </div>

                        <div class="card">
                            <h3 style="font-size: 1.125rem; font-weight: 600; margin-bottom: 1rem;">Quick Actions</h3>
                            <div style="display: flex; flex-direction: column; gap: 0.5rem;">
                                <button style="width: 100%; text-align: left; padding: 0.5rem 0.75rem; border: 1px solid #d1d5db; border-radius: 0.375rem; transition: background-color 0.15s ease-in-out;">
                                    <i class="fas fa-download mr-2" style="color: #3b82f6;"></i>
                                    Download Profile Summary
                                </button>
                                <button style="width: 100%; text-align: left; padding: 0.5rem 0.75rem; border: 1px solid #d1d5db; border-radius: 0.375rem; transition: background-color 0.15s ease-in-out;">
                                    <i class="fas fa-edit mr-2" style="color: #22c55e;"></i>
                                    Update Information
                                </button>
                                <button style="width: 100%; text-align: left; padding: 0.5rem 0.75rem; border: 1px solid #d1d5db; border-radius: 0.375rem; transition: background-color 0.15s ease-in-out;">
                                    <i class="fas fa-shield-alt mr-2" style="color: #8b5cf6;"></i>
                                    Privacy Settings
                                </button>
                                <button style="width: 100%; text-align: left; padding: 0.5rem 0.75rem; border: 1px solid #d1d5db; border-radius: 0.375rem; transition: background-color 0.15s ease-in-out;">
                                    <i class="fas fa-sign-out-alt mr-2" style="color: #dc2626;"></i>
                                    Logout
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Add Product Modal -->
    <div id="addProductModal" class="modal">
        <div class="modal-content">
            <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 1rem;">
                <h3 style="font-size: 1.125rem; font-weight: 600;">Add New Product</h3>
                <button onclick="hideAddProductModal()" style="color: #6b7280;">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <form style="display: flex; flex-direction: column; gap: 1rem;">
                <div>
                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Product Name</label>
                    <input type="text" class="input-field" placeholder="Enter product name">
                </div>
                <div>
                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Category</label>
                    <select class="select-field">
                        <option>Select category</option>
                        <option>Seeds</option>
                        <option>Fertilizers</option>
                        <option>Bio-pesticides</option>
                        <option>Compost</option>
                    </select>
                </div>
                <div>
                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Price</label>
                    <input type="number" class="input-field" placeholder="Enter price">
                </div>
                <div>
                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Description</label>
                    <textarea class="textarea-field" style="height: 5rem; resize: none;" placeholder="Product description"></textarea>
                </div>
                <div class="flex-items-center space-x-3">
                    <button type="button" onclick="hideAddProductModal()" class="btn-secondary" style="flex: 1;">
                        Cancel
                    </button>
                    <button type="submit" class="btn-primary" style="flex: 1;">
                        Add Product
                    </button>
                </div>
            </form>
        </div>
    </div>

    <!-- Add Crop Modal -->
    <div id="addCropModal" class="modal">
        <div class="modal-content">
            <div class="flex-items-center" style="justify-content: space-between; margin-bottom: 1rem;">
                <h3 style="font-size: 1.125rem; font-weight: 600;">Add New Crop</h3>
                <button onclick="hideAddCropModal()" style="color: #6b7280;">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <form style="display: flex; flex-direction: column; gap: 1rem;">
                <div>
                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Crop Name</label>
                    <input type="text" class="input-field" placeholder="Enter crop name">
                </div>
                <div>
                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Variety</label>
                    <input type="text" class="input-field" placeholder="Enter variety">
                </div>
                <div>
                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Season</label>
                    <select class="select-field">
                        <option>Select season</option>
                        <option>Kharif</option>
                        <option>Rabi</option>
                        <option>Zaid</option>
                    </select>
                </div>
                <div>
                    <label style="display: block; font-size: 0.875rem; font-weight: 500; color: #374151; margin-bottom: 0.25rem;">Expected Yield</label>
                    <input type="text" class="input-field" placeholder="e.g., 45 quintals/hectare">
                </div>
                <div class="flex-items-center space-x-3">
                    <button type="button" onclick="hideAddCropModal()" class="btn-secondary" style="flex: 1;">
                        Cancel
                    </button>
                    <button type="submit" class="btn-primary" style="flex: 1;">
                        Add Crop
                    </button>
                </div>
            </form>
        </div>
    </div>

    <script>
        // Global state
        let currentSection = 'dashboard';
        let currentLanguage = 'en';

        // Language translations
        const translations = {
            en: {
                welcome: "Welcome back, Farmer Raj!",
                dashboard: "Dashboard",
                marketplace: "Marketplace",
                crops: "Crops",
                advisory: "Advisory",
                profile: "Profile"
            },
            hi: {
                welcome: "वापसी पर स्वागत है, किसान राज!",
                dashboard: "डैशबोर्ड",
                marketplace: "बाज़ार",
                crops: "फसलें",
                advisory: "सलाह",
                profile: "प्रोफ़ाइल"
            },
            te: {
                welcome: "తిరిగి స్వాగతం, రైతు రాజ్!",
                dashboard: "డాష్‌బోర్డ్",
                marketplace: "మార్కెట్‌ప్లేస్",
                crops: "పంటలు",
                advisory: "సలహా",
                profile: "ప్రొఫైల్"
            },
            ta: {
                welcome: "மீண்டும் வரவேற்கிறோம், விவசாயி ராஜ்!",
                dashboard: "டாஷ்போர்டு",
                marketplace: "சந்தை",
                crops: "பயிர்கள்",
                advisory: "ஆலோசனை",
                profile: "சுயவிவரம்"
            }
        };

        // Initialize the app
        document.addEventListener('DOMContentLoaded', function() {
            showSection('dashboard');
            initializeChart();
        });

        // Navigation functions
        function showSection(sectionName) {
            // Hide all sections
            const sections = document.querySelectorAll('.section');
            sections.forEach(section => {
                section.classList.add('hidden');
            });

            // Show selected section
            const targetSection = document.getElementById(sectionName);
            if (targetSection) {
                targetSection.classList.remove('hidden');
                currentSection = sectionName;
            }
        }

        function toggleMobileMenu() {
            const mobileMenu = document.getElementById('mobileMenu');
            mobileMenu.classList.toggle('open');
        }

        // Language change function
        function changeLanguage(lang) {
            currentLanguage = lang;
            // In a real app, this would update all text content
            console.log('Language changed to:', lang);
        }

        // Modal functions
        function showAddProductModal() {
            document.getElementById('addProductModal').style.display = 'flex';
        }

        function hideAddProductModal() {
            document.getElementById('addProductModal').style.display = 'none';
        }

        function showAddCropModal() {
            document.getElementById('addCropModal').style.display = 'flex';
        }

        function hideAddCropModal() {
            document.getElementById('addCropModal').style.display = 'none';
        }

        // Chart initialization
        function initializeChart() {
            const canvas = document.getElementById('salesChart');
            const ctx = canvas.getContext('2d');
            if (ctx) {
                // Since there is no external library, we will draw a simple message on the canvas.
                ctx.fillStyle = '#f9fafb';
                ctx.fillRect(0, 0, canvas.width, canvas.height);
                ctx.fillStyle = '#6b7280';
                ctx.textAlign = 'center';
                ctx.font = '16px Arial';
                ctx.fillText("Chart functionality removed. Add a library to enable.", canvas.width / 2, canvas.height / 2);
            }
        }

        // Close modals when clicking outside
        document.addEventListener('click', function(event) {
            const modals = ['addProductModal', 'addCropModal'];
            modals.forEach(modalId => {
                const modal = document.getElementById(modalId);
                if (modal && event.target === modal) {
                    modal.style.display = 'none';
                }
            });
        });

        // Simulate real-time updates
        setInterval(function() {
            // Update weather, prices, etc.
            console.log('Updating real-time data...');
        }, 30000);

        // Form submissions
        document.addEventListener('submit', function(event) {
            event.preventDefault();
            
            // Show success message
            const successDiv = document.createElement('div');
            successDiv.className = 'fixed top-4 right-4 bg-green-600 text-white px-4 py-2 rounded-lg shadow-lg z-50';
            successDiv.textContent = 'Successfully saved!';
            document.body.appendChild(successDiv);
            
            setTimeout(() => {
                successDiv.remove();
            }, 3000);
            
            // Close modals
            hideAddProductModal();
            hideAddCropModal();
        });
    </script>
</body>
</html>
