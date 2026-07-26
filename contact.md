---
layout: page
title: Contact Us
permalink: /contact/
---

If you have any questions or would like to discuss a project, please reach out using the form below.

<form id="contact-form" action="https://formspree.io/f/YOUR_FORMSPREE_ID" method="POST" style="max-width: 500px; display: flex; flex-direction: column; gap: 15px;">
  
  <!-- Honeypot Spam Protection (Hidden from real users) -->
  <input type="text" name="_gotcha" style="display:none !important;" tabindex="-1" autocomplete="off">

  <div>
    <label for="name" style="display: block; font-weight: bold; margin-bottom: 5px;">Name</label>
    <input type="text" id="name" name="name" required style="width: 100%; padding: 8px; box-sizing: border-box;">
  </div>

  <div>
    <label for="email" style="display: block; font-weight: bold; margin-bottom: 5px;">Email</label>
    <input type="email" id="email" name="email" required style="width: 100%; padding: 8px; box-sizing: border-box;">
  </div>

  <div>
    <label for="message" style="display: block; font-weight: bold; margin-bottom: 5px;">Message</label>
    <textarea id="message" name="message" rows="5" required style="width: 100%; padding: 8px; box-sizing: border-box;"></textarea>
  </div>

  <button type="submit" style="padding: 10px 20px; cursor: pointer; max-width: 150px;">Send Message</button>
  <p id="form-status" style="display: none; margin-top: 10px; font-weight: bold;"></p>
</form>

<script>
  const form = document.getElementById("contact-form");
  const status = document.getElementById("form-status");

  form.addEventListener("submit", async function(event) {
    event.preventDefault();
    const data = new FormData(event.target);
    
    status.style.display = "block";
    status.style.color = "#555";
    status.textContent = "Sending...";

    try {
      const response = await fetch(event.action, {
        method: form.method,
        body: data,
        headers: { 'Accept': 'application/json' }
      });

      if (response.ok) {
        status.style.color = "green";
        status.textContent = "Thank you! Your message has been sent successfully.";
        form.reset();
      } else {
        const result = await response.json();
        status.style.color = "red";
        status.textContent = result.errors ? result.errors.map(e => e.message).join(", ") : "Oops! There was a problem submitting your form.";
      }
    } catch (error) {
      status.style.color = "red";
      status.textContent = "Oops! There was a network problem submitting your form.";
    }
  });
</script>
