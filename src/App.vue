<script setup>
import { createDirectus, rest, readAssetRaw } from '@directus/sdk';

const FILE_ID = '9be59ee6-4617-488e-aac8-eb47e046e007';

const directus = createDirectus('http://photography.directus.local:8055/').with(
  rest()
);
const result = await directus.request(
  readAssetRaw(FILE_ID, {
    width: 300,
    height: 300,
    quality: 50,
    fit: 'contain',
  })
);
</script>

<template>
  <div></div>
</template>
