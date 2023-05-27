<template>
  <div>
    <DropdownMenu @selection-changed="handleSelectionChanged" />
    <PictureDisplay :selectedOptions="selectedOptions" />
  </div>
</template>

<script>
import DropdownMenu from '../components/DropdownMenu.vue';
import PictureDisplay from '../components/PictureDisplay.vue';

export default {
  components: {
    DropdownMenu,
    PictureDisplay
  },
  data() {
    return {
      selectedOptions: {
        option1: '',
        option2: ''
      }
    };
  },
  methods: {
    handleSelectionChanged(selection) {
      this.selectedOptions = selection;
    }
  }
};
</script>
