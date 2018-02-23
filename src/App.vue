<template>
    <div id="app">
        <div class="cursors">
            <div v-for="(c, i) in cursors" :key="i" :class="c">{{c}}</div>
        </div>
    </div>
</template>

<script>
const cursors = 'auto, default, none, context-menu, help, pointer, progress, wait, cell, crosshair, text, vertical-text, alias, copy, move, no-drop, not-allowed, all-scroll, col-resize, row-resize, n-resize, e-resize, s-resize, w-resize, ne-resize, nw-resize, se-resize, sw-resize, ew-resize, ns-resize, nesw-resize, nwse-resize, zoom-in, zoom-out'.replace(/\s+/g, "").split(',')
cursors.push('custom')

export default {
    name: "App",
    data() {
        return {
            cursors,
        }
    },
    components: {
    }
};
</script>

<style lang="postcss">
*{
    margin: 0;
}
#app{
    min-height: 100vh;
    background: radial-gradient(#edeced, #e9e9ea);
}
.cursors {
    display: flex;
    flex-wrap: wrap;
    & > div{
        flex: 200px;
        padding: 10px 0;
        white-space: nowrap;
        margin: 4px;
        text-align: center;
        background: #fff;
        border-radius: 2px;
        &:hover{
            box-shadow: 0 4px 10px rgba(186, 188, 210, .3);
        }
    }
}

@each $val, $i in auto, default, none, context-menu, help, pointer, progress, wait, cell, crosshair, text, vertical-text, alias, copy, move, no-drop, not-allowed, all-scroll, col-resize, row-resize, n-resize, e-resize, s-resize, w-resize, ne-resize, nw-resize, se-resize, sw-resize, ew-resize, ns-resize, nesw-resize, nwse-resize, zoom-in, zoom-out {
    .$(val) {
        cursor: $(val);
    }
}
.custom{
    cursor: url('./assets/jk.svg'), auto;
}
</style>
