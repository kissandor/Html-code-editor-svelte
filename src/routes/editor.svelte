<script>
   export let value="<strong><i>Type the HTML code here...</i></strong>";
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
        width: 46%;
        display: inline-block;
        vertical-align: middle;
        margin-left: 20px;
        margin-top: 20px;
        padding: 10px;
        overflow-wrap:break-word;
        background-color: white;
    }
</style>
