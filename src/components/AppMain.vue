<template>
    <div class="containerMain">
        <div class="headMain">
            <p>Found 39 card</p>
        </div>

        <div class="containerBox">
            <div class="box">
                <div class="boxImg"></div>
                <div class="boxText"></div>
            </div>

            <div class="box">
                <div class="boxImg"></div>
                <div class="boxText">
                    <p>prova</p>
                </div>
            </div>
            <div class="box">
                <div class="boxImg"></div>
                <div class="boxText"></div>
            </div>
            <div class="box">
                <div class="boxImg"></div>
                <div class="boxText"></div>
            </div>
            <div class="box">
                <div class="boxImg"></div>
                <div class="boxText"></div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

.containerMain{
    max-width: 1680px;
    height: 1000px;
    background-color: white;
    padding: 70px;
}

.headMain{
    padding: 1rem;
    background-color: #222;
    color: white;
}

.containerBox{
    display: flex;
    flex-wrap: wrap;
}

.box{
    width: calc(100% / 5);
    height: 520px;
    border: 1px solid black;
}

.boxImg{
    width: 100%;
    height: 400px;
    border: 1px solid black;
}

</style>