<script>
  import newsData from '$lib/news-list.json';

  const septemberMain = newsData.Headlines.Descriptions["2024-25"].September.main;
  const octoberMain = newsData.Headlines.Descriptions["2024-25"].October.main;
  const novemberMain = newsData.Headlines.Descriptions["2024-25"].November.main;
  const decFebMain = newsData.Headlines.Descriptions["2024-25"].Dec-Feb.main;
  const marchMain = newsData.Headlines.Descriptions["2024-25"].March.main;
  const aprilMain = newsData.Headlines.Descriptions["2024-25"].April.main;
  const mayMain = newsData.Headlines.Descriptions["2024-25"].May.main;
</script>
<h1 class="huge2timesText">AMS News</h1>
<h4>Welcome to the AMS News Website!</h4>
<br><hr>
<div id="Months">
    <h3>May</h3>
    <h5>{mayMain}</h5>
    <hr>
    <h3>April</h3>
    <h5>{aprilrMain}</h5>
    <hr>
    <h3>March</h3>
    <h5>{marchMain}</h5>
    <hr>
    <h3>Dec-Feb</h3>
    <h5>{decFebMain}</h5>
    <hr>
    <h3>November</h3>
    <h5>{novemberMain}</h5>
    <hr>
    <h3>October</h3>
    <h5>{octoberMain}</h5>
    <hr>
    <h3>September</h3>
    <h5>{septemberMain}</h5>
    <hr>
</div>