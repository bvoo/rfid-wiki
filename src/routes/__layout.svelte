<script lang="ts">
  import '../app.scss';

  import { activeNode, getFriendlyNodeName, kebabToSentenceCase } from '$lib/utils';

  let nodeName = '';

  $: {
    nodeName = $activeNode ? kebabToSentenceCase(getFriendlyNodeName($activeNode)) : '';
  }
</script>

<svelte:head>
  <title>RFID Wiki{$activeNode ? ` - ${nodeName}` : ''}</title>

  <meta content="en_US" name="locale" />
  <meta content="#1a1c1d" name="theme-color" />
  <meta content="yep wiki :) :D" name="description" />
  <meta content="yep wiki :) :D" property="og:description" />
  <meta content="yep wiki :) :D" name="twitter:description" />

  <meta content="RFID Wiki{$activeNode ? ` - ${nodeName}` : ''}" property="og:title" />
  <meta content="RFID Wiki{$activeNode ? ` - ${nodeName}` : ''}" name="twitter:title" />
  <meta content="RFID Wiki" property="og:site_name" />

  <meta content="website" property="og:type" />
  <meta content="/favicon.png" property="og:image" />
  <meta content="/favicon.png" name="twitter:image" />
  <meta content="summary" name="twitter:card" />
  <meta content="@kryptonsh" name="twitter:creator" />
  <meta content="@kryptonsh" name="twitter:site" />
</svelte:head>

<slot />
