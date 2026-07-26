---
layout: home

---

## Products & Services
We specialize in professional IT consulting and advanced digital tools, including our AI-driven revenue recognition application designed to streamline automated financial tracking and compliance.

---

## Contact Us
<!-- We will replace this placeholder with a working form in the next step -->
<form id="contact-form" action="https://formspree.io/f/xykrbqje" method="POST">
  <div style="margin-bottom: 1rem;">
    <label for="name" style="display:block; margin-bottom: 0.5rem; font-weight: bold;">Name</label>
    <input type="text" id="name" name="name" required style="width: 100%; padding: 8px; box-sizing: border-box;">
  </div>

  <div style="margin-bottom: 1rem;">
    <label for="email" style="display:block; margin-bottom: 0.5rem; font-weight: bold;">Email</label>
    <input type="email" id="email" name="email" required style="width: 100%; padding: 8px; box-sizing: border-box;">
  </div>

  <div style="margin-bottom: 1rem;">
    <label for="message" style="display:block; margin-bottom: 0.5rem; font-weight: bold;">Message</label>
    <textarea id="message" name="message" rows="5" required style="width: 100%; padding: 8px; box-sizing: border-box;"></textarea>
  </div>
   <!-- Invisible Honeypot Field -->
   <input type="text" name="_gotcha" style="display:none !important" tabindex="-1" autocomplete="off">

  <button type="submit" id="submit-btn" style="padding: 10px 20px; cursor: pointer;">Send Message</button>
  <p id="form-status" style="margin-top: 1rem; font-weight: bold;"></p>
</form>

<script>
  const form = document.getElementById("contact-form");
  const status = document.getElementById("form-status");

  form.addEventListener("submit", async function(event) {
    event.preventDefault();
    const data = new FormData(event.target);
    
    status.style.color = "#333";
    status.innerHTML = "Sending...";

    try {
      const response = await fetch(event.target.action, {
        method: form.method,
        body: data,
        headers: {
          'Accept': 'application/json'
        }
      });

      if (response.ok) {
        status.style.color = "green";
        status.innerHTML = "Thank you! Your message has been sent successfully.";
        form.reset();
      } else {
        const result = await response.json();
        status.style.color = "red";
        if (Object.hasOwn(result, 'errors')) {
          status.innerHTML = result["errors"].map(error => error["message"]).join(", ");
        } else {
          status.innerHTML = "Oops! There was a problem submitting your form.";
        }
      }
    } catch (error) {
      status.style.color = "red";
      status.innerHTML = "Oops! Network error. Please try again later.";
    }
  });
</script>

---

## Blog & Insights
*Below is a collection of our latest professional updates and industry insights. Click any post to read the full article directly on LinkedIn.*
