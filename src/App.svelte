<script lang="ts">
	import Header from "./Components/Header.svelte";
	import Home from "./Components/Home.svelte";
	import About from "./Components/About.svelte";
	import Skill from "./Components/Skills.svelte";
	import Stack from "./Components/Stack.svelte";
	import Projects from "./Components/Projects.svelte";
	import Contact from "./Components/Contact.svelte";
	import Footer from "./Components/Footer.svelte";


	let navBg = false;

	window.onscroll = function () {
		navBg = window.scrollY >= 80;
	}

</script>

<style>

</style>


<main>
	<Header navBg={navBg}/>
	<Home/>
	<About/>
	<Skill/>
	<Stack/>
	<Projects/>
	<Contact/>
	<Footer/>
</main>
