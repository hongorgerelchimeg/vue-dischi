<template>
  <div id="loader">
            <div l a></div>
            <div l b></div>
            <div l c></div>
            <div l d></div>
            <div l e></div>
            <div l f></div>
            <div l g></div>
            <div l h></div>
           
        </div>
</template>

<script>
export default {
    name: 'PageLoader',
}
</script>

<style scoped lang="scss">
    #loader{
        height:80px;
        width:80px;
        position:relative;
        }[l]{
        position:absolute;
        width:10px;
        height:10px;
        border-radius:50%;
        animation:loader 1.6s linear infinite;
        }
        [a]{left:35px;}
        [b]{right:10px;top:10px;animation-delay:.2s}
        [c]{top:35px;right:0;animation-delay:.4s}
        [d]{right:10px;bottom:10px;animation-delay:.6s}
        [e]{left:35px;bottom:0;animation-delay:.8s}
        [f]{left:10px;bottom:10px;animation-delay:1s}
        [g]{top:35px;left:0;animation-delay:1.2s}
        [h]{left:10px;top:10px;animation-delay:1.4s}
        @keyframes loader{
        0%{
            background:none;
        }
        100%{
            background:white;
        }
    }
</style>