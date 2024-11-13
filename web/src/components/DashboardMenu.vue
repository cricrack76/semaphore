<template>
  <v-tabs show-arrows class="pl-4">
    <v-tab
      v-if="projectType === ''"
      key="history"
      :to="`/project/${projectId}/history`"
    >{{ $t('history') }}
    </v-tab>
    <v-tab key="activity" :to="`/project/${projectId}/activity`">{{ $t('activity') }}</v-tab>
    <v-tab
      v-if="canUpdateProject"
      key="settings"
      :to="`/project/${projectId}/settings`"
    >{{ $t('settings') }}
    </v-tab>
    <v-tab key="activity" :to="`/project/${projectId}/runners`">
      {{ $t('runners') }}
      <v-chip small class="ml-1" color="purple">Pro</v-chip>
    </v-tab>
  </v-tabs>
</template>
<script>
import PermissionsCheck from '@/components/PermissionsCheck';

export default {

  mixins: [PermissionsCheck],

  props: {
    projectId: String,
    projectType: String,
    canUpdateProject: Boolean,
  },

  data() {
    return {
      id: null,
    };
  },
};
</script>
