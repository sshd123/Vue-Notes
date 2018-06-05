<template>
  <div id="note-editor">
    <input :value="activeNoteTitle" @input="editNote"/>
    <textarea :value="activeNoteContent" class="form-control"></textarea>
  </div>
</template>

<script>
  export default {
    computed: {
      activeNoteTitle() {
        return this.$store.getters.activeNote.title
      },
      activeNoteContent() {
        return this.$store.getters.activeNote.content
      }
    },
    methods: {
      editNote: function (e) {
        this.$store.dispatch('editNote', e.target.value)
      }
    }
  }
</script>
<style type="text/css">
  #note-editor {
    height: 100%;
    margin-left: 380px;
  }

  #note-editor textarea {
    height: 100%;
    border: 0;
    border-radius: 0;
  }

  #note-editor input {
    width: 100%;
    height: 35px;
    border: none;
  }
</style>
