<template>
    <div>
        <button @click="incrementParam()">Increment param</button>
    </div>
</template>

<script setup lang="ts">
    import { useRoute as useRouteVue } from 'vue-router'

    const vueRoute = useRouteVue()
    const nuxtRoute = useRoute()

    const getRouteInfo = (): string => {
        return [
            `useRoute (vue-router): ${vueRoute.fullPath}`,
            `useRoute (nuxt): ${nuxtRoute.fullPath}`,
            `location: ${location.pathname}`
        ].join('\n')
    }

    console.log(`Setup\n${getRouteInfo()}`)

    await useAsyncData(async () => {
        console.log(`Refresh\n${getRouteInfo()}`)
    })

    const incrementParam = async (): Promise<void> => {
        console.log(`Increment param\n${getRouteInfo()}`)
        await navigateTo(`/${Number(nuxtRoute.params.count) + 1}`)
    }
</script>