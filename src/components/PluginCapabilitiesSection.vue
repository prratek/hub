<template>
  <div>
    <p class="text-3xl py-4" id="capabilities">Capabilities</p>
    <span class="space-y-3" v-if="capabilities && capabilities.length">
      <p>
        The current capabilities for
        <code>{{ name }}</code>
        may have been automatically set when originally added to the Hub. Please review the
        capabilities when using this {{ plugin_type }}. If you find they are out of date, please
        consider updating them by making a pull request to the YAML file that defines the
        capabilities for this {{ plugin_type }}.
      </p>
      <p>This plugin has the following capabilities:</p>
      <ul class="list-disc list-inside pl-4">
        <li v-for="(capability, index) in capabilities" v-bind:key="index">
          {{ capability }}
        </li>
      </ul>
      <p>
        You can
        <a
          href="https://docs.meltano.com/guide/configuration#overriding-discoverable-plugin-properties"
          >override these capabilities or specify additional ones</a
        >
        in your <code>meltano.yml</code> by adding the <code>capabilities</code> key.
      </p>
    </span>
    <span v-else
      >This plugin currently has no capabilities defined. If you know the capabilities required by
      this plugin, <a href="#contribute">please contribute!</a></span
    >
  </div>
</template>

<script>
export default {
  name: "PluginCapabilitiesSection",
  props: ["capabilities", "name", "plugin_type"],
};
</script>

<style></style>
