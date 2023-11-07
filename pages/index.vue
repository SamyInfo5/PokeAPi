<template>
    <main>
        <div class="region">
            <button>
                <NuxtLink href="/acceuil">
                    ALL
                </NuxtLink>
            </button>
            <div class="kantho">
                <NuxtLink href="/region/kanto">
                    <h1>kanto</h1>
                    <img src="@/assets/kantho.webp" style="width: 300px;">
                </NuxtLink>
            </div>
            <div class="Jotho">
                <NuxtLink href="">
                    <h1>Jotho</h1>
                    <img src="@/assets/jotho.jpg" style="width: 300px;">
                </NuxtLink>
            </div>
            <div class="Hoenn">
                <NuxtLink href="">
                    <h1>Hoenn</h1>
                    <img src="@/assets/Hoenn.png" style="width: 300px;">
                </NuxtLink>
            </div>
            <div class="Sinnoh">
                <NuxtLink href="">
                    <h1>Sinnoh</h1>
                    <img src="@/assets/Sinnoh.png" style="width: 300px;">
                </NuxtLink>
            </div>
            <div class="Unys">
                <NuxtLink href="">
                    <h1>Unys</h1>
                    <img src="@/assets/Unys.webp" style="width: 300px;">
                </NuxtLink>
            </div>
            <div class="Kalos">
                <NuxtLink href="">
                    <h1>Kalos</h1>
                    <img src="@/assets/Kalos.png" style="width: 300px;">
                </NuxtLink>
            </div>
            <div class="Alola">
                <NuxtLink href="">
                    <h1>Alolah</h1>
                    <img src="@/assets/alola.webp" style="width: 300px;">
                </NuxtLink>
            </div>
            <div class="Galar">
                <NuxtLink href="">
                    <h1>Galar</h1>
                    <img src="@/assets/galar.jpg" style="width: 300px;">
                </NuxtLink>
            </div>
            <div class="Hisui">
                <NuxtLink href="">
                    <h1>Hisui</h1>
                    <img src="@/assets/Hisui.webp" style="width: 300px;">
                </NuxtLink>
            </div>
        </div>
    </main>
</template>

<style scoped>
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    text-decoration: none;
    color: cornflowerblue;
}

body {
    background: url("../assets/bg.jpg");
    background-position: center center;

}

main {
    height: 100vh;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.region {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    text-align: center;

    & div {
        margin: 20px;
    }
}
</style>