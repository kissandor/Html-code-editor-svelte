<script>
    import Editor from "./editor.svelte";
    import Header from "./header.svelte";
    let demoText = "<h3>Welcome to the free online \n   <span style=\"background-color: #914c53; color: #ffffff; padding: 0 3px;\">\nHTML Code Editor\n</span>\n</h3>\n" + 
        "<p><strong>\nCompose the content in the source editor on the left and see the preview changing instantly on the right as you're typing.\n</strong></p>" + 
        "\n<p>Use the bar above the editor to create new HTML elements. Explore the tag wizard and many other integrated fratures that make web code composing really easy \n<img src=\"https://htmlcodeeditor.com/images/smiley.png\" alt=\"smiley\" />\n</p>";
    let text = "";

</script>


<Header on:click = "{() => 
        { 
            text = demoText;
        }
    }"/>

<Editor bind:inValue = {text}/>   

