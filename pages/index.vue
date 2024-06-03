<template>
    <div class="bg-slate-100 h-screen dark:bg-gray-900">
    <nav class="bg-white border-gray-200 dark:bg-gray-900">
        <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
            <a href="https://flowbite.com/" class="flex items-center space-x-3 rtl:space-x-reverse">
                <img src="../assets/Layer.png.png" class="h-8" alt="Flowbite Logo" />
            </a>
            <button data-collapse-toggle="navbar-default" type="button"
                class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
                aria-controls="navbar-default" aria-expanded="false">
                <span class="sr-only">Open main menu</span>
                <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                        d="M1 1h15M1 7h15M1 13h15" />
                </svg>
            </button>
            <div class="hidden w-full md:block md:w-auto" id="navbar-default">
                <ul
                    class="items-center font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700">
                    <li>
                        <a href="#"
                            class="block py-2 px-3 text-white bg-blue-700 rounded md:bg-transparent md:text-[#d20753] md:p-0 dark:text-white md:dark:text-[#d20753]"
                            aria-current="page">Home</a>
                    </li>
                    <li>
                        <a href="#"
                            class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-[#d20753] md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">About</a>
                    </li>
                    <li>
                        <a href="#"
                            class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-[#d20753] md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">Services</a>
                    </li>
                    <li>
                        <a href="#"
                            class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-[#d20753] md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">Pricing</a>
                    </li>
                    <li>
                        <a href="#"
                            class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-[#d20753] md:p-0 dark:text-white md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent">Contact</a>
                    </li>
                    <li class="bottom-3">

                        <ModeSwich />
                    </li>

                </ul>
            </div>
        </div>
    </nav>
        <section class=" relative dark:bg-gray-900">
            <!-- <img class="absolute h-screen -top-[1rem] left-1/2 -ml-[40rem] w-[163.125rem] max-w-none sm:-ml-[67.5rem] " src="https://tailwindui.com/img/beams-home@95.jpg" alt=""> -->
            <div class="flex items-center justify-center">
                <h1 class="mt-3 flex items-center text-5xl font-extrabold dark:text-white">
                    Welcome to our
                    <span
                        class="bg-[#fca1c2] text-[#d20753] text-2xl font-semibold me-2 px-2.5 py-0.5 rounded dark:bg-[#fca1c2] dark:text-blue-800 ms-2">website!</span>
                </h1>
            </div>
            <div class="relative py-8 px-4 mx-auto max-w-2xl lg:py-16">
                <form class="bg-white z-50 rounded-lg p-4 sm:p-6 dark:bg-gray-800" @submit.prevent="handleSubmit">
                    <div class="grid gap-4 sm:grid-cols-2 sm:gap-6">
                        <!-- Start Main Category -->
                        <div class="sm:col-span-2">
                            <label for="main-category"
                                class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Main Category <span
                                    class="text-red-500">*</span></label>
                            <select id="main-category" v-model="selectedCategory" @change="updateSubCategories"
                                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                                <option value="" disabled selected>Choose Main Category</option>
                                <option v-for="category in categories" :key="category.id" :value="category.id">
                                    {{ category.name }}
                                </option>
                            </select>
                        </div>
                        <!-- End Main Category -->
                        <!-- Start Sub Category -->
                        <div class="sm:col-span-2">
                            <label for="sub-category"
                                class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Sub Category <span
                                    class="text-red-500">*</span></label>
                            <select id="sub-category" v-model="selectedSubCategory" @change="updateproperties"
                                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                                <option value="" disabled selected>Choose Sub Category</option>
                                <option v-for="subCategory in subCategories" :key="subCategory.id" :value="subCategory.id">
                                    {{ subCategory.name }}
                                </option>
                            </select>
                        </div>
                        <!-- End Sub Category -->
                        <!-- Start Process Type -->
                        <div class="sm:col-span-2">
                            <label for="name" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Process
                                Type</label>
                            <select id="process-type" v-model="processType"
                                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                                <option value="" disabled selected>Choose Process</option>
                                <option v-for="process in processes" :key="process.id" :value="process.id">
                                    {{ process.name }}
                                </option>
                                <option>other</option>
                            </select>
                            <input type="text" v-if="processType === 'other'"
                                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 mt-5 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                                placeholder="from user" v-model="otherProcess" />
                        </div>
                        <!-- End Process Type -->
                        <!-- Start Brand -->
                        <div class="sm:col-span-2">
                            <label for="brand" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">
                                Brand
                            </label>
                            <select id="brand" v-model="selectedBrand" @change="updateModels"
                                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                                <option value="" disabled selected>Select Brand</option>
                                <option v-for="brand in brands" :key="brand.id" :value="brand.id">
                                    {{ brand.name }}
                                </option>
                            </select>
                        </div>
                        <!-- End Brand -->
                        <!-- Start Model -->
                        <div v-if="selectedBrand !== ''" class="sm:col-span-2">
                            <label for="brand" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">
                                Model
                            </label>
                            <select v-model="selectedModel"
                                class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                                <option value="" disabled selected>Select Model</option>
                                <optgroup v-for="model in models" :label="model.name" :key="model.id">
                                    <option v-for="option in model.options" :value="option.id" :key="option.id">
                                        {{ option.name }}
                                    </option>
                                </optgroup>
                            </select>
                        </div>
                        <!-- End Model -->

                    </div>
                    <button type="submit"
                        class=" bg-gradient-to-r from-[#d20753] to-[#ff951d] hover:bg-gradient-to-bl  inline-flex items-center px-5 py-2.5 mt-4 sm:mt-6 text-sm font-medium text-center text-white rounded-lg focus:ring-4 focus:ring-purple-200 dark:focus:ring-purple-900 hover:bg-purple-800">
                        Submit
                    </button>
                </form>
            </div>
        </section>
    </div>
</template>

<script setup>
import layout from "../layout/layout.vue";
import ModeSwich from "./ModeSwich.vue";


import { ref, onMounted, computed } from "vue";
import axios from "axios";
import { useRouter } from 'vue-router';
import { initFlowbite } from "flowbite";

onMounted(() => {
    initFlowbite();
});

const selectedCategory = ref("");
const selectedSubCategory = ref("");
const processType = ref("");
const otherProcess = ref("");
const processes = ref([]);
const brands = ref([]);
const categories = ref([]);
const selectedBrand = ref("");
const selectedModel = ref('');
const models = ref([]);

const subCategories = computed(() => {
    const mainCategory = categories.value.find((cat) => cat.id === selectedCategory.value);
    return mainCategory ? mainCategory.children : [];
});

const updateSubCategories = async () => {
    try {
        const response = await axios.get(
            `https://staging.mazaady.com/api/v1/properties?cat=${selectedCategory.value}`,
            {
                headers: {
                    "private-key": "3%o8i}_;3D4bF]G5@22r2)Et1&mLJ4?$@+16",
                },
            }
        );
    } catch (error) {
        console.error("Error fetching sub categories:", error);
    }
};

const updateproperties = async () => {
    try {
        const response = await axios.get(
            `https://staging.mazaady.com/api/v1/properties?cat=${selectedSubCategory.value}`,
            {
                headers: {
                    "private-key": "3%o8i}_;3D4bF]G5@22r2)Et1&mLJ4?$@+16",
                },
            }
        );
        processes.value = response.data.data[0].options.map(option => ({
            id: option.id,
            name: option.name,
        }));

        brands.value = response.data.data.find(prop => prop.slug === 'brand')?.options || [];
    } catch (error) {
        console.error("Error fetching sub categories:", error);
    }
};

watch(selectedBrand, async (newBrand) => {
    try {
        const response = await axios.get(`https://staging.mazaady.com/api/v1/get-options-child/${newBrand}`, {
            headers: {
                'private-key': '3%o8i}_;3D4bF]G5@22r2)Et1&mLJ4?$@+16'
            }
        });
        models.value = response.data.data; // Assuming data is an array of models with 'options' array
    } catch (error) {
        console.error('Error fetching models:', error);
    }
});

onMounted(async () => {
    try {
        const response = await axios.get("https://staging.mazaady.com/api/v1/get_all_cats", {
            headers: {
                "private-key": "3%o8i}_;3D4bF]G5@22r2)Et1&mLJ4?$@+16",
            },
        });
        categories.value = response.data.data.categories;
    } catch (error) {
        console.error("Error fetching categories:", error);
    }
});
const router = useRouter();
const handleSubmit = () => {
    const selectedData = {
        category: categories.value.find(cat => cat.id === selectedCategory.value)?.name || '',
        subCategory: subCategories.value.find(subCat => subCat.id === selectedSubCategory.value)?.name || '',
        processType: processType.value === 'other' ? otherProcess.value : processes.value.find(proc => proc.id === processType.value)?.name || '',
        brand: brands.value.find(br => br.id === selectedBrand.value)?.name || '',
        model: models.value.find(mdl => mdl.options.find(opt => opt.id === selectedModel.value))?.options.find(opt => opt.id === selectedModel.value)?.name || ''

    };
    router.push({ path: '/show', query: selectedData });
};

</script>

