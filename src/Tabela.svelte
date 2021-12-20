<script>
    export let city
</script>

<div class="tabela">
    <h1>{city.name}</h1>
    <p>
        1 DOLAR = {city.id} TL
    </p>
</div>

<style>
.tabela {
    width: 250px;
    height: 120px;
    background: blue;
    color: #fff;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    border-radius: 10px;
    box-shadow: 0 0 0 4px #fff inset;
    border: 6px solid blue;
    position: relative;
}
.tabela::before,
.tabela::after {
    content: '';
    width: 10px;
    height: 120px;
    background: #ccc;
    position: absolute;
    top: calc(100% + 6px);
    left: 25px;
}
.tabela::after {
    left: auto;
    right: 25px;
}
.tabela h1 {
    font-size: 30px;
    font-weight: 600;
    margin-bottom: 10px;
}
.tabela p {
    font-size: 17px;
    font-weight: 500;
    opacity: .8;
}
</style>
