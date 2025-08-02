<script lang="ts">
  import favicon from "$lib/assets/favicon.svg";

  let { children } = $props();
  import ShareBar from './share.svelte';
  import PlayListName from './PlayListTitle.svelte';
  import Viewport from './Viewport.svelte'
</script>

<svelte:head>
  <link rel="icon" href={favicon} />
</svelte:head>
{@render children?.()}


<div class="site_layout">
<div class="box" style="grid-area:empty-tr"> 
	1
</div>
<div class="box" style="grid-area:name"> 
	<PlayListName/>
</div>

<div class="box" style="grid-area:empty-tl"> 
	3
</div>

<div class="box" style="grid-area:social"> 
	<ShareBar/>
</div>

<div class="box" style="grid-area:disc"> 
	<Viewport/>
</div>

<div class="box" style="grid-area:settings"> 
	6
</div>
<div class="box" style="grid-area:empty-br"> 
	7
</div>
<div class="box" style="grid-area:input"> 
	8
</div>
<div class="box" style="grid-area:empty-bl"> 
	9
</div>
</div>

<style>
:global(body){
  margin: 0;
  padding: 1em;
  background-color:grey;
  min-height: 100vh;             
  display: flex;
  align-items: center;          
  justify-content: center;
}

.site_layout{
	display: grid;
	width: clamp(800px, 80vw, 900px);
	height: clamp(800px, 100vh, 1000px);
	margin:auto;
	grid-template-columns: 10% 70% 10%;
	grid-template-rows: 10% 80% 10%;
	grid-template-areas: 
		"empty-tr name name empty-tl"
		"social disc disc settings"
		"empty-br input input empty-bl";

	border: 10px solid brown;
}

.box{
	border: 3px solid black;
	background-color: hsla(172,20%,55%,100%);
	font-size: 2em;
	display: flex;
	justify-content: center; 
	align-items: center; 
}

</style>
