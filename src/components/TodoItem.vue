<template>
    <li class="item">
        <input type="checkbox" v-model="checked">
        <!-- 传递给父组件App.vue checked-->
        <slot name='item' v-bind="{checked}"></slot>
    </li>
</template>

<script>
export default {
    //给标签自定义属性item
    props:['item'],
    data() {
        return {
            checked:false
        }
    }
}
</script>
/* scoped是让样式都是独立存在不会因为重名的类名相互污染 */
<style scoped>
    /*样式也是全局的 */
    .item{
        color: green;
    }
</style>
