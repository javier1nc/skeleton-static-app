<script>
  import { DateInput, DatePicker, localeFromDateFnsLocale } from 'date-picker-svelte'
  import { onMount } from 'svelte';

  let deg = 0;
  onMount(() => {
    const interval = setInterval(() => {
      deg += 2;
      if (deg >= 360) deg = 0;
      //console.log("::deg::",deg);
    }, 60);
    return () => clearInterval(interval);
  });
</script>

<div>
  <DatePicker />
  <DateInput
    format="yyyy-MM-dd"
    placeholder="2000-31-12" />
</div>

<style>
  :global(body) {
    --date-picker-foreground: white;
    --date-picker-background: silver;
    --date-picker-highlight-border: hsl(var(--deg), 98%, 49%);
    --date-picker-highlight-shadow: hsla(var(--deg), 98%, 49%, 50%);
    --date-picker-selected-color: hsl(var(--deg), 100%, 85%);
    --date-picker-selected-background: hsla(var(--deg), 98%, 49%, 20%);
    background: #0d0e12;
    color: #ffffff;
    transition: all 80ms ease-in-out;
    font-size: 14px;
  }
  div > :global(*) {
    margin-bottom: 10px;
  }
</style>