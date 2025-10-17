# Project Responsive Web Design using Bootstrap
## Date:17/10/2025

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
~~~
<!--
File: 1_index.html
Simple landing page
-->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Landing — Acme Co.</title>
  <style>
    body{font-family:Inter,system-ui,Segoe UI,Roboto,Arial;margin:0;color:#111}
    .hero{min-height:80vh;display:grid;place-items:center;text-align:center;padding:3rem;background:linear-gradient(180deg,#f7fbff,#ffffff)}
    .card{max-width:900px}
    .btn{display:inline-block;margin-top:1rem;padding:.75rem 1.25rem;border-radius:8px;text-decoration:none;border:1px solid #0b63d1}
  </style>
</head>
<body>
  <main class="hero">
    <div class="card">
      <h1>Acme Co.</h1>
      <p>Beautiful, tiny digital products &amp; ideas built to move your business forward.</p>
      <a class="btn" href="2_portfolio.html">View portfolio</a>
    </div>
  </main>
</body>
</html>


<!--
File: 2_portfolio.html
Simple portfolio grid
-->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Portfolio — Acme Co.</title>
  <style>
    body{font-family:Inter,system-ui,Segoe UI,Roboto,Arial;margin:0;padding:2rem;color:#222}
    .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:1rem}
    .item{padding:1rem;border-radius:10px;box-shadow:0 6px 18px rgba(15,15,15,0.06)}
    header{display:flex;justify-content:space-between;align-items:center}
    a{color:#0b63d1;text-decoration:none}
  </style>
</head>
<body>
  <header>
    <h2>Selected work</h2>
    <nav><a href="1_index.html">Home</a> • <a href="3_blog.html">Blog</a></nav>
  </header>
  <section class="grid">
    <article class="item"><h3>Project A</h3><p>Design + Front-end</p></article>
    <article class="item"><h3>Project B</h3><p>Mobile app</p></article>
    <article class="item"><h3>Project C</h3><p>Brand identity</p></article>
    <article class="item"><h3>Project D</h3><p>Marketing site</p></article>
  </section>
</body>
</html>


<!--
File: 3_blog.html
Simple blog listing with lightweight CSS
-->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Blog — Acme Co.</title>
  <style>
    body{font-family:Inter,system-ui,Segoe UI,Roboto,Arial;margin:0;padding:2rem;color:#222}
    .post{padding:1rem 0;border-bottom:1px solid #eee}
    .meta{font-size:.9rem;color:#666}
    a{color:#0b63d1;text-decoration:none}
  </style>
</head>
<body>
  <header><h2>Latest articles</h2></header>
  <main>
    <article class="post">
      <h3><a href="#">Design systems: a pragmatic guide</a></h3>
      <div class="meta">Oct 15, 2025 — 6 min read</div>
      <p>Short excerpt that previews the article and invites the reader.</p>
    </article>
    <article class="post">
      <h3><a href="#">How we prototype faster</a></h3>
      <div class="meta">Sep 2, 2025 — 4 min read</div>
      <p>Short excerpt with the key idea and takeaways.</p>
    </article>
  </main>
</body>
</html>


<!--
File: 4_contact.html
Contact form with minimal client validation (no backend)
-->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Contact — Acme Co.</title>
  <style>
    body{font-family:Inter,system-ui,Segoe UI,Roboto,Arial;margin:0;padding:2rem;color:#222}
    form{max-width:560px}
    label{display:block;margin-top:.6rem}
    input,textarea{width:100%;padding:.6rem;margin-top:.25rem;border-radius:6px;border:1px solid #ddd}
    button{margin-top:.75rem;padding:.6rem 1rem;border-radius:8px}
    .error{color:#a12}
  </style>
</head>
<body>
  <h2>Contact us</h2>
  <form id="contact">
    <label>Name <input name="name" id="name" required /></label>
    <label>Email <input type="email" name="email" id="email" required /></label>
    <label>Message <textarea id="message" name="message" rows="6" required></textarea></label>
    <button type="submit">Send</button>
    <div id="status" role="status"></div>
  </form>
  <script>
    document.getElementById('contact').addEventListener('submit', function(e){
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const message = document.getElementById('message').value.trim();
      const status = document.getElementById('status');
      status.textContent = '';
      if(!name || !email || !message){ status.textContent = 'Please fill all fields.'; status.className='error'; return; }
      status.textContent = 'Thanks! This demo form does not submit — wire up a backend to finish.';
      status.className='';
    });
  </script>
</body>
</html>


<!--
File: 5_product.html
Simple product card / catalogue item
-->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Product — Acme Co.</title>
  <style>
    body{font-family:Inter,system-ui,Segoe UI,Roboto,Arial;margin:0;padding:2rem;color:#222}
    .card{max-width:420px;padding:1rem;border-radius:12px;box-shadow:0 8px 30px rgba(2,6,23,0.06)}
    .img{height:200px;border-radius:8px;background:#eef;display:block;margin-bottom:1rem}
    .price{font-weight:700;font-size:1.25rem}
    .buy{display:inline-block;margin-top:1rem;padding:.6rem 1rem;border-radius:8px;text-decoration:none;border:1px solid #0b63d1}
  </style>
</head>
<body>
  <div class="card">
    <div class="img" aria-hidden="true">Product image</div>
    <h3>Minimal Lamp</h3>
    <p>Handmade modern lamp — perfect for desks and bedside tables.</p>
    <div class="price">₹2,499</div>
    <a class="buy" href="#">Add to cart</a>
  </div>
</body>
</html>


~~~

## OUTPUT:
<img width="897" height="674" alt="Screenshot 2025-10-17 202651 - Copy" src="https://github.com/user-attachments/assets/669107df-f9df-4823-b2a9-6d737e5e0a98" />
<img width="924" height="732" alt="Screenshot 2025-10-17 202722" src="https://github.com/user-attachments/assets/4f616e8c-62b2-42e0-ad22-8d9e53b50344" />
<img width="964" height="730" alt="Screenshot 2025-10-17 202742" src="https://github.com/user-attachments/assets/e503b228-7245-4739-beaa-9165f1b3fb31" />
<img width="958" height="897" alt="Screenshot 2025-10-17 202810" src="https://github.com/user-attachments/assets/0b527f15-d571-4222-9264-162cc669cc0d" />




## RESULT:
The Project for responsive web design using Bootstrap is completed successfully.
