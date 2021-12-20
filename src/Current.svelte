<script>
    export let prev
    export let current
    export let next
</script>

<div class="current">
    <h3>DOLAR HANGİ ŞEHİRDE?</h3>
    <ul>
        <li>
            Dış güçler tarafından <strong>{prev.name}</strong> şubesinden kargoya verildi.
        </li>
        <li>
            Allahın izniyle <strong>{current.name}</strong> şubesine ulaştı.
        </li>
        <li>
            Bir sonraki hedefi olan <strong>{next.name}</strong> şubesine doğru yola çıktı.
        </li>
    </ul>
</div>

<style>
    .current {
        width: 600px;
        position: absolute;
        top: 0;
        max-width: 100%;
        padding: 15px;
        left: 50%;
        border-radius: 0 0 15px 15px;
        box-shadow: 0 10px 15px 0 rgba(0, 0, 0, .2);
        transform: translateX(-50%);
        background: #fff;
    }

    .current h3 {
        text-align: center;
        font-size: 35px;
        font-weight: 300;
        margin-bottom: 15px;
    }

    .current ul li {
        border-bottom: 1px solid #ddd;
        padding: 10px 0;
    }

    .current ul li:last-child {
        border: none;
    }
</style>
