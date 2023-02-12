<script lang="js">
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();


    /**
	 * @param {string} msg
	 */
    function addHtmlTag(msg) {
		dispatch(msg, {
			text: '<' + msg + '>' + '</' + msg + '>'
		});
	}


</script>
<div class="ribbon"> 
        <button on:click = {()=>
        { 
            dispatch('h1', {
              text: '<h1></h1>'
           })
        }}>h1</button>
        
        <button on:click = {()=>addHtmlTag('h2')}>h2</button>
        <button on:click = {()=>addHtmlTag("h3")}>h3</button>
        <button on:click = {()=>
        {
          dispatch('br', {
              text: '</br>'
           })
        }}>br</button> 
        <button on:click = {()=>addHtmlTag("div")}>div</button>
        <button on:click = {()=>addHtmlTag("ul")}>ul</button>
        <button on:click = {()=>addHtmlTag("li")}>li</button>
        
        <button class="clear" on:click = {()=>
        {
            dispatch('clear',{
              text: ''
            })
        }}>Clear</button>
</div>

<style>
    div {
      overflow: hidden;
      background-color: #914C53;
      color: white;
    }
    
    button {
      background-color: #914C53;
      border: none;
      color: white;
      font-size: medium;
      padding : 5px 10px;
    }    

    button:hover{
        background-color: #633035;
        cursor: pointer;
    }

    .clear{
      float: right;
      padding-right: 20px;
      padding-left: 20px;
    }

</style>