<!--  -->
<template>
    <div ref="container" class="d-flex" style="min-width: 200px; position: relative;">
        <div :style="`width: 100%; height: 100%;padding-right:${resizeShow ? resizeWidth : '0'}`">
            <slot>默认信息</slot>
        </div>
        <!-- 拖拽条 -->
        <div v-if="resizeShow" class="dragbox-resize" :style="`width:${resizeWidth}`" />
    </div>
</template>

<script>
export default {
    props: {
        // 控制拖拽条的是否显示，默认显示
        resizeShow: {
            type: Boolean,
            default: true,
        },
    },
    data() {
        return {
            resizeWidth: "15px",
        };
    },
    methods: {},
};
</script>
<style scoped>
.dragbox-resize {
    position: absolute;
    top: 0;
    right: 0;
    height: 100%;
    cursor: col-resize;
    background-color: #d6d6d6;
}
</style>
