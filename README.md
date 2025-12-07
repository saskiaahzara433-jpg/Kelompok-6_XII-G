<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jamur Crispy Kel 6 XII-G</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        /* Custom styles for the Inter font and general body styling */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f7f7f7; /* Light background */
        }
        /* Custom utility for subtle shadow */
        .card-shadow {
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.06);
        }
    </style>
</head>
<body class="min-h-screen flex flex-col">

    <!-- Navbar -->
    <header class="sticky top-0 z-50 bg-green-700 shadow-xl">
        <div class="max-w-4xl mx-auto p-4 flex justify-between items-center">
            <h1 class="text-xl font-bold text-white tracking-wider">Jamur Crispy Kel 6 XII-G</h1>
            <nav class="flex space-x-4">
                <button onclick="showPage('home')" class="nav-button text-white hover:text-green-200 transition duration-150 ease-in-out font-medium">Beranda</button>
                <button onclick="showPage('menu')" class="nav-button text-white hover:text-green-200 transition duration-150 ease-in-out font-medium">Menu</button>
                <button onclick="showPage('checkout')" class="nav-button relative text-white hover:text-green-200 transition duration-150 ease-in-out font-medium">
                    Keranjang (<span id="cart-count">0</span>)
                </button>
            </nav>
        </div>
    </header>

    <!-- Main Content Area -->
    <main class="flex-grow max-w-4xl mx-auto w-full p-4 sm:p-6">

        <!-- 1. Halaman Beranda (Home) -->
        <section id="home-page" class="page-section space-y-8">
            <div class="bg-white p-6 sm:p-8 rounded-xl card-shadow border-t-4 border-green-600">
                <h2 class="text-3xl font-extrabold text-gray-800 mb-4 text-center">Selamat Datang di Dunia Jamur Crispy!</h2>
                <img src="https://placehold.co/800x400/38a169/ffffff?text=JAMUR+CRISPY+KEL+6" alt="Placeholder gambar Jamur Crispy" class="w-full h-auto rounded-lg mb-6 shadow-md" onerror="this.onerror=null;this.src='https://placehold.co/600x300/38a169/ffffff?text=JAMUR+CRISPY+KEL+6';">

                <div class="space-y-6 text-gray-700 leading-relaxed">
                    <!-- Pengertian Jamur Crispy -->
                    <div class="p-4 bg-green-50 rounded-lg">
                        <h3 class="text-2xl font-semibold text-green-700 mb-2 border-b pb-1">Apa Itu Jamur Crispy?</h3>
                        <p>Jamur Crispy adalah camilan inovatif yang dibuat dari jamur tiram segar pilihan, dibalut dengan adonan tepung spesial yang renyah dan gurih. Camilan ini diolah hingga menghasilkan tekstur krispi di luar namun tetap lembut dan lezat di dalam. Ini adalah cara terbaik menikmati kebaikan jamur dengan cita rasa yang bikin ketagihan!</p>
                    </div>

                    <!-- Asal Usul Jamur Crispy -->
                    <div class="p-4 bg-green-50 rounded-lg">
                        <h3 class="text-2xl font-semibold text-green-700 mb-2 border-b pb-1">Asal Usul Singkat</h3>
                        <p>Awalnya, Jamur Crispy merupakan kreasi sederhana dari para penggiat kuliner rumahan yang ingin membuat variasi makanan ringan sehat dari hasil pertanian lokal. Berasal dari inovasi di dapur-dapur kecil, kini Jamur Crispy telah menjadi salah satu camilan populer di Indonesia berkat rasanya yang unik dan teksturnya yang sangat renyah.</p>
                    </div>

                    <!-- Kalimat Ajakan -->
                    <div class="p-5 bg-yellow-100 rounded-xl text-center shadow-inner">
                        <p class="text-2xl font-bold text-red-600 mb-2">Jangan Hanya Membaca, Rasakan Sendiri!</p>
                        <p class="text-xl text-gray-800">Camilan renyah, gurih, dan penuh rasa! Segera cek menu kami dan dapatkan kelezatan tiada tara dari Jamur Crispy Kel 6 XII-G!</p>
                        <button onclick="showPage('menu')" class="mt-4 px-6 py-3 bg-red-500 text-white font-bold rounded-full hover:bg-red-600 transition transform hover:scale-105 duration-300 shadow-lg">
                            Lihat Menu & Pesan Sekarang!
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- 2. Halaman Menu (Menu) -->
        <section id="menu-page" class="page-section hidden">
            <h2 class="text-3xl font-extrabold text-gray-800 mb-6 text-center">Pilihan Rasa Jamur Crispy Kami</h2>
            <div id="product-list" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Products will be rendered here by JavaScript -->
            </div>
        </section>

        <!-- 3. Halaman Checkout (Checkout) -->
        <section id="checkout-page" class="page-section hidden">
            <h2 class="text-3xl font-extrabold text-gray-800 mb-6 text-center">Keranjang Belanja Anda</h2>

            <div id="cart-items-container" class="bg-white p-4 sm:p-6 rounded-xl card-shadow border-t-4 border-green-600 space-y-4">
                <!-- Cart items will be rendered here -->
            </div>

            <div class="mt-8 p-4 bg-yellow-100 rounded-xl card-shadow flex justify-between items-center">
                <p class="text-xl font-bold text-gray-800">Total Harga:</p>
                <p id="total-price" class="text-3xl font-extrabold text-green-600">Rp 0</p>
            </div>

            <div class="mt-6 text-center">
                <button id="checkout-button" onclick="checkoutWhatsApp()" class="w-full sm:w-auto px-8 py-4 bg-green-500 text-white font-bold text-lg rounded-xl hover:bg-green-600 transition duration-300 shadow-lg disabled:opacity-50" disabled>
                    Checkout ke WhatsApp 089514461076
                </button>
                <p id="checkout-message" class="text-sm text-red-500 mt-2 hidden">Keranjang Anda masih kosong. Silakan tambahkan produk!</p>
            </div>
        </section>

    </main>
    
    <!-- Footer -->
    <footer class="bg-gray-100 mt-8 py-4 text-center text-gray-500 text-sm border-t">
        <p>&copy; 2024 Jamur Crispy Kel 6 XII-G. Dibuat dengan cinta.</p>
    </footer>

    <script>
        // --- DATA PRODUK DAN KERANJANG ---
        const PRODUCTS = [
            {
                id: 1,
                name: "Jamur Crispy Rasa Balado",
                price: 5000,
                image: "https://iili.io/fIt0sK7.jpg",
                description: "Rasa pedas manis khas balado yang membangkitkan selera. Krispi pedas yang sempurna!"
            },
            {
                id: 2,
                name: "Jamur Crispy Rasa Jagung Bakar",
                price: 5000,
                image: "https://iili.io/fIt1Sg1.jpg",
                description: "Manis, gurih, dengan aroma jagung bakar yang menggoda. Favorit semua usia."
            },
            {
                id: 3,
                name: "Jamur Crispy Rasa Keju Asin",
                price: 5000,
                image: "https://iili.io/fItwX72.jpg",
                description: "Rasa keju yang creamy dan asin, memberikan sensasi ngemil yang mewah dan gurih."
            },
        ];

        let cart = []; // Keranjang belanja: [{id: 1, name: "...", price: 5000, quantity: 1}]
        
        const WHATSAPP_NUMBER = "6289514461076"; // Gunakan kode negara 62 untuk WhatsApp

        // --- FUNGSI TAMPILAN HALAMAN (SPA) ---
        function showPage(pageId) {
            // Hide all pages
            document.querySelectorAll('.page-section').forEach(section => {
                section.classList.add('hidden');
            });
            // Show the requested page
            const page = document.getElementById(pageId + '-page');
            if (page) {
                page.classList.remove('hidden');
            }

            // Update content for specific pages
            if (pageId === 'menu') {
                renderProducts();
            } else if (pageId === 'checkout') {
                renderCart();
            }
        }

        // --- FUNGSI PRODUK DAN KERANJANG ---
        
        // Fungsi untuk memformat harga ke Rupiah
        function formatRupiah(number) {
            return new Intl.NumberFormat('id-ID', {
                style: 'currency',
                currency: 'IDR',
                minimumFractionDigits: 0
            }).format(number);
        }

        // 1. Render Produk di Halaman Menu
        function renderProducts() {
            const productListContainer = document.getElementById('product-list');
            productListContainer.innerHTML = ''; // Clear previous content

            PRODUCTS.forEach(product => {
                const productCard = `
                    <div class="bg-white rounded-xl overflow-hidden card-shadow hover:shadow-lg transition duration-300">
                        <!-- Image with fallback and styling -->
                        <img src="${product.image}" alt="${product.name}" 
                             class="w-full h-48 object-cover object-center" 
                             onerror="this.onerror=null;this.src='https://placehold.co/400x300/4c4c4c/ffffff?text=${encodeURIComponent(product.name)}';" 
                             loading="lazy">
                        
                        <div class="p-5 space-y-3">
                            <h3 class="text-xl font-bold text-gray-800">${product.name}</h3>
                            <p class="text-sm text-gray-600">${product.description}</p>
                            <p class="text-2xl font-extrabold text-green-600">${formatRupiah(product.price)}</p>
                            
                            <button onclick="addToCart(${product.id})" 
                                    class="w-full px-4 py-2 bg-yellow-500 text-gray-900 font-semibold rounded-lg hover:bg-yellow-600 transition transform hover:scale-[1.02] duration-200 flex items-center justify-center space-x-2 shadow-md">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                                    <path d="M3 1a1 1 0 000 2h1.22l.305 1.222a.997.997 0 00.01.042l1.375 5.499a1 1 0 00.944.606h9.096l1.493-4.478A1 1 0 0014.288 6H7.382L7 4H3z" />
                                    <path d="M5 14a2 2 0 100 4 2 2 0 000-4zm11 0a2 2 0 100 4 2 2 0 000-4z" />
                                </svg>
                                <span>+ Keranjang</span>
                            </button>
                        </div>
                    </div>
                `;
                productListContainer.innerHTML += productCard;
            });
        }

        // 2. Tambahkan ke Keranjang
        function addToCart(productId) {
            const product = PRODUCTS.find(p => p.id === productId);
            if (!product) return;

            const existingItem = cart.find(item => item.id === productId);

            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({ ...product, quantity: 1 });
            }

            updateCartCount();
            console.log("Keranjang:", cart);
        }

        // 3. Hapus Item dari Keranjang
        function removeFromCart(productId) {
            const existingItemIndex = cart.findIndex(item => item.id === productId);

            if (existingItemIndex > -1) {
                const existingItem = cart[existingItemIndex];
                
                if (existingItem.quantity > 1) {
                    existingItem.quantity -= 1;
                } else {
                    cart.splice(existingItemIndex, 1);
                }
            }
            
            updateCartCount();
            renderCart(); // Re-render checkout page
        }

        // 4. Update Tampilan Jumlah Keranjang di Navbar
        function updateCartCount() {
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            document.getElementById('cart-count').textContent = totalItems;
        }

        // 5. Render Keranjang di Halaman Checkout
        function renderCart() {
            const container = document.getElementById('cart-items-container');
            const totalElement = document.getElementById('total-price');
            const checkoutBtn = document.getElementById('checkout-button');
            const checkoutMsg = document.getElementById('checkout-message');

            container.innerHTML = ''; // Clear previous content

            if (cart.length === 0) {
                container.innerHTML = '<p class="text-center text-gray-500 py-8">Keranjang belanja Anda kosong. Yuk, pilih jamur favoritmu!</p>';
                totalElement.textContent = formatRupiah(0);
                checkoutBtn.disabled = true;
                checkoutMsg.classList.remove('hidden');
                return;
            }

            let grandTotal = 0;
            checkoutBtn.disabled = false;
            checkoutMsg.classList.add('hidden');

            cart.forEach(item => {
                const subtotal = item.price * item.quantity;
                grandTotal += subtotal;

                const cartItemHtml = `
                    <div class="flex items-center justify-between border-b pb-3 pt-3 last:border-b-0">
                        <div class="flex items-center space-x-4">
                             <img src="${item.image}" alt="${item.name}" class="w-16 h-16 object-cover rounded-md" 
                                onerror="this.onerror=null;this.src='https://placehold.co/100x100/4c4c4c/ffffff?text=Produk';" 
                                loading="lazy">
                            <div>
                                <p class="font-semibold text-gray-800">${item.name}</p>
                                <p class="text-sm text-gray-500">${formatRupiah(item.price)} x ${item.quantity}</p>
                            </div>
                        </div>
                        <div class="flex flex-col items-end">
                            <p class="font-bold text-lg text-green-700">${formatRupiah(subtotal)}</p>
                            <button onclick="removeFromCart(${item.id})" class="text-red-500 hover:text-red-700 text-sm mt-1">
                                Hapus 1
                            </button>
                        </div>
                    </div>
                `;
                container.innerHTML += cartItemHtml;
            });

            totalElement.textContent = formatRupiah(grandTotal);
        }

        // 6. Fungsi Checkout ke WhatsApp
        function checkoutWhatsApp() {
            if (cart.length === 0) {
                // Should not happen if button is disabled, but for safety
                console.error("Keranjang kosong!");
                return;
            }

            let orderSummary = "Halo, saya ingin memesan Jamur Crispy:\n\n";
            let grandTotal = 0;
            
            cart.forEach((item, index) => {
                const subtotal = item.price * item.quantity;
                grandTotal += subtotal;
                
                // Construct the message line by line
                orderSummary += `${index + 1}. ${item.name} (${formatRupiah(item.price)}) x ${item.quantity} = ${formatRupiah(subtotal)}\n`;
            });
            
            orderSummary += `\nTotal Belanja: ${formatRupiah(grandTotal)}`;
            orderSummary += "\n\nMohon konfirmasi pesanan saya. Terima kasih!";

            // Encode the message for URL
            const encodedMessage = encodeURIComponent(orderSummary);

            // Construct the final WhatsApp URL
            const whatsappUrl = `https://wa.me/${WHATSAPP_NUMBER}?text=${encodedMessage}`;

            // Open the WhatsApp URL in a new tab
            window.open(whatsappUrl, '_blank');
        }

        // --- INICIALISASI APLIKASI ---
        window.onload = function() {
            // Start on the home page
            showPage('home'); 
            // Update cart count immediately (should be 0)
            updateCartCount();
            console.log("Website Jamur Crispy siap!");
        };
    </script>
</body>
</html>
