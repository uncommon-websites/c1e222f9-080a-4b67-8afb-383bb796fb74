<svelte:head>
	<title>BL Wellness - Acupuncture & Traditional Chinese Medicine in Ellicott City, MD</title>
	<meta name="description" content="Experience pain relief through authentic TCM treatments covered by insurance. Licensed acupuncturist serving Ellicott City with extended hours. Call 301-795-5888." />
</svelte:head>

<script lang="ts">
	import { onMount } from 'svelte';

	// Icons
	const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;
	const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
	const PlayCircle = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>`;
	const Plus = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>`;
	const Check = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>`;
	const Instagram = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>`;
	const Linkedin = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>`;
	const XIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 18"/></svg>`;

	let faqs = [
		{ question: "Does BL Wellness accept my insurance?", open: false },
		{ question: "What is traditional Chinese medicine (TCM)?", open: false },
		{ question: "Does acupuncture hurt?", open: false },
		{ question: "How many treatments will I need?", open: false },
		{ question: "What conditions can acupuncture treat?", open: false }
	];

	function toggleFaq(index: number) {
		faqs = faqs.map((faq, i) => {
			if (i === index) return { ...faq, open: !faq.open };
			return faq;
		});
	}
</script>

<div class="min-h-screen flex flex-col font-sans text-gray-900 bg-[#FAFAFA]">
	<!-- Top Banner -->
	<div class="bg-black text-white text-[11px] font-medium py-3 text-center tracking-wide px-4">
		Now accepting CareFirst, Aetna, United Healthcare & Optum insurance • Extended hours available
	</div>

	<!-- Navigation -->
	<nav class="flex items-center justify-between px-6 md:px-12 py-5 bg-[#FAFAFA]">
		<div class="flex items-center gap-3">
			<!-- Logo -->
			<div class="flex items-center gap-3">
				<div class="w-8 h-8 text-primary-600">
					<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M6.99251 12.196C6.85314 12.5757 6.62925 12.9208 6.33682 13.2067H6.33835C6.00191 13.5351 5.58566 13.7756 5.12816 13.9059C4.67065 14.0362 4.18671 14.0522 3.72118 13.9523C3.25564 13.8524 2.82357 13.64 2.46501 13.3345C2.10645 13.0291 1.83299 12.6406 1.66998 12.2051C1.50697 11.7696 1.45969 11.3012 1.5325 10.8432C1.60532 10.3852 1.79587 9.95244 2.08653 9.58516C2.37718 9.21781 2.75852 8.9277 3.1952 8.74177C3.63188 8.55585 4.10979 8.48002 4.58462 8.52142L4.57074 8.50792C5.0567 8.54782 5.54575 8.48407 6.00378 8.32124C6.4618 8.15846 6.87776 7.90043 7.2226 7.56521C7.56746 7.22998 7.83285 6.82564 8.00036 6.38041C8.16786 5.93517 8.23344 5.45976 8.1924 4.98737L8.20628 5.00087C8.15181 4.43594 8.27796 3.86844 8.56753 3.37575C8.85701 2.88307 9.29579 2.48919 9.82407 2.24782C10.3523 2.00645 10.9443 1.92933 11.5192 2.02701C12.0942 2.12467 12.6243 2.39237 13.037 2.79358C13.4497 3.19479 13.7251 3.70999 13.8256 4.26892C13.926 4.82785 13.8467 5.4033 13.5984 5.9168C13.3501 6.4303 12.9449 6.85685 12.4381 7.13828C11.9313 7.41971 11.3474 7.54233 10.7663 7.4894L10.781 7.5029C10.2949 7.46279 9.80563 7.52632 9.34741 7.68904C8.88919 7.85176 8.47309 8.10975 8.12805 8.44499C7.78301 8.78025 7.51742 9.18466 7.34983 9.63001C7.18224 10.0754 7.11669 10.551 7.15774 11.0235L7.14309 11.01C7.1833 11.4112 7.13189 11.8162 6.99251 12.196ZM11.5077 14.7121L11.493 14.6986C11.9061 14.739 12.3232 14.6897 12.7143 14.5543C13.1053 14.4188 13.4605 14.2007 13.7542 13.9154C14.0477 13.6302 14.2726 13.285 14.4121 12.905C14.5518 12.525 14.6028 12.1196 14.5615 11.718L14.5762 11.7315C14.5351 11.2591 14.6007 10.7838 14.7681 10.3385C14.9356 9.89327 15.2011 9.48893 15.5459 9.15368C15.8908 8.8185 16.3068 8.56042 16.7648 8.39767C17.2228 8.23481 17.7118 8.17111 18.1978 8.21099L18.1832 8.19749C18.7645 8.25059 19.3485 8.12801 19.8556 7.84656C20.3627 7.56511 20.7681 7.13845 21.0165 6.62479C21.265 6.11114 21.3444 5.53548 21.2439 4.97634C21.1435 4.4172 20.868 3.9018 20.4551 3.50044C20.0422 3.09909 19.512 2.8313 18.9368 2.73364C18.3616 2.63596 17.7695 2.71315 17.241 2.95467C16.7126 3.19618 16.2737 3.59027 15.9842 4.08319C15.6946 4.57609 15.5685 5.14383 15.6232 5.70895L15.6093 5.6947C15.6504 6.16712 15.585 6.64259 15.4175 7.08788C15.2501 7.53318 14.9846 7.93758 14.6398 8.27287C14.2949 8.60805 13.8789 8.86612 13.4208 9.02888C12.9627 9.19163 12.4736 9.25523 11.9876 9.21526L12.0015 9.22951C11.5885 9.18908 11.1713 9.23836 10.7803 9.37381C10.3893 9.50919 10.034 9.72744 9.74039 10.0127C9.44674 10.2979 9.22199 10.6431 9.08234 11.0231C8.94276 11.4031 8.89176 11.8085 8.93304 12.2101L8.91915 12.1966C8.96005 12.6689 8.89439 13.1443 8.72688 13.5895C8.5593 14.0346 8.29389 14.4389 7.94908 14.7741C7.60425 15.1093 7.18835 15.3673 6.73039 15.5302C6.27242 15.693 5.78342 15.7569 5.29749 15.7171L5.31138 15.7306C4.73003 15.6775 4.14599 15.8001 3.63892 16.0815C3.13186 16.363 2.72644 16.7896 2.478 17.3033C2.22954 17.817 2.15013 18.3926 2.25061 18.9518C2.35109 19.5109 2.62657 20.0263 3.03945 20.4276C3.45234 20.829 3.98253 21.0968 4.55773 21.1944C5.13293 21.2921 5.72512 21.2149 6.25353 20.9734C6.78193 20.7319 7.22085 20.3379 7.51038 19.8449C7.79994 19.352 7.92601 18.7843 7.87139 18.2191L7.88605 18.2326C7.845 17.7602 7.91058 17.2849 8.07809 16.8396C8.24551 16.3944 8.511 15.99 8.85581 15.6548C9.20069 15.3196 9.61664 15.0615 10.0746 14.8988C10.5327 14.7359 11.0217 14.6722 11.5077 14.7121ZM17.1996 10.7633C16.9071 11.0493 16.6832 11.3944 16.5437 11.7741C16.4042 12.1538 16.3526 12.5587 16.3925 12.9601L16.3786 12.9466C16.4197 13.419 16.3541 13.8944 16.1866 14.3396C16.0191 14.7849 15.7537 15.1892 15.4089 15.5244C15.064 15.8596 14.648 16.1177 14.19 16.2804C13.732 16.4433 13.2429 16.507 12.757 16.4671L12.7708 16.4806C12.1896 16.4281 11.6057 16.551 11.0989 16.8328C10.5921 17.1145 10.1871 17.5414 9.93902 18.0551C9.69097 18.5689 9.61188 19.1444 9.71265 19.7035C9.81349 20.2625 10.0892 20.7777 10.5022 21.1788C10.9152 21.5799 11.4454 21.8474 12.0205 21.9448C12.5957 22.0423 13.1877 21.9649 13.716 21.7234C14.2443 21.4817 14.683 21.0877 14.9724 20.5947C15.2618 20.1018 15.3878 19.5342 15.3332 18.9692L15.3478 18.9827C15.3068 18.5103 15.3723 18.0349 15.5398 17.5896C15.7073 17.1444 15.9728 16.7401 16.3176 16.4048C16.6625 16.0696 17.0784 15.8115 17.5364 15.6488C17.9945 15.486 18.4835 15.4222 18.9695 15.4621L18.9548 15.4486C19.4296 15.4901 19.9076 15.4144 20.3444 15.2286C20.7811 15.0427 21.1625 14.7527 21.4533 14.3854C21.744 14.0181 21.9347 13.5854 22.0075 13.1274C22.0805 12.6694 22.0332 12.2009 21.8703 11.7653C21.7073 11.3298 21.4339 10.9413 21.0754 10.6358C20.7168 10.3303 20.2848 10.1178 19.8192 10.0179C19.3536 9.91795 18.8697 9.93385 18.4121 10.0641C17.9546 10.1945 17.5383 10.4349 17.2019 10.7633H17.1996Z"
							fill="currentColor"
						/>
					</svg>
				</div>
				<span class="text-xl font-bold tracking-tight">BL Wellness</span>
			</div>
		</div>
		<div class="hidden md:flex items-center gap-8 text-[13px] font-medium text-gray-600">
			<a href="#services" class="hover:text-black transition-colors">Services</a>
			<a href="#insurance" class="hover:text-black transition-colors">Insurance</a>
			<a href="#about" class="hover:text-black transition-colors">About</a>
			<a href="#faq" class="hover:text-black transition-colors">FAQ</a>
			<a href="tel:301-795-5888" class="bg-black text-white px-5 py-2 rounded text-[13px] font-medium hover:bg-gray-800 transition-colors">Call: 301-795-5888</a>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="flex flex-col items-center pt-16 pb-20 px-4 text-center">
		<h1 class="text-4xl md:text-[56px] leading-[1.1] font-medium tracking-tight max-w-3xl mb-6">
			Pain relief through<br>traditional Chinese medicine.
		</h1>
		<p class="text-gray-500 text-[15px] max-w-xl mb-8 leading-relaxed">
			Experience authentic acupuncture and TCM treatments covered by your insurance. Serving Ellicott City with extended hours Monday-Saturday.
		</p>
		<div class="flex flex-col sm:flex-row gap-4 mb-20">
			<a href="tel:301-795-5888" class="bg-black text-white px-6 py-3 rounded text-[13px] font-medium hover:bg-gray-800 transition-colors">
				Book Appointment
			</a>
			<a href="#insurance" class="bg-white border border-gray-200 text-black px-6 py-3 rounded text-[13px] font-medium hover:bg-gray-50 transition-colors">
				Check Insurance
			</a>
		</div>

		<!-- Hero Image -->
		<div class="w-full max-w-[1200px] overflow-hidden relative mt-12">
			<div class="rounded-[32px] overflow-hidden shadow-2xl">
				<img src="/generated/image-professional-acupuncture-treatment-sessi-1765686594193-0.webp" alt="Professional acupuncture treatment" class="w-full h-auto object-cover" />
			</div>
		</div>
	</section>

	<!-- Treatment Modalities -->
	<section id="services" class="py-24 px-6 md:px-12 flex justify-center">
		<div class="bg-white rounded-[32px] p-12 md:p-20 flex flex-col md:flex-row items-center gap-16 max-w-[1200px] w-full shadow-sm">
			<!-- Image -->
			<div class="relative w-full md:w-[480px] rounded-[24px] overflow-hidden shadow-xl flex-shrink-0">
				<img src="/generated/image-close-up-of-cupping-therapy-treatment-on-1765686598447-2.webp" alt="Cupping therapy treatment" class="w-full h-auto object-cover" />
			</div>

			<!-- Content -->
			<div class="flex-1 max-w-lg">
				<h2 class="text-3xl font-medium mb-6 leading-tight">
					Comprehensive traditional Chinese medicine treatments.
				</h2>
				<p class="text-gray-500 text-[15px] mb-8 leading-relaxed">
					We offer a full range of TCM modalities, customized to your specific condition and health goals. Each treatment plan combines multiple techniques for optimal healing.
				</p>
				<ul class="space-y-3 text-sm text-gray-600">
					<li class="flex gap-3">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						Acupuncture with electrical stimulation
					</li>
					<li class="flex gap-3">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						Cupping therapy and Gua Sha
					</li>
					<li class="flex gap-3">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						Therapeutic massage and Tuina
					</li>
					<li class="flex gap-3">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						Foot reflexology and acupressure
					</li>
					<li class="flex gap-3">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						Traditional Chinese herbal remedies
					</li>
					<li class="flex gap-3">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						Moxibustion and ear seeds
					</li>
				</ul>
			</div>
		</div>
	</section>

	<!-- Benefits Grid -->
	<section class="py-20 px-6 md:px-12 max-w-[1400px] mx-auto w-full">
		<div class="flex flex-col md:flex-row justify-between items-start mb-16 gap-10">
			<h2 class="text-4xl md:text-5xl font-medium tracking-tight max-w-md leading-[1.1]">
				Healing that addresses the root cause.
			</h2>
			<p class="text-gray-500 text-[15px] max-w-md leading-relaxed">
				Traditional Chinese medicine treats your body as an interconnected system, not just isolated symptoms. Our approach combines ancient wisdom with modern understanding to provide lasting relief and improved wellness.
			</p>
		</div>

		<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
			<!-- Card 1 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="/generated/image-peaceful-acupuncture-clinic-interior-cle-1765686600436-3.webp" alt="Peaceful clinic interior" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Chronic pain relief.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Effective treatment for back pain, neck pain, arthritis, migraines, and other persistent conditions.</p>
				</div>
			</div>
			<!-- Card 2 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="/generated/image-acupuncturist-performing-foot-reflexolog-1765686604518-5.webp" alt="Reflexology treatment" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Stress and anxiety reduction.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Natural approaches to calm your nervous system and restore emotional balance.</p>
				</div>
			</div>
			<!-- Card 3 -->
			<div class="relative h-[480px] rounded-[32px] overflow-hidden group">
				<img src="/generated/image-middle-aged-suburban-professional-woman--1765686602455-4.webp" alt="Happy patient" class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex flex-col justify-end p-8 text-white">
					<h3 class="text-2xl font-medium mb-2">Overall wellness support.</h3>
					<p class="text-sm text-white/80 leading-relaxed">Improve sleep, digestion, energy levels, and immune function through holistic treatment.</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Testimonial -->
	<section class="py-24 px-6 text-center bg-[#F5F5F3]">
		<div class="max-w-3xl mx-auto">
			<blockquote class="text-2xl md:text-3xl font-medium leading-tight mb-10">
				"After years of chronic back pain and trying everything Western medicine offered, I was skeptical about acupuncture. But Weidong's treatments have given me my life back. I'm sleeping better, moving freely, and finally feeling like myself again."
			</blockquote>
			<div class="flex flex-col items-center gap-3">
				<img src="/generated/image-middle-aged-suburban-professional-woman--1765686602455-4.webp" alt="Patient testimonial" class="w-12 h-12 rounded-full object-cover" />
				<div class="text-sm">
					<div class="font-bold">Sarah M.</div>
					<div class="text-gray-500">Ellicott City Patient</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Process Steps -->
	<section class="py-20 px-6 md:px-12 max-w-[1400px] mx-auto w-full border-b border-gray-200">
		<div class="grid grid-cols-1 md:grid-cols-3 gap-12">
			<div>
				<h3 class="text-xl font-medium mb-2">Initial consultation.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">Comprehensive assessment of your condition, health history, and treatment goals.</p>
			</div>
			<div>
				<h3 class="text-xl font-medium mb-2">Customized treatment plan.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">Personalized combination of TCM techniques tailored to your specific needs.</p>
			</div>
			<div>
				<h3 class="text-xl font-medium mb-2">Ongoing care and support.</h3>
				<p class="text-sm text-gray-500 leading-relaxed">Regular treatments with progress tracking to ensure optimal healing outcomes.</p>
			</div>
		</div>
	</section>

	<!-- About Section -->
	<section id="about" class="py-24 px-6 md:px-12 max-w-[1400px] mx-auto w-full">
		<div class="bg-white rounded-[32px] p-12 md:p-20 flex flex-col lg:flex-row items-center gap-16 shadow-sm">
			<!-- Practitioner Image -->
			<div class="relative w-full lg:w-[400px] rounded-[24px] overflow-hidden shadow-xl flex-shrink-0">
				<img src="/generated/image-older-chinese-male-acupuncturist-with-ge-1765686596404-1.webp" alt="Weidong Li, Licensed Acupuncturist" class="w-full h-auto object-cover" />
			</div>

			<!-- Content -->
			<div class="flex-1">
				<h2 class="text-3xl font-medium mb-6 leading-tight">
					Meet Weidong Li, Licensed Acupuncturist
				</h2>
				<div class="space-y-4 text-gray-600 text-[15px] leading-relaxed">
					<p>
						Weidong brings decades of experience studying and practicing traditional Chinese medicine across multiple countries. His unique perspective comes from deep training in both Eastern and Western medical approaches.
					</p>
					<p>
						After experiencing the limitations of Western medicine firsthand, Weidong dedicated himself to bridging the gap between these two worlds. He understands the skepticism many suburban communities have toward TCM, and takes special care to explain treatments in ways that resonate with Western patients.
					</p>
					<p>
						His practice philosophy is simple: combine the ancient wisdom of Chinese medicine with modern understanding to provide effective, personalized care. Every treatment plan is customized to address not just symptoms, but the underlying imbalances causing your condition.
					</p>
					<p class="font-medium text-black">
						Licensed and experienced in treating a wide range of conditions, from chronic pain to stress management, digestive issues, and overall wellness optimization.
					</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Insurance & Location Cards -->
	<section id="insurance" class="py-10 px-6 md:px-12 max-w-[1400px] mx-auto w-full">
		<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
			<!-- Insurance Card -->
			<div class="bg-[#111] rounded-[32px] p-10 md:p-12 text-white min-h-[400px] flex flex-col justify-between relative overflow-hidden">
				<div class="relative z-10">
					<div class="text-xs text-gray-400 mb-2">Insurance accepted.</div>
					<h3 class="text-2xl font-medium mb-8 max-w-xs">We accept most major insurance plans.</h3>
					<div class="space-y-3 text-sm">
						<div class="flex items-center gap-2">
							<span class="text-primary-400">{@html Check}</span>
							<span>CareFirst Blue Cross Blue Shield (in-network)</span>
						</div>
						<div class="flex items-center gap-2">
							<span class="text-primary-400">{@html Check}</span>
							<span>Aetna (in-network)</span>
						</div>
						<div class="flex items-center gap-2">
							<span class="text-primary-400">{@html Check}</span>
							<span>United Healthcare (in-network)</span>
						</div>
						<div class="flex items-center gap-2">
							<span class="text-primary-400">{@html Check}</span>
							<span>Optum (in-network)</span>
						</div>
						<div class="flex items-center gap-2">
							<span class="text-primary-400">{@html Check}</span>
							<span>All other insurances (out-of-network)</span>
						</div>
					</div>
				</div>
				<p class="text-xs text-gray-400 mt-8 relative z-10">Call us to verify your specific coverage and benefits.</p>
			</div>
			<!-- Location Card -->
			<div class="bg-[#111] rounded-[32px] p-10 md:p-12 text-white min-h-[400px] flex flex-col justify-between relative overflow-hidden">
				<div class="relative z-10">
					<div class="text-xs text-gray-400 mb-2">Convenient location & hours.</div>
					<h3 class="text-2xl font-medium mb-8 max-w-xs">Extended hours to fit your schedule.</h3>
					<div class="space-y-6">
						<div>
							<div class="text-xs text-gray-400 mb-1">ADDRESS</div>
							<div class="text-sm">10320 B Baltimore National Pike<br>Centennial Square Office Park<br>Ellicott City, MD 21042</div>
						</div>
						<div>
							<div class="text-xs text-gray-400 mb-1">HOURS</div>
							<div class="text-sm">Monday - Saturday: 10am - 10pm<br>Sunday: By appointment</div>
						</div>
						<div>
							<div class="text-xs text-gray-400 mb-1">CONTACT</div>
							<div class="text-sm">Phone: <a href="tel:301-795-5888" class="hover:text-primary-400 transition-colors">301-795-5888</a><br>Email: <a href="mailto:acupressurereflexology@gmail.com" class="hover:text-primary-400 transition-colors">acupressurereflexology@gmail.com</a></div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Insurance & Pricing Section -->
	<section class="py-24 px-6 md:px-12 max-w-[1400px] mx-auto w-full text-center">
		<h2 class="text-3xl md:text-4xl font-medium mb-4">Affordable care through insurance coverage.</h2>
		<p class="text-gray-500 text-sm max-w-lg mx-auto mb-16">
			Most treatments are covered by insurance, making traditional Chinese medicine accessible and affordable. We handle the paperwork so you can focus on healing.
		</p>

		<div class="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-4xl mx-auto">
			<!-- Insurance Covered -->
			<div class="bg-white rounded-[32px] p-8 text-left flex flex-col shadow-sm border-2 border-primary-100 relative overflow-hidden">
                <div class="absolute top-0 right-0 bg-primary-100 text-primary-700 text-[10px] font-bold px-3 py-1 rounded-bl-xl">MOST POPULAR</div>
				<div class="w-10 h-10 bg-primary-50 rounded-lg mb-6 flex items-center justify-center text-primary-600">
					{@html Check}
				</div>
				<h3 class="text-xl font-bold mb-1">Insurance Covered</h3>
				<p class="text-xs text-gray-500 mb-6">Use your health insurance benefits.</p>
				
				<div class="flex items-baseline gap-1 mb-1">
					<span class="text-2xl font-bold">$0-50</span>
					<span class="text-xs text-gray-500">copay per visit</span>
				</div>
				<div class="text-[10px] text-gray-400 mb-8">Actual cost depends on your specific insurance plan and benefits.</div>

				<ul class="space-y-4 mb-8 flex-1">
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						Full coverage for acupuncture treatments
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						Multiple sessions per year typically covered
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						We bill your insurance directly
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-primary-600 shrink-0">{@html Check}</span>
						In-network with major carriers
					</li>
				</ul>

				<a href="tel:301-795-5888" class="w-full bg-black text-white py-3 rounded-lg text-xs font-bold hover:bg-gray-800 transition-colors text-center block">Verify Coverage</a>
			</div>

			<!-- Self-Pay -->
			<div class="bg-white rounded-[32px] p-8 text-left flex flex-col shadow-sm">
				<div class="w-10 h-10 bg-gray-100 rounded-lg mb-6"></div>
				<h3 class="text-xl font-bold mb-1">Self-Pay</h3>
				<p class="text-xs text-gray-500 mb-6">Pay directly without insurance.</p>
				
				<div class="flex items-baseline gap-1 mb-1">
					<span class="text-2xl font-bold">$80-150</span>
					<span class="text-xs text-gray-500">per session</span>
				</div>
				<div class="text-[10px] text-gray-400 mb-8">Pricing varies based on treatment type and duration.</div>

				<ul class="space-y-4 mb-8 flex-1">
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-gray-400 shrink-0">{@html Check}</span>
						All treatment modalities available
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-gray-400 shrink-0">{@html Check}</span>
						Flexible scheduling options
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-gray-400 shrink-0">{@html Check}</span>
						Package discounts available
					</li>
					<li class="flex gap-3 text-xs text-gray-600">
						<span class="text-gray-400 shrink-0">{@html Check}</span>
						Same quality care and attention
					</li>
				</ul>

				<a href="tel:301-795-5888" class="w-full bg-white border border-gray-200 text-black py-3 rounded-lg text-xs font-bold hover:bg-gray-50 transition-colors text-center block">Book Appointment</a>
			</div>
		</div>
	</section>

	<!-- FAQ Section -->
	<section id="faq" class="py-20 px-6 md:px-12 max-w-3xl mx-auto w-full">
		<h2 class="text-3xl font-medium text-center mb-16">Your questions answered.</h2>
		<div class="space-y-4">
			{#each faqs as faq, i}
				<button 
					class="w-full flex items-center justify-between p-4 text-left hover:bg-gray-100 rounded-lg transition-colors group"
					onclick={() => toggleFaq(i)}
				>
					<span class="text-sm font-medium text-gray-800">{faq.question}</span>
					<span class="text-gray-400 transition-transform duration-200 {faq.open ? 'rotate-45' : ''}">{@html Plus}</span>
				</button>
                {#if faq.open}
                    <div class="px-4 pb-4 text-xs text-gray-500 leading-relaxed">
                        {#if i === 0}
							We accept CareFirst Blue Cross Blue Shield, Aetna, United Healthcare, and Optum as in-network providers. We also accept all other health insurances as out-of-network. Call us at 301-795-5888 to verify your specific coverage.
                        {:else if i === 1}
							Traditional Chinese Medicine (TCM) is a comprehensive healing system that has been practiced for thousands of years. It views the body as an interconnected system and uses techniques like acupuncture, herbal medicine, and massage to restore balance and promote natural healing.
                        {:else if i === 2}
							Most patients report minimal to no discomfort. Acupuncture needles are extremely thin—much finer than needles used for injections. You may feel a slight tingling or dull ache, which indicates the treatment is working. Many patients find the experience deeply relaxing.
                        {:else if i === 3}
							Treatment duration varies by condition. Acute issues may improve in 3-6 sessions, while chronic conditions typically require 8-12 sessions for lasting results. We'll create a personalized treatment plan and adjust based on your progress.
                        {:else if i === 4}
							Acupuncture effectively treats chronic pain (back, neck, arthritis), migraines, stress and anxiety, insomnia, digestive issues, sports injuries, and many other conditions. During your consultation, we'll assess whether TCM is appropriate for your specific needs.
                        {/if}
                    </div>
                {/if}
			{/each}
		</div>
		<div class="text-center mt-12">
			<a href="tel:301-795-5888" class="inline-block bg-white border border-gray-200 px-6 py-3 rounded text-xs font-medium hover:bg-gray-50 transition-colors">
				Call with More Questions
			</a>
		</div>
	</section>

	<!-- Footer -->
	<footer class="bg-[#F5F5F3] py-16 px-6 md:px-12 text-[11px] text-gray-500">
		<div class="max-w-[1400px] mx-auto">
			<div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-12 gap-8">
				<div class="flex items-center gap-3">
					<div class="w-8 h-8 text-primary-600">
						<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path
								fill-rule="evenodd"
								clip-rule="evenodd"
								d="M6.99251 12.196C6.85314 12.5757 6.62925 12.9208 6.33682 13.2067H6.33835C6.00191 13.5351 5.58566 13.7756 5.12816 13.9059C4.67065 14.0362 4.18671 14.0522 3.72118 13.9523C3.25564 13.8524 2.82357 13.64 2.46501 13.3345C2.10645 13.0291 1.83299 12.6406 1.66998 12.2051C1.50697 11.7696 1.45969 11.3012 1.5325 10.8432C1.60532 10.3852 1.79587 9.95244 2.08653 9.58516C2.37718 9.21781 2.75852 8.9277 3.1952 8.74177C3.63188 8.55585 4.10979 8.48002 4.58462 8.52142L4.57074 8.50792C5.0567 8.54782 5.54575 8.48407 6.00378 8.32124C6.4618 8.15846 6.87776 7.90043 7.2226 7.56521C7.56746 7.22998 7.83285 6.82564 8.00036 6.38041C8.16786 5.93517 8.23344 5.45976 8.1924 4.98737L8.20628 5.00087C8.15181 4.43594 8.27796 3.86844 8.56753 3.37575C8.85701 2.88307 9.29579 2.48919 9.82407 2.24782C10.3523 2.00645 10.9443 1.92933 11.5192 2.02701C12.0942 2.12467 12.6243 2.39237 13.037 2.79358C13.4497 3.19479 13.7251 3.70999 13.8256 4.26892C13.926 4.82785 13.8467 5.4033 13.5984 5.9168C13.3501 6.4303 12.9449 6.85685 12.4381 7.13828C11.9313 7.41971 11.3474 7.54233 10.7663 7.4894L10.781 7.5029C10.2949 7.46279 9.80563 7.52632 9.34741 7.68904C8.88919 7.85176 8.47309 8.10975 8.12805 8.44499C7.78301 8.78025 7.51742 9.18466 7.34983 9.63001C7.18224 10.0754 7.11669 10.551 7.15774 11.0235L7.14309 11.01C7.1833 11.4112 7.13189 11.8162 6.99251 12.196ZM11.5077 14.7121L11.493 14.6986C11.9061 14.739 12.3232 14.6897 12.7143 14.5543C13.1053 14.4188 13.4605 14.2007 13.7542 13.9154C14.0477 13.6302 14.2726 13.285 14.4121 12.905C14.5518 12.525 14.6028 12.1196 14.5615 11.718L14.5762 11.7315C14.5351 11.2591 14.6007 10.7838 14.7681 10.3385C14.9356 9.89327 15.2011 9.48893 15.5459 9.15368C15.8908 8.8185 16.3068 8.56042 16.7648 8.39767C17.2228 8.23481 17.7118 8.17111 18.1978 8.21099L18.1832 8.19749C18.7645 8.25059 19.3485 8.12801 19.8556 7.84656C20.3627 7.56511 20.7681 7.13845 21.0165 6.62479C21.265 6.11114 21.3444 5.53548 21.2439 4.97634C21.1435 4.4172 20.868 3.9018 20.4551 3.50044C20.0422 3.09909 19.512 2.8313 18.9368 2.73364C18.3616 2.63596 17.7695 2.71315 17.241 2.95467C16.7126 3.19618 16.2737 3.59027 15.9842 4.08319C15.6946 4.57609 15.5685 5.14383 15.6232 5.70895L15.6093 5.6947C15.6504 6.16712 15.585 6.64259 15.4175 7.08788C15.2501 7.53318 14.9846 7.93758 14.6398 8.27287C14.2949 8.60805 13.8789 8.86612 13.4208 9.02888C12.9627 9.19163 12.4736 9.25523 11.9876 9.21526L12.0015 9.22951C11.5885 9.18908 11.1713 9.23836 10.7803 9.37381C10.3893 9.50919 10.034 9.72744 9.74039 10.0127C9.44674 10.2979 9.22199 10.6431 9.08234 11.0231C8.94276 11.4031 8.89176 11.8085 8.93304 12.2101L8.91915 12.1966C8.96005 12.6689 8.89439 13.1443 8.72688 13.5895C8.5593 14.0346 8.29389 14.4389 7.94908 14.7741C7.60425 15.1093 7.18835 15.3673 6.73039 15.5302C6.27242 15.693 5.78342 15.7569 5.29749 15.7171L5.31138 15.7306C4.73003 15.6775 4.14599 15.8001 3.63892 16.0815C3.13186 16.363 2.72644 16.7896 2.478 17.3033C2.22954 17.817 2.15013 18.3926 2.25061 18.9518C2.35109 19.5109 2.62657 20.0263 3.03945 20.4276C3.45234 20.829 3.98253 21.0968 4.55773 21.1944C5.13293 21.2921 5.72512 21.2149 6.25353 20.9734C6.78193 20.7319 7.22085 20.3379 7.51038 19.8449C7.79994 19.352 7.92601 18.7843 7.87139 18.2191L7.88605 18.2326C7.845 17.7602 7.91058 17.2849 8.07809 16.8396C8.24551 16.3944 8.511 15.99 8.85581 15.6548C9.20069 15.3196 9.61664 15.0615 10.0746 14.8988C10.5327 14.7359 11.0217 14.6722 11.5077 14.7121ZM17.1996 10.7633C16.9071 11.0493 16.6832 11.3944 16.5437 11.7741C16.4042 12.1538 16.3526 12.5587 16.3925 12.9601L16.3786 12.9466C16.4197 13.419 16.3541 13.8944 16.1866 14.3396C16.0191 14.7849 15.7537 15.1892 15.4089 15.5244C15.064 15.8596 14.648 16.1177 14.19 16.2804C13.732 16.4433 13.2429 16.507 12.757 16.4671L12.7708 16.4806C12.1896 16.4281 11.6057 16.551 11.0989 16.8328C10.5921 17.1145 10.1871 17.5414 9.93902 18.0551C9.69097 18.5689 9.61188 19.1444 9.71265 19.7035C9.81349 20.2625 10.0892 20.7777 10.5022 21.1788C10.9152 21.5799 11.4454 21.8474 12.0205 21.9448C12.5957 22.0423 13.1877 21.9649 13.716 21.7234C14.2443 21.4817 14.683 21.0877 14.9724 20.5947C15.2618 20.1018 15.3878 19.5342 15.3332 18.9692L15.3478 18.9827C15.3068 18.5103 15.3723 18.0349 15.5398 17.5896C15.7073 17.1444 15.9728 16.7401 16.3176 16.4048C16.6625 16.0696 17.0784 15.8115 17.5364 15.6488C17.9945 15.486 18.4835 15.4222 18.9695 15.4621L18.9548 15.4486C19.4296 15.4901 19.9076 15.4144 20.3444 15.2286C20.7811 15.0427 21.1625 14.7527 21.4533 14.3854C21.744 14.0181 21.9347 13.5854 22.0075 13.1274C22.0805 12.6694 22.0332 12.2009 21.8703 11.7653C21.7073 11.3298 21.4339 10.9413 21.0754 10.6358C20.7168 10.3303 20.2848 10.1178 19.8192 10.0179C19.3536 9.91795 18.8697 9.93385 18.4121 10.0641C17.9546 10.1945 17.5383 10.4349 17.2019 10.7633H17.1996Z"
								fill="currentColor"
							/>
						</svg>
					</div>
					<span class="text-lg font-bold tracking-tight text-black">BL Wellness</span>
				</div>
				<div class="flex flex-wrap gap-6 font-medium text-gray-600">
					<a href="#services" class="hover:text-black">Services</a>
					<a href="#insurance" class="hover:text-black">Insurance</a>
					<a href="#about" class="hover:text-black">About</a>
					<a href="#faq" class="hover:text-black">FAQ</a>
					<a href="tel:301-795-5888" class="hover:text-black">Contact</a>
				</div>
				<div class="flex flex-col gap-2 text-right">
					<a href="tel:301-795-5888" class="text-black hover:text-primary-600 font-medium">301-795-5888</a>
					<a href="mailto:acupressurereflexology@gmail.com" class="text-xs hover:text-primary-600">acupressurereflexology@gmail.com</a>
				</div>
			</div>
			
			<div class="space-y-4 leading-relaxed opacity-60">
				<p><strong>BL Wellness</strong> • 10320 B Baltimore National Pike, Centennial Square Office Park, Ellicott City, MD 21042</p>
				<p>Weidong Li is a licensed acupuncturist providing traditional Chinese medicine services. All treatments are provided by licensed practitioners. Services do not replace medical care or consultations with a licensed physician. If you have questions about your health condition, consult your primary care physician. Information provided is for general informational purposes only.</p>
				<p>Insurance coverage and benefits vary by plan. Contact us to verify your specific coverage. Some services may require additional payments beyond insurance coverage.</p>
			</div>
		</div>
	</footer>
</div>

<style>
    /* Hide scrollbar for horizontal scroll */
    .overflow-hidden::-webkit-scrollbar {
        display: none;
    }
</style>

