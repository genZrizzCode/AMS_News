<script>
  import { goto } from '$app/navigation';

  function goToMonth(month) {
    goto(`/articles/202425/${month}`);
  }
</script>

<h1>Summary coming your way soon!</h1>
<div id="center-align">
    <button class="button-reg">May</button>
    <button class="button-reg">April</button>
    <button class="button-reg">March</button>
    <button class="button-reg">Winter (Dec-Feb)</button>
    <button class="button-reg" on:click={() => goToMonth('November')}>November</button>
    <button class="button-reg" on:click={() => goToMonth('October')}>October</button>
    <button class="button-reg" on:click={() => goToMonth('September')}>September</button>
</div>