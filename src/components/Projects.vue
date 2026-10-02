<template>
  <section id="projects" class="section projects">
    <span class="section-label">Projects</span>
    <h2>Case studies</h2>
    <p class="intro">
      Each project below is framed the way I'd walk a recruiter through it:
      the problem, what I used to solve it, my role, and the result.
    </p>

    <div class="case-list">
      <article class="case-card" v-for="p in projects" :key="p.name">
        <div class="case-head">
          <h3>{{ p.name }}</h3>
          <span class="status" :class="p.statusClass">{{ p.status }}</span>
        </div>
        <p class="summary">{{ p.summary }}</p>

        <dl class="case-grid">
          <div>
            <dt>Problem</dt>
            <dd>{{ p.problem }}</dd>
          </div>
          <div>
            <dt>My role</dt>
            <dd>{{ p.role }}</dd>
          </div>
          <div>
            <dt>Tools</dt>
            <dd>
              <span class="tool" v-for="t in p.tools" :key="t">{{ t }}</span>
            </dd>
          </div>
          <div>
            <dt>Outcome</dt>
            <dd>{{ p.outcome }}</dd>
          </div>
        </dl>

        <div class="case-links" v-if="p.links?.length">
          <a v-for="l in p.links" :key="l.label" :href="l.href" class="btn btn-ghost small">{{ l.label }}</a>
        </div>
      </article>
    </div>
  </section>
</template>

<script setup>

const projects = [
  {
    name: 'FinView',
    status: 'In progress',
    statusClass: 'wip',
    summary: 'An open-banking dashboard that gives people one view of money spread across multiple banks.',
    problem: 'People with accounts at several banks have no single place to see their total balance — they have to check each banking app separately to know where they stand.',
    role: 'Full-stack builder — designing the Vue.js frontend and building the backend/database layer that aggregates balances across connected banks.',
    tools: ['Vue.js', 'Node.js', 'REST APIs', 'Database'],
    outcome: 'A view-only aggregator (deliberately no payments or transfers) that shows a single combined balance across banks — reducing "which app do I check" friction to one screen.',
   links: ['https://finview1.netlify.app/'],
  },
  {
    name: 'ECMS — Electronic Court & Management System',
    status: 'In development',
    statusClass: 'wip',
    summary: 'A multi-page web app that digitizes legal affidavit templates so people can generate the correct declaration without visiting a document typist.',
    problem: 'Getting a legal affidavit (change of name, age declaration, address, next of kin, etc.) in Nigeria typically means finding a typist and manually adapting a paper template for each declaration type — slow and error-prone.',
    role: 'Frontend & systems engineer — built the CSS design system, consolidated JavaScript (modals, routing, carousel), and implemented a dozen-plus individual declaration form pages on a consistent layout pattern.',
    tools: ['HTML/CSS', 'JavaScript', 'Node.js (docx generation)', 'Design system / carousel UI'],
    outcome: 'A working template browser covering 12+ affidavit types with a consistent, reusable form pattern — plus generated documentation (a beginner guide and a full technical spec) so the system is handoff-ready.',
    links: [],
  },
]
</script>

<style scoped>
.intro {
  color: var(--warm-gray);
  margin-top: 0.5rem;
}

.case-list {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin-top: 2.5rem;
}

.case-card {
  background: var(--off-white);
  border: 1px solid rgba(75, 83, 32, 0.12);
  border-radius: var(--radius-lg);
  padding: 2.25rem;
  box-shadow: var(--shadow-card);
}

.case-head {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  flex-wrap: wrap;
}
.case-head h3 {
  margin: 0;
  font-size: 1.4rem;
}

.status {
  font-size: 0.75rem;
  font-weight: 600;
  padding: 0.3rem 0.8rem;
  border-radius: 999px;
  white-space: nowrap;
}
.status.wip { background: rgba(225, 173, 1, 0.18); color: #8a6a00; }
.status.done { background: rgba(75, 83, 32, 0.15); color: var(--army-green-dark); }

.summary {
  color: var(--charcoal);
  margin: 0.75rem 0 1.5rem;
}

.case-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5rem 2rem;
  margin: 0;
}

dt {
  font-size: 0.78rem;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  color: var(--burnt-orange);
  font-weight: 700;
  margin-bottom: 0.35rem;
}
dd {
  margin: 0;
  font-size: 0.95rem;
  color: var(--charcoal);
}

.tool {
  display: inline-block;
  background: var(--cream);
  border-radius: 6px;
  padding: 0.15rem 0.55rem;
  margin: 0 0.35rem 0.35rem 0;
  font-size: 0.82rem;
  color: var(--army-green-dark);
}

.case-links {
  margin-top: 1.5rem;
  display: flex;
  gap: 0.75rem;
}
.btn.small {
  padding: 0.55rem 1.1rem;
  font-size: 0.85rem;
}

@media (max-width: 700px) {
  .case-grid { grid-template-columns: 1fr; }
}
</style>
