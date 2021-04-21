<template>
  <span v-if="field.value">
    <span v-if="$parent.resource.authorizedToUpdate">
      <router-link
        :to="{
            name: 'edit',
            params: {
                resourceName: resourceName,
                resourceId: $parent.resource.id.value,
            },
        }"
        class="no-underline dim text-primary font-bold"
      >{{ field.value }}</router-link>
    </span>
    <span v-else>{{ field.value }}</span>
  </span>
  <span v-else>&mdash;</span>
</template>

<script>
export default {
  props: ["resourceName", "field"]
};
</script>
