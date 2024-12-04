<script>
	import { sign } from '$lib/store.js';


</script>

<div id="board">
	<div id="light">
		{$sign}
	</div>
</div>

<style>
    #board {
        overflow: hidden;
        block-size: 100dvh;
    }

    #light {
				font-size: 50dvh;

        color: lemonchiffon;

				user-select: none;
				white-space: nowrap;

				display: inline-block;
				padding-inline: 100%;
				block-size: 100%;
        animation: marquee 3s linear infinite;

				&:active {
					animation-play-state: paused;
				}
    }

    @keyframes marquee {
        0% {
            transform: translateX(0);
        }
        100% {
            transform: translateX(-100%);
        }
    }
</style>