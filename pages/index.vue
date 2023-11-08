<template>
    <header>
        <img src="/assets/logo.png" alt="">
    </header>
    <main>
        <button>
            <NuxtLink href="/acceuil">
                ALL
            </NuxtLink>
        </button>
        <div class="region">
            <div class="card">
                <NuxtLink href="/region/kanto">
                    <h1>kanto</h1>
                    <img src="@/assets/kantho.webp">
                </NuxtLink>
            </div>
            <div class="card">
                <NuxtLink href="/region/johto">
                    <h1>Jotho</h1>
                    <img src="@/assets/jotho.jpg">
                </NuxtLink>
            </div>
            <div class="card">
                <NuxtLink href="/region/hoenn">
                    <h1>Hoenn</h1>
                    <img src="@/assets/Hoenn.png">
                </NuxtLink>
            </div>
            <div class="card">
                <NuxtLink href="/region/sinnoh">
                    <h1>Sinnoh</h1>
                    <img src="@/assets/Sinnoh.png">
                </NuxtLink>
            </div>
            <div class="card">
                <NuxtLink href="/region/unova">
                    <h1>Unys</h1>
                    <img src="@/assets/Unys.webp">
                </NuxtLink>
            </div>
            <div class="card">
                <NuxtLink href="/region/kalos">
                    <h1>Kalos</h1>
                    <img src="@/assets/Kalos.png">
                </NuxtLink>
            </div>
            <div class="card">
                <NuxtLink href="/region/alola">
                    <h1>Alolah</h1>
                    <img src="@/assets/alola.webp">
                </NuxtLink>
            </div>
            <div class="card">
                <NuxtLink href="/region/galar">
                    <h1>Galar</h1>
                    <img src="@/assets/galar.jpg">
                </NuxtLink>
            </div>
            <div class="card">
                <NuxtLink href="/region/hisui">
                    <h1>Hisui</h1>
                    <img src="@/assets/Hisui.webp">
                </NuxtLink>
            </div>
        </div>
    </main>
    <ul>
        <li><img class="pikachu" src="/assets/pikachuu.png" alt=""></li>
    </ul>
</template>



<style>
@import url("~/assets/style/home.css");

main{
    position: relative;
}

body{
    overflow: hidden;
}

.pikachu {
    height: 60%;
    width: 30%;
    position: absolute;
    bottom: 0;
    right: 0;
}
</style>