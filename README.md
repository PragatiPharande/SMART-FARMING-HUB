# SMART-FARMING-HUB
PROGRAM CODE:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Farmers Hub</title>
    <style>

        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to bottom, #e8f5e8, #c8e6c9);
            color: #333;
        }
        header {
            background: #4caf50;
            color: white;
            padding: 20px;
            text-align: center;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        nav {
            background: #388e3c;
            padding: 10px;
            text-align: center;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s;
        }
        nav a:hover {
            color: #c8e6c9;
        }
        section {
            padding: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }
        h2 {
            color: #2e7d32;
            border-bottom: 2px solid #4caf50;
            padding-bottom: 10px;
        }
        .container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
        }
        .card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            padding: 20px;
            flex: 1 1 300px;
            transition: transform 0.3s;
        }
        .card:hover {
            transform: translateY(-5px);
        }
        img {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
        }
        button {
            background: #4caf50;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s;
        }
        button:hover {
            background: #388e3c;
        }
        form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        input, select {
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .recommendation {
            display: none;
            margin-top: 20px;
        }
        .tip {
            cursor: pointer;
            background: #f1f8e9;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
        }
        .tip-content {
            display: none;
            margin-top: 10px;
        }
        .gallery {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        .gallery img {
            width: 300px;
            display: none;
        }
        .gallery img.active {
            display: block;
        }
        .video-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }
        .video-container iframe {
            width: 100%;
            max-width: 560px;
            height: 315px;
            border-radius: 8px;
        }
        footer {
            background: #2e7d32;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 40px;
        }
        footer a {
            color: #c8e6c9;
            text-decoration: none;
        }
        footer a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <header>
        <h1>Smart Farmers Hub</h1>
        <p>Your AI-Powered Guide to Profitable Farming</p>
    </header>
    <nav>
        <a href="#home">Home</a>
        <a href="#recommendation">Crop Recommendation</a>
        <a href="#tips">Farming Tips</a>
        <a href="#gallery">Crop Gallery</a>
        <a href="#resources">Resources</a>
        <a href="#videos">Farming Videos</a>
    </nav>

    <section id="home">
        <h2>Welcome to Smart Farmers Hub</h2>
        <p>Get personalized crop recommendations based on your location, soil, budget, and profit goals. Explore farming tips, galleries, and resources to boost your yield!</p>
        <img src="https://images.unsplash.com/photo-1500651230702-0e2d8a49d4ad?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Farm Landscape">
    </section>

    <section id="recommendation">
        <h2>Crop Recommendation Tool</h2>
        <div class="container">
            <div class="card">
                <form id="cropForm">
                    <label for="location">Location :</label>
                    <select id="location" required>
                        <option value="">Select</option>
                        <option value="tropical">Pune</option>
                        <option value="temperate">Solapur</option>
                        <option value="arid">Nagpur</option>
                    </select>
                   
                    <label for="soil">Soil Type:</label>
                    <select id="soil" required>
                        <option value="">Select</option>
                        <option value="sandy">Sandy</option>
                        <option value="clay">Clay</option>
                        <option value="loam">Loam</option>
                    </select>
                   
                    <label for="cost">Available Cost :</label>
                    <input type="number" id="cost" min="0" required>
                   
                    <label for="profitFocus">Prioritize Profit:</label>
                    <input type="checkbox" id="profitFocus">
                   
                    <button type="submit">Get Recommendation</button>
                </form>
            </div>
            <div class="card recommendation" id="result">
                <h3>Recommended Crop</h3>
                <p id="cropName"></p>
                <p id="cropReason"></p>
                <p id="cropProfit"></p>
                <img id="cropImage" src="" alt="Crop Image">
            </div>
        </div>
    </section>

    <section id="tips">
        <h2>Farming Tips</h2>
        <div class="tip" onclick="toggleTip('tip1')">Soil Preparation Tips</div>
        <div id="tip1" class="tip-content">
            <p>Test your soil pH and nutrient levels. Amend with compost for better fertility. Rotate crops to prevent soil depletion.</p>
            <img src="https://images.unsplash.com/photo-1574943320219-553eb213f72d?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Soil Preparation">
        </div>
        <div class="tip" onclick="toggleTip('tip2')">Water Management</div>
        <div id="tip2" class="tip-content">
            <p>Use drip irrigation to conserve water. Monitor rainfall and adjust watering schedules. Mulching helps retain moisture.</p>
            <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Irrigation">
        </div>
        <div class="tip" onclick="toggleTip('tip3')">Pest Control</div>
        <div id="tip3" class="tip-content">
            <p>Opt for organic pesticides. Introduce beneficial insects. Regular scouting prevents infestations.</p>
            <img src="https://images.unsplash.com/photo-1592982375566-7b9b5a3b5b5b?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80" alt="Pest Control">
        </div>
    </section>

    <section id="gallery">
        <h2>Crop Gallery</h2>
        <div class="gallery">
            <button onclick="prevImage()">Prev</button>
            <img id="galleryImg1" src="https://images.unsplash.com/photo-1574323347407-f5e1ad6d020b?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80" alt="Rice" class="active">
            <img id="galleryImg2" src="https://images.unsplash.com/photo-1551754655-cd27e38d2076?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80" alt="Cotton">
            <img id="galleryImg3" src="https://images.unsplash.com/photo-1592150621744-aca64f48394a?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80" alt="Sugarcane">
            <img id="galleryImg4" src="https://images.unsplash.com/photo-1574943320219-553eb213f72d?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Jowar">
            <button onclick="nextImage()">Next</button>
        </div>
    </section>

    <section id="resources">
        <h2>Additional Resources</h2>
        <div class="container">
            <div class="card">
                <h3>Farming Apps</h3>
                <p>Download apps like FarmLogs or AgriWebb for tracking and analytics or refer to websites like krushimitra for more information about the farming methods .</p>
               
            </div>
            <div class="card">
                <h3>Market Prices</h3>
                <p>Check real-time crop prices on sites like  or local markets.</p>
                <img src="https://images.unsplash.com/photo-1554224155-6726b3ff858f?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Market">
            </div>
        </div>
    </section>

    <section id="videos">
        <h2>Farming Videos in Maharashtra</h2>
        <div class="video-container">
            <div class="card">
                <h3>How to start rice farming?</h3>
                <p>click here <a href="https://www.youtube.com/watch?v=-eBrAm64fpg" target="_blank">start rice farming now </a> --learn rice farming through vidoes .</p>
                <p>Learn about rice cultivation techniques in Maharashtra.</p>
            </div>
            <div class="card">
                <h3>Cotton Farming Methods</h3>
                <p>click here <a href="https://www.youtube.com/watch?v=eN-TqqBQOAk" target="_blank">cotton farming methods </a> --learn about cotton farming through videos</p>
                <p>Explore cotton farming practices in Vidarbha region.</p>
            </div>
            <div class="card">
                <h3>Sugarcane Cultivation</h3>
               <p>click here <a href="https://www.youtube.com/watch?v=wdvrzWtkHfA" target="_blank">sugarcane farming methods </a>-- the right way of cultivating sugar cane </p>
                <p>Discover sugarcane farming in Maharashtra.</p>
            </div>
            <div class="card">
                <h3>General Farming Tips</h3>
               <p>click here <a href="https://www.youtube.com/watch?v=heTxEsrPVdQ" target="_blank">overall farming tips </a> --more tips on general farming </p>
                <p>Useful tips for sustainable farming in Maharashtra.</p>
            </div>
        </div>
    </section>
<section id="trends">
        <h2>Market Trends & Weather</h2>
        <div class="container">
            <div class="card">
                <h3>Crop Cost Trends (in ₹)</h3>
                <p>Sample trends for major crops in Maharashtra (based on recent data; check local markets for updates).</p>
                <table class="trend-table">
                    <thead>
                        <tr>
                            <th>Crop</th>
                            <th>Current Price (₹/kg)</th>
                            <th>Trend (Last Month)</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Rice</td>
                            <td>25-30</td>
                            <td>Stable</td>
                        </tr>
                        <tr>
                            <td>Wheat</td>
                            <td>20-25</td>
                            <td>50-60</td>
                            <td>Decreasing</td>
                        </tr>
                        <tr>
                            <td>Sugarcane</td>
                            <td>3-4</td>
                            <td>Stable</td>
                        </tr>
                        <tr>
                            <td>Jowar</td>
                            <td>15-20</td>
                            <td>Increasing</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <div class="card">
                <h3>Weather in Maharashtra Cities</h3>
                <p>Current weather conditions (demo data; use a weather app for real-time info).</p>
                <ul>
                    <li><strong>Pune:</strong> Sunny, 28°C, Humidity 60%</li>
                    <li><strong>Nagpur:</strong> Partly Cloudy, 32°C, Humidity 55%</li>
                    <li><strong>Kolhapur:</strong> Rainy, 26°C, Humidity 75%</li>
                </ul>
            </div>
        </div>
    </section>
    <footer>
        <p>&copy;  Smart Farmers Hub. Empowering Farmers Worldwide.</p>
        <p>Visit <a href="https://www.krushimitr.in/" target="_blank">Krushimitra</a> for more farming resources in Maharashtra.</p>
    </footer>

    <script>
        // Crop Data (Hardcoded for Demo)
        const crops = [
            { name: "Rice", location: "tropical", soil: "clay", minCost: 100, profit: 500, image: "https://images.unsplash.com/photo-1574323347407-f5e1ad6d020b?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80", reason: "Thrives in tropical climates with clay soil, high yield." },
            { name: "Wheat", location: "temperate", soil: "loam", minCost: 150, profit: 600, image: "https://plus.unsplash.com/premium_photo-1661963447711-27f892ffe292?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8d2hlYXR8ZW58MHx8MHx8fDA%3D", reason: "Ideal for temperate regions with loam soil, excellent profit." },
            { name: "Corn", location: "tropical", soil: "sandy", minCost: 200, profit: 700, image: "https://images.unsplash.com/photo-1551754655-cd27e38d2076?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80", reason: "Grows well in tropical sandy soil, high profit potential." },
            { name: "Tomatoes", location: "arid", soil: "loam", minCost: 50, profit: 300, image: "https://images.unsplash.com/photo-1592150621744-aca64f48394a?ixlib=rb-4.0.3&auto=format&fit=crop&w=300&q=80", reason: "Suitable for arid climates with loam soil, quick returns." }
        ];

        // Form Submission
        document.getElementById('cropForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const location = document.getElementById('location').value;
            const soil = document.getElementById('soil').value;
            const cost = parseInt(document.getElementById('cost').value);
            const profitFocus = document.getElementById('profitFocus').checked;

            let recommendations = crops.filter(crop => crop.location === location && crop.soil === soil && crop.minCost <= cost);
            if (profitFocus) {
                recommendations.sort((a, b) => b.profit - a.profit);
            }

            if (recommendations.length > 0) {
                const rec = recommendations[0];
                document.getElementById('cropName').textContent = rec.name;
                document.getElementById('cropReason').textContent = rec.reason;
                document.getElementById('cropProfit').textContent = `Estimated Profit: ₹${rec.profit}`;
                document.getElementById('cropImage').src = rec.image;
                document.getElementById('result').style.display = 'block';
            } else {
                alert('No suitable crop found. Try adjusting inputs.');
            }
        });

        // Toggle Tips
        function toggleTip(id) {
            const content = document.getElementById(id);
            content.style.display = content.style.display === 'block' ? 'none' : 'block';
        }

        // Gallery Navigation
        let currentImage = 0;
        const images = document.querySelectorAll('.gallery img');
        function showImage(index) {
            images.forEach(img => img.classList.remove('active'));
            images[index].classList.add('active');
        }
        function nextImage() {
            currentImage = (currentImage + 1) % images.length;
            showImage(currentImage);
        }
        function prevImage() {
            currentImage = (currentImage - 1 + images.length) % images.length;
            showImage(currentImage);
        }
    </script>
</body>
</html>
