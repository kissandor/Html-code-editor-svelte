<script>
    import Ribbon from "./ribbon.svelte";
    export let value="<strong><i>Type the HTML code here...</i></strong>";
   
    /**
	 * @param {{ detail: { text: string; }; }} event
	 */
    function handleMessage(event) {
		value += event.detail.text;
	}




</script>

<div class="parent">
    <div class="left child">
        <Ribbon 
            on:h1="{handleMessage}" 
            on:h2="{handleMessage}"
            on:h3="{handleMessage}"
            on:br="{handleMessage}"
            on:div="{handleMessage}"
            on:ul="{handleMessage}"
            on:li="{handleMessage}"/>
        <textarea bind:value={value} ></textarea>
    </div>
    <div class="right child">
        {@html (value)}  
    </div>
</div>


<style>
	textarea { 
        width: 96%; 
        height: 455px;
        resize: none; 
        border: none;
        outline: none;
        margin: 10px;
    }
    
    .parent{
        margin-top: 10px;
        text-align: center;
        width: 100%;
    }
   
    .child{
        height:500px;
        width: 48%;
        display: inline-block;
        vertical-align: middle;
        overflow-wrap:break-word;
        background-color: white;
        text-align: left;
        margin: 5px;
    }

    .right{
        padding: 10px;        
    }
</style>
