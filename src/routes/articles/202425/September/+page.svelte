<script>
    import { 
        septemberMain,
        septemberArticle
     } from "$lib";
</script>
<div class="huge2timesText">
    <h1 id="center-align">{ septemberMain }</h1>
    <hr><br>
    {#each [
      ...septemberArticle["General Announcements"].split('\n'),
      ...septemberArticle["Ask Adams"].split('\n'),
      ...septemberArticle.Organization.split('\n')
    ] as line}
      <p id="news-align">{line}</p>
    {/each}
    <br>
</div>