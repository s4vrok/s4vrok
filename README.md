# S4vrok

👋 Cześć! Jestem S4vrok, developer HTML/CSS/JS/TS z pasją do tworzenia animacji i interaktywnych doświadczeń webowych. Uwielbiam zamieniać statyczne strony w dynamiczne i angażujące aplikacje.

<div id="header-animation" style="background: linear-gradient(to right, #4facfe 0%, #00f2fe 100%); color: white; padding: 20px; border-radius: 10px;">
  <h1>s4vrok</h1>
  <p id="typed-text"></p>
</div>

## Umiejętności

<p>
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white" alt="HTML5" width="32" class="skill-icon">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white" alt="CSS3" width="32" class="skill-icon">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript" width="32" class="skill-icon">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" width="32" class="skill-icon">
  <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React" width="32" class="skill-icon">
  <img src="https://img.shields.io/badge/GSAP-88CE02?style=flat-square&logo=greensock&logoColor=black" alt="GSAP" width="32" class="skill-icon">
</p>

## Statystyki GitHub

<div id="github-stats">
  <p>Commits: <span id="commits">0</span></p>
  <p>Repositories: <span id="repos">0</span></p>
  <p>Stars: <span id="stars">0</span></p>
</div>

## Kontakt

*   Email: [kontakt@bogotavibe.pl]
*   Discord: [s4vrok]

## Współpraca

Jestem otwarty na współpracę przy ciekawych projektach! Skontaktuj się ze mną, jeśli masz jakieś pomysły.

<script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/countup.js/2.0.8/countUp.min.js"></script>
<script>
  // Animacja nagłówka
  const header = document.getElementById('header-animation');
  header.addEventListener('mousemove', (e) => {
    const x = e.clientX / header.offsetWidth;
    const y = e.clientY / header.offsetHeight;
    header.style.backgroundPosition = `${x * 100}% ${y * 100}%`;
  });

  // Efekt pisania
  var typed = new Typed('#typed-text', {
    strings: ["Developer HTML/CSS/JS/TS", "Pasjonat animacji", "Tworzę interaktywne strony"],
    typeSpeed: 50,
    backSpeed: 25,
    loop: true
  });

  // Statystyki GitHub (wymaga pobrania danych z API)
  async function fetchGitHubStats() {
    const username = 's4vrok';
    const apiUrl = `https://api.github.com/users/${username}`;

    try {
      const response = await fetch(apiUrl);
      const data = await response.json();

      const commitsElement = document.getElementById('commits');
      const reposElement = document.getElementById('repos');
      const starsElement = document.getElementById('stars');

      // Symulacja danych (zastąp prawdziwymi danymi z API)
      const commitsCount = 1234;
      const reposCount = data.public_repos;
      const starsCount = 567;

      // Animacja liczb
      const commits = new CountUp('commits', 0, commitsCount, 0, 2.5, { useEasing: true, useGrouping: true });
      const repos = new CountUp('repos', 0, reposCount, 0, 2.5, { useEasing: true, useGrouping: true });
      const stars = new CountUp('stars', 0, starsCount, 0, 2.5, { useEasing: true, useGrouping: true });

      commits.start();
      repos.start();
      stars.start();

    } catch (error) {
      console.error('Błąd pobierania statystyk GitHub:', error);
    }
  }

  fetchGitHubStats();
</script>

<style>
  .skill-icon {
    transition: transform 0.3s ease-in-out;
  }
  .skill-icon:hover {
    transform: scale(1.2);
  }
</style>
