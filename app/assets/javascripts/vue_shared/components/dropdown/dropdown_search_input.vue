<script>
import { __ } from '~/locale';

export default {
  props: {
    placeholderText: {
      type: String,
      required: true,
      default: __('Search'),
    },
  },
  data() {
    return { searchQuery: this.value };
  },
  watch: {
    searchQuery(query) {
      this.$emit('input', query);
    },
  },
};
</script>

<template>
  <div class="dropdown-input">
    <input
      v-model="searchQuery"
      :placeholder="placeholderText"
      class="dropdown-input-field"
      type="search"
      autocomplete="off"
    />
    <i class="fa fa-search dropdown-input-search" aria-hidden="true" data-hidden="true"> </i>
    <i
      class="fa fa-times dropdown-input-clear js-dropdown-input-clear"
      aria-hidden="true"
      data-hidden="true"
      role="button"
    >
    </i>
  </div>
</template>
