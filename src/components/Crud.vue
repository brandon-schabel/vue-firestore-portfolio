<template>
  <v-container>
    <v-layout row>
      <v-flex xs8>
        <v-text-field name="note" label="Note" multi-line v-model="noteTextField"></v-text-field>
      </v-flex>
    </v-layout>
    <v-layout row>
      <v-btn @click.prevent="createNote()" v-if="updateKey === null">Create</v-btn>
      <v-btn @click.prevent="updateNote(updateKey)" v-else>Update</v-btn>
      <v-btn @click.prevent="updateKey = null" v-if="updateKey !== null">Cancel</v-btn>
    </v-layout>
    <v-layout row wrap>
      <v-flex xs12>
        <v-card v-for="(note, key) in notes" :key="key" class="noteCard">{{note.content}}
          <v-btn @click.prevent="deleteNote(note.key)" class="delete">X</v-btn>
          <v-btn @click.prevent="fillNoteContent(note.key)" class="delete">Edit</v-btn>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  import { notesRef } from '../main.js'

  export default {
    created: function () {
      this.getNotes();
    },
    data() {
      return {
        notes: [],
        noteTextField: null,
        updateKey: null
      }
    },
    methods: {
      createNote() {
        notesRef.add({
          content: this.noteTextField,
        }).then(function (docRef) {
          console.log('Document written with ID: ', docRef.id)
        }).catch(function (error) {
          console.error('Error adding document: ', error)
        })
        this.noteTextField = null; // clear text field content;
        this.getNotes()
      },
      getNotes() {
        this.notes = []
        let context = this
        notesRef.get().then(function (querySnapshot) {
          querySnapshot.forEach(function (doc) {
            // doc.data() is never undefined for query doc snapshots
            // console.log(doc.id, ' => ', doc.data()) // uncomment this line to see what it is getting
            let noteDoc = {
              content: doc.data().content,
              userID: doc.data().userID,
              data: doc.data().date,
              key: doc.id
            }
            context.notes.push(noteDoc)
          })
        })
      },

      deleteNote(key) {
        notesRef.doc(key).delete().then(function() {
          console.log("Document was successfully deleted")
        }).catch(function(error) {
          console.log("Error removing document: ", error)
        })
        this.getNotes()
      },

      fillNoteContent(key) {
        // store key that we want to update if used submits the update
        this.updateKey = key;
        for(let note in this.notes) {
          if(key === this.notes[note].key) {
            this.noteTextField = this.notes[note].content
          }
        }

        /* above we used the existing data we already pulled from firestore to get our update note content,
        // alternatively demonstrated below we can query firestore for the content of the given update key

        // get doc based on key passed in
        let docRef = notesRef.doc(key)

        // context is the context of vue component so when we refer to it, it isn't referring to the firebase function's "this"
        let context = this
        docRef.get().then(function(doc) {
          if(doc.exists) {
            let data = doc.data() // returned document data
            context.noteTextField = data.content
          } else {
            console.log("no doc")
          }
        }).catch(function(error) {
          console.log("Error: ", error)
        })
        */
      },

      updateNote(key) {
        let docRef = notesRef.doc(key)
        docRef.set({content: this.noteTextField})
        this.noteTextField = null
        this.updateKey = null
        this.getNotes()
      }
    }
  }
</script>

<style>
  .noteCard {
    margin-top: 1% !important;
    padding-left: 1% !important;
    overflow: hidden;
  }

  .delete {
    float: right  !important;
  }
</style>
