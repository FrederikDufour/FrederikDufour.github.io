---
layout: default
title: Home
---

<style>
.page-content:has(.academic-home) { padding-top: 0.75rem; }
.academic-home { display: grid; gap: 1.5rem; }
.academic-home .panel[id] { scroll-margin-top: 6rem; }
@media (max-width: 600px) { .academic-home .panel[id] { scroll-margin-top: 9rem; } }
.academic-home .panel { background: #f1f6fa; border: 1px solid #d4dfe7; padding: clamp(1.25rem, 4vw, 2.5rem); min-width: 0; }
.academic-home > .panel, .academic-home .mast { border-radius: 12px; box-shadow: 0 4px 16px rgba(31, 57, 77, .09); }
.academic-home .mast { --card-pad: clamp(1.25rem, 4vw, 2.5rem); border: 1px solid #d4dfe7; overflow: hidden; }
.academic-home .photo-band { height: clamp(125px, 18vw, 220px); overflow: hidden; }
.academic-home .landscape { display: block; width: 100%; height: 100%; object-fit: cover; object-position: center 65%; }
.academic-home .resume-link { display: inline-block; padding: .4rem .85rem; border: 1px solid #a9becd; border-radius: .3rem; background: white; color: #24475d; font-weight: 600; }
.academic-home .resume-link:hover, .academic-home .resume-link:focus-visible { background: #e0edf5; }
.academic-home .mast .panel { border: 0; padding: var(--card-pad); background: white; }
.academic-home .mast .profile-column { position: relative; margin-top: calc(-32px - var(--card-pad)); }
.academic-home .mast .profile-photo { box-sizing: border-box; border: 3px solid white; border-radius: 50%; }
.academic-home .home-grid { gap: clamp(1.5rem, 4vw, 3rem); }
.academic-home .profile-photo { max-width: 100%; }
.academic-home .contact-icon { width: 1em; height: 1em; vertical-align: middle; }
.academic-home .panel h1 { font: 2rem/1.2 Georgia, serif; color: #263f50; }
.academic-home .panel > h2 { margin-top: 1.5rem; }
.academic-home video { max-width: 100%; }
.academic-home .teaching-role strong { color: #294f65; font-size: 1.25rem; }
.academic-home .course-with-project + .teaching-row { border-top: 1px solid #d4dfe7; }
.academic-home .course-with-project > .teaching-row { border-bottom: 0; }
.academic-home .wip-list > .paper { border: 0; }
.academic-home .wip-list > .paper + .paper { border-top: 2px solid #8295a1; }
@media (max-width: 700px) { .academic-home .home-grid { grid-template-columns: 1fr; } }
</style>

<script type="module">
  const photo = document.querySelector(".academic-home .landscape");
  const motion = window.matchMedia("(prefers-reduced-motion: reduce)");
  let pending = false;

  function updatePhoto() {
    pending = false;
    const spareHeight = Math.max(0, photo.clientWidth * 0.75 - photo.clientHeight);
    const displacement = Math.min(window.scrollY * 0.34, spareHeight * 0.65, 105);
    photo.style.objectPosition = motion.matches
      ? "center 65%"
      : "center calc(65% + " + displacement + "px)";
  }

  function scheduleUpdate() {
    if (!pending) {
      pending = true;
      requestAnimationFrame(updatePhoto);
    }
  }

  window.addEventListener("scroll", scheduleUpdate, { passive: true });
  motion.addEventListener("change", scheduleUpdate);
  updatePhoto();
</script>

<div class="academic-home">
<div class="mast">
<div class="photo-band">
  <img class="landscape" src="{{ '/assets/eoliennes.jpg' | relative_url }}" width="4000" height="3000" alt="Wind turbines above a wooded lakeshore">
</div>
<div class="panel home-grid">
  <aside class="profile-column">
  <img class="profile-photo"
       src="{{ '/assets/portrait-outdoors.jpg' | relative_url }}"
       alt="Portrait of Frédérik Dufour">

  <ul class="contact-links">
    <li>
      <a href="mailto:frederik.dufour@mail.utoronto.ca">
        <img class="contact-icon" src="{{ '/assets/envelope.svg' | relative_url }}" alt="">
        Email
      </a>
    </li>
    <li>
      <a href="https://www.linkedin.com/in/fr%C3%A9d%C3%A9rik-dufour-5b2489186/" target="_blank" rel="noopener">
        <img class="contact-icon" src="{{ '/assets/linkedin.svg' | relative_url }}" alt="">
        LinkedIn
      </a>
    </li>
    <li>
      <a href="https://github.com/FrederikDufour" target="_blank" rel="noopener">
        <img class="contact-icon" src="{{ '/assets/github.svg' | relative_url }}" alt="">
        GitHub
      </a>
    </li>
    <li><img class="contact-icon" src="{{ '/assets/geo-alt-fill.svg' | relative_url }}" alt="">Toronto, Canada</li>
  </ul>
  </aside>
  <section class="introduction">
    <h1>Biography</h1>

    <p>I am a doctoral student at the University of Toronto. My research focuses on applied topics in energy economics, industrial organization, and financial economics, with a particular focus on energy markets and electricity distribution.</p>
    <p>I am excited about using research to address real-world issues faced by decision-makers. In our <a href="https://www.oeb.ca/sites/default/files/Review%20of%20Total%20Cost%20Benchmarking%20Methodology%20for%20Electricity%20Distributors.pdf" target="_blank" rel="noopener">2024 report for the Ontario Energy Board</a>, my coauthors and I review how the Board benchmarks costs across electricity distributors and compare its approach with methods used by regulators elsewhere. My <a href="#research">research</a> and <a href="#teaching">teaching</a> experience are available below.</p>

    <h2>Education</h2>
    <ul>
    <li><strong>Ph.D. in Economics</strong>, University of Toronto
      (expected 2027)</li>
    <li><strong>M.Sc. in Economics</strong>, Université de Montréal
      (2021)</li>
    <li><strong>B.Sc. in Economics (Honours)</strong>, Université de Montréal
      (2020)</li>
    </ul>
    <a class="resume-link" href="{{ '/cv.pdf' | relative_url }}" target="_blank" rel="noopener">View résumé (PDF)</a>
    </section>
</div>
</div>

<div class="panel research-content" id="research">
  <h1>Research</h1>
  <h2>Reports</h2>
  <div class="paper-list">
    <article class="paper">
      <h2>Review of Total Cost Benchmarking Methodology for Electricity Distributors</h2>
      <p class="paper-meta">With Adonis Yatchew et al. (2024)</p>
      <p>Produced through a collaboration with the Ontario Energy Board and Climate Positive Energy.</p>
      <p><a href="https://www.oeb.ca/sites/default/files/Review%20of%20Total%20Cost%20Benchmarking%20Methodology%20for%20Electricity%20Distributors.pdf" target="_blank" rel="noopener">Available on the OEB website</a></p>
      <details>
        <summary><strong>Summary</strong></summary>
        <p>This report reviews the Ontario Energy Board (OEB) total cost benchmarking methodology
for electricity distributors. The work is a collaboration between the University of Toronto’s
Economics Department and the OEB; and is funded by the OEB and Climate Positive Energy at
the University of Toronto. The project addresses methodological issues, particularly the
statistical benchmarking approach used by the OEB, explores alternative approaches and
benchmarking practices in other jurisdictions, conducts an extensive literature review and
identifies observations and considerations for modifications. A separate and closely related
report conducts statistical analyses of distributor cost benchmarking.
The vision of the OEB is “To be a trusted regulator who is recognized for enabling Ontario’s
growing economy and improving the quality of life for the people of this province who deserve
safe, reliable and affordable energy.” Its stated mission is “To deliver public value through
prudent regulation and independent adjudicative decision-making which contributes to
Ontario’s economic, social and environmental development.” Within this context, the OEB has
regulated electricity distribution utilities for a quarter of a century. The OEB turned to incentive
regulation early and developed a systematic framework for regulating numerous utilities,
promoted energy conservation, encouraged efficiency gains through mergers and acquisitions,
held major stakeholder consolidations, maintained an ‘open data’ process, and most
importantly, ensured that ‘the lights stayed on’. The OEB’s use of data-based approaches as
tools for informing the regulation of a diverse and disparate set of utilities is at the leading edge,
globally.
The landscape of electricity industries is being transformed as we move into an energy
transition driven by decarbonization, digitization, and decentralization. Arguably, electricity
industries are also experiencing a degree of democratization as small-scale alternatives compete
with conventional systems. Electricity distribution companies are evolving from distributing
electricity and providing energy services, to actively managing bi-directional energy flows,
integrating distributed energy resources (DERs), and adapting to changes in consumption
paterns. Their activities include managing the growing adoption of electric vehicles (EVs), the
electrification of heating, and incorporation of new digital and smart grid technologies which
require significant upgrades to infrastructure and operations. As we move further into the
energy transition, one of the explicitly stated guiding lights should be promoting and
incentivizing innovation. Electric utilities tend to be risk-averse, but incremental technological
change and game-changing breakthroughs inevitably involve projects that fail and other
projects that succeed. Promoting change requires support from the Government and a
willingness and incentives for distributors to take risks.</p>
      </details>
    </article>
  </div>
  <h2>Work-in-Progress</h2>
  <div class="paper-list wip-list">
    <article class="paper">
      <h2>Electricity Distribution in the Energy Transition:
Revisiting Productivity Growth in Ontario</h2>
      <p class="paper-meta">With Michael Scafe and Adonis Yatchew</p>
      <details>
        <summary><strong>Abstract</strong></summary>
          <p>With distribution accounting for a substantial share of electricity bills, understanding the sources of productivity growth is important for containing costs and sustaining consumer support for grid investment during the energy transition. This paper examines productivity growth among Ontario electricity distributors over 2013–2022 using a translog cost function estimated by feasible generalized least squares, complemented by Törnqvist productivity indices, semiparametric models, and frontier methods. Our main estimates of annual productivity growth range from −0.2% to 0.2%, representing an improvement of approximately one percentage point relative to the preceding decade. The results suggest that accounting for electric vehicle charging infrastructure and asset age is important for measuring distributor productivity. Despite numerous mergers during the sample period, gains in scale efficiency appear unlikely to explain much of the improvement in productivity growth. Distributor rankings also exhibit persistence over time.</p>
      </details>
    </article>
    <article class="paper">
      <h2>Electricity Futures and Time-Varying Risk Premia: Evidence from Alberta</h2>
      <p class="paper-meta">With Derek Olmstead and Adonis Yatchew</p>
    </article>
    <article class="paper">
      <h2>Investment Timing Under Regulatory Cycles</h2>
    </article>
    <article class="paper">
      <h2>Power Outages and Household Consumption - Evidence from California</h2>
      <details>
        <summary><strong>Abstract</strong></summary>
          <p>Leveraging Nighttime Lights (NTL) satellite data and the unique wildfire-related preemptive power shutoffs of Pacific Gas and Electric (PG&E) of October 2019 in California, I study the impact of prolonged electricity outages on household consumption. Recent improvements in NTL data provide tools for a novel assessment of changes in household choices during and after extended outages at a granular level. I find that, during the event, the volume sold of essential emergency items, notably flashlights and bottled water, surged while other non-perishable and refrigerated foods' sales remained largely stable, with sales across most categories reverting to normal levels a month later. Evidence suggests a largely homogeneous impact among zip codes with different levels of outage intensity. However, some groups, such as elderly individuals, experienced higher outage intensities and different consumer responses to the event. Supplemental analysis suggests potential stockouts for flashlights and bottled water items, while no evidence of price gouging was found.</p>
      </details>
    </article>
  </div>
  
</div>

<div class="panel teaching-content" id="teaching">
  <h1>Teaching</h1>
  
  <p class="teaching-role"><strong>Teaching Assistant</strong> at the University of Toronto</p>
  <div class="teaching-list" role="list">
    <div class="course-with-project" role="listitem">
      <div class="teaching-row">
        <span><strong>ECO1960</strong>: Energy and Regulation</span>
        <span class="teaching-year"> 2024 - 2026</span>
      </div>
  <section>
  <h3>Data Visualization</h3>
  <p>Electric vehicles per capita in Toronto, 2020–2025 (<a href="https://github.com/FrederikDufour/ECO414_DataVisualizationTutorial" target="_blank" rel="noopener">code</a>)</p>
  <video poster="{{ '/assets/ev-first00001.jpg' | relative_url }}" preload="none" controls style="width: 100%;">
    <source src="{{ '/assets/EV_Adoption_Toronto_2020-2025.mp4' | relative_url }}" type="video/mp4">
  </video>
  <h3>Sankey diagrams</h3>
  <p>Helped students produce energy and carbon Sankey diagrams for Canada and its provinces. Read from left to right, these diagrams are a great way to visualize the energy flows of an economy. Explore selected student work:
  <a href="https://dev-sankey.economics.utoronto.ca/?page_id=78" target="_blank" rel="noopener">Energy diagram</a> ·
  <a href="https://dev-sankey.economics.utoronto.ca/?page_id=76" target="_blank" rel="noopener">Carbon diagram</a>.
</p>
  </section>
    </div>
    <div class="teaching-row" role="listitem">
      <span><strong>ECO313</strong>: Environmental Economics and Policies</span>
      <span class="teaching-year"> 2026</span>
    </div>
    <div class="teaching-row" role="listitem">
      <span><strong>ECO314</strong>: Energy and the Environment</span>
      <span class="teaching-year"> 2025</span>
    </div>
    <div class="teaching-row" role="listitem">
      <span><strong>ECO475</strong>: Applied Econometrics II</span>
      <span class="teaching-year"> 2023</span>
    </div>
    <div class="teaching-row" role="listitem">
      <span><strong>ECO333</strong>: Urban Economics</span>
      <span class="teaching-year"> 2023</span>
    </div>
    <div class="teaching-row" role="listitem">
      <span><strong>ECO316</strong>: Applied Game Theory</span>
      <span class="teaching-year"> 2022</span>
    </div>
    <div class="teaching-row" role="listitem">
      <span><strong>ECO502</strong>: Software TA (tutorials and general help for ECO courses)</span>
      <span class="teaching-year"> 2022 - 2026</span>
    </div>
    <div class="teaching-row" role="listitem">
      <span><strong>Other courses</strong>: ECO101, ECO102, ECO220</span>
      <span class="teaching-year"> 2021 - 2026</span>
    </div>
  </div>
</div>
<p><a class="resume-link" href="#top">Home ↑</a></p>
</div>
