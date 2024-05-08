<script>
  let currentTab = 'Home';

  function changeTab(tab) {
    currentTab = tab;
  }

  let teamMembers = [
    { name: "Richard Schoonhoven", role: "AI, Data Science, Computer Vision", img: "./richard.jpeg", bio: "Richard Schoonhoven is a leading AI and machine learning expert at Photo-Motion and a PhD researcher at Centrum Wiskunde & Informatica, specializing in high-performance computing optimizations for imaging systems. He holds dual cum laude Master's degrees in Mathematics and Computer Science from Utrecht University. Richard's work combines advanced computational methods with state-of-the-art machine learning, contributing significantly to both academic research and practical applications in AI. His scholarly and professional achievements underscore his role as a visionary in the integration of mathematics, physics, and computer science." },
    { name: "Murat Delibas", role: "Data Science, Data Engineering", img: "./murat.jpg", bio: "Murat Delibas is an emerging talent in data science currently developing innovative projects at AICRD and completing his Master's in Applied Mathematics at Delft University of Technology. Previously a Data Science Intern at Dealroom.co, he honed his skills in Python and Google Cloud Platform, applying advanced mathematical concepts to real-world data problems. Murat combines his passion for math, and coding to deliver algorithmic solutions, embodying a creative and analytical approach to technology and data science." },
  ];

  const services = [
    {
      icon: '🤖',
      title: 'AI-Driven Decision Making',
      description: 'We develop advanced AI models tailored to enhance decision-making processes, helping organizations like Çimsa make informed, data-driven choices.'
    },
    {
      icon: '⚙️',
      title: 'Operational Optimization',
      description: 'Our custom AI solutions are designed to streamline operations, increase efficiency, and reduce costs, transforming everyday business practices.'
    },
    {
      icon: '🚀',
      title: 'Innovation Facilitation',
      description: 'By integrating the latest in machine learning and data analysis, we empower businesses to unlock new opportunities for innovation and growth.'
    }
  ];
</script>

<nav>
  <button on:click={() => changeTab('Home')}>Home</button>
  <button on:click={() => changeTab('WhoWeAre')}>Who We Are</button>
  <button on:click={() => changeTab('WhatWeDo')}>What We Do</button>
  <button on:click={() => changeTab('Contact')}>Contact</button>
</nav>

<main>
  {#if currentTab === 'Home'}
    <div id="title">AICRD</div>
    <div class="content">
      <p>Welcome to AICRD, where we harness cutting-edge AI and novel scientific methodologies to solve complex challenges and propel industries forward.</p>
    </div>
  {:else if currentTab === 'WhoWeAre'}
    <div class="content">
      <h2>Our Team</h2>
  <p>Our team is comprised of experts in AI, data science, and engineering. We are passionate about developing innovative solutions that drive progress and create value for our clients.</p>
  <div>
    {#each teamMembers as member}
      <div class="team-member">
        <img class="member-photo" src={member.img} alt={member.name} />
        <div class="member-info">
          <h3>{member.name}</h3>
          <p>{member.role}</p>
          <p>{member.bio}</p>
        </div>
      </div>
    {/each}
  </div>
    </div>
  {:else if currentTab === 'WhatWeDo'}
  <div class="content" style="margin: 20px; font-family: Arial, sans-serif;">
    <h2>Our Services</h2>
    <p>At AICRD, we specialize in custom AI solutions that integrate the latest advancements in machine learning and data analysis. Our team excels in deploying AI models that enhance decision-making, optimize operations, and create new opportunities for innovation.</p>
    <ul style="list-style: none; padding: 0;">
      {#each services as service}
      <div class="team-member">
        <li style="display: flex; align-items: center; margin-bottom: 20px;">
          <span style="font-size: 24px; margin-right: 15px; margin-top: 30px">{service.icon}</span>
          <div>
            <h3>{service.title}</h3>
            <p>{service.description}</p>
          </div>
        </li>
      </div>
      {/each}
    </ul>
  </div>
  {:else if currentTab === 'Contact'}
  <div class="content">
    <h2>Contact Us</h2>
    <p>If you have any questions or would like to learn more about our services, please feel free to reach out to us.</p>

    <ul>
      <li style="display: flex; align-items: center; margin-bottom: 20px;">
        <span class="icon">📧</span>Email:  <a href="mailto:r.a.schoonhoven@hotmail.com"> r.a.schoonhoven@hotmail.com</a>
      </li>
        <li style="display: flex; align-items: center; margin-bottom: 20px;">
          <span class="icon">🏢</span>Address: Science Park 608, Amsterdam, North Holland 1098 XH, NL
      </li>
        <li style="display: flex; align-items: center; margin-bottom: 20px;">
        <span class="icon">📞</span>Phone: <a href="tel:+31201234567">+31 6 30 23 32 98</a>
      </li>
        <li style="display: flex; align-items: center; margin-bottom: 20px;">
        <span class="icon">🔗</span>LinkedIn: <a href="https://www.linkedin.com/company/aicrd/" target="_blank">Visit our LinkedIn</a>
        </li>
    </ul>
  </div>
  {/if}
</main>


<style>
  :global(body) {
    background-color: black;
    color: white;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
    font-size: 16px;
  }
  nav {
    text-align: center;
    padding: 20px 0;
  }
  nav button {
    padding: 12px 24px;
    margin: 10px;
    border: 1px solid white;
    background-color: transparent;
    color: white;
    font-size: 16px;
    cursor: pointer;
  }
  nav button:hover {
    background-color: white;
    color: black;
  }
  #title {
    font-size: 300px;
    text-align: center;
    margin: 0px 0;
  }
  main {
    padding: 20px;
    text-align: center;
  }
  .content {
    max-width: 800px;
    margin: auto;
  }
  .content p {
    line-height: 1.6;
  }

  .team-member {
    margin: 20px;
    padding: 20px;
    border-radius: 8px;
    background: rgba(255, 255, 255, 0.1); /* Light background for text visibility */
  }
  .member-photo {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover; /* Ensures the image fits well */
  }
  .member-info {
    margin-top: 10px;
  }
  .member-info h3, p {
    margin: 5px 0;
  }
</style>
