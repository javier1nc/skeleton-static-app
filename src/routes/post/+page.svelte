<script>
	let foo = 'baz'
let bar = 'qux'
let result = null

async function doPost () {
    const res = await fetch('https://httpbin.org/post', {
        method: 'POST',
        body: JSON.stringify({
            foo,
            bar
        })
    })
    
    const json = await res.json()
    result = JSON.stringify(json)
}
</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<input bind:value={foo} />
    <input bind:value={bar} />
    <button type="button" on:click={doPost}>
    Post it.
    </button>
</div>

<p>
    Result:
    </p>
    <pre>
    {result}
    </pre>
