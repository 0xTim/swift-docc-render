<!--
  This source file is part of the Swift.org open source project

  Copyright (c) 2021-2023 Apple Inc. and the Swift project authors
  Licensed under Apache License v2.0 with Runtime Library Exception

  See https://swift.org/LICENSE.txt for license information
  See https://swift.org/CONTRIBUTORS.txt for Swift project authors
-->

<template>
  <figcaption class="caption" :class="{ centered }">
    <template v-if="title">
      <strong>{{ title }}</strong>&nbsp;<slot />
    </template>
    <template v-else>
      <slot />
    </template>
  </figcaption>
</template>

<script>
export default {
  name: 'FigureCaption',
  props: {
    title: {
      type: String,
      required: false,
    },
    centered: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style scoped lang="scss">
@import 'docc-render/styles/_core.scss';

.caption {
  @include font-styles(documentation-figcaption);

  &:last-child {
    margin-top: var(--spacing-stacked-margin-large);
  }

  &.centered {
    text-align: center;
  }
}

/deep/ p {
  display: inline-block;
}
</style>
