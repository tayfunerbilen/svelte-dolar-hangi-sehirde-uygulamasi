<script>
    import cities from "./cities.js"
    import Tabela from "./Tabela.svelte"
    import Current from "./Current.svelte"

    let usd = Math.floor(17.79)

    let prev = cities.find(city => city.id === usd - 1)
    let current = cities.find(city => city.id === usd)
    let next = cities.find(city => city.id === usd + 1)

</script>

<Current current={current} prev={prev} next={next}/>

<div class="mobile-content">
    Dış güçler tarafından mobil görüntülenme engellenmiştir. Lütfen bir bilgisayarda deneyin, tabi bu şartlarda iyi bir bilgisayar alabildiyseniz.
</div>

<div class="road">
    <div class="left">
        <Tabela city={prev}/>
    </div>
    <div class="right">
        <Tabela city={next}/>
    </div>
    <script src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js"></script>
    <div class="truck">
        <lottie-player src="https://assets5.lottiefiles.com/packages/lf20_m7tty33r.json" background="transparent"
                       speed="1" style="width: 1100px; height: 1100px" loop autoplay></lottie-player>
    </div>
</div>

<style>
    .road {
        position: fixed;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 300px;
        background: #000;
        display: flex;
        align-items: center;
    }

    .road::before {
        content: '';
        width: 100%;
        height: 25px;
        background: repeating-linear-gradient(to right, #000 0 50%, #fff 50% 100%);
        background-size: 25%;
        transform: skewX(-20deg);
        animation: 2.5s moveLine infinite linear;
    }

    .left {
        position: absolute;
        top: -50%;
        left: 50px;
        transform: scale(.8);
    }

    .right {
        position: absolute;
        top: -50%;
        right: 50px;
        transform: scale(.8);
    }

    @keyframes moveLine {
        to {
            background-position-x: -100%;
        }
    }

    .truck {
        position: absolute;
        top: -500px;
        left: 100px;
        transform: scale(.7);
    }

    .mobile-content {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 10;
        background: #000;
        color: #fff;
        display: none;
        align-items: center;
        justify-content: center;
        font-size: 30px;
        text-align: center;
        padding: 25px;
        line-height: 1.6;
    }

    @media(max-width: 1000px) {
        .mobile-content {
            display: flex;
        }
        .road {
            display: none;
        }
    }
</style>
