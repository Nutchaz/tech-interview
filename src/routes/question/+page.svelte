<script>
	import { page } from '$app/stores';

	var point = [];
	let current = '';
	let current1 = '';
	let current2 = '';
	let name = 'Q1';
	let steptab = 'show';
	let other = '';

	function ShowQuestion(trim) {
		current = '';
		console.log(trim);
		var next_page1 = event.currentTarget.id;
		console.log(next_page1);

		if (next_page1 === 'B1') {
			document.getElementById('p-question1').style.display = 'block';
			document.getElementById('p-question2').style.display = 'none';
			document.getElementById('p-question3').style.display = 'none';
			document.getElementById('p-question4').style.display = 'none';
			document.getElementById('p-question5').style.display = 'none';
			document.getElementById('p-question6').style.display = 'none';
			document.getElementById('p-question7').style.display = 'none';
		} else if (next_page1 === 'Q1') {
			document.getElementById('p-question1').style.display = 'none';
			document.getElementById('p-question2').style.display = 'block';
			document.getElementById('p-question3').style.display = 'none';
			document.getElementById('p-question4').style.display = 'none';
			document.getElementById('p-question5').style.display = 'none';
			document.getElementById('p-question6').style.display = 'none';
			document.getElementById('p-question7').style.display = 'none';
		} else if (next_page1 === 'Q2') {
			document.getElementById('p-question1').style.display = 'none';
			document.getElementById('p-question2').style.display = 'none';
			document.getElementById('p-question3').style.display = 'block';
			document.getElementById('p-question4').style.display = 'none';
			document.getElementById('p-question5').style.display = 'none';
			document.getElementById('p-question6').style.display = 'none';
			document.getElementById('p-question7').style.display = 'none';
		} else if (next_page1 === 'Q3') {
			document.getElementById('p-question1').style.display = 'none';
			document.getElementById('p-question2').style.display = 'none';
			document.getElementById('p-question3').style.display = 'none';
			document.getElementById('p-question4').style.display = 'block';
			document.getElementById('p-question5').style.display = 'none';
			document.getElementById('p-question6').style.display = 'none';
			document.getElementById('p-question7').style.display = 'none';
		} else if (next_page1 === 'Q4') {
			document.getElementById('p-question1').style.display = 'none';
			document.getElementById('p-question2').style.display = 'none';
			document.getElementById('p-question3').style.display = 'none';
			document.getElementById('p-question4').style.display = 'none';
			document.getElementById('p-question5').style.display = 'block';
			document.getElementById('p-question6').style.display = 'none';
			document.getElementById('p-question7').style.display = 'none';
		} else if (next_page1 === 'Q5') {
			document.getElementById('p-question1').style.display = 'none';
			document.getElementById('p-question2').style.display = 'none';
			document.getElementById('p-question3').style.display = 'none';
			document.getElementById('p-question4').style.display = 'none';
			document.getElementById('p-question5').style.display = 'none';
			document.getElementById('p-question6').style.display = 'block';
			document.getElementById('p-question7').style.display = 'none';
		} else if (next_page1 === 'Q6') {
			document.getElementById('p-question1').style.display = 'none';
			document.getElementById('p-question2').style.display = 'none';
			document.getElementById('p-question3').style.display = 'none';
			document.getElementById('p-question4').style.display = 'none';
			document.getElementById('p-question5').style.display = 'none';
			document.getElementById('p-question6').style.display = 'none';
			document.getElementById('p-question7').style.display = 'block';
		} else if (next_page1 === 'Q7') {
			document.getElementById('p-question1').style.display = 'none';
			document.getElementById('p-question2').style.display = 'none';
			document.getElementById('p-question3').style.display = 'none';
			document.getElementById('p-question4').style.display = 'none';
			document.getElementById('p-question5').style.display = 'none';
			document.getElementById('p-question6').style.display = 'none';
			document.getElementById('p-question7').style.display = 'none';
			document.getElementById('p-result1').style.display = 'none';
			document.getElementById('nav').style.display = 'none';
		}
	}

	function getValueChoices() {
		var Choices = event.currentTarget.value;
		var CheckInput = event.currentTarget.name;
		console.log(Choices);
		console.log(CheckInput);

		// point[0] = Choices;

		if (CheckInput === 'answer1') {
			point[0] = parseInt(Choices);
		} else if (CheckInput === 'answer2') {
			point[1] = parseInt(Choices);
		} else if (CheckInput === 'answer3') {
			point[2] = parseInt(Choices);
		} else if (CheckInput === 'answer4') {
			point[3] = parseInt(Choices);
		} else if (CheckInput === 'answer5') {
			point[4] = parseInt(Choices);
		} else if (CheckInput === 'answer6') {
			point[5] = parseInt(Choices);
		} else if (CheckInput === 'answer9') {
			document.getElementById('input-other').style.display = 'block';
		}

		console.log(point);
		console.log(
			'คะแนนรวม',
			point.reduce((a, b) => a + b, 0)
		);
	}

	function result() {
		var allPoint = point.reduce((a, b) => a + b, 0);
		if (allPoint > '131') {
			document.getElementById('p-question7').style.display = 'none';
			document.getElementById('p-result1').style.display = 'block';
		} else if (allPoint > '91') {
			document.getElementById('p-question7').style.display = 'none';
			document.getElementById('p-result2').style.display = 'block';
		} else if (allPoint < '90') {
			document.getElementById('p-question7').style.display = 'none';
			document.getElementById('p-result3').style.display = 'block';
		}
	}

	function backpage() {
		if (Home) window.history.back();
	}
