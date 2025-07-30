<script>
  import '$lib/styles/links.scss';
  import { IconMail, IconBrandLinkedin, IconWriting, IconDeviceDesktop, IconAddressBook } from '@tabler/icons-svelte';
</script>

<main class="links-main">
  <header>
    <h1 class="title">
      <div class="top">
        <img src="/assets/headshot.png" alt="Headshot" class="avatar">
        <span class="top-text">Sam</span>
      </div>
      <span class="bottom">Cheng</span>
    </h1>
    <p>Designer, Maker, & Storyteller</p>
  </header>
  <div class="main-links">
    
    <a href="https://www.classmate.app/contact/sam.vcf">
      <IconAddressBook/>
      Contact Info
    </a>
    <a href="mailto:sam@classmate.app">
      <IconMail/>
      sam@classmate.app
    </a>
    <a href="https://www.linkedin.com/in/samfcheng/" target="_blank">
      <IconBrandLinkedin/>
      LinkedIn
    </a>
    <a href="https://www.classmate.app">
      <IconWriting/>
      Check out Classmate!
    </a>
    <a href="https://www.samcheng.co">
      <IconDeviceDesktop/>
      My Personal Website
    </a>
  </div>
</main>