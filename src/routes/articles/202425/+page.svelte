<script>
  import { goto } from '$app/navigation';

  function goToMonth(month) {
    goto(`/AMS_News/articles/202425/${month}`);
  }
</script>

<h1>Summary coming your way soon!</h1>
<div class="twelveM" id="center-align">
    <button disabled class="button-reg">May</button>
    <button disabled class="button-reg">April</button>
    <button disabled class="button-reg">March</button>
    <button disabled class="button-reg">Winter (Dec-Feb)</button>
    <button disabled class="button-reg" on:click={() => goToMonth('November')}>November</button>
    <button class="button-reg" on:click={() => goToMonth('October')}>October</button>
    <button class="button-reg" on:click={() => goToMonth('September')}>September</button>
</div>