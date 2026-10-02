<template>
  <section id="contact" class="section contact">
    <div class="blob blob-c"></div>

    <div class="contact-inner">
      <div>
        <span class="section-label">Contact</span>
        <h2>Let's work together</h2>
        <p>
          Have a role, a project, or a question? I'd like to hear about it.
        </p>

        <ul class="contact-list">
          <li>
            <span class="icon">✉</span>
            <a href="mailto:rukynmamm05@gmail.com">rukynmamm05@gmail.com</a>
          </li>
          <li>
            <span class="icon">🐙</span>
            <a href="https://github.com/Ruks-dev" target="_blank" rel="noopener">github.com/Ruks-dev</a>
          </li>
          <li>
            <span class="icon">📍</span>
            <span>Abuja, Nigeria</span>
          </li>
        </ul>
      </div>

      <form class="contact-form" @submit.prevent="handleSubmit">
        <label>
          Name
          <input type="text" v-model="form.name" required />
        </label>
        <label>
          Email
          <input type="email" v-model="form.email" required />
        </label>
        <label>
          Message
          <textarea v-model="form.message" rows="4" required></textarea>
        </label>
        <button type="submit" class="btn btn-primary">Send message</button>
        <p v-if="sent" class="sent-note">Thanks — I'll get back to you soon.</p>
      </form>
    </div>
  </section>
</template>

<script setup>

import { reactive, ref } from 'vue'

const form = reactive({ name: '', email: '', message: '' })
const sent = ref(false)

function handleSubmit() {

  sent.value = true
}
</script>

<style scoped>
.contact {
  position: relative;
  overflow: hidden;
}

.blob-c {
  width: 320px;
  height: 320px;
  bottom: -140px;
  left: -100px;
  background: radial-gradient(circle at 40% 40%, var(--sage), var(--army-green) 80%);
  opacity: 0.18;
}

.contact-inner {
  position: relative;
  z-index: 1;
  display: grid;
  grid-template-columns: 1fr 1.1fr;
  gap: 3rem;
  align-items: start;
}

.contact-list {
  list-style: none;
  padding: 0;
  margin: 2rem 0 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.contact-list li {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}
.icon {
  width: 34px;
  height: 34px;
  border-radius: 50%;
  background: var(--cream);
  color: var(--army-green-dark);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-size: 0.95rem;
}

.contact-form {
  background: var(--off-white);
  border: 1px solid rgba(75, 83, 32, 0.12);
  border-radius: var(--radius-lg);
  padding: 2rem;
  display: flex;
  flex-direction: column;
  gap: 1.1rem;
}
label {
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--charcoal);
}
input, textarea {
  font-family: var(--font-body);
  padding: 0.7rem 0.9rem;
  border-radius: 10px;
  border: 1.5px solid var(--sand);
  background: var(--off-white);
  font-size: 0.95rem;
  resize: vertical;
}
input:focus, textarea:focus {
  outline: 2px solid var(--army-green);
  outline-offset: 1px;
}

.sent-note {
  color: var(--army-green-dark);
  font-size: 0.9rem;
  margin: 0;
}

@media (max-width: 800px) {
  .contact-inner { grid-template-columns: 1fr; }
}
</style>
