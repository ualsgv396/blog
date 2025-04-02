---
layout: page
title: Contacte con nosotros
permalink: /contacto/
---

<h1>Contacte con nosotros</h1>

<p>Somos un equipo de apasionados de la informática, dedicados a compartir conocimientos, experiencias y soluciones innovadoras en el mundo de la tecnología. Cada miembro de nuestro equipo aporta su experiencia única en diversas áreas de la informática, trabajando juntos para ofrecer contenido de alta calidad y relevante para nuestra comunidad.</p>

<h3>👥 Rellene el formulario</h3>

<style>
  .contact-form {
    max-width: 600px;
    margin: 0 auto;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  
  .form-group {
    margin-bottom: 1.5rem;
  }
  
  .form-label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 600;
    color: #333;
  }
  
  .form-control {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-size: 1rem;
    transition: border-color 0.3s;
  }
  
  .form-control:focus {
    border-color: #4a90e2;
    outline: none;
    box-shadow: 0 0 0 3px rgba(74, 144, 226, 0.2);
  }
  
  textarea.form-control {
    min-height: 120px;
    resize: vertical;
  }
  
  .submit-btn {
    width: 100%;
    height: 45px;
    background-color #cccccc;
    border: none;
    border-radius: 40px;
    cursor: pointer;
    font-size: 1em;
    color: #000
    font-weight: 500;

  }
  
  .submit-btn:hover {
    background-color:rgb(224, 220, 220);
  }
  
  .submit-btn:disabled {
    background-color: #cccccc;
    cursor: not-allowed;
  }
  
  .alert {
    padding: 1rem;
    border-radius: 4px;
    margin-bottom: 1rem;
    display: none;
  }
  
  .alert-success {
    background-color: #d4edda;
    color: #155724;
    border: 1px solid #c3e6cb;
  }
  
  .alert-error {
    background-color: #f8d7da;
    color: #721c24;
    border: 1px solid #f5c6cb;
  }
  
  .error-message {
    color: #dc3545;
    font-size: 0.875rem;
    margin-top: 0.25rem;
    display: none;
  }
  
  .form-control.error {
    border-color: #dc3545;
  }
</style>

<div class="contact-form">
  <form id="contact-form">
    <div class="form-group">
      <label for="name" class="form-label">Nombre completo:</label>
      <input type="text" id="name" name="name" class="form-control" required>
      <div id="name-error" class="error-message">Por favor ingrese su nombre</div>
    </div>
    
    <div class="form-group">
      <label for="email" class="form-label">Correo electrónico:</label>
      <input type="email" id="email" name="email" class="form-control" required>
      <div id="email-error" class="error-message">Por favor ingrese un email válido</div>
    </div>
    
    <div class="form-group">
      <label for="subject" class="form-label">Asunto:</label>
      <input type="text" id="subject" name="subject" class="form-control" required>
      <div id="subject-error" class="error-message">Por favor ingrese un asunto</div>
    </div>
    
    <div class="form-group">
      <label for="message" class="form-label">Mensaje:</label>
      <textarea id="message" name="message" rows="4" class="form-control" required></textarea>
      <div id="message-error" class="error-message">Por favor ingrese su mensaje</div>
    </div>
    
    <button type="submit" class="submit-btn" id="submit-btn">Enviar mensaje</button>
  </form>

  <div id="success-message" class="alert alert-success">
    <strong>¡Mensaje enviado con éxito!</strong> Nos pondremos en contacto contigo pronto.
  </div>

  <div id="error-message" class="alert alert-error">
    <strong>Error al enviar el mensaje.</strong> Por favor intente nuevamente más tarde.
  </div>
</div>

<!-- Incluye EmailJS SDK -->
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
<script>
  // Inicializa EmailJS
  (function() {
    emailjs.init('Cu0AIZE2gxbmZYEM1'); // Reemplaza con tu User ID
  })();

  // Validación en tiempo real
  document.querySelectorAll('.form-control').forEach(input => {
    input.addEventListener('blur', function() {
      validateField(this);
    });
  });

  function validateField(field) {
    const errorElement = document.getElementById(`${field.id}-error`);
    
    if (field.required && !field.value.trim()) {
      field.classList.add('error');
      errorElement.style.display = 'block';
      return false;
    }
    
    if (field.type === 'email' && !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(field.value)) {
      field.classList.add('error');
      errorElement.textContent = 'Por favor ingrese un email válido';
      errorElement.style.display = 'block';
      return false;
    }
    
    field.classList.remove('error');
    errorElement.style.display = 'none';
    return true;
  }

  // Maneja el envío del formulario
  document.getElementById('contact-form').addEventListener('submit', function(event) {
    event.preventDefault();
    
    // Validar todos los campos
    let isValid = true;
    document.querySelectorAll('.form-control').forEach(field => {
      if (!validateField(field)) {
        isValid = false;
      }
    });
    
    if (!isValid) return;
    
    // Deshabilitar botón durante el envío
    const submitBtn = document.getElementById('submit-btn');
    submitBtn.disabled = true;
    submitBtn.textContent = 'Enviando...';
    
    // Ocultar mensajes previos
    document.getElementById('success-message').style.display = 'none';
    document.getElementById('error-message').style.display = 'none';
    
    // Enviar formulario
    emailjs.sendForm('service_3vrmeua', 'template_l97divq', this)
      .then(function() {
        document.getElementById('success-message').style.display = 'block';
        document.getElementById('contact-form').reset();
        
        setTimeout(function() {
          document.getElementById('success-message').style.display = 'none';
        }, 5000);
      }, function(error) {
        console.error('Error:', error);
        document.getElementById('error-message').style.display = 'block';
      })
      .finally(function() {
        submitBtn.disabled = false;
        submitBtn.textContent = 'Enviar mensaje';
      });
  });
</script>