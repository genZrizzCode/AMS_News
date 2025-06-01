<!-- Only works in localhost :( -->
<script>
  import { page } from '$app/stores';
  import directories from '$lib/directories.json';

  const currentPath = $page.url.pathname;
  const currentStatus = $page.status || 500;

  function levenshtein(a, b) {
    const matrix = Array.from({ length: b.length + 1 }, (_, i) => [i]);
    for (let j = 0; j <= a.length; j++) matrix[0][j] = j;

    for (let i = 1; i <= b.length; i++) {
      for (let j = 1; j <= a.length; j++) {
        if (b.charAt(i - 1) === a.charAt(j - 1)) {
          matrix[i][j] = matrix[i - 1][j - 1];
        } else {
          matrix[i][j] = Math.min(
            matrix[i - 1][j - 1] + 1,
            matrix[i][j - 1] + 1,
            matrix[i - 1][j] + 1
          );
        }
      }
    }
    return matrix[b.length][a.length];
  }

  function getSuggestion(pathList, targetPath) {
    let minDistance = Infinity;
    let suggestion = null;

    for (const path of pathList) {
      const dist = levenshtein(targetPath, path);
      if (dist < minDistance) {
        minDistance = dist;
        suggestion = path;
      }
    }

    if (minDistance <= 5) {
      return suggestion;
    }

    return null;
  }

  const suggestion = getSuggestion(directories, currentPath);
</script>

<h1>ERROR {currentStatus}</h1>

{#if currentStatus === 404}
  <h2>Oops! This page doesn't exist.</h2>
  <hr />
  <p>Check the URL or go back to the <a href="/AMS_News">home page</a>.</p>
  <p>Did you mean <a href="{suggestion}">{suggestion}</a>?</p>
{:else if currentStatus === 400}
  <h2>Bad Request.</h2>
  <hr />
  <p>The server cannot or will not process the request due to an apparent client error <i>(e.g., malformed request syntax, size too large, invalid request message framing, or deceptive request routing).</i></p>
  <p>Did you mean to go to <a href="{suggestion}">{suggestion}</a>?</p>
{:else if currentStatus === 408}
  <h2>Request Timeout</h2>
  <hr />
  <p>The server timed out waiting for the request.</p>
{:else if currentStatus === 409}
  <h2>Conflict</h2>
  <hr />
  <p>The request could not be processed because of conflict in the current state of the resource.</p>
  <p>Did you mean to go to <a href="{suggestion}">{suggestion}</a>?</p>

{:else if currentStatus === 413}
  <h2>Payload Too Large</h2>
  <hr />
  <p>The request is larger than the server is willing or able to process.</p>
{:else if currentStatus === 429}
  <h2>Too Many Requests</h2>
{:else if currentStatus === 500}
  <h2>Generic Server Error</h2>
  <hr />
  <p>This error might happen for many reasons, usually when something is wrong but no other error message fits.</p>
  <p>Please go back to the <a href="/AMS_News">home page</a>.</p>
{:else if currentStatus === 502}
  <h2>Bad Gateway</h2>
  <hr />
  <p>The server was acting as a gateway or proxy and received an invalid response from the upstream server.</p>
{:else if currentStatus === 505}
  <h2>HTTP Version Not Supported</h2>
  <hr />
  <p>Please Update your Browser, Device, or whatever you used to get here.</p>
{:else}
  <h2>Unexpected or Unknown error occurred.</h2>
  <hr />
  <p>Please try again later.</p>
  <p>Did you mean <a href="{suggestion}">{suggestion}</a>?</p>

{/if}

<p>You tried to visit: {currentPath}</p>