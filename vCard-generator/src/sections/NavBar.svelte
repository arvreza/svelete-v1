<script>
    export let title;

    let disabled = true;
    let name = "";
    let firstInput = "";

    function keyPressed(event) {
        console.log(event);
        disabled = false;
    }

    function resetPressed() {
        disabled = true;
        name = "";
        firstInput.focus();
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
            on:keydown={ keyPressed } 
            bind:value={name}
            bind:this={firstInput} />
    </label>
    <button type="reset" {disabled} on:click={resetPressed}>Reset</button>
</form>

<section>{name}</section>

