<script>
    import Ribbon from "./ribbon.svelte";
    let value="";
    export let inValue="";
    let indexToInsert = 0;

    $: {value = inValue;}

    /**
	 * @param {{ detail: { text: string; }; }} event
	 */
    function handleMessage(event) { 
        if (inValue.length === 0 || indexToInsert === inValue.length){
            inValue += event.detail.text;
        } else {
            let temp = inValue;
            inValue = temp.slice(0,indexToInsert) + event.detail.text + temp.slice(indexToInsert);
            indexToInsert += event.detail.text.length;
        }
	}

    /**
	 * @param {{ detail: { text: string; }; }} event
	 */
    function clearTextArea(event) {
        inValue = event.detail.text;
      }
      
    /**
	 * @param {any} event
	 */
    function call(event){
        console.log(indexToInsert);
        indexToInsert = event.target.selectionStart
        console.log(indexToInsert);
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
            on:li="{handleMessage}"
            on:clear = "{clearTextArea}"/>
        <textarea  on:click={call} bind:value={inValue} ></textarea>
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
