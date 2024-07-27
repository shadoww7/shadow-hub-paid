<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Shadow Executor</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&family=Poppins:wght@400;700&display=swap" rel="stylesheet">
  <link rel="icon" href="https://cdn.discordapp.com/icons/1264486818578038838/67d48ed87c2d2f1553eba56784d66fa9.webp?size=96">
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      position: relative;
      width: 100%;
      overflow-x: hidden;
      background-color: #1a001a; /* Background color */
      color: #b3b3b3;
    }

    .star {
      position: absolute;
      width: 2px;
      height: 2px;
      background: white;
      border-radius: 50%;
      box-shadow: 0 0 5px rgba(255, 255, 255, 0.5);
    }

    .star::before {
      content: '';
      position: absolute;
      top: -1px;
      left: -1px;
      width: 4px;
      height: 4px;
      background: rgba(255, 255, 255, 0.5);
      border-radius: 50%;
      filter: blur(2px);
    }

    .spacing {
      --nav-main-spacing: -3rem;
      --main-faq-spacing: 3rem;
      --faq-features-spacing: 3rem;
    }

    .main-content {
      margin-top: var(--nav-main-spacing);
      animation: fadeIn 1s ease-out;
    }

    .faq-section {
      margin-top: var(--main-faq-spacing);
      animation: fadeIn 1.5s ease-out;
    }

    .features-section {
      margin-top: var(--faq-features-spacing);
      animation: fadeIn 2s ease-out;
    }

    .faq-content {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.5s ease-in-out;
      color: #b3b3b3; /* Update text color inside of FAQ */
    }

    .faq-content.open {
      max-height: 500px; /* Adjust as necessary */
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
      }

      to {
        opacity: 1;
      }
    }

    /* Custom Scrollbar */
    ::-webkit-scrollbar {
      width: 10px;
    }

    ::-webkit-scrollbar-track {
      background: #2d2d2d;
    }

    ::-webkit-scrollbar-thumb {
      background: #6b21a8;
    }

    ::-webkit-scrollbar-thumb:hover {
      background: #9d4edd;
    }

    .card {
      background-color: #290029; /* Slightly lighter than background */
      transition: transform 0.3s ease, background-color 0.3s ease;
    }

    .card:hover {
      transform: translateY(-10px);
      background-color: #330033; /* Slightly lighter on hover */
    }

    .faq-button {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .faq-button .emoji {
      transition: transform 0.3s ease;
    }

    .faq-button .emoji.open {
      transform: rotate(180deg);
    }
  </style>
</head>

<body class="spacing">
  <div class="container mx-auto p-4">
    <!-- Navigation -->
    <nav class="flex justify-between items-center py-4">
      <div class="text-2xl font-bold bg-gradient-to-r from-purple-500 to-purple-700 text-transparent bg-clip-text">Shadow Executor</div>
      <div class="space-x-4 text-lg">
        <a href="https://discord.gg/z4DazfFyX9" class="hover:text-gray-400"><i class="fab fa-discord"></i></a>
        <a href="https://github.com/DevilishRar/Novas/tree/main" class="hover:text-gray-400" onclick="redirectToGitHub()"><i class="fab fa-github"></i></a>
      </div>
    </nav>

    <!-- Main Content -->
    <div class="main-content flex flex-col lg:flex-row items-center py-16 min-h-screen justify-center">
      <div class="text-center lg:text-left lg:w-1/2">
        <h1 class="text-4xl font-bold mb-4 text-purple-500">Shadow Executor for <span class="text-purple-700">Roblox</span></h1>
        <h2 class="text-3xl mb-4">Bypass with <span class="text-purple-700">power</span>. Inject with <span class="text-purple-700">ease</span>.</h2>
        <p class="text-lg mb-6">Experience the ultimate cheating tool for Roblox. Our dedicated developers ensure constant updates and superior performance.</p>
        <div class="flex space-x-4">
          <a href="https://github.com/shadoww7/shadow-hub-paid/raw/main/shadow%20exec%20loader.exe" class="bg-purple-600 text-white py-2 px-4 rounded-full text-lg">Get Shadow Executor Now!</a>
          <button onclick="scrollToSection('faq')" class="bg-gray-800 text-white py-2 px-4 rounded-full text-lg">FAQ</button>
          <button onclick="scrollToSection('features')" class="bg-gray-800 text-white py-2 px-4 rounded-full text-lg">Features</button>
        </div>
      </div>
      <div class="mt-8 lg:mt-0 lg:w-1/2 flex justify-center">
        <img src="https://media.discordapp.net/attachments/1265328495307788290/1265387400746766427/image.png?ex=66a1fc1a&is=66a0aa9a&hm=ef6c7778214dac998cff984f06a4696b5178eb799fbdfd8fa84058e4432e28d6&=&format=webp&quality=lossless" alt="Shadow Executor" class="rounded-lg shadow-2xl">
      </div>
    </div>

    <!-- FAQ Section -->
    <section id="faq" class="faq-section py-16">
      <h2 class="text-3xl font-bold mb-8 text-center text-purple-500">Frequently Asked Questions</h2>
      <div class="space-y-8">
        <div class="card p-6 rounded-lg">
          <button class="faq-button text-2xl font-semibold mb-4 w-full text-left focus:outline-none" onclick="toggleFaq(this)">
            What is Shadow Executor?
            <span class="emoji">⌄</span>
          </button>
          <div class="faq-content">
            <p>Shadow Executor is a powerful Roblox executor that allows you to inject scripts and bypass restrictions effortlessly.</p>
          </div>
        </div>
        <div class="card p-6 rounded-lg">
          <button class="faq-button text-2xl font-semibold mb-4 w-full text-left focus:outline-none" onclick="toggleFaq(this)">
            Is Shadow Executor safe to use?
            <span class="emoji">⌄</span>
          </button>
          <div class="faq-content">
            <p>Yes, our team of dedicated developers constantly updates Shadow Executor to ensure its safety and reliability.</p>
          </div>
        </div>
        <div class="card p-6 rounded-lg">
          <button class="faq-button text-2xl font-semibold mb-4 w-full text-left focus:outline-none" onclick="toggleFaq(this)">
            How can I get Shadow Executor?
            <span class="emoji">⌄</span>
          </button>
          <div class="faq-content">
            <p>You can download Shadow Executor by clicking on the "Get Shadow Executor Now!" button above.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="features-section py-16">
      <h2 class="text-3xl font-bold mb-8 text-center text-purple-500">Features</h2>
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div class="card p-6 rounded-lg">
          <h3 class="text-2xl font-semibold mb-4">Advanced Scripting</h3>
          <p>Inject and execute scripts with unparalleled ease and precision.</p>
        </div>
        <div class="card p-6 rounded-lg">
          <h3 class="text-2xl font-semibold mb-4">Regular Updates</h3>
          <p>Our team ensures that Shadow Executor is always up-to-date with the latest Roblox patches.</p>
        </div>
        <div class="card p-6 rounded-lg">
          <h3 class="text-2xl font-semibold mb-4">User-Friendly Interface</h3>
          <p>Navigating through Shadow Executor's features is simple and intuitive.</p>
        </div>
        <div class="card p-6 rounded-lg">
          <h3 class="text-2xl font-semibold mb-4">High Performance</h3>
          <p>Experience lightning-fast script execution and bypassing.</p>
        </div>
        <div class="card p-6 rounded-lg">
          <h3 class="text-2xl font-semibold mb-4">Customizable Settings</h3>
          <p>Tailor Shadow Executor to fit your specific needs and preferences.</p>
        </div>
        <div class="card p-6 rounded-lg">
          <h3 class="text-2xl font-semibold mb-4">Dedicated Support</h3>
          <p>Our support team is always ready to assist you with any issues.</p>
        </div>
      </div>
    </section>
  </div>

  <!-- SVG Stars -->
  <div id="stars-container" class="absolute inset-0 -z-10"></div>

  <script>
    function createStars() {
      const starsContainer = document.getElementById('stars-container');
      for (let i = 0; i < 100; i++) {
        const star = document.createElement('div');
        star.classList.add('star');
        star.style.top = `${Math.random() * 100}%`;
        star.style.left = `${Math.random() * 100}%`;
        starsContainer.appendChild(star);
      }
    }

    function toggleFaq(button) {
      const content = button.nextElementSibling;
      const emoji = button.querySelector('.emoji');
      content.classList.toggle('open');
      emoji.classList.toggle('open');
      if (content.classList.contains('open')) {
        emoji.textContent = '⌃';
      } else {
        emoji.textContent = '⌄';
      }
    }

    function scrollToSection(id) {
      document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
    }

    function redirectToGitHub() {
      window.location.href = 'https://github.com/YOUR_GITHUB_LINK_HERE';
    }

    createStars();
  </script>
</body>

</html>
