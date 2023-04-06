<script>
	import { Button } from 'flowbite-svelte';
	import { Heading, P, Hr, Img, Card, Label, Input, Checkbox } from 'flowbite-svelte';
</script>

<main class="dark:bg-gray-800 bg-gray-100  dark:text-gray-100">
	<section class="sm:py-20">
		<div class="container flex flex-col justify-center  p-4 mx-auto md:p-8">
			<div class="grid grid-cols-1 gap-4 md:grid-cols-2 aspect-w-4 aspect-h-3">
				<div class="md:order-2">
					<figure class="">
						<img
							src="/images/mission.webp"
							class="h-auto mx-auto rounded w-96 mt-5 md:w-102 lg:w-148"
							alt="mission"
						/>
						<figcaption class="mt-2 text-sm text-center text-gray-500 dark:text-gray-400" />
					</figure>
				</div>
				<div class="md:order-1 ">
					<h2 class="text-center font-bold md:text-left md:text-6xl text-2xl">
						PROGRAMMING IS <span class=" text-purple-600 "> MORE </span> DIFFICULT NOW, JOIN TODAY AND
						BE FREE
					</h2>
					<P
						class="text-md font-normal text-2xl text-center md:text-left  text-gray-900 dark:text-gray-200 py-4"
					>
						Join Asterisc Today and Solidify your IT career
					</P>
					<div class="mx-auto text-center  md:text-left"><Button href="/">Contact Us</Button></div>
				</div>
			</div>
			<Hr class="h-px my-8 bg-gray-200 border-0 dark:bg-gray-700" />
			<div class="grid grid-cols-1 gap-4 md:grid-cols-2 aspect-w-4 aspect-h-3">
				<div class="md:order-2">
					<figure class="">
						<img
							src="/images/mission.webp"
							class="h-auto mx-auto rounded w-96 mt-5 md:w-102 lg:w-148"
							alt="mission"
						/>
						<figcaption class="mt-2 text-sm text-center text-gray-500 dark:text-gray-400" />
					</figure>
				</div>
				<div class="md:order-1 ">
					<Heading class="text-center md:text-left">THE ASTERISC MISSION</Heading>

					<P
						class="text-lg font-normal  text-center md:text-left text-gray-900 dark:text-gray-200 py-4"
					>
						Our Approach for technology Training recognises critical IT Skills which provides early
						and midcareer professionals opportunities to excel in their Careers. We facilitate
						individuals, professionals and entrepreneurs to up skill and retrain their software
						training & development career. The Course curriculum is designed considering key and
						emerging technologies and is advised by Industry Experts. The course enable Raw
						Fresher’s to be industry ready.
					</P>
				</div>
			</div>
			<Hr class="h-px my-8 bg-black-200 border-0 dark:bg-gray-700" />
		</div>
	</section>

	<section id="getstarted" class="  bg-purple-500 dark:bg-purple-500 ">
		<div class="container flex flex-col items-center justify-center p-4 mx-auto md:p-8">
			<Hr class="h-px my-8 bg-gray-200 border-0 dark:bg-gray-700" />

			<h2
				class="mb-4 text-4xl tracking-tight font-semibold text-center text-white dark:text-gray-900"
			>
				Get a free consultation call from our experts
			</h2>
			<h2 class="mb-4 text-2xl tracking-tight font-lg text-white text-center  dark:text-gray-900">
				Take advantage of our free consultation call and let our experts help you to choose the best
				career.
			</h2>

			<Card>
				<form class="flex flex-col justify-center px-9 space-y-6" action="/">
					<Label class="space-y-2">
						<span>Name </span>
						<Input type="text" name="Name" placeholder="Name" required />
					</Label>
					<Label class="space-y-2">
						<span>Email</span>
						<Input type="email" name="email" placeholder="Email" required />
					</Label>
					<Label class="space-y-2">
						<span>Mobile Number</span>
						<Input type="text" name="Mobile Number" placeholder="Mobile Number" required />
					</Label>

					<Button type="submit" class="w-full">Let's Talk</Button>
				</form>
			</Card>
			<Hr class="h-px my-8 bg-gray-200 border-0 dark:bg-gray-700" />
		</div>
	</section>
</main>
