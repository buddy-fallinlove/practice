<template>
<div>
    <top @add='add'></top>
</div>
</template>

<script>
import Top from ''
import Item from '../components/eew/Item.vue'
import Foot from '../components/eew/Foot.vue'
export default {
    name: '',
    props: {},
    components: {
        Top,
        Item,
        Foot
    },
    data() {
        return {
            todos: [{
                    title: '吃饭',
                    complete: false
                },
                {
                    title: '睡觉',
                    complete: false
                },
                {
                    title: '敲代码',
                    complete: false
                }
            ]
        }
    },
    methods: {
        add(data) {
            this.todos.push(data)
        }
    },
    mounted() {

    },
    watch: {

    },
    computed: {

    }
}
</script>

<style scoped lang='scss'>

</style>