</script>

<div class="content-area">
	<div id="nav" class="tap-step" class:none={steptab === 'hide'}>
		<div class="container">
			<div class="progress-container">
				<div class="progress" id="progress"></div>
				<div class="step" class:step-active={name === 'Q1'}></div>
				<div class="step" class:step-active={name === 'Q2'}></div>
				<div class="step" class:step-active={name === 'Q3'}></div>
				<div class="step" class:step-active={name === 'Q4'}></div>
				<div class="step" class:step-active={name === 'Q5'}></div>
				<div class="step" class:step-active={name === 'Q6'}></div>
				<div class="step" class:step-active={name === 'Q7'}></div>
			</div>
		</div>
	</div>

	<!-- question1 -->
	<div id="p-question1" class="content show">
		<div class="area">
			<h1>Q1</h1>
			<h2 class="topic">ถ้าวันนี้เป็นวันหยุด คุณจะ...</h2>
			<div class="choices">
				<button
					class="choice"
					id="choice_1_1"
					value="10"
					name="answer1"
					class:active={current === '1'}
					on:click={() => getValueChoices((current = '1'))}
				>
					นอนเล่น พักผ่อน
				</button>
				<button
					class="choice"
					id="choice_1_2"
					value="20"
					name="answer1"
					class:active={current === '2'}
					on:click={() => getValueChoices((current = '2'))}
				>
					ดูหนัง ดูซีรี่ส์ เล่นเกม
				</button>
				<button
					class="choice"
					id="choice_1_3"
					value="30"
					name="answer1"
					class:active={current === '3'}
					on:click={() => getValueChoices((current = '3'))}
				>
					เรียนรู้อะไรใหม่ ๆ
				</button>
			</div>
		</div>
		<div class="button-area">
			<button class="button back" on:click={() => history.back()}>กลับ</button>
			<button id="Q1" class="button next" on:click={() => ShowQuestion((name = 'Q2'))}>ต่อไป</button
			>
		</div>
	</div>

	<!-- question2 -->
	<div id="p-question2" class="content">
		<div class="area">
			<h1>Q2</h1>
			<h2 class="topic">คุณต้องการพัฒนาภาษาอังกฤษเพื่ออะไร?</h2>
			<div class="choices">
				<button
					class="choice"
					id="choice_2_1"
					value="30"
					name="answer2"
					class:active={current === '1'}
					on:click={() => getValueChoices((current = '1'))}
				>
					การทำงาน
				</button>
				<button
					class="choice"
					id="choice_2_2"
					value="10"
					name="answer2"
					class:active={current === '2'}
					on:click={() => getValueChoices((current = '2'))}
				>
					เที่ยวต่างประเทศ
				</button>
				<button
					class="choice"
					id="choice_2_3"
					value="20"
					name="answer2"
					class:active={current === '3'}
					on:click={() => getValueChoices((current = '3'))}
				>
					ใช้ในชีวิตประจำวัน
				</button>
			</div>
		</div>
		<div class="button-area">
			<button id="B1" class="button back" on:click={() => ShowQuestion((name = 'Q1'))}>กลับ</button>
			<button id="Q2" class="button next" on:click={() => ShowQuestion((name = 'Q3'))}>ต่อไป</button
			>
		</div>
	</div>

	<!-- question3 -->
	<div id="p-question3" class="content">
		<div class="area">
			<h1>Q3</h1>
			<h2 class="topic">สไตล์การเรียนภาษาอังกฤษของคุณ เป็นแบบไหน?</h2>
			<div class="choices">
				<button
					class="choice"
					id="choice_3_1"
					value="30"
					name="answer3"
					class:active={current === '1'}
					on:click={() => getValueChoices((current = '1'))}
				>
					เรียนคอร์สออนไลน์ / โรงเรียนสอนภาษา
				</button>
				<button
					class="choice"
					id="choice_3_2"
					value="20"
					name="answer3"
					class:active={current === '2'}
					on:click={() => getValueChoices((current = '2'))}
				>
					เรียนด้วยตนเอง เช่น อ่านหนังสือ ดูหนัง ฟังเพลง
				</button>
				<button
					class="choice"
					id="choice_3_3"
					value="10"
					name="answer3"
					class:active={current === '3'}
					on:click={() => getValueChoices((current = '3'))}
				>
					คุยกับเพื่อนต่างชาติ / ไปเที่ยวต่างประเทศ
				</button>
			</div>
		</div>
		<div class="button-area">
			<button id="Q1" class="button back" on:click={() => ShowQuestion((name = 'Q2'))}>กลับ</button>
			<button id="Q3" class="button next" on:click={() => ShowQuestion((name = 'Q4'))}>ต่อไป</button
			>
		</div>
	</div>

	<!-- question4 -->
	<div id="p-question4" class="content">
		<div class="area">
			<h1>Q4</h1>
			<h2 class="topic">คุณใช้ภาษาอังกฤษบ่อยแค่ไหน?</h2>
			<div class="choices">
				<button
					class="choice"
					id="choice_4_1"
					value="30"
					name="answer4"
					class:active={current === '1'}
					on:click={() => getValueChoices((current = '1'))}
				>
					เป็นประจำทุกวัน
				</button>
				<button
					class="choice"
					id="choice_4_2"
					value="10"
					name="answer4"
					class:active={current === '2'}
					on:click={() => getValueChoices((current = '2'))}
				>
					เป็นบางครั้ง
				</button>
				<button
					class="choice"
					id="choice_4_3"
					value="20"
					name="answer4"
					class:active={current === '3'}
					on:click={() => getValueChoices((current = '3'))}
				>
					นาน ๆ ที / ไม่ได้ใช้เลย
				</button>
			</div>
		</div>
		<div class="button-area">
			<button id="Q2" class="button back" on:click={() => ShowQuestion((name = 'Q3'))}>กลับ</button>
			<button id="Q4" class="button next" on:click={() => ShowQuestion((name = 'Q5'))}>ต่อไป</button
			>
		</div>
	</div>

	<!-- question5 -->
	<div id="p-question5" class="content">
		<div class="area">
			<h1>Q5</h1>
			<h2 class="topic">คุณอยากพัฒนาสกิลภาษาอังกฤษ สกิลไหนมากที่สุด?</h2>
			<div class="choices">
				<button
					class="choice"
					id="choice_5_1"
					value="20"
					name="answer5"
					class:active={current === '1'}
					on:click={() => getValueChoices((current = '1'))}
				>
					การฟัง
				</button>
				<button
					class="choice"
					id="choice_5_2"
					value="10"
					name="answer5"
					class:active={current === '2'}
					on:click={() => getValueChoices((current = '2'))}
				>
					การพูด
				</button>
				<button
					class="choice"
					id="choice_5_3"
					value="30"
					name="answer5"
					class:active={current === '3'}
					on:click={() => getValueChoices((current = '3'))}
				>
					การเขียน
				</button>
			</div>
		</div>
		<div class="button-area">
			<button id="Q3" class="button back" on:click={() => ShowQuestion((name = 'Q4'))}>กลับ</button>
			<button id="Q5" class="button next" on:click={() => ShowQuestion((name = 'Q6'))}>ต่อไป</button
			>
		</div>
	</div>

	<!-- question6 -->
	<div id="p-question6" class="content">
		<div class="area">
			<h1>Q6</h1>
			<h2 class="topic">อยากเรียนภาษาอังกฤษ แต่...</h2>
			<div class="choices">
				<button
					class="choice"
					id="choice_6_1"
					value="20"
					name="answer6"
					class:active={current === '1'}
					on:click={() => getValueChoices((current = '1'))}
				>
					ไม่มีเวลา
				</button>
				<button
					class="choice"
					id="choice_6_2"
					value="10"
					name="answer6"
					class:active={current === '2'}
					on:click={() => getValueChoices((current = '2'))}
				>
					เนื้อหาไม่น่าสนใจ / สอนไม่สนุก
				</button>
				<button
					class="choice"
					id="choice_6_3"
					value="30"
					name="answer6"
					class:active={current === '3'}
					on:click={() => getValueChoices((current = '3'))}
				>
					ไม่มั่นใจ
				</button>
			</div>
		</div>
		<div class="button-area">
			<button id="Q4" class="button back" on:click={() => ShowQuestion((name = 'Q5'))}>กลับ</button>
			<button id="Q6" class="button next" on:click={() => ShowQuestion((name = 'Q7'))}>ต่อไป</button
			>
		</div>
	</div>

	<!-- question7 -->
	<div id="p-question7" class="content">
		<div class="area">
			<h1>Q7</h1>
			<h2 class="topic">คุณรู้จัก Globish ผ่านช่องทางใด (เลือกได้มากกว่า 1 ข้อ)</h2>
			<div class="choices">
				<button
					class="choice"
					id="choice_3_1"
					value="Instagram"
					name="Instagram"
					class:active={current === '1'}
					on:click={() => getValueChoices((current = '1'))}
				>
					Instagram
				</button>
				<button
					class="choice"
					id="choice_3_2"
					value="Facebook"
					name="Facebook"
					class:active={current1 === '2'}
					on:click={() => getValueChoices((current1 = '2'))}
				>
					Facebook
				</button>
				<button
					class="choice"
					id="choice_3_3"
					value=""
					name="answer9"
					class:active={current2 === '3'}
					on:click={() => getValueChoices((current2 = '3'))}
				>
					อื่นๆ (โปรดระบุ)
				</button>
				<input id="input-other" class="input none" bind:value={other} placeholder="โปรดระบุ" />
			</div>
		</div>
		<div class="button-area">
			<button id="Q5" class="button back" on:click={() => ShowQuestion((name = 'Q6'))}>กลับ</button>
			<button id="Q7" class="button next" on:click={() => result((steptab = 'hide'))}
				>ดูผลลัพธ์</button
			>
		</div>
	</div>

	<!-- result1 -->
	<div id="p-result1" class="content">
		<div class="area-result">
			<div class="result">
				<h1>ผลลัพธ์ของคุณคือ</h1>
				<img class="img-result" src="/src/lib/images/image 12.jpg" />
				<p class="font">คุณรู้จัก Globisg ผ่าน</p>
				<p class="font">{other || ''}</p>
			</div>
		</div>
	</div>

	<!-- result2 -->
	<div id="p-result2" class="content">
		<div class="area-result">
			<div class="result">
				<h1>ผลลัพธ์ของคุณคือ</h1>
				<img class="img-result" src="/src/lib/images/image 13.jpg" />
				<p class="font">คุณรู้จัก Globisg ผ่าน</p>
				<p class="font">{other || ''}</p>
			</div>
		</div>
	</div>

	<!-- result3 -->
	<div id="p-result3" class="content">
		<div class="area-result">
			<div class="result">
				<h1>ผลลัพธ์ของคุณคือ</h1>
				<img class="img-result" src="/src/lib/images//image 14.jpg" />
				<p class="font">คุณรู้จัก Globisg ผ่าน</p>
				<p class="font">{other || ''}</p>
			</div>
		</div>
	</div>
