<script>
    import { onMount } from "svelte";
    export let text; //表示する文字列(親コンポーネントから渡される)
    export let size; //文字列のサイズ(親コンポーネントから渡される)
    export let color;//文字列の色(親コンポーネントから渡される)
    let style = "";
    const resize = () => {
        //Math.trunc()は引数の値の小数部の桁を取り除いて整数部を返す。
        // 画面幅と文字列全体の幅から、文字が流れる速度を決める
        //durationの値が小さくなるほど流れる速度が速くなる
        const duration = Math.trunc(window.innerWidth / 60) + text.length / 10;

        // フォントサイズが変わるならここを適宜調整する
        const textWidth = text.length * 100;
        style = `animation-duration:${duration}s;` + `width:${textWidth}px;` + `font-size: ${size}px;` + `color: ${color};`;
    };
    onMount(() => {
      resize();
    });
  </script>

    <svelte:window on:resize={resize} />
    <div class="marquee">
        <div class="marquee_text" {style}>{text}</div>
    </div>
  
  <style>
    .marquee {
        width: 100vw;
        height: 80px;
        overflow: hidden;
        position: relative;
        right: 30px;
        top: 5px;
      
    }
    .marquee_text {
        padding-left: 100%;
        padding-bottom:500px;
        animation-name: marquee;
        animation-timing-function: linear;
        animation-iteration-count: infinite;
    }
    @keyframes marquee {
      from {
        transform: translate(0%);
      }
      100%,
      to {
        transform: translate(-100%);
      }
    }
  </style>
  
  
