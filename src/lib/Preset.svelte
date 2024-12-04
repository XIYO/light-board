<script>
	import { sign } from '$lib/store.js';
	import { goto } from '$app/navigation';

	const preset = [
		'네',
		'네?',
		'아니요',
		'아니요?',
		'🤔 생각중입니다.',
		'잠시만요.',
		'🤫 비밀입니다.'
	];

	const handleClick = (e) => {
		$sign = e.target.textContent;
		goto('/display');
	};

	const handleKeydown = (e) => {
		if (e.key === 'Enter') {
			$sign = e.target.value;
			goto('/display');
		}
	};
</script>

<div id="board">
	<div id="buttons">
		{#each preset as p}
			<button onclick={handleClick}>{p}</button>
		{/each}
	</div>
	<div id="input-area">
		<label>메시지 : <input type="text" placeholder="입력 후 엔터" onkeydown={handleKeydown} /></label>
	</div>
</div>

<style>
    /* 버튼 스타일 */
    button {
        background-color: black;
        color: lemonchiffon;
        border: none;
        border-radius: 12px; /* 모서리 둥글게 */
        padding: 10px 20px; /* 버튼 크기 조정 */
        margin: 8px; /* 버튼 간격 */
        font-size: 16px; /* 텍스트 크기 */
        cursor: pointer;
        transition: background-color 0.3s ease, transform 0.2s ease; /* 애니메이션 */
    }

    button:hover {
        background-color: lemonchiffon;
        color: black;
        transform: scale(1.05); /* 호버 시 살짝 확대 */
    }

    button:active {
        transform: scale(0.95); /* 클릭 시 살짝 축소 */
    }

    /* 전체 배치 스타일 */
    #board {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        block-size: 100dvh;
        background-color: #575757;
        overflow: hidden;
        gap: 20px; /* 요소 간격 */
        padding: 20px;
    }

    /* 버튼 배치 */
    #buttons {
        display: flex;
        flex-wrap: wrap; /* 버튼이 화면 밖으로 나가지 않게 줄 바꿈 */
        justify-content: center;
        gap: 12px; /* 버튼 사이 간격 */
    }

    /* 입력 영역 스타일 */
    #input-area {
        margin-top: 20px;
    }

    label {
        color: lemonchiffon;
        font-size: 16px;
    }

    input {
        border: 1px solid lemonchiffon;
        border-radius: 8px;
        padding: 5px 10px;
        font-size: 16px;
        background-color: black;
        color: lemonchiffon;
        outline: none;
        transition: border-color 0.3s ease;
    }

    input:focus {
        border-color: white;
    }

    button {
        font-family: "Jua", sans-serif;
        font-weight: 400;
        font-style: normal;
    }
</style>
