# Project Responsive Web Design using Bootstrap
# Date:07-12-2024
# AIM:
To create a simplified clone of Dribbble (https://dribbble.com/) landing page.

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Insert the necessary CSS and JavaScript files as external in order to use Bootstrap.

## Step 5:
Create a HTML file and include the needed Bootstrap components.

## Step 6:
Publish the website in the LocalHost.

# PROGRAM :
```
index.html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dribbble Clone</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
      .shot-card img {
        height: 200px;
        object-fit: cover;
      }
      .profile-banner {
        height: 250px;
        background-color: #969899;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 1.5rem;
      }
      .profile-img {
        width: 120px;
        height: 120px;
        border-radius: 50%;
        border: 5px solid #fff;
        margin-top: -60px;
      }
    </style>
  </head>
  <body>
  
    <!-- Header -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container">
        <a class="navbar-brand" href="#">Dribbble Clone</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item"><a class="nav-link" href="Explore.html">Explore</a></li>
            <li class="nav-item"><a class="nav-link" href="shots.html">Shots</a></li>
            <li class="nav-item"><a class="nav-link" href="Sign In.html">Sign In</a></li>
            <li class="nav-item"><a class="nav-link" href="profile.html">profile</a></li>
          </ul>
        </div>
      </div>
    </nav>
  
    <!-- Profile Section -->
    <div class="profile-banner text-center text-grey">
      <div>Welcome to Designer's Portfolio</div>
    </div>
    <div class="text-center mt-3">
      <img src="image5.png" alt="Profile" class="profile-img">
      <h3>John Doe</h3>
      <p>Creative Designer | UI/UX Enthusiast</p>
    </div>
  
    <!-- Shots Gallery -->
    <div class="container mt-5">
      <h4 class="mb-4">Recent Shots</h4>
      <div id="shots-gallery" class="row g-3">
        <!-- JavaScript will populate shots here -->
      </div>
    </div>
  
    <!-- Modal -->
    <div class="modal fade" id="shotModal" tabindex="-1" aria-labelledby="shotModalLabel" aria-hidden="true">
      <div class="modal-dialog modal-lg">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="shotModalLabel">Shot Title</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <img id="modal-shot-img" src="" alt="Shot" class="img-fluid">
            <p id="modal-shot-desc" class="mt-3"></p>
          </div>
        </div>
      </div>
    </div>
  
    <!-- Footer -->
    <footer class="bg-light text-center py-3 mt-5">
      <p>&copy; 2024 Dribbble Clone | Designed with Maha shree M</p>
    </footer>
  
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.s0/dist/js/bootstrap.bundle.min.j"></script>
    <script>
      // Sample shots data
      const shots = [
        { title: "Modern UI Design", description: "A clean and modern user interface design.", img: "image1.png" },
        { title: "Landing Page Concept", description: "A creative landing page design.", img: "image2.png" },
        { title: "E-commerce App", description: "A sleek e-commerce app design.", img: "image3.png" },
        { title: "Portfolio Design", description: "A professional portfolio design for creatives.", img: "image4.png" }
      ];
  
      // Populate shots gallery
      const gallery = document.getElementById('shots-gallery');
      shots.forEach((shot, index) => {
        const col = document.createElement('div');
        col.className = 'col-sm-6 col-md-4 col-lg-3';
        col.innerHTML = `
          <div class="card shot-card" data-bs-toggle="modal" data-bs-target="#shotModal" onclick="viewShot(${index})">
            <img src="${shot.img}" class="card-img-top" alt="${shot.title}">
            <div class="card-body">
              <h6 class="card-title">${shot.title}</h6>
              <p class="card-text">${shot.description}</p>
            </div>
          </div>
        `;
        gallery.appendChild(col);
      });
  
      // View shot in modal
      function viewShot(index) {
        const shot = shots[index];
        document.getElementById('shotModalLabel').textContent = shot.title;
        document.getElementById('modal-shot-img').src = shot.img;
        document.getElementById('modal-shot-desc').textContent = shot.description;
      }
    </script>
  </body>
  </html>

#profile.html

  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile - Dribbble Clone</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" />
    
  </head>
  <body>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Dribbble Clone</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link active" href="index.html">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="Sign In.html">Upload</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="profile.html">Profile</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  
    <!-- Profile Content -->
    <div class="container my-4">
      <div class="row">
        <div class="col-md-4">
          <img src="image7.jpg" class="img-fluid rounded-circle" alt="Profile Picture">
          <h3>John Doe</h3>
          <p>Designer & Illustrator</p>
        </div>
        <div class="col-md-8">
          <h4>My Shots</h4>
          <div class="row">
            <div class="col-md-4">
              <div class="card">
                <img src="image8.png" class="card-img-top" alt="Shot 2">
              </div>
            </div>
            <!-- Repeat for other shots -->
          </div>
        </div>
      </div>
    </div>
  
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
  </body>
  </html>

shot.html

  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Upload Shot - Dribbble Clone</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" />
    
  </head>
  <body>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Dribbble Clone</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link" href="index.html">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link active" href="Sign In.html.html">Upload</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="profile.html">Profile</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  
    <!-- Upload Form -->
    <div class="container my-4">
      <h3>Upload Your Shot</h3>
      <form id="uploadForm">
        <div class="mb-3">
          <label for="shotTitle" class="form-label">Title</label>
          <input type="text" class="form-control" id="shotTitle" required>
        </div>
        <div class="mb-3">
          <label for="shotDescription" class="form-label">Description</label>
          <textarea class="form-control" id="shotDescription" rows="3" required></textarea>
        </div>
        <div class="mb-3">
          <label for="shotImage" class="form-label">Upload Image</label>
          <input class="form-control" type="file" id="shotImage" required>
        </div>
        <button type="submit" class="btn btn-primary">Upload</button>
      </form>
    </div>
  
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
    <script src="scripts/main.js"></script>
  </body>
  </html>
sign in.html

  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Find Jobs - Dribbble Clone</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" />
    
  </head>
  <body>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="index.html">Dribbble Clone</a>
      </div>
    </nav>
  
    <!-- Find Jobs Content -->
    <div class="container my-4">
      <h1 class="text-center">Find Jobs</h1>
      <div class="card my-3">
        <div class="card-body">
          <h5 class="card-title">UI/UX Designer</h5>
          <p class="card-text">Location: Remote | Full-time</p>
          <a href="#" class="btn btn-primary">Apply Now</a>
        </div>
      </div>
      <div class="card my-3">
        <div class="card-body">
          <h5 class="card-title">Graphic Designer</h5>
          <p class="card-text">Location: New York | Part-time</p>
          <a href="#" class="btn btn-primary">Apply Now</a>
        </div>
      </div>
    </div>
  
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
  </body>
  </html>
```
# OUTPUT:
![Screenshot (129)](https://github.com/user-attachments/assets/7bf19919-7604-4f7c-bc7f-62a49c7184d4)
![Screenshot (134)](https://github.com/user-attachments/assets/066dd3fe-bc40-4c84-af82-137daad64570)
![Screenshot (130)](https://github.com/user-attachments/assets/2ee26526-d99c-42b8-8706-02c20098aef8)
![Screenshot (131)](https://github.com/user-attachments/assets/5570e929-af33-489d-9c37-6085cbd194f0)
![Screenshot (132)](https://github.com/user-attachments/assets/9bd36a20-2105-4d90-af0e-44972c207cc3)
![Screenshot (133)](https://github.com/user-attachments/assets/189d96ce-d611-471b-a621-ea46c18426a2)

# RESULT:
The Project for responsive web design using Bootstrap is completed successfully.
