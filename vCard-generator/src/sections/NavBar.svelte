<script>
    export let title;

    let disabled = true;

    function keyPressed() {
        disabled = false;
    }

    function resetPressed() {
        disabled = true;
    }
</script>

<style>
    nav {
        width: 100%;
        font-size: 2rem;
        background-color:darkslategray;
        color: whitesmoke;
        text-align: center;
    }
</style>

<nav>{title}</nav>

<form>
    <label>
        Name 
        <input type="text" 
            placeholder="Please input your name:" 
            on:keydown={ keyPressed } />
    </label>
    <button type="reset" {disabled} on:click={resetPressed}>Reset</button>
</form>

