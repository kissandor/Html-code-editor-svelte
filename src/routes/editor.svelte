<script>
    let value="Hello";
</script>

<div class="parent">
    <div class="left child">
        <textarea bind:value={value} ></textarea>
    </div>
    <div class="right child">
        {@html (value)}  
    </div>
</div>


<style>
	textarea { 
        width: 99%; 
        height: 390px;
        resize: none; 
        border: none;
        outline: none;
    }
   
    .child{
        height:400px;
        width: 48%;
        display: inline-block;
        vertical-align: middle;
        margin: 10px;
        overflow-wrap:break-word;
        background-color: white;
    }
</style>
