<template>
	<div class="vazirmatn flex-col h-svh bg-transparent text-white w-full relative flex justify-center items-center">
		<section
			class="h-svh w-full flex flex-col bg-[#16171b] justify-center items-center px-4 py-4 relative overflow-hidden z-10">
			<div
				class="relative text-center w-full flex justify-between items-center flex-col py-5 sm:py-12 px-3 sm:px-2 h-svh gap-5">
				<div class="flex flex-col items-center gap-2 sm:gap-5">
					<div class="flex flex-col justify-center items-center gap-1 sm:gap-5">
						<h1 class="name gradient-text text-center text-6xl sm:text-8xl break-words">
							آکادمی مالی اورند
						</h1>
						<h3 class="text-gray-300/40 text-2xl sm:text-4xl">کارهات گره خورده؟ بسپارش به اروند!</h3>
					</div>
				</div>
				<div class="flex flex-wrap justify-around gap-5 items-center w-full flex-row-reverse">
					<div>
						<ul class="grid grid-cols-2 gap-5 sm:gap-10">
							<li class="flex items-center text-2xl gap-1 bg-transparent border-[1px] rounded-md px-12 py-2 justify-center cursor-pointer"
								@click="itemsToggle('one')">
								درباره ما
							</li>
							<li
								class="flex items-center text-2xl gap-1 bg-transparent border-[1px] rounded-md px-12 py-2 justify-center cursor-pointer">
								ارتباط با ما
							</li>
							<li
								class="flex items-center text-2xl gap-1 bg-transparent border-[1px] rounded-md px-12 py-2 justify-center cursor-pointer">
								خدمات ما
							</li>
							<li
								class="flex items-center text-2xl gap-1 bg-transparent border-[1px] rounded-md px-12 py-2 justify-center cursor-pointer">
								نمایندگی ها
							</li>
						</ul>
					</div>
					<Transition>
						<div class="max-w-screen-sm text-2xl leading-10" v-if="itemsShow.one">
							ما یک تیم جوان با بیش از ۱۰ سال سابقه
							در زمینه آموزش و خدمات مالی هستیم. از ابتدا هدفمان این بود که دنیای مالی را برای افراد و
							کسب‌وکارها ساده‌تر و هوشمندتر کنیم. ما به دانشجویان و صاحبان مشاغل کمک می‌کنیم تا با یادگیری
							اصول مالی و بهره‌گیری از ابزارهای دیجیتالی، فرایندهای مالی خود را سریع‌تر و مؤثرتر مدیریت
							کنند. تمرکز ما همواره روی ارائه راهکارهای عملی، دوستانه و کاربردی است تا تجربه‌ای متفاوت و
							مطمئن از خدمات مالی برای شما ایجاد کنیم.
						</div>
					</Transition>
				</div>
				<div class="text-white/5">
					<a href="http://imdanieldev.github.io" target="_blank" rel="noopener noreferrer"
						class="cursor-pointer">Designed and Created by Daniel</a>
				</div>
			</div>
		</section>
	</div>
</template>
<script setup>
import { ref } from 'vue';
let itemsShow = ref({
	one: false,
	two: false,
	three: false,
	four: false
});
const itemsToggle = (key) => {
	itemsShow.value[key] = !itemsShow.value[key];
	for (let skey in itemsShow.value) {
		if (skey !== key) {
			itemsShow.value[skey] = false;
		}
	}
}
</script>
<style scoped>
.v-enter-active,
.v-leave-active {
	transition: all 1s ease-in-out;
}

.v-enter-from,
.v-leave-to {
	font-size: 0;
	opacity: 0;
	transform: translateY(100px);
}

.vazirmatn {
	font-family: "Vazirmatn", sans-serif;
	font-optical-sizing: auto;
	font-weight: 400;
	font-style: normal;
}

.gradient-text {
	background-image: linear-gradient(to top, #175472, #3c93be);
	-webkit-background-clip: text;
	background-clip: text;
	-webkit-text-fill-color: transparent;
	color: transparent;
}
</style>
