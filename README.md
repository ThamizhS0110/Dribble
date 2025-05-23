# Project Responsive Web Design using Bootstrap
## Date:23.05.2025

## AIM:
To create a simplified clone of Dribbble (https://dribbble.com/) landing page.


## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Insert the necessary CSS and JavaScript files as external in order to use Bootstrap.

### Step 5:
Create a HTML file and include the needed Bootstrap components.

### Step 6:
Publish the website in the LocalHost.

## PROGRAM :
### login.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Login - Saveetha Engineering College</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" />
  <style>
    body {
      position: relative;
      font-family: 'Segoe UI', sans-serif;
      padding-top: 70px;
      min-height: 100vh;
      color: #fff;
    }
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: url('im.png') no-repeat center center/cover;
      opacity: 0.5;
      z-index: -1;
      filter: brightness(0.7);
    }
    nav {
      background: rgba(0, 64, 128, 0.85);
      padding: 10px 20px;
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
      display: flex;
      align-items: center;
      gap: 15px;
    }
    nav img.logo {
      width: 50px;
      border-radius: 8px;
      box-shadow: 0 0 8px rgba(255, 255, 255, 0.7);
    }
    nav a {
      color: #aaddff;
      font-weight: 600;
      text-decoration: none;
      margin-left: 15px;
      font-size: 1.1rem;
    }
    nav a:hover, nav a.active {
      color: #d0f0ff;
      text-decoration: underline;
    }
    .login-box {
      position: relative;
      max-width: 400px;
      margin: 100px auto;
      background: rgba(0, 51, 102, 0.85);
      border-radius: 12px;
      padding: 30px;
      box-shadow: 0 0 20px rgba(0, 102, 204, 0.6);
      overflow: hidden;
      height: 450px; /* fix height for forms */
      text-align: center;
    }
    .login-box img {
      width: 200px;
      margin-bottom: 20px;
      position: relative;
      z-index: 10;
    }
    .form-toggle {
      position: relative;
      z-index: 30;
      display: flex;
      justify-content: center;
      margin-bottom: 10px;
      gap: 10px;
    }
    .form-toggle button {
      padding: 8px 20px;
      border: none;
      background: #004080;
      color: #aaddff;
      font-weight: 600;
      cursor: pointer;
      border-radius: 6px;
      transition: background-color 0.3s ease;
    }
    .form-toggle button.active,
    .form-toggle button:hover {
      background: #007bff;
      color: white;
    }
    form {
      position: absolute;
      top: 120px;
      left: 0;
      width: 100%;
      padding: 0 15px;
      transition: transform 0.5s ease, opacity 0.5s ease;
      opacity: 0;
      pointer-events: none;
      z-index: 10;
    }
    form.active-form {
      opacity: 1;
      pointer-events: auto;
      transform: translateX(0);
      z-index: 20;
    }
    form.slide-out-left {
      transform: translateX(-100%);
      opacity: 0;
      pointer-events: none;
      z-index: 10;
    }
    form.slide-in-right {
      transform: translateX(100%);
      opacity: 0;
      pointer-events: none;
      z-index: 10;
    }
    h1 {
      color: #cce6ff;
      margin-bottom: 20px;
    }
    .form-control {
      margin-bottom: 15px;
    }
  </style>
</head>
<body>
  <nav>
    <img class="logo" src="imag.png" alt="Saveetha Engineering College Logo" />
  </nav>

  <div class="login-box">
    <img src="image.png" alt="College Logo" />

    <div class="form-toggle">
      <button id="login-btn" class="active">Login</button>
      <button id="register-btn">Register</button>
    </div>

    <!-- Login Form -->
    <form id="login-form" class="active-form">
      <h1>Login</h1>
      <input type="email" class="form-control" placeholder="Email" required />
      <input type="password" class="form-control" placeholder="Password" required />
      <button type="submit" class="btn btn-primary w-100">Login</button>
    </form>

    <!-- Register Form -->
    <form id="register-form" class="slide-in-right">
      <h1>Register</h1>
      <input type="text" class="form-control" placeholder="Full Name" required />
      <input type="email" class="form-control" placeholder="Email" required />
      <input type="password" class="form-control" placeholder="Password" required />
      <input type="password" class="form-control" placeholder="Confirm Password" required />
      <button type="submit" class="btn btn-success w-100">Register</button>
    </form>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
  <script>
    const loginBtn = document.getElementById('login-btn');
    const registerBtn = document.getElementById('register-btn');
    const loginForm = document.getElementById('login-form');
    const registerForm = document.getElementById('register-form');

    loginBtn.addEventListener('click', () => {
      if (loginBtn.classList.contains('active')) return;

      loginBtn.classList.add('active');
      registerBtn.classList.remove('active');

      registerForm.classList.add('slide-out-left');
      registerForm.classList.remove('active-form');

      loginForm.classList.remove('slide-in-right');
      loginForm.classList.add('active-form');
    });

    registerBtn.addEventListener('click', () => {
      if (registerBtn.classList.contains('active')) return;

      registerBtn.classList.add('active');
      loginBtn.classList.remove('active');

      loginForm.classList.add('slide-out-left');
      loginForm.classList.remove('active-form');

      registerForm.classList.remove('slide-in-right');
      registerForm.classList.add('active-form');
    });
    document.getElementById('login-form').addEventListener('submit', e => {
      e.preventDefault();
  // validation if any
       window.location.href = 'search.html';
    });

  </script>
