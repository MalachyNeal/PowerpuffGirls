
    <script>
</script>

<!-- TITLE -->
<h1 class="title">About This Website</h1>

<!-- MAIN SECTION -->
<div class="about-container">

  <!-- LEFT SIDE TEXT -->
  <div class="about-text">
    <h2>Welcome 👋</h2>
    <p>
      This travel website helps visitors explore Carlow and discover amazing places,
      attractions, and activities.
    </p>

    <h3>What you can do:</h3>
    <ul>
      <li>Browse Travel Guides</li>
      <li>Discover Popular Places</li>
      <li>Plan your itinerary</li>
      <li>Explore entertainment & shopping</li>
    </ul>

    <h3>About Me</h3>
    <p>
      This project was created as part of my course in Computing in Interactive Digital Art and Design.
    </p>

    <a href="/" class="btn">Back to Home</a>
  </div>

  <!-- RIGHT SIDE IMAGE -->
  <div class="about-image">
    <img src="/images/about/Carlow.jfif" alt="Travel Image" />
  </div>

</div>

<style>
/* TITLE CENTER */
.title {
  text-align: center;
  font-size: 32px;
  margin-bottom: 30px;
}

/* MAIN LAYOUT */
.about-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 40px;
}

/* LEFT TEXT */
.about-text {
  flex: 1;
}

.about-text p {
  margin-bottom: 10px;
  color: #444;
}

.about-text ul {
  margin: 10px 0;
}

/* RIGHT IMAGE */
.about-image {
  flex: 1;
}

.about-image img {
  width: 100%;
  border-radius: 10px;
  object-fit: cover;
}

/* BUTTON */
.btn {
  display: inline-block;
  margin-top: 20px;
  background: #2e7d32;
  color: white;
  padding: 10px 16px;
  border-radius: 6px;
  text-decoration: none;
}

/* MOBILE RESPONSIVE */
@media (max-width: 768px) {
  .about-container {
    flex-direction: column;
  }
}
</style>