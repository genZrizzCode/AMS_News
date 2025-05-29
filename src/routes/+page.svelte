<script>
  import {
    septemberMain,
    octoberMain,
    novemberMain,
    decFebMain,
    marchMain,
    aprilMain,
    mayMain
  } from '$lib';

  import { base } from '$app/paths'
</script>
<h1 class="huge2timesText">AMS News</h1>
<p>Welcome to the AMS News Website!</p>
<br><hr>
<div id="Months">
    <h3>May</h3>
    <h5>{mayMain}</h5>
    <hr>
    <h3>April</h3>
    <h5>{aprilMain}</h5>
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
    <a href="{ base }/articles/202425/October"><h5>{octoberMain}</h5></a>
    <hr>
    <h3>September</h3>
    <a href="{ base }/articles/202425/September"><h5>{septemberMain}</h5></a>
    <hr>
</div>