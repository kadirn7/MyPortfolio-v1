<script setup>
import InputField from '@/components/InputField.vue';
import InputLabel from '@/components/InputLabel.vue';
import NButton from '@/components/NButton.vue';
import SectionHeading from '@/components/SectionHeading.vue';
import TextArea from '@/components/TextArea.vue';
import Toast from '@/components/Toast.vue';
import { reactive, ref } from 'vue';

const api =
    'https://discord.com/api/webhooks/1300811660424122389/KjpDyii1R07h-Fqzk6leNmpPyFDBVBv8R-Ok-1Vna-pcOc8ww0EnX5gyvf_xWO2944Lw';

const contactForm = reactive({
    name: '',
    email: '',
    subject: '',
    message: '',
});

const contactFormErrors = reactive({
    name: '',
    email: '',
    subject: '',
    message: '',
});

let loading = ref(false);

let showToast = ref(false);
const handleClose = () => {
    showToast.value = false;
};

const submitContactForm = () => {
    if (contactForm.name === '' || contactForm.name.length <= 3) {
        contactFormErrors.name = 'Lütfen adınızı giriniz';
        return;
    }
    const emailPattern = /^[^ ]+@[^ ]+\.[a-z]{2,3}$/;
    if (contactForm.email === '' || !emailPattern.test(contactForm.email)) {
        contactFormErrors.email = 'Lütfen geçerli bir e-posta adresi giriniz';
        return;
    }
    if (contactForm.message === '' || contactForm.message.length <= 20) {
        contactFormErrors.message = 'Lütfen mesajınızı giriniz';
        return;
    }

    // E-posta gönderme işlemi
    const subject = contactForm.subject ? contactForm.subject : 'Portfolio İletişim Formu';
    const body = `İsim: ${contactForm.name}\nE-posta: ${contactForm.email}\nMesaj: ${contactForm.message}`;
    window.location.href = `mailto:kadirneidik398@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;

    // Formu sıfırla
    resetForm();
    showToast.value = true;
};

const resetForm = () => {
    contactForm.name = '';
    contactForm.email = '';
    contactForm.subject = '';
    contactForm.message = '';
    contactFormErrors.name = '';
    contactFormErrors.email = '';
    contactFormErrors.subject = '';
    contactFormErrors.message = '';
};
</script>

<template>
    <transition name="fade" mode="in-out">
        <Toast
            v-if="showToast"
            :message="'Teşekkürler! Mesajınız için en kısa sürede size dönüş yapacağım.'"
            @close="handleClose"
        />
    </transition>

    <!-- Contact -->
    <section id="contact" class="relative py-28 lg:py-36 overflow-hidden">
        <div
            class="absolute top-44 -left-64 h-[250px] w-[900px] -rotate-25 rounded-3xl bg-gradient-to-r from-cyan-600 to-indigo-800 opacity-20 dark:opacity-20 blur-3xl filter block"
        ></div>
        <div class="container px-3 mx-auto max-w-6xl 2xl:max-w-7xl">
            <SectionHeading>İletişim</SectionHeading>

            <div
                class="grid grid-cols-1 md:grid-cols-12 gap-10 dark:text-slate-300 tracking-wide"
            >
                <div class="md:col-span-5">
                    <h3 class="font-medium text-3xl mb-2 dark:text-white">
                        Hızlı İletişim
                    </h3>
                    <p class="text-lg text-slate-600 dark:text-slate-300">
                        Form doldurmak istemiyorsanız WhatsApp'tan yazabilirsiniz!
                        <a
                            href="https://wa.me/905309915910"
                            target="_blank"
                            class="font-medium text-secondary-500 hover:text-secondary-600 dark:text-secondary-300 dark:hover:text-secondary-400 transition-all duration-300"
                            >buraya tıklayın</a
                        >
                    </p>
                    <ul class="mt-10 space-y-8">
                        <li class="flex items-center space-x-4">
                            <div>
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    fill="none"
                                    viewBox="0 0 24 24"
                                    stroke-width="1.5"
                                    stroke="currentColor"
                                    class="w-7 h-7 text-primary-500 dark:text-primary-300"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"
                                    />
                                </svg>
                            </div>
                            <div>
                                <h4 class="text-xl dark:text-white mb-1">
                                    E-posta
                                </h4>
                                <div class="flex items-center space-x-3">
                                    <a
                                        href="mailto:kadirneidik398@gmail.com"
                                        class="transition-all duration-300 hover:text-secondary-500 dark:hover:text-secondary-300"
                                        >kadirneidik398@gmail.com</a
                                    >
                                </div>
                            </div>
                        </li>
                        <li class="flex items-center space-x-4">
                            <div>
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    fill="none"
                                    viewBox="0 0 24 24"
                                    stroke-width="1.5"
                                    stroke="currentColor"
                                    class="w-7 h-7 text-primary-500 dark:text-primary-300"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        d="M9 6.75V15m6-6v8.25m.503 3.498l4.875-2.437c.381-.19.622-.58.622-1.006V4.82c0-.836-.88-1.38-1.628-1.006l-3.869 1.934c-.317.159-.69.159-1.006 0L9.503 3.252a1.125 1.125 0 00-1.006 0L3.622 5.689C3.24 5.88 3 6.27 3 6.695V19.18c0 .836.88 1.38 1.628 1.006l3.869-1.934c.317-.159.69-.159 1.006 0l4.994 2.497c.317.158.69.158 1.006 0z"
                                    />
                                </svg>
                            </div>
                            <div>
                                <h4 class="text-xl dark:text-white mb-1">
                                    Konum
                                </h4>
                                <p>
                                    <a
                                        href="https://www.google.com/maps/place/Trabzon"
                                        target="_blank"
                                        class="transition-all duration-300 hover:text-secondary-500 dark:hover:text-secondary-300"
                                        >Trabzon, Türkiye</a
                                    >
                                </p>
                            </div>
                        </li>
                    </ul>
                </div>

                <div class="md:col-span-7">
                    <form
                        @submit.prevent="submitContactForm"
                        class="grid grid-cols-2 gap-x-6 gap-y-8"
                    >
                        <div
                            class="col-span-2 md:col-span-1 flex flex-col space-y-3"
                        >
                            <InputLabel
                                for="name"
                                title="İsim"
                                :required="true"
                            />
                            <InputField
                                v-model="contactForm.name"
                                type="text"
                                id="name"
                                name="name"
                                placeholder="Adınızı giriniz"
                                :error="contactFormErrors.name"
                            />
                            <span
                                class="text-red-600 text-sm font-medium"
                                v-if="contactFormErrors.name"
                                >{{ contactFormErrors.name }}</span
                            >
                        </div>
                        <div
                            class="col-span-2 md:col-span-1 flex flex-col space-y-3"
                        >
                            <InputLabel
                                for="email"
                                title="E-posta"
                                :required="true"
                            />
                            <InputField
                                v-model="contactForm.email"
                                type="email"
                                id="email"
                                name="email"
                                placeholder="E-posta adresinizi giriniz"
                                :error="contactFormErrors.email"
                            />
                            <span
                                class="text-red-600 text-sm font-medium"
                                v-if="contactFormErrors.email"
                                >{{ contactFormErrors.email }}</span
                            >
                        </div>
                        <div class="col-span-2 flex flex-col space-y-3">
                            <InputLabel for="subject" title="Konu" />
                            <InputField
                                v-model="contactForm.subject"
                                type="text"
                                id="subject"
                                name="subject"
                                placeholder="Mesaj konusu (opsiyonel)"
                                :error="contactFormErrors.subject"
                            />
                            <span
                                class="text-red-600 text-sm font-medium"
                                v-if="contactFormErrors.subject"
                                >{{ contactFormErrors.subject }}</span
                            >
                        </div>
                        <div class="col-span-2 flex flex-col space-y-3">
                            <InputLabel
                                for="message"
                                title="Mesaj"
                                :required="true"
                            />
                            <TextArea
                                v-model="contactForm.message"
                                id="message"
                                name="message"
                                placeholder="Mesajınızı giriniz"
                                :error="contactFormErrors.message"
                            />
                            <span
                                class="text-red-600 text-sm font-medium"
                                v-if="contactFormErrors.message"
                                >{{ contactFormErrors.message }}</span
                            >
                        </div>
                        <div class="col-span-2">
                            <NButton
                                :loading="loading"
                                btn-type="filled"
                                class="w-full py-4 text-lg"
                                type="submit"
                            >
                                <span>Gönder</span>
                                <template #icon>
                                    <svg
                                        xmlns="http://www.w3.org/2000/svg"
                                        class="fill-current w-5 h-5"
                                        viewBox="0 0 16 16"
                                    >
                                        <path
                                            d="M15.964.686a.5.5 0 0 0-.65-.65L.767 5.855H.766l-.452.18a.5.5 0 0 0-.082.887l.41.26.001.002 4.995 3.178 3.178 4.995.002.002.26.41a.5.5 0 0 0 .886-.083l6-15Zm-1.833 1.89L6.637 10.07l-.215-.338a.5.5 0 0 0-.154-.154l-.338-.215 7.494-7.494 1.178-.471-.47 1.178Z"
                                        />
                                    </svg>
                                </template>
                            </NButton>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </section>
    <!-- Contact -->
</template>

<style scoped>
.fade-enter-from,
.fade-leave-to {
    transform: translateY(-120px);
    opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
    transition-duration: 300ms;
    transition-property: transform, opacity;
    transition-timing-function: cubic-bezier(0.6, 0.15, 0.35, 0.8);
}
</style>