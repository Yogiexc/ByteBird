<script setup>
// Composition API
import { ref } from 'vue'
import ButtonPrimary from '@/components/ButtonPrimary.vue'
import imageLogo from "@/assets/img/logo-brand.png"
import figure from "@/assets/img/Group 3.png"

import icon from "@/assets/img/services/Icon.png"
import icon2 from "@/assets/img/services/Icon 2.png"
import icon3 from "@/assets/img/services/Icon 3.png"

import img1 from '@/assets/img/partner/img-1.png';
import img2 from '@/assets/img/partner/img-2.png';
import img3 from '@/assets/img/partner/img-3.png';
import img4 from '@/assets/img/partner/img-4.png';
import img5 from '@/assets/img/partner/img-5.png';
import img6 from '@/assets/img/partner/img-6.png';

import blog1 from '@/assets/img/blog/img1.png';
import blog2 from '@/assets/img/blog/img2.png';
import blog3 from '@/assets/img/blog/img3.png';
import blog4 from '@/assets/img/blog/img4.png';

import visi from "@/assets/img/visi.png";

import people1 from "@/assets/img/orang/ahmad.png";
import people2 from "@/assets/img/orang/KW.png";
import people3 from "@/assets/img/orang/tasya.png";

import IconBrand from '@/components/IconBrandwhite.vue'
import IconBrandwhite from '@/components/IconBrandwhite.vue'

// services object
const services = ref([
  {
    id: 1, img: icon, title: "Build Community"
  },
  {
    id: 2, img: icon2, title: "Share Events"
  },
  {
    id: 3, img: icon3, title: "Get Information"
  }
])

//kerjasama object
const partners = ref([
  {
    id: 1, img: img1
  },
  {
    id: 2, img: img2
  },
  {
    id: 3, img: img3
  },
  {
    id: 4, img: img4
  },
  {
    id: 5, img: img5
  },
  {
    id: 6, img: img6
  },
])

//event 
const events = ref([
  {
    id: 1, img: blog1
  },
  {
    id: 2, img: blog2
  },
  {
    id: 3, img: blog3
  },
  {
    id: 4, img: blog4
  },
])

//people
const peoples = ref ([
  {
    id: 1, img: people1
  },
  {
    id: 2, img: people2
  },
  {
    id: 3, img: people3
  },
])

// Data binding

const isOpen = ref(false)
const openPopUp = () => {
  isOpen.value = !isOpen.value
}

</script>

