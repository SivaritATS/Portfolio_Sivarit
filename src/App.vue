<template>
  <div>
    <Navbar :current-page="currentPage" :theme="theme" @navigate="goTo" @toggle-theme="toggleTheme" />

    <HomeSection :class="{ active: currentPage === 'home' }" :projects="projects" :skills-list="skillsList"
      @navigate="goTo" />

    <ProjectsSection :class="{ active: currentPage === 'projects' }" :projects="projects" />

    <ContactSection :class="{ active: currentPage === 'contact' }" />

    <Footer />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import Navbar from './components/Navbar.vue';
import HomeSection from './components/HomeSection.vue';
import ProjectsSection from './components/ProjectsSection.vue';
import ContactSection from './components/ContactSection.vue';
import Footer from './components/Footer.vue';

// --- Navigation Logic ---
const currentPage = ref('home');

const goTo = (page) => {
  currentPage.value = page;
  window.scrollTo({ top: 0, behavior: 'smooth' });
};

// --- Theme Logic ---
const theme = ref('light');

const toggleTheme = () => {
  theme.value = theme.value === 'light' ? 'dark' : 'light';
  document.documentElement.setAttribute('data-theme', theme.value);
  localStorage.setItem('theme', theme.value);
};

onMounted(() => {
  const savedTheme = localStorage.getItem('theme');
  if (savedTheme) {
    theme.value = savedTheme;
  }
  document.documentElement.setAttribute('data-theme', theme.value);
});

// --- About Section Data ---
const skillsList = ref(['HTML5', 'Vue.js', 'JavaScript', 'React', 'Next.js', 'Docker', 'Tailwind CSS', 'Git & GitHub', 'Figma', 'TypeScript', 'Node.js']);

// --- Projects Database ---
const projects = ref([
  {
    id: '01',
    title: 'Maintenance System',
    tag: 'Next JS',
    thumbClass: 'thumb-1',
    desc: 'A comprehensive system for tracking and managing maintenance requests.',
    link: 'https://github.com/SivaritATS/maintenance-system',
    liveLink: 'https://maintenance-system-tczo.vercel.app/'
  },
  {
    id: '02',
    title: 'Booking Item System',
    tag: 'Vue JS',
    thumbClass: 'thumb-2',
    desc: 'Complete booking and reservation system for managing resources effectively.',
    link: 'https://github.com/SivaritATS/Booking-Item-System-Final',
    liveLink: 'https://booking-item-system-final.vercel.app/'
  },
  {
    id: '03',
    title: 'HR Payroll System',
    tag: 'Vue JS',
    thumbClass: 'thumb-3',
    desc: 'An HR management application to handle employee payroll and data.',
    link: 'https://github.com/SivaritATS/Project-HR-Payroll-System'
  },
  {
    id: '04',
    title: 'Valorant Web',
    tag: 'Next JS',
    thumbClass: 'thumb-4',
    desc: 'A Next.js web application providing statistics and information for Valorant.',
    link: 'https://github.com/SivaritATS/nextjs-web-valorant',
    liveLink: 'https://nextjs-web-valorant-one.vercel.app/'
  },
  {
    id: '05',
    title: 'Valorant Guide App',
    tag: 'Flutter',
    thumbClass: 'thumb-5',
    desc: 'A mobile application guide for Valorant built with Flutter.',
    link: 'https://github.com/SivaritATS/MoblieApp_Project'
  },
  {
    id: '06',
    title: 'Portfolio Sivarit',
    tag: 'Vue JS',
    thumbClass: 'thumb-6',
    desc: 'My personal portfolio website built with Vue.js to showcase my projects and skills.',
    link: 'https://github.com/SivaritATS/Portfolio_Sivarit',
    liveLink: 'https://portfolio-sivarit.vercel.app/'
  }
]);
</script>