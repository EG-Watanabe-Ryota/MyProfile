<script>
	import Greeting from "./Greeting.svelte";
	import Card from "./Card.svelte";
	import Marquee from "./Marquee.svelte";
	import { text } from "svelte/internal";
	document.oncontextmenu = function(){alert('右クリックは禁止です！やめてください！'); return false}
</script>

<!--本当は以下のHTML部分はindex.htmlに移した方がいいのかもしれない...-->
<div class="main-wrapper">
	<div class="menu">
		<div class="img">
			<!-- svelte-ignore a11y-missing-attribute -->
			<img src="ダウンロード.png">
		</div>
		<ul>
			<li>トップ</li>
			<li><a href="profile.html">プロフィール</a></li>
			<!-- svelte-ignore a11y-invalid-attribute -->
			<li><a href="">掲示板</a></li>
			<!-- svelte-ignore a11y-invalid-attribute -->
			<li><a href="">リンク集</a></li>
		</ul>
	</div>

	<div class="top">
		<div class="title">
			<h1>ようこそ渡邊良太のホームページへ！</h1>
			<h2>Welcome to Watanabe's HP!</h2>
		</div>
			<div class="content">
				<Marquee text="Welcome to My HomePage!!" size="60" color="red"/>
				<p class="yukkuri">ゆっくりしていってね</p>
				<p class="jpn">Sorry,This HomePage is Japanese only!</p>
				<p class="cnt">あなたは<span>365</span>人目の来訪者です。キリ番ゲットした方は<a href="">掲示板</a>で報告してください。キリ番踏み逃げ禁止！</p>
				<!-- svelte-ignore a11y-invalid-attribute -->
				<p><a href="">★★相互リンク募集中です。無断リンクは禁止です★★</a></p>
				<!-- svelte-ignore a11y-missing-attribute -->
				<img src="neko.png" height="200px" width="200px">
				<p>↑我が家のネコちゃんです</p>
			</div>
		</div>
	</div>
<style>
	  
</style>