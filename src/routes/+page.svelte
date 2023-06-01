<script>
	let unixToTime = (unix) => {
		let date = new Date(unix * 1000);
		let gun = date.getDate();
		let ay = date.getMonth() + 1;
		let yil = date.getFullYear();
		return gun + '/' + ay + '/' + yil;
	};

	let secimDate = 1841864401 * 1000;
	let now = Date.now();

	let kalan = secimDate - now;

	setInterval(() => {
		kalan = secimDate - Date.now();
	}, 1000);
</script>

<div class="calendar">
	<h1>Seçime</h1>
	<div>
		<span>
			{Math.floor(kalan / (1000 * 60 * 60 * 24))} gün
		</span>
		<span>
			{Math.floor((kalan % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))} saat
		</span>
		<span>
			{Math.floor((kalan % (1000 * 60 * 60)) / (1000 * 60))} dakika
		</span>
		<span>
			{Math.floor((kalan % (1000 * 60)) / 1000)} saniye
		</span>
	</div>
	<h1>kaldı</h1>
</div>

<head>
	<title>Seçime Kalan Süre</title>
	<meta charset="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1" />

	<meta name="description" content="Seçime Kalan Süre" />
	<meta
		name="keywords"
		content="seçim, seçimler,
    seçime kalan süre, seçime kalan süre sorgulama, seçime kalan süre sorgulama, seçime kalan süre sorgulama,
    seçime kalan süre sorgulama, seçime kalan süre sorgulama,
    "
	/>

	<meta property="og:title" content="Seçime Kalan Süre" />
	<meta property="og:description" content="Seçime Kalan Süre" />
</head>

<style lang="scss">
	:global(body) {
		background-color: #131619;
		margin: 0;
		padding: 0;
		height: 100vh;

		display: flex;
		justify-content: center;
		align-items: center;
	}
	.calendar {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		background-color: #1e2124;
		border-radius: 1rem;
		padding: 1rem;
		color: #fff;
		font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		font-size: 1.5rem;
		box-shadow: 0 0 1rem #000;
		width: 100%;
		max-width: 500px;
		margin: 0 1rem;

		& > div {
			display: flex;
			flex-direction: row;
			justify-content: center;
			align-items: center;
			margin: 0 1rem;
			gap: 1rem;
		}

		& > h1 {
			margin: 0 1rem;
		}

		& > div > span {
			margin: 0.5rem 0;

			&:nth-child(1) {
				color: #ff0000;
			}

			&:nth-child(2) {
				color: #ff7f00;
			}

			&:nth-child(3) {
				color: #ffff00;
			}

			&:nth-child(4) {
				color: #00ff00;
			}
		}
	}
</style>
