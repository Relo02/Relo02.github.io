---
# Leave the homepage title empty to use the site title
title: ''
date: 2026-06-25
type: landing

design:
  # Default section spacing
  spacing: '6rem'

sections:
  # ──────────────────────────────────────────────────────────────────────────
  # HERO — full-screen VLA humanoid demo video
  # Drop your clip at static/videos/vla-humanoid-demo.mp4 (poster: vla-humanoid-poster.jpg)
  # ──────────────────────────────────────────────────────────────────────────
  - block: markdown
    content:
      title: ''
      text: |-
        <section class="lo-hero">
          <video class="lo-hero__video" autoplay muted loop playsinline preload="auto" poster="/videos/vla-humanoid-poster.jpg">
            <source src="/videos/vla-humanoid-demo.mp4" type="video/mp4" />
          </video>
          <div class="lo-hero__grid"></div>
          <div class="lo-hero__overlay"></div>

          <div class="lo-hero__content">
            <p class="lo-hero__eyebrow">PHYSICAL&nbsp;AI&nbsp;·&nbsp;VISION–LANGUAGE–ACTION</p>
            <h1 class="lo-hero__title">
              Teaching humanoids to <span class="lo-grad">learn skills</span><br/>
              and <span class="lo-grad">choose</span> the right one.
            </h1>
            <p class="lo-hero__sub">
              I'm <strong>Lorenzo Ortolani</strong> — roboticist, co-founder &amp; CTO of
              <a href="#" class="lo-link">TalOS&nbsp;Robotics&nbsp;AI</a>. I build VLA policies
              that let a single robot acquire a library of skills and generalize across
              diverse industrial tasks.
            </p>
            <div class="lo-hero__cta">
              <a class="lo-btn lo-btn--solid" href="/uploads/resume.pdf">Download CV</a>
              <a class="lo-btn lo-btn--ghost" href="https://arxiv.org/abs/2606.14763" target="_blank" rel="noopener">Read the Paper</a>
              <a class="lo-btn lo-btn--ghost" href="https://github.com/Relo02" target="_blank" rel="noopener">GitHub</a>
            </div>
          </div>

          <a href="#mission" class="lo-hero__scroll" aria-label="Scroll down">
            <span></span>
          </a>
        </section>

        <style>
        .lo-hero{
          position:relative; left:50%; transform:translateX(-50%);
          width:100vw; min-height:92vh; display:flex; align-items:center;
          overflow:hidden; border-radius:0; isolation:isolate;
          background:#05060a;
        }
        /* Animated gradient fallback — shows if the video file isn't there yet */
        .lo-hero::before{
          content:""; position:absolute; inset:0; z-index:0;
          background:linear-gradient(120deg,#0a0f1f,#10193a,#0b2a3a,#1a0f2e,#0a0f1f);
          background-size:300% 300%; animation:loGrad 18s ease infinite;
        }
        .lo-hero__video{
          position:absolute; inset:0; width:100%; height:100%;
          object-fit:cover; z-index:1; opacity:.55;
        }
        .lo-hero__grid{
          position:absolute; inset:0; z-index:2; opacity:.25;
          background-image:linear-gradient(rgba(120,180,255,.18) 1px,transparent 1px),
            linear-gradient(90deg,rgba(120,180,255,.18) 1px,transparent 1px);
          background-size:48px 48px;
          mask-image:radial-gradient(circle at 50% 40%,#000 0%,transparent 75%);
          -webkit-mask-image:radial-gradient(circle at 50% 40%,#000 0%,transparent 75%);
        }
        .lo-hero__overlay{
          position:absolute; inset:0; z-index:3;
          background:radial-gradient(ellipse at 50% 60%,transparent 0%,rgba(5,6,10,.55) 70%,rgba(5,6,10,.92) 100%);
        }
        .lo-hero__content{
          position:relative; z-index:4; max-width:64rem; margin:0 auto;
          padding:7rem 1.5rem 6rem; text-align:center; color:#eaf0ff;
        }
        .lo-hero__eyebrow{
          letter-spacing:.32em; font-size:.78rem; font-weight:600;
          color:#8fb6ff; margin-bottom:1.4rem; opacity:0;
          animation:loUp .8s .1s ease forwards;
        }
        .lo-hero__title{
          font-size:clamp(2.2rem,6vw,4.6rem); line-height:1.05; font-weight:800;
          letter-spacing:-.02em; margin:0 0 1.3rem; color:#fff;
          opacity:0; animation:loUp .9s .25s ease forwards;
        }
        .lo-grad{
          background:linear-gradient(90deg,#5eead4,#60a5fa,#a78bfa,#5eead4);
          background-size:200% auto; -webkit-background-clip:text; background-clip:text;
          color:transparent; animation:loShine 6s linear infinite;
        }
        .lo-hero__sub{
          font-size:clamp(1rem,2.2vw,1.3rem); line-height:1.6; max-width:42rem;
          margin:0 auto 2.4rem; color:#b9c4e0;
          opacity:0; animation:loUp 1s .45s ease forwards;
        }
        .lo-hero__sub strong{color:#fff;}
        .lo-link{color:#7dd3fc; text-decoration:none; border-bottom:1px solid rgba(125,211,252,.4);}
        .lo-hero__cta{display:flex; gap:.9rem; justify-content:center; flex-wrap:wrap;
          opacity:0; animation:loUp 1s .6s ease forwards;}
        .lo-btn{
          display:inline-flex; align-items:center; padding:.85rem 1.6rem;
          border-radius:999px; font-weight:600; font-size:.98rem; text-decoration:none;
          transition:transform .2s ease, box-shadow .2s ease, background .2s ease;
        }
        .lo-btn--solid{
          color:#06121f;
          background:linear-gradient(90deg,#5eead4,#60a5fa);
          box-shadow:0 8px 30px rgba(96,165,250,.35);
        }
        .lo-btn--solid:hover{transform:translateY(-3px); box-shadow:0 14px 40px rgba(96,165,250,.5);}
        .lo-btn--ghost{
          color:#dbe7ff; border:1px solid rgba(160,190,255,.35); background:rgba(160,190,255,.06);
        }
        .lo-btn--ghost:hover{transform:translateY(-3px); background:rgba(160,190,255,.16);}
        .lo-hero__scroll{
          position:absolute; bottom:2rem; left:50%; transform:translateX(-50%); z-index:4;
          width:26px; height:42px; border:2px solid rgba(180,200,255,.5); border-radius:14px;
        }
        .lo-hero__scroll span{
          position:absolute; top:8px; left:50%; transform:translateX(-50%);
          width:4px; height:8px; border-radius:2px; background:#9fc1ff;
          animation:loScroll 1.6s ease infinite;
        }
        @keyframes loGrad{0%{background-position:0% 50%}50%{background-position:100% 50%}100%{background-position:0% 50%}}
        @keyframes loShine{to{background-position:200% center}}
        @keyframes loUp{from{opacity:0;transform:translateY(22px)}to{opacity:1;transform:translateY(0)}}
        @keyframes loScroll{0%{opacity:0;top:8px}40%{opacity:1}80%{opacity:0;top:24px}100%{opacity:0}}
        @media (prefers-reduced-motion:reduce){
          .lo-hero::before,.lo-grad,.lo-hero__scroll span{animation:none}
          .lo-hero__eyebrow,.lo-hero__title,.lo-hero__sub,.lo-hero__cta{animation:none;opacity:1}
        }
        </style>
    design:
      spacing:
        padding: [0, 0, 0, 0]
        margin: [0, 0, 0, 0]

  # ──────────────────────────────────────────────────────────────────────────
  # MISSION — Physical AI / VLA narrative, animated pillar cards
  # ──────────────────────────────────────────────────────────────────────────
  - block: markdown
    content:
      title: ''
      text: |-
        <section id="mission" class="lo-mission">
          <p class="lo-kicker">THE&nbsp;MISSION</p>
          <h2 class="lo-h2">One robot. Many skills. <span class="lo-grad">The right choice.</span></h2>
          <p class="lo-lead">
            Industrial robots today are brittle — hard-coded for one job. I work on
            <strong>Vision–Language–Action</strong> policies so a single embodiment can learn a
            growing library of skills and <strong>decide which one to deploy</strong> for the task in
            front of it, generalizing across messy, real-world industrial settings.
          </p>

          <div class="lo-pillars">
            <div class="lo-card">
              <div class="lo-card__icon">👁️</div>
              <h3>Perceive</h3>
              <p>Multimodal perception — vision, language, and proprioception fused into a shared world model.</p>
            </div>
            <div class="lo-card">
              <div class="lo-card__icon">🧠</div>
              <h3>Reason &amp; Choose</h3>
              <p>The policy reads the task, retrieves the right skill from its library, and sequences sub-skills to solve it.</p>
            </div>
            <div class="lo-card">
              <div class="lo-card__icon">🦾</div>
              <h3>Act &amp; Generalize</h3>
              <p>Closed-loop control that transfers from simulation (MuJoCo, Isaac Sim) to real hardware and unseen tasks.</p>
            </div>
          </div>
        </section>

        <style>
        .lo-mission{max-width:60rem; margin:0 auto; padding:1rem 1.5rem; text-align:center;}
        .lo-kicker{letter-spacing:.3em; font-size:.78rem; font-weight:700; color:#3b82f6;}
        .dark .lo-kicker{color:#7dd3fc;}
        .lo-h2{font-size:clamp(1.8rem,4.5vw,3rem); font-weight:800; letter-spacing:-.02em; margin:.6rem 0 1.2rem;}
        .lo-lead{font-size:clamp(1rem,2vw,1.2rem); line-height:1.7; max-width:44rem; margin:0 auto 3rem; opacity:.85;}
        .lo-pillars{display:grid; grid-template-columns:repeat(3,1fr); gap:1.2rem; text-align:left;}
        @media (max-width:780px){.lo-pillars{grid-template-columns:1fr;}}
        .lo-card{
          position:relative; padding:1.8rem 1.5rem; border-radius:1.1rem;
          background:rgba(125,160,255,.06); border:1px solid rgba(125,160,255,.16);
          transition:transform .25s ease, box-shadow .25s ease, border-color .25s ease;
          overflow:hidden;
        }
        .lo-card::before{
          content:""; position:absolute; inset:0; border-radius:inherit; padding:1px;
          background:linear-gradient(135deg,#5eead4,#60a5fa,#a78bfa); opacity:0;
          -webkit-mask:linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);
          -webkit-mask-composite:xor; mask-composite:exclude; transition:opacity .25s ease;
        }
        .lo-card:hover{transform:translateY(-6px); box-shadow:0 18px 40px rgba(40,80,180,.18);}
        .lo-card:hover::before{opacity:1;}
        .lo-card__icon{font-size:2rem; margin-bottom:.7rem;}
        .lo-card h3{font-size:1.25rem; font-weight:700; margin:0 0 .5rem;}
        .lo-card p{margin:0; line-height:1.6; opacity:.82; font-size:.98rem;}
        </style>
    design:
      spacing:
        padding: [4, 0, 2, 0]

  # ──────────────────────────────────────────────────────────────────────────
  # PROFILE — structured bio, education, experience, interests
  # ──────────────────────────────────────────────────────────────────────────
  - block: resume-biography-3
    content:
      username: me
      text: ''
      button:
        text: Download CV
        url: /uploads/resume.pdf
      headings:
        about: ''
        education: ''
        interests: ''
    design:
      background:
        gradient_mesh:
          enable: true
      name:
        size: lg
      avatar:
        size: medium
        shape: circle

  # ──────────────────────────────────────────────────────────────────────────
  # FEATURED WORK — local-mp4 video showcase
  # Drop clips at static/videos/{go2-navigation,moonbot,drone-ekf,humanoid-sim}.mp4
  # ──────────────────────────────────────────────────────────────────────────
  - block: markdown
    id: projects
    content:
      title: ''
      text: |-
        <section class="lo-work">
          <p class="lo-kicker" style="text-align:center">FEATURED&nbsp;WORK</p>
          <h2 class="lo-h2" style="text-align:center">Robots in the loop</h2>
          <p class="lo-lead" style="text-align:center;margin-bottom:2.6rem">
            Navigation, learned manipulation, and sim-to-real — across humanoids, quadrupeds, and drones.
          </p>

          <div class="lo-vgrid">
            <a class="lo-vcard" href="https://github.com/talos-robotics-ai/Go2_navigation" target="_blank" rel="noopener">
              <div class="lo-vcard__screen">
                <video autoplay muted loop playsinline preload="metadata"><source src="/videos/go2-navigation.mp4" type="video/mp4" /></video>
              </div>
              <div class="lo-vcard__body">
                <h3>Go2 Autonomous Navigation</h3>
                <p>Nonlinear MPC tuned by Bayesian Optimization on a Unitree Go2 quadruped. <span class="lo-tag">ICRA&nbsp;2026</span></p>
              </div>
            </a>

            <a class="lo-vcard" href="#projects">
              <div class="lo-vcard__screen">
                <video autoplay muted loop playsinline preload="metadata"><source src="/videos/humanoid-sim.mp4" type="video/mp4" /></video>
              </div>
              <div class="lo-vcard__body">
                <h3>Humanoid VLA in Simulation</h3>
                <p>Skill-library policies trained in MuJoCo &amp; Isaac Sim. <span class="lo-tag">Physical&nbsp;AI</span></p>
              </div>
            </a>

            <a class="lo-vcard" href="#projects">
              <div class="lo-vcard__screen">
                <video autoplay muted loop playsinline preload="metadata"><source src="/videos/moonbot.mp4" type="video/mp4" /></video>
              </div>
              <div class="lo-vcard__body">
                <h3>MoonBot — YC Hackathon</h3>
                <p>Edge-first inspection robot with an ACT imitation policy. <span class="lo-tag">w/&nbsp;Innate</span></p>
              </div>
            </a>

            <a class="lo-vcard" href="#projects">
              <div class="lo-vcard__screen">
                <video autoplay muted loop playsinline preload="metadata"><source src="/videos/drone-ekf.mp4" type="video/mp4" /></video>
              </div>
              <div class="lo-vcard__body">
                <h3>GPS-Denied Drone Autonomy</h3>
                <p>EKF sensor fusion + ORB-SLAM3 + MPC on Jetson Orin / PX4. <span class="lo-tag">AEA</span></p>
              </div>
            </a>
          </div>
        </section>

        <style>
        .lo-work{max-width:72rem; margin:0 auto; padding:1rem 1.5rem;}
        .lo-vgrid{display:grid; grid-template-columns:repeat(2,1fr); gap:1.4rem;}
        @media (max-width:780px){.lo-vgrid{grid-template-columns:1fr;}}
        .lo-vcard{
          display:block; text-decoration:none; color:inherit; border-radius:1.1rem; overflow:hidden;
          border:1px solid rgba(125,160,255,.16); background:rgba(125,160,255,.05);
          transition:transform .25s ease, box-shadow .25s ease;
        }
        .lo-vcard:hover{transform:translateY(-6px); box-shadow:0 22px 50px rgba(40,80,180,.22);}
        .lo-vcard__screen{
          position:relative; aspect-ratio:16/9; overflow:hidden;
          background:linear-gradient(120deg,#0a0f1f,#13224a,#0b2a3a,#1a0f2e);
          background-size:300% 300%; animation:loGrad 14s ease infinite;
        }
        .lo-vcard__screen::after{
          content:"▶ preview"; position:absolute; inset:0; display:flex; align-items:center; justify-content:center;
          color:rgba(200,215,255,.45); font-size:.82rem; letter-spacing:.18em; pointer-events:none;
        }
        .lo-vcard__screen video{
          position:relative; z-index:1; width:100%; height:100%; object-fit:cover; display:block;
        }
        .lo-vcard__body{padding:1.2rem 1.3rem;}
        .lo-vcard__body h3{font-size:1.2rem; font-weight:700; margin:0 0 .45rem;}
        .lo-vcard__body p{margin:0; opacity:.82; line-height:1.55; font-size:.95rem;}
        .lo-tag{
          display:inline-block; margin-left:.3rem; padding:.12rem .55rem; border-radius:999px;
          font-size:.72rem; font-weight:600; letter-spacing:.04em;
          background:linear-gradient(90deg,rgba(94,234,212,.18),rgba(96,165,250,.18));
          border:1px solid rgba(125,160,255,.3); color:#5eead4;
        }
        </style>
    design:
      spacing:
        padding: [2, 0, 2, 0]

  # ──────────────────────────────────────────────────────────────────────────
  # PUBLICATIONS
  # ──────────────────────────────────────────────────────────────────────────
  - block: collection
    id: papers
    content:
      title: Research & Publications
      text: ''
      filters:
        folders:
          - publications
    design:
      view: article-grid
      columns: 2

  # ──────────────────────────────────────────────────────────────────────────
  # CONTACT CTA
  # ──────────────────────────────────────────────────────────────────────────
  - block: markdown
    content:
      title: ''
      text: |-
        <section class="lo-contact">
          <h2 class="lo-h2">Let's build Physical&nbsp;AI together.</h2>
          <p class="lo-lead" style="margin-bottom:2rem">
            Working on humanoids, manipulation, or VLA — or just want to talk robots? Reach out.
          </p>
          <div class="lo-hero__cta" style="animation:none;opacity:1">
            <a class="lo-btn lo-btn--solid" href="mailto:ortolore@gmail.com">Email me</a>
            <a class="lo-btn lo-btn--ghost" href="https://www.linkedin.com/in/lorenzo-ortolani-6135b7240/" target="_blank" rel="noopener">LinkedIn</a>
            <a class="lo-btn lo-btn--ghost" href="https://github.com/Relo02" target="_blank" rel="noopener">GitHub</a>
          </div>
        </section>

        <style>
        .lo-contact{max-width:48rem; margin:0 auto; padding:2rem 1.5rem; text-align:center;}
        .lo-contact .lo-btn--ghost{border-color:rgba(120,140,180,.4);}
        </style>
    design:
      spacing:
        padding: [3, 0, 3, 0]
---