</body>
</html>

```
### navigate.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Navigate - Saveetha Engineering College Nav</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" />
  <style>
    body {
      background: linear-gradient(to right, #003366, #66ccff);
      font-family: 'Segoe UI', sans-serif;
      color: #fff;
      padding: 40px;
      min-height: 100vh;
    }
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: url('im.png') no-repeat center center/cover;
      opacity: 0.5;
      z-index: -1;
      filter: brightness(0.7);
    }
    .container {
      background: rgba(0, 64, 128, 0.8);
      border-radius: 12px;
      max-width: 700px;
      margin: 0 auto;
      padding: 30px;
      box-shadow: 0 0 20px rgba(0, 102, 204, 0.6);
    }
    h1 {
      margin-bottom: 20px;
    }
    p {
      font-size: 1.2rem;
    }
    a.back-link {
      color: #aaddff;
      text-decoration: none;
      font-weight: 600;
    }
    a.back-link:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1 id="roomName">Navigation</h1>
    <p id="directions"></p>
    <a href="search.html" class="back-link">← Back to Search</a>
  </div>

  <script>
    const urlParams = new URLSearchParams(window.location.search);
    const room = urlParams.get('room') || 'Unknown Room';
    document.getElementById('roomName').textContent = `Navigate to: ${room}`;

    // Simple directions for demo purposes, you can expand this with actual maps or detailed text
    const directionsData = {
      'Principal Office': 'From the main entrance, go straight and take the first right. The Principal\'s Office is the large building on your left.',
      'Admission Office': 'Enter the campus, walk towards the main block. Admission Office is next to the library on the ground floor.',
      'Kit Room': 'From the main gate, turn left and walk past the canteen. The Kit Room is opposite the student lounge.'
    };

    document.getElementById('directions').textContent = directionsData[room] || 'Directions are currently unavailable for this room.';
  </script>
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```
### search.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Search Classrooms - Saveetha Engineering College Nav</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" />
  <style>
    body {
      padding-top: 70px;
      background: linear-gradient(to right, #003366, #66ccff);
      font-family: 'Segoe UI', sans-serif;
      color: #fff;
      min-height: 100vh;
    }
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: url('im.png') no-repeat center center/cover;
      opacity: 0.5;
      z-index: -1;
      filter: brightness(0.7);
    }
    nav img.logo {
      height: 50px;
      width: auto;
      border-radius: 8px;
      box-shadow: 0 0 8px rgba(255,255,255,0.7);
    }
    nav {
      background: #004080;
      padding: 10px 20px;
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
    }
    nav a {
      color: #aaddff;
      margin-right: 20px;
      font-weight: 600;
      text-decoration: none;
    }
    nav a:hover {
      color: #d0f0ff;
      text-decoration: underline;
    }
    section {
      background: rgba(255, 255, 255, 0.1);
      border-radius: 12px;
      padding: 30px;
      margin: 20px auto;
      max-width: 900px;
      box-shadow: 0 0 20px rgba(0, 102, 204, 0.6);
    }
    .room-card .card {
      background: rgba(0, 64, 128, 0.8);
      border: none;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      color: #d0e7ff;
    }
    .room-card .card:hover {
      transform: scale(1.05);
      box-shadow: 0 6px 20px rgba(0, 102, 204, 0.7);
    }
    .room-card img {
      height: 180px;
      object-fit: cover;
      border-radius: 10px 10px 0 0;
    }
    .btn-primary {
      background-color: #3399ff;
      border-color: #3399ff;
      width: 100%;
    }
    .btn-primary:hover {
      opacity: 0.9;
    }
  </style>
