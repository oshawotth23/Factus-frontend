<template>
    <q-layout view="hhh LpR fFf">
        <q-drawer v-model="leftDrawerOpen" side="left" behavior="mobile" bordered>
            <q-img class="absolute-top" src="https://cdn.quasar.dev/img/material.png"
                style="height: 150px; background-color: #1d1d1d">
                <div class="absolute-bottom bg-transparent">
                    <q-avatar size="56px" class="q-mb-sm">
                        <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                    </q-avatar>
                    <div class="text-weight-bold">Razvan Stoenescu</div>
                    <div>@rstoenescu</div>
                </div>
            </q-img>
            <q-scroll-area style="height: calc(100% - 150px); margin-top: 150px; border-right: 1px solid #ddd">
                <q-list padding>
                    <q-item clickable v-ripple to="/inicio" active-class="my-menu-link" exact>
                        <q-item-section avatar>
                            <q-icon name="home" />
                        </q-item-section>
                        <q-item-section>Inicio</q-item-section>
                    </q-item>
                </q-list>
            </q-scroll-area>
        </q-drawer>
        <q-page-container>
            <router-view />
        </q-page-container>
        <q-footer elevated class="bg-purple-9 text-white">
            <q-toolbar>
                <q-toolbar-title>
                    <div class="text-footer">Copyright - 2025 © Todos los derechos reservados</div>
                </q-toolbar-title>
            </q-toolbar>
        </q-footer>
    </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'
const router = useRouter()
const leftDrawerOpen = ref(false)
function toggleLeftDrawer() {
    leftDrawerOpen.value = !leftDrawerOpen.value
}
function logout() {
    router.replace('/')
}
</script>

<style scoped>
#header-main {
    background-color: rgb(2, 21, 38);
    color: white;
}

.logo {
    width: 50px;
}

.text-footer {
    font-size: 14px; 
    color: rgb(255, 255, 255);
    text-align: center;
    font-weight: bold;
}

.material-symbols-outlined {
    font-size: 18px;
    vertical-align: middle;
}

.my-menu-link {
    color: white;
    background-color: rgba(2, 21, 38, 0.37);
}
</style>
