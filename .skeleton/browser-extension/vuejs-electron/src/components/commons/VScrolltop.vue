<template>
    <v-fab-transition>
        <v-btn fab dark fixed bottom right
               color="red"
               v-scroll="onScroll"
               v-show="fab"
               @click="toTop">
            <v-icon>keyboard_arrow_up</v-icon>
        </v-btn>
    </v-fab-transition>

</template>
<script>
    export default {
        name: 'v-scrolltop',
        data: () => ({
            fab: false
        }),
        methods: {
            onScroll() {
                if (typeof window === 'undefined') return
                const top = window.pageYOffset ||
                    document.documentElement.offsetTop ||
                    0
                this.fab = top > 300
            },
            toTop() {
                this.$router.push({hash: ''})
                window.scrollTo(0, 0)
            }
        }
    }
</script>