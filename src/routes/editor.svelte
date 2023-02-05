<script>
    import Ribbon from "./ribbon.svelte";
   export let value="<strong><i>Type the HTML code here...</i></strong>";
</script>

<div class="parent">
    <div class="left child">
        <Ribbon />
        <textarea bind:value={value} ></textarea>
    </div>
    <div class="right child">
        {@html (value)}  
    </div>
</div>


<style>
	textarea { 
        width: 96%; 
        height: 360px;
        resize: none; 
        border: none;
        outline: none;
        margin: 10px;
    }
    
    .parent{
        margin-top: 20px;
        width: 100%;
    }
   
    .child{
        height:400px;
        width: 47%;
        display: inline-block;
        vertical-align: middle;
        margin-left: 25px;
        overflow-wrap:break-word;
        background-color: white;
    }
    .right{
        padding:10px;
    }
</style>
