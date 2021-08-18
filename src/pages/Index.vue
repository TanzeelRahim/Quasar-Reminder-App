<script>
/* eslint-disable */
import Container from 'src/components/Container.vue'
import NoteCards from 'src/components/NoteCards.vue'
import { useLocalNotes } from 'src/helper'
import { defineComponent } from 'vue'
import { useRouter } from 'vue-router'

export default defineComponent({
  components: { NoteCards, Container },
  name: 'PageIndex',
  setup() {
    const notes = useLocalNotes()
    const router = useRouter()
    return { router, notes }
  }
})
</script>

<template>
  <q-page padding>
    <Container>
      <div class="row items-center justify-between">
        <h3>Set your reminders</h3>
        <div>
          <q-btn round color="dark" icon="add" to="/new"></q-btn>
        </div>
      </div>

      <NoteCards
        v-for="({ title, description }, idx) in notes"
        :key="idx"
        :title="title"
        :description="description"
        @click="router.push(`/note/${idx}`)"
      />
      <div v-if="notes.length === 0">Are you ready to set your first reminder.</div>
    </Container>
  </q-page>
</template>