</div>

<style>
	.font {
		font-size: 30px;
		font-weight: bold;
	}
	.result {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
	.img-result {
		width: 100%;
	}
	.area-result {
		height: 60vh;
		display: flex;
		flex-direction: column;
		background-color: #fff;
		border-radius: 30px;
		margin: 50px;
		border: solid;
		border-color: black;
		/* padding: 0px 50px 0px 50px; */
	}

	.none,
	#p-question2,
	#p-question3,
	#p-question4,
	#p-question5,
	#p-question6,
	#p-question7,
	#p-result1,
	#p-result2,
	#p-result3 {
		display: none;
	}

	.content-area {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 720px;
		height: 1200px;
		flex-direction: column;
		background: #39b7e8;
	}

	.content {
		width: 720px;
	}

	.container {
		padding: 0px 40px 0px 40px;
	}

	.area {
		height: 55vh;
		display: flex;
		flex-direction: column;
		background-color: #fff;
		border-radius: 30px;
		margin: 50px;
		border: solid;
		border-color: black;
		padding: 0px 50px 0px 50px;
	}

	.topic {
		font-size: 20px;
		font-weight: bold;
	}

	.button-area {
		display: flex;
		justify-content: center;
		margin: 50px;
	}

	.button {
		display: flex;
		padding: 20px;
		border-radius: 50px;
		justify-content: center;
		align-content: center;
		align-items: center;
		background-color: #fff;
		color: black;
		width: 100%;
		border: solid;
	}

	.button a {
		color: black;
	}

	.active {
		background-color: #ef7b4b !important;
		border: solid;
		border-color: black !important;
	}
	.step-active {
		background-color: black !important;
		border: solid;
	}

	.back {
		width: 30%;
		margin-right: 30px;
		background-color: #fff;
		cursor: pointer;
	}

	.next {
		background-color: #f6c117;
		cursor: pointer;
	}

	.choice {
		width: 100%;
		font-size: 20px;
		font-weight: bold;
		display: flex;
		padding: 40px;
		border: solid;
		border-color: #f5f5f5;
		background: #fff;
		border-radius: 30px;
		margin: 30px 0px 30px 0px;
		cursor: pointer;
	}

	.input {
		border: none;
		width: 100%;
		border-bottom: solid #f5f5f5;
		padding: 40px 0px 40px 0px;
		font-size: 20px;
		font-weight: bold;
	}

	.tap-step {
		width: 720px;
	}

	.progress-container {
		display: flex;
		justify-content: space-between;
		position: relative;
		margin-bottom: 30px;
		max-width: 100%;
	}

	.progress-container::before {
		content: '';
		background-color: var(--line-border-empty);
		position: absolute;
		top: 50%;
		left: 0;
		transform: translateY(-50%);
		height: 4px;
		width: 100%;
		z-index: -1;
	}

	.progress {
		background-color: var(--line-border-fill);
		position: absolute;
		top: 50%;
		left: 0;
		transform: translateY(-50%);
		height: 4px;
		width: 0%;
		z-index: -1;
		transition: 0.4s ease;
	}

	.step {
		background-color: #fff;
		color: #999;
		height: 20px;
		width: 85px;
		border-radius: 10px;
		display: flex;
		align-items: center;
		justify-content: center;
		border: 3px solid var(--line-border-empty);
		transition: 0.4s ease;
	}

	.step.active {
		border-color: var(--line-border-fill);
	}

	@media only screen and (max-width: 720px) {
		.content-area {
			display: flex;
			justify-content: center;
			align-items: center;
			width: 720px;
			height: 100vh;
			flex-direction: column;
			background: #39b7e8;
		}

		.area-result {
			height: 80vh;
			display: flex;
			flex-direction: column;
			background-color: #fff;
			border-radius: 30px;
			margin: 50px;
			border: solid;
			border-color: black;
			/* padding: 0px 50px 0px 50px; */
		}

		.area {
		height: 65vh;
		display: flex;
		flex-direction: column;
		background-color: #fff;
		border-radius: 30px;
		margin: 50px;
		border: solid;
		border-color: black;
		padding: 0px 50px 0px 50px;
	}
	}
</style>