</head>
<body>
  <nav>
     <img class="logo" src="imag.png" alt="Saveetha Engineering College Logo" />
    <a href="search.html">Search</a>
    <a href="contact.html">Contact</a>
    <a href="login.html">Logout</a>
  </nav>

  <section id="searchSection">
    <h2 class="mb-4 text-center">Search for a Classroom</h2>
    <input
      type="text"
      id="searchInput"
      class="form-control mb-4"
      placeholder="Enter room name or description..."
      oninput="filterRooms()"
    />
    <div class="row" id="roomList">
      <div class="col-md-4 room-card" data-name="Principal Office" data-description="College principal's main office">
        <div class="card">
          <img src="pri.jpeg" alt="Principal Office" />
          <div class="card-body">
            <h5 class="card-title">Principal Office</h5>
            <p class="card-text">College principal's main office.</p>
            <a href="navigate.html?room=Principal+Office" class="btn btn-primary">Navigate</a>
          </div>
        </div>
      </div>
      <div class="col-md-4 room-card" data-name="Admission Office" data-description="New student admissions and help desk">
        <div class="card">
          <img src="add.jpeg" alt="Admission Office" />
          <div class="card-body">
            <h5 class="card-title">Admission Office</h5>
            <p class="card-text">New student admissions and help desk.</p>
            <a href="navigate.html?room=Admission+Office" class="btn btn-primary">Navigate</a>
          </div>
        </div>
      </div>
      <div class="col-md-4 room-card" data-name="Kit Room" data-description="Collect your ID card, books, and uniforms here">
        <div class="card">
          <img src="kit.jpeg" alt="Kit Room" />
          <div class="card-body">
            <h5 class="card-title">College Kit Room</h5>
            <p class="card-text">Collect your ID card, books, and uniforms here.</p>
            <a href="navigate.html?room=Kit+Room" class="btn btn-primary">Navigate</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <script>
    function filterRooms() {
      const input = document.getElementById('searchInput').value.toLowerCase();
      const rooms = document.querySelectorAll('.room-card');
      rooms.forEach(room => {
        const name = room.getAttribute('data-name').toLowerCase();
        const desc = room.getAttribute('data-description').toLowerCase();
        room.style.display = (name.includes(input) || desc.includes(input)) ? 'block' : 'none';
      });
    }
  </script>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>

```
### contact.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Contact & About - Saveetha Engineering College Nav</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" />
  <style>
    body {
      position: relative;
      font-family: 'Segoe UI', sans-serif;
      padding-top: 70px;
      min-height: 100vh;
      color: #fff;
      overflow-x: hidden;
    }
    /* Background image with overlay */
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: url('im.png') no-repeat center center/cover;
      opacity: 0.5;
      z-index: -1;
      filter: brightness(0.7);
    }
    nav {
      background: rgba(0, 64, 128, 0.85);
      padding: 10px 20px;
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
      display: flex;
      align-items: center;
      gap: 15px;
    }
    nav img.logo {
      height: 50px;
      width: auto;
      border-radius: 8px;
      box-shadow: 0 0 8px rgba(255,255,255,0.7);
    }
    nav a {
      color: #aaddff;
      font-weight: 600;
      text-decoration: none;
      margin-left: 15px;
      font-size: 1.1rem;
    }
    nav a:hover, nav a.active {
      color: #d0f0ff;
      text-decoration: underline;
    }
    section {
      max-width: 900px;
      margin: 20px auto;
      background: rgba(0, 51, 102, 0.75);
      border-radius: 12px;
      padding: 30px;
      box-shadow: 0 0 20px rgba(0, 102, 204, 0.6);
    }
    h1, h2 {
      margin-bottom: 20px;
      color: #cce6ff;
    }
    p {
      font-size: 1.1rem;
      line-height: 1.5;
    }
    .contact-info {
      margin-top: 20px;
      font-size: 1.2rem;
    }
    .contact-info strong {
      display: inline-block;
      width: 120px;
      color: #aaddff;
    }
    .contact-info a {
      color: #aaddff;
      text-decoration: none;
    }
    .contact-info a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <nav>
    <img class="logo" src="imag.png" alt="Saveetha Engineering College Logo" />
    <a href="search.html">Search</a>
    <a href="contact.html" class="active">Contact</a>
    <a href="login.html">Logout</a>
  </nav>

  <section>
    <h1>About Saveetha Engineering College (Autonomous)</h1>
    <p>
      Saveetha Engineering College, located in Chennai, Tamil Nadu, is an autonomous institution dedicated to excellence in engineering education and research. Established with the vision to nurture competent engineers with strong ethical values, the college offers undergraduate and postgraduate programs with modern infrastructure and experienced faculty.
    </p>

    <h2>Contact Information</h2>
    <div class="contact-info">
      <p><strong>Address:</strong> Saveetha Engineering College, Thandalam, Chennai - 602105, Tamil Nadu, India</p>
      <p><strong>Phone:</strong> +91 44 2670 8999</p>
      <p><strong>Email:</strong> info@saveethaengineering.ac.in</p>
      <p><strong>Website:</strong> <a href="https://www.saveethaengineering.ac.in" target="_blank" rel="noopener">www.saveethaengineering.ac.in</a></p>
    </div>
  </section>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>

```


## OUTPUT:
![Screenshot 2025-05-23 113204](https://github.com/user-attachments/assets/2bfa56a1-d347-4064-a7ed-eae5fcc1f6d7)
![Screenshot 2025-05-23 113210](https://github.com/user-attachments/assets/2f65d64a-60de-43aa-a7b0-0378f4304292)
![Screenshot 2025-05-23 113233](https://github.com/user-attachments/assets/0f71d154-ccd5-48b5-9aec-7afdb5108659)
![Screenshot 2025-05-23 113239](https://github.com/user-attachments/assets/939e57e3-577b-4534-aa31-e3a4fd9d071a)
![Screenshot 2025-05-23 113247](https://github.com/user-attachments/assets/42878ad9-b07a-4151-a9f8-86debf4536e0)


## RESULT:
The Project for responsive web design using Bootstrap is completed successfully.