<template>
  <header class="flex items-center justify-between px-3 py-6 lg:px-32">
    <img class="h-full" :src="imageLogo" alt="logo join sistem">
    <ul class="hidden lg:flex">
      <li class="mx-3">
        <a href="#">Home</a>
      </li>
      <li class="mx-3">
        <a href="#">Blog</a>
      </li>
      <li class="mx-3">
        <a href="#">About Us </a>
      </li>
      <li class="mx-3">
        <a href="#">Contact Us</a>
      </li>
    </ul>
    <button type="button" class="hidden px-3 py-3 font-bold text-white rounded-full lg:block bg-primary">
      Contact Us
    </button>
    <ButtonPrimary class="lg:hidden">
      <img src="@/assets/img/menu-icon.png" class="w-6" alt="Menu Icon">
    </ButtonPrimary>
  </header>
  <div v-if="isOpen"
    class="fixed z-20 flex items-center justify-between w-5/6 h-32 p-2 transform -translate-x-1/2 -translate-y-1/2 bg-white rounded-lg top-1/2 left-1/2">
    <span>Pop Up Content</span>
    <ButtonPrimary>Close</ButtonPrimary>
  </div>
  <div v-if="isOpen" @click="isOpen = false" class="fixed top-0 left-0 z-10 w-full h-full bg-black opacity-50"></div>


  <header>
    <div class="flex w-full px-32 py-16">
      <div class="flex flex-col w-1/2 gap-5">
        <h2 class="text-lg font-semibold leading-relaxed text-yellow-500 uppercase">CAREER ACELERATE</h2>
        <h1 class="text-3xl font-bold leading-snug text-slate-800">Meningkatkan Karir Anda di SISTEM Bootcamp</h1>
        <p class="text-sm leading-relaxed text-slate-500">Pelajari dari ahli Teknik Perangkat Lunak yang berpengalaman
          di SEA dan mempercepat karir Anda sebagai Software Engineer.</p>
        <div class="flex flex-row items-center justify-between">
          <div class="flex gap-3 fles-row" v-for="service in services" :key="service.id">
            <img :src="service.img" :alt="service.title">
            <h3 class="text-base font-semibold">{{ service.title }}</h3>
          </div>
        </div>
        <ButtonPrimary>Contact Us</ButtonPrimary>
      </div>
      <div class="flex justify-center w-1/2 item-center">
        <img :src="figure" alt="young mans">
      </div>
    </div>
  </header>

  <main>
    <section classs="w-full px-32 py-5">
      <h2 class="text-3xl font-bold text-center">Berbagai Mitra Untuk Mendukung Ekosistem Digital SISTEM</h2>
      <div class="flex flex-row items-center justify-between w-full">
        <div class="w-48 p-2" v-for="partner in partners" :key="partner.id">
          <img :src="partner.img" alt="partner">
        </div>
      </div>
    </section>

    <section class="w-full px-32 py-16">
      <h2 class="text-3xl font-bold text-center">Pilih Pengalaman Event Terbaik</h2>
      <p class="text-sm leading-relaxed text-center text-slate-500">Cari berbagai macam event teknologi terbaik yang
        diadakan oleh komunitas dan di dukung oleh banyak perusahaan besar lainnya</p>
      <div class="flex flex-row items-center justify-between w-full">
        <div class="p-2 w-600" v-for="event in events" :key="event.id">
          <img :src="event.img" alt="event">
        </div>
      </div>
    </section>

    <section class="w-full px-32 py-16">
      <div class="flex flex-row items-center justify-between w-full">
          <img :src="visi" alt="visi&misi">
      </div>
    </section>

    <section class="w-full px-32 py-16">
      <h2 class="text-3xl font-bold text-center">Cerita Sukses Peserta</h2>
      <p class="text-sm leading-relaxed text-center text-slate-500">Cari berbagai macam event teknologi terbaik yang diadakan oleh komunitas dan di dukung oleh banyak perusahaan besar lainnya</p>
      <div class="flex flex-row items-center justify-between w-full">
        <div class="p-2 w-600" v-for="people in peoples" :key="people.id">
          <img :src="people.img" alt="people">
        </div>
      </div>
    </section>

<section class="flex flex-col items-center justify-center w-full gap-2 px-32 py-16">
  <h2 class="text-3xl font-bold text-center">Gabung Jadi Talenta Digital Terbaik <br> Bersama SISTEM</h2>
  <p class="text-sm leading-relaxed text-center text-slate-500">Lorem ipsum dolor sit amet, consectetur adipiscing <br>elit, sed do eiusmod tempor incididunt.</p>
  <br><ButtonPrimary class="rounded-sm">Daftar Sekarang</ButtonPrimary>
</section>

<section>

</section>

  </main>

  <footer>
        <div class="column">
            <i>
                <IconBrandwhite />
            </i>
            <div class="address">
                <h5>Jogja Office</h5>
                <p>Jl. Kresna. Gamping kidul, Amberketawang, Kec.<br />
                    Gamping, Kabupaten Sleman, DIY 55294</p>
            </div>
            <div class="address">
                <h5>Jakarta Office</h5>
                <p>Cibis Nine Building Lantai 11 Jl. TB Simatupang No. <br />
                    2, Jakarta Selatan</p>
            </div>
        </div>
        <div class="column">
            <h2>Bootcamp</h2>
            <ul>
                <li>Devops</li>
                <li>Quality Assurance</li>
                <li>Fullstack Developer</li>
                <li>Project Manager</li>
            </ul>
        </div>
        <div class="column">
            <h2>SISTEM</h2>
            <ul>
                <li>Tentang Kami</li>
                <li>Events</li>
                <li>FAQ</li>
            </ul>
        </div>
        <div class="column">
            <h2>Ikuti Kami</h2>
            <button><img src="@/assets/symbol/Container.png" alt="Instagram"></button>
            <div class="line"><img src="@/assets/symbol/Symbol_1.png" alt="Phone">
                <p>+62 811-269-086</p>
            </div>
            <div class="line"><img src="@/assets/symbol/Symbol.png" alt="Mail">
                <p>putro@solutionlabs.id</p>
            </div>
        </div>
    </footer>

</template>

<style scoped>
footer {
    display: flex;
    justify-content: space-around;
    align-items: start;
    background: #071F51;
    color: #ABB0BA;
    padding: 60px;
}
.line {
    display: flex;
    gap: 15px;
}
.column {
    display: flex;
    flex-direction: column;
    gap: 20px;
}
</style>