<script>
    import WhoWeAre from './WhoWeAre.svelte';
    import WhatWeDo from './WhatWeDo.svelte';
    import Contact from './Contact.svelte';
  
    export let currentTab;
  </script>
  
  <div>
    {#if currentTab === 'WhoWeAre'}
      <WhoWeAre />
    {:else if currentTab === 'WhatWeDo'}
      <WhatWeDo />
    {:else if currentTab === 'Contact'}
      <Contact />
    {/if}
  </div>
  