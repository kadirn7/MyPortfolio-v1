<script setup>
import AboutTab from "@/components/AboutTab.vue";
import Education from "@/components/Education.vue";
import Experience from "@/components/Experience.vue";
import SectionHeading from "@/components/SectionHeading.vue";
import Skill from "@/components/Skill.vue";
import { skills } from "@/data/skills.json";
import { ref } from "vue";

let currentTab = ref(1);
</script>

<template>
    <section id="about" class="relative py-28 lg:py-36">
        <div class="container px-3 mx-auto max-w-6xl 2xl:max-w-7xl">
            <SectionHeading>Hakkımda</SectionHeading>

            <div class="grid grid-cols-1 md:grid-cols-12 gap-10">
                <div class="md:col-span-5 flex justify-center items-start">
                    <div class="relative">
                        <img class="w-full rounded-e-lg rounded-b-lg h-auto" src="/images/about_svg.svg" alt="Kadir Paşaoğlu" />
                    </div>
                </div>

                <div class="md:col-span-7">
                    <div class="tabs mb-10 border-b border-slate-200 dark:border-slate-800 pb-5">
                        <ul class="grid grid-cols-2 justify-center md:justify-start gap-y-6 md:flex md:flex-wrap md:space-x-6 md:gap-y-0 font-medium">
                            <li>
                                <AboutTab @click="currentTab = 1" :class="currentTab === 1 ? 'dark:bg-slate-800 bg-slate-200 dark:text-white' : ''">
                                    <template #icon>
                                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5 dark:text-primary-300 text-primary-600 mr-2">
                                            <path stroke-linecap="round" stroke-linejoin="round" d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z" />
                                        </svg>
                                    </template>
                                    <span>Hakkımda</span>
                                </AboutTab>
                            </li>
                            <li>
                                <AboutTab @click="currentTab = 2" :class="currentTab === 2 ? 'dark:bg-slate-800 bg-slate-200 dark:text-white' : ''">
                                    <template #icon>
                                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5 dark:text-primary-300 text-primary-600 mr-2">
                                            <path stroke-linecap="round" stroke-linejoin="round" d="M6.75 7.5l3 2.25-3 2.25m4.5 0h3m-9 8.25h13.5A2.25 2.25 0 0021 18V6a2.25 2.25 0 00-2.25-2.25H5.25A2.25 2.25 0 003 6v12a2.25 2.25 0 002.25 2.25z" />
                                        </svg>
                                    </template>
                                    <span>Yetenekler</span>
                                </AboutTab>
                            </li>
                            <li>
                                <AboutTab @click="currentTab = 3" :class="currentTab === 3 ? 'dark:bg-slate-800 bg-slate-200 dark:text-white' : ''">
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5 dark:text-primary-300 text-primary-600 mr-2">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M20.25 14.15v4.25c0 1.094-.787 2.036-1.872 2.18-2.087.277-4.216.42-6.378.42s-4.291-.143-6.378-.42c-1.085-.144-1.872-1.086-1.872-2.18v-4.25m16.5 0a2.18 2.18 0 00.75-1.661V8.706c0-1.081-.768-2.015-1.837-2.175a48.114 48.114 0 00-3.413-.387m4.5 8.006c-.194.165-.42.295-.673.38A23.978 23.978 0 0112 15.75c-2.648 0-5.195-.429-7.577-1.22a2.016 2.016 0 01-.673-.38m0 0A2.18 2.18 0 013 12.489V8.706c0-1.081.768-2.015 1.837-2.175a48.111 48.111 0 013.413-.387m7.5 0V5.25A2.25 2.25 0 0013.5 3h-3a2.25 2.25 0 00-2.25 2.25v.894m7.5 0a48.667 48.667 0 00-7.5 0M12 12.75h.008v.008H12v-.008z" />
                                    </svg>
                                    <span>Deneyim</span>
                                </AboutTab>
                            </li>
                            <li>
                                <AboutTab @click="currentTab = 4" :class="currentTab === 4 ? 'dark:bg-slate-800 bg-slate-200 dark:text-white' : ''">
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5 dark:text-primary-300 text-primary-600 mr-2">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M4.26 10.147a60.436 60.436 0 00-.491 6.347A48.627 48.627 0 0112 20.904a48.627 48.627 0 018.232-4.41 60.46 60.46 0 00-.491-6.347m-15.482 0a50.57 50.57 0 00-2.658-.813A59.905 59.905 0 0112 3.493a59.902 59.902 0 0110.399 5.84c-.896.248-1.783.52-2.658.814m-15.482 0A50.697 50.697 0 0112 13.489a50.702 50.702 0 017.74-3.342M6.75 15a.75.75 0 100-1.5.75.75 0 000 1.5zm0 0v-3.675A55.378 55.378 0 0112 8.443m-7.007 11.55A5.981 5.981 0 006.75 15.75v-1.5" />
                                    </svg>
                                    <span>Eğitim</span>
                                </AboutTab>
                            </li>
                        </ul>
                    </div>

                    <div class="contents">
                        <transition name="fade" mode="out-in">
                            <div v-if="currentTab === 1" class="dark:text-slate-200 tracking-wide">
                                <div class="prose dark:prose-invert prose-teal tracking-wide mb-7 text-left md:text-justify">
                                    <p>Merhaba, Ben <strong>Kadir Paşaoğlu</strong></p>
                                    <p>
                                        Karadeniz Teknik Üniversitesi Bilgisayar Mühendisliği son sınıf öğrencisiyim. Modern web teknolojileri konusunda 
                                        kendimi sürekli geliştiriyor ve Full Stack Developer olarak kariyer hedefliyorum. Özellikle C# ve .NET Core 
                                        backend teknolojileri ile Vue.js frontend framework'ünde projeler geliştirerek deneyim kazanıyorum.
                                    </p>
                                    <p>
                                        Clean Architecture, SOLID prensipleri ve modern yazılım geliştirme pratiklerini yakından takip ediyor, 
                                        bu bilgileri projelerime yansıtmaya özen gösteriyorum. Teknoloji sektöründe Full Stack Developer olarak 
                                        çalışmayı ve edindiğim bilgileri kurumsal projelerde kullanmayı hedefliyorum.
                                    </p>
                                </div>

                                <a href="/files/resume.pdf" target="_blank" class="text-primary-500 hover:text-primary-700 dark:text-primary-400 dark:hover:text-primary-300 font-medium flex items-center justify-start w-fit transition-all duration-300">
                                    <span class="mr-2">CV'mi İncele</span>
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M17.25 8.25L21 12m0 0l-3.75 3.75M21 12H3" />
                                    </svg>
                                </a>
                            </div>
                            <div v-else-if="currentTab === 2" class="dark:text-slate-200">
                                <div class="flex flex-wrap gap-4 justify-center md:justify-start">
                                    <Skill v-for="skill in skills" :key="skill.id" :link="skill.link" :name="skill.name" :image="skill.image" />
                                </div>
                            </div>
                            <div v-else-if="currentTab === 3" class="dark:text-slate-200 tracking-wide">
                                <Experience designation=" Kişisel Projeler" company="Portföy" timeline="2023 - Devam Ediyor">
                                    <template #description>
                                        <ul>
                                            <li>C# ve .NET Core kullanarak RESTful API'ler geliştirme</li>
                                            <li>Vue.js ile modern ve responsive web uygulamaları oluşturma</li>
                                            <li>Clean Architecture, CQRS ve Repository pattern implementasyonları</li>
                                            <li>SQL Server ve PostgreSQL veritabanı yönetimi</li>
                                            <li>Git versiyon kontrol sistemi ile proje yönetimi</li>
                                        </ul>
                                    </template>
                                </Experience>
                                
                            </div>
                            <div v-else-if="currentTab === 4" class="dark:text-slate-200 tracking-wide space-y-5">
                                <Education 
                                    degree="Bilgisayar Mühendisliği" 
                                    institute="Karadeniz Teknik Üniversitesi" 
                                    timeline="2020 - 2024" 
                                    website="https://www.ktu.edu.tr/" 
                                />
                            </div>
                        </transition>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>