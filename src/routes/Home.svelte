<script>
</script>

<div class="container">
	<div class="content-area">
		<div class="background">
			<!-- <img class="bg" src="/src/lib/images/image 15.jpg" /> -->
			<div class="button-area">
				<div class="button"><a href="\question">เริ่มเลย</a></div>
			</div>
		</div>
	</div>
</div>

<style>
	.background {
		background-image: url('/src/lib/images/image 15.jpg');
		width: 720px;
		height: 1200px;
		background-repeat: no-repeat;
		background-size: auto;
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
	}

	.bg {
		height: -webkit-fill-available;
	}

	.button-area {
		padding: 150px 50px 150px 50px;
	}

	.button {
		font-size: 20px;
		font-weight: bold;
		background-color: #f6c117;
		display: flex;
		padding: 20px;
		border-radius: 50px;
		justify-content: center;
		align-content: center;
		align-items: center;
		color: black;
	}

	.button a {
		color: black;
	}

	@media only screen and (max-width: 720px) {
		.background {
			background-image: url('/src/lib/images/image 15.jpg');
			width: 720px;
			height: 100vh;
			background-repeat: no-repeat;
			background-size: auto;
			display: flex;
			flex-direction: column;
			justify-content: flex-end;
		}

		.bg {
			height: -webkit-fill-available;
		}

		.button-area {
			padding: 150px 50px 150px 50px;
		}
	}
</style>
