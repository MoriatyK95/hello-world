<script lang="ts"> 
    let { 
        name 
    } :{
        name: string
    } = $props();
</script>

<h1> Hello {name}</h1>
<h1> {name.replaceAll('k', 't')}</h1>

<style>

</style>