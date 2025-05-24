<script>
    import { 
        octoberMain,
        octoberArticle
     } from "$lib";
</script>
<div class="huge2timesText">
    <h1 id="center-align">{ octoberMain }</h1>
    <hr><br>
    {#each [
      ...octoberArticle["General Announcements"].split('\n'),
      ...octoberArticle["Eagle Alert"].split('\n'),
      ...octoberArticle["Meet the South Bay"].split('\n')
    ] as line}
      <p id="news-align">{line.replaceAll('\t', '\u00A0\u00A0\u00A0\u00A0')}</p>
    {/each}
    <br>
</div>