<template>
    <div class="flex flex-row justify-around my-6 py-4 bg-white shadow rounded text-grey">
      <div @click="activateThisTab('tasks')"
        :class="[(active === 'tasks') ? 'text-teal-dark font-semibold border-teal border-b-2 pb-4 -mb-4' : 'cursor-pointer', 'text-center w-1/6']">
        <font-awesome-icon :icon="faTasks" class="text-2xl"></font-awesome-icon>
        <span class="block text-xs font-regular pt-2">{{ 'Tasks' | localize }}</span>
      </div>
      <div @click="activateThisTab('discussions')"
        :class="[(active === 'discussions') ? 'text-teal-dark font-semibold border-teal border-b-2 pb-4 -mb-4' : 'cursor-pointer', 'text-center w-1/6']">
        <font-awesome-icon :icon="faClipboardList" class="text-2xl"></font-awesome-icon>
        <span class="block text-xs font-regular pt-2">{{ 'Discussions' | localize }}</span>
      </div>
      <div @click="activateThisTab('messages')"
        :class="[(active === 'messages') ? 'text-teal-dark font-semibold border-teal border-b-2 pb-4 -mb-4' : 'cursor-pointer', 'text-center w-1/6']">
        <font-awesome-icon :icon="faComments" class="text-2xl"></font-awesome-icon>
        <span class="block text-xs font-regular pt-2">{{ 'Messages' | localize }}</span>
      </div>
      <div @click="activateThisTab('events')"
        :class="[(active === 'events') ? 'text-teal-dark font-semibold border-teal border-b-2 pb-4 -mb-4' : 'cursor-pointer', 'text-center w-1/6']">
        <font-awesome-icon :icon="faCalendarAlt" class="text-2xl"></font-awesome-icon>
        <span class="block text-xs font-regular pt-2">{{ 'Events' | localize }}</span>
      </div>
      <div @click="activateThisTab('files')"
        :class="[(active === 'files') ? 'text-teal-dark font-semibold border-teal border-b-2 pb-4 -mb-4' : 'cursor-pointer', 'text-center w-1/6']">
        <font-awesome-icon :icon="faFileAlt" class="text-2xl"></font-awesome-icon>
        <span class="block text-xs font-regular pt-2">{{ 'Files' | localize }}</span>
      </div>
      <div @click="activateThisTab('activities')"
        :class="[(active === 'activities') ? 'text-teal-dark font-semibold border-teal border-b-2 pb-4 -mb-4' : 'cursor-pointer', 'text-center w-1/6']">
        <font-awesome-icon :icon="faBolt" class="text-2xl"></font-awesome-icon>
        <span class="block text-xs font-regular pt-2">{{ 'Activities' | localize }}</span>
      </div>
    </div>
</template>

<script>
import {
  faBolt,
  faCalendarAlt,
  faClipboardList,
  faComments,
  faFileAlt,
  faTasks,
} from '@fortawesome/free-solid-svg-icons'

export default {
  props: {
    active: {
      required: true,
      type: String
    }
  },
  data: () => ({
    faBolt,
    faCalendarAlt,
    faClipboardList,
    faComments,
    faFileAlt,
    faTasks,
  }),
  methods: {
    activateThisTab (tab) {
      this.$emit('activate', tab)
    }
  }
}
</script>
