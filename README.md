# newjobs1<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Multi-Section Dashboard with WhatsApp Contact</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      background-color: #e0f7fa;
      color: #000;
    }
    header {
      background-color: white;
      border: 2px solid #29b6f6;
      padding: 15px;
      margin-bottom: 30px;
      text-align: center;
      font-weight: bold;
      font-size: 24px;
      color: #0277bd;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .container {
      display: flex;
      justify-content: center;
      gap: 40px;
      margin-bottom: 50px;
      flex-wrap: wrap;
    }
    .button {
      padding: 20px 50px;
      background-color: white;
      color: #0288d1;
      border: 3px solid #03a9f4;
      cursor: pointer;
      font-size: 20px;
      border-radius: 12px;
      font-weight: bold;
      transition: background-color 0.3s ease, color 0.3s ease;
      box-shadow: 2px 2px 8px rgba(3,169,244,0.3);
      width: 160px;
      text-align: center;
    }
    .button:hover {
      background-color: #03a9f4;
      color: white;
      box-shadow: 2px 2px 12px rgba(3,169,244,0.7);
    }
    .section {
      max-width: 600px;
      margin: 0 auto 40px auto;
      padding: 20px;
      background-color: white;
      border-radius: 8px;
      border: 2px solid #29b6f6;
      box-shadow: 1px 1px 5px rgba(2,119,189,0.3);
    }
    .section h2, .section h3 {
      color: #01579b;
      margin-bottom: 15px;
      text-align: center;
    }
    label {
      font-weight: bold;
      display: block;
      margin-bottom: 8px;
      color: #01579b;
      text-align: center;
    }
    input[type="text"], input[type="email"], input[type="tel"], textarea {
      display: block;
      margin: 0 auto 20px auto;
      padding: 8px;
      font-size: 16px;
      border: 2px solid #03a9f4;
      border-radius: 6px;
      width: 250px;
      transition: border-color 0.3s ease;
      box-sizing: border-box;
    }
    input[type="text"]:focus,
    input[type="email"]:focus,
    input[type="tel"]:focus,
    textarea:focus {
      border-color: #0288d1;
      outline: none;
    }
    .back-button {
      display: block;
      margin: 0 auto;
      margin-top: 20px;
      background-color: white;
      color: #0288d1;
      border: 3px solid #03a9f4;
      cursor: pointer;
      font-size: 18px;
      border-radius: 12px;
      font-weight: bold;
      padding: 12px 50px;
      box-shadow: 2px 2px 8px rgba(3,169,244,0.3);
      transition: background-color 0.3s ease, color 0.3s ease;
      text-align: center;
      width: 200px;
      text-decoration: none;
    }
    .back-button:hover {
      background-color: #03a9f4;
      color: white;
      box-shadow: 2px 2px 12px rgba(3,169,244,0.7);
    }
  </style>
  <script>
    function showSection(sectionId) {
      document.getElementById('mainContainer').style.display = 'none';

      // Hide all sections
      const sections = document.querySelectorAll('.section');
      sections.forEach(sec => sec.style.display = 'none');

      // Show the selected section
      const selected = document.getElementById(sectionId);
      if(selected) selected.style.display = 'block';

      // Scroll to top for better UX
      window.scrollTo(0, 0);
    }

    function backToDashboard() {
      document.getElementById('mainContainer').style.display = 'flex';
      const sections = document.querySelectorAll('.section');
      sections.forEach(sec => sec.style.display = 'none');

      window.scrollTo(0, 0);
    }

    function handleSubmit(event, section) {
      event.preventDefault();
      const form = event.target;
      const name = form.name.value.trim();
      const email = form.email.value.trim();
      const phone = form.phone.value.trim();
      const message = form.message.value.trim();
      if (!name || !email || !phone || !message) {
        alert('Please fill all fields.');
        return;
      }
      const phoneNumber = '8977143043';
      const textMsg = `Name: ${name}%0AEmail: ${email}%0APhone: ${phone}%0ASection: ${section}%0AMessage: ${encodeURIComponent(message)}`;
      const url = `https://wa.me/${phoneNumber}?text=${textMsg}`;
      window.open(url, '_blank');
      form.reset();
    }
  </script>
</head>
<body>

<header>Multi-Section Dashboard</header>

<!-- Dashboard -->
<div class="container" id="mainContainer">
  <button class="button" onclick="showSection('jobSection')">Job</button>
  <button class="button" onclick="showSection('serviceSection')">Service</button>
  <button class="button" onclick="showSection('otherSection')">Other Folder</button>
</div>

<!-- Job Section -->
<div class="section" id="jobSection" style="display:none;">
  <h2>Job Section</h2>
  <form onsubmit="handleSubmit(event, 'Job')">
    <label for="name-job">Name:</label>
    <input type="text" id="name-job" name="name" required />
    <label for="email-job">Email:</label>
    <input type="email" id="email-job" name="email" required />
    <label for="phone-job">Phone:</label>
    <input type="tel" id="phone-job" name="phone" required />
    <label for="message-job">Message:</label>
    <textarea id="message-job" name="message" required></textarea>
    <button type="submit">Submit via WhatsApp</button>
  </form>
  <button class="back-button" onclick="backToDashboard()">Back to Dashboard</button>
</div>

<!-- Service Section -->
<div class="section" id="serviceSection" style="display:none;">
  <h2>Service Section</h2>
  <form onsubmit="handleSubmit(event, 'Service')">
    <label for="name-service">Name:</label>
    <input type="text" id="name-service" name="name" required />
    <label for="email-service">Email:</label>
    <input type="email" id="email-service" name="email" required />
    <label for="phone-service">Phone:</label>
    <input type="tel" id="phone-service" name="phone" required />
    <label for="message-service">Message:</label>
    <textarea id="message-service" name="message" required></textarea>
    <button type="submit">Submit via WhatsApp</button>
  </form>
  <button class="back-button" onclick="backToDashboard()">Back to Dashboard</button>
</div>

<!-- Other Folder Section -->
<div class="section" id="otherSection" style="display:none;">
  <h2>Other Folder Section</h2>
  <form onsubmit="handleSubmit(event, 'Other Folder')">
    <label for="name-other">Name:</label>
    <input type="text" id="name-other" name="name" required />
    <label for="email-other">Email:</label>
    <input type="email" id="email-other" name="email" required />
    <label for="phone-other">Phone:</label>
    <input type="tel" id="phone-other" name="phone" required />
    <label for="message-other">Message:</label>
    <textarea id="message-other" name="message" required></textarea>
    <button type="submit">Submit via WhatsApp</button>
  </form>
  <button class="back-button" onclick="backToDashboard()">Back to Dashboard</button>
</div>

</body>
</html>
