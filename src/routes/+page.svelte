<script>
  import technologies from '$lib/data/tech.json';
  import projects from '$lib/data/projects.json';
  import socials from '$lib/data/socials.json';
  import education from '$lib/data/education.json';
</script>

<main class="max-w-4xl mx-auto px-8 py-16 font-sans bg-[var(--gruv-bg)] text-[var(--gruv-fg)] rounded-lg shadow-lg pt-20 scroll-smooth mt-12">

  <header class="mt-3 mb-12 text-center">
    <h1 class="text-6xl font-extrabold mb-4 tracking-tight" style="color: var(--gruv-subject)">
      Alexander Meade
    </h1>
    <p class="text-xl max-w-2xl mx-auto leading-relaxed">
      Computer Science & Mathematics student with a passion for full-stack development, programming languages, and creating/maintaing software solutions.
    </p>
  </header>

  <!-- Education Section -->
  <section id="education" class="mt-16 max-w-4xl mx-auto px-6">
    <h2 class="text-3xl font-bold mb-8 text-[var(--gruv-highlight)] border-b-4 border-[var(--gruv-highlight)] pb-2">
      Education
    </h2>

    <div class="space-y-10">
      {#each education as school}
        <div>
          <h3 class="text-2xl font-semibold text-[var(--gruv-subject)]">{school.institution}</h3>
          <p class="italic text-sm text-[var(--gruv-fg)] mb-1">{school.degree} {school.majors.length ? `- ${school.majors.join(", ")}` : ""}</p>
          <p class="text-xs text-[var(--gruv-fg)] mb-3">{school.dates}</p>
          <ul class="list-disc list-inside space-y-1 text-[var(--gruv-fg)] marker:text-[var(--gruv-highlight)]">
            {#each school.details as detail}
              <li style = "color:var(--gruv-fg)">{detail}</li>
            {/each}
          </ul>
        </div>
      {/each}
    </div>
  </section>

  <!-- Projects Section -->
  <section id="projects" class="mt-16 max-w-4xl mx-auto px-6">
    <h2 class="text-3xl font-bold mb-8 text-[var(--gruv-highlight)] border-b-4 border-[var(--gruv-highlight)] pb-2">
      Projects
    </h2>

    <div class="space-y-10">
        {#each projects as project}
          <div class="mb-6">
            <div class="flex justify-between items-center">
              <h3 class="text-2xl font-semibold text-[var(--gruv-subject)]">
                <a href={project.link} target="_blank" class="hover:underline">{project.title}</a>
              </h3>
              {#if project.isPublic}
                <span class="text-base font-semibold" style = "color: var(--gruv-red);">(PUBLIC)</span>
              {/if}
            </div>
            <p class="text-[var(--gruv-fg)] mt-1">{project.description}</p>
          </div>
        {/each}    
    </div>
  </section>

  <!-- Technologies Section -->
  <section id="technologies" class="mt-16 max-w-4xl mx-auto px-6">
    <h2 class="text-3xl font-bold mb-8 text-[var(--gruv-highlight)] border-b-4 border-[var(--gruv-highlight)] pb-2">
      Technologies I Use
    </h2>

    <p class="mb-6 max-w-3xl text-lg mx-auto text-[var(--gruv-fg)]">
      Throughout my projects, I frequently use the following languages, frameworks, and tools to build robust, efficient, and scalable software:
    </p>

    <div class="flex flex-wrap gap-10 justify-center">
      {#each technologies as tech}
        <div class="flex flex-col items-center w-24 space-y-2">
          <img src={tech.icon} alt={tech.name} class="w-16 h-16 shadow-lg rounded opacity-70" />
          <span class="text-[var(--gruv-fg)] font-semibold text-center">{tech.name}</span>
        </div>
      {/each}
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="mt-16 max-w-4xl mx-auto px-6">
    <h2 class="text-3xl font-bold mb-8 text-[var(--gruv-highlight)] border-b-4 border-[var(--gruv-highlight)] pb-2">
      Contact me
    </h2>

    <!-- Email Form connected to Formspree -->
    <form 
      class="max-w-xl mx-auto space-y-6 mb-12" 
      action="https://formspree.io/f/xzzvzaeo" 
      method="POST"
    >
      <div>
        <label for="name" class="block text-[var(--gruv-fg)] font-semibold mb-1">Name</label>
        <input id="name" name="name" type="text" required class="w-full rounded border border-gray-400 px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[var(--gruv-highlight)]" />
      </div>

      <div>
        <label for="email" class="block text-[var(--gruv-fg)] font-semibold mb-1">Email</label>
        <input id="email" name="email" type="email" required class="w-full rounded border border-gray-400 px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[var(--gruv-highlight)]" />
      </div>

      <div>
        <label for="subject" class="block text-[var(--gruv-fg)] font-semibold mb-1">Subject</label>
        <input id="subject" name="subject" type="text" required class="w-full rounded border border-gray-400 px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[var(--gruv-highlight)]" />
      </div>

      <div>
        <label for="message" class="block text-[var(--gruv-fg)] font-semibold mb-1">Message</label>
        <textarea id="message" name="message" rows="5" required class="w-full rounded border border-gray-400 px-3 py-2 resize-y focus:outline-none focus:ring-2 focus:ring-[var(--gruv-highlight)]"></textarea>
      </div>

      <button type="submit" class="bg-[var(--gruv-highlight)] text-[var(--gruv-bg)] font-semibold px-6 py-3 rounded hover:bg-[var(--gruv-subject)] transition-colors duration-300 mx-auto block">
        Send Message
      </button>
    </form>

    <ul class="flex space-x-10 text-xl text-[var(--gruv-subject)] justify-center">
      {#each socials as social}
        <li>
          <a href={social.url} target="_blank" class="hover:underline hover:text-[var(--gruv-highlight)] transition-colors duration-300">
            {social.name}
          </a>
        </li>
      {/each}
    </ul>

    <p class="mt-8 max-w-xl mx-auto text-center text-sm text-[var(--gruv-fg)]">
      Feel free to reach out via any of the platforms above. I’m always open to new opportunities, collaborations, and interesting projects!
    </p>
  </section>

</main>

