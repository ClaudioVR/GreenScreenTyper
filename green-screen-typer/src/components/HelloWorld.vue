<template>
  <div class="screen black">
    <v-container class="">
      <div id="title" class="text-center mt-n3">#3ab508 Neo typer</div>
      <div id="subtitle" class="text-center">your mindfulness online typer</div>
      <!-- <span class="white--text">{{typedText}}</span> -->
      <!-- <v-container class="">
        <v-textarea
          v-model="typedText"
          color="#3ab508"
          background-color="black"
          class="mt-12 mx-12 px-12 blue--text"
          name="input-7-4"
          rows="100"
         ></v-textarea>
      </v-container> -->

      <div class="mt-12 editor">
        <editor-menu-bar :editor="editor" v-slot="{ commands, isActive }">
          <div class="menubar text-center">

            <button
              class="menubar__button"
              :class="{ 'is-active': isActive.bold() }"
              @click="commands.bold"
            >
              <v-icon color="#3ab508">mdi-format-bold</v-icon>
            </button>

            <button
              class="menubar__button"
              :class="{ 'is-active': isActive.italic() }"
              @click="commands.italic"
            >
              <v-icon color="#3ab508">mdi-format-italic</v-icon>
            </button>

            <!-- <button
              class="menubar__button"
              :class="{ 'is-active': isActive.strike() }"
              @click="commands.strike"
            >
              <v-icon small color="#3ab508">mdi-format-strikethrough-variant</v-icon>
            </button> -->

            <button
              class="menubar__button"
              :class="{ 'is-active': isActive.underline() }"
              @click="commands.underline"
            >
              <v-icon color="#3ab508">mdi-format-underline</v-icon>
            </button>

            <button
              class="menubar__button"
              :class="{ 'is-active': isActive.code() }"
              @click="commands.code"
            >
              <v-icon color="#3ab508">mdi-code-tags</v-icon>
            </button>

            <button
              class="menubar__button"
              :class="{ 'is-active': isActive.paragraph() }"
              @click="commands.paragraph"
            >
              <v-icon color="#3ab508">mdi-format-paragraph</v-icon>
            </button>

            <button
              class="mx-1 menubar__button"
              :class="{ 'is-active': isActive.heading({ level: 1 }) }"
              @click="commands.heading({ level: 1 })"
            >
              <span class="font-weight-bold">H1</span>
            </button>

            <button
              class="mx-1 menubar__button"
              :class="{ 'is-active': isActive.heading({ level: 2 }) }"
              @click="commands.heading({ level: 2 })"
            >
              <span class="font-weight-bold">H2</span>
            </button>

            <button
              class="mx-1 menubar__button"
              :class="{ 'is-active': isActive.heading({ level: 3 }) }"
              @click="commands.heading({ level: 3 })"
            >
              <span class="font-weight-bold">H3</span>
            </button>

            <button
              class="menubar__button"
              :class="{ 'is-active': isActive.bullet_list() }"
              @click="commands.bullet_list"
            >
              <v-icon color="#3ab508">mdi-format-list-bulleted</v-icon>
            </button>

            <!-- <button
              class="menubar__button"
              :class="{ 'is-active': isActive.ordered_list() }"
              @click="commands.ordered_list"
            >
              <icon name="ol" />
            </button> -->

            <!-- <button
              class="menubar__button"
              :class="{ 'is-active': isActive.blockquote() }"
              @click="commands.blockquote"
            >
              <icon name="quote" />
            </button> -->

            <button
              class="mx-1 menubar__button"
              :class="{ 'is-active': isActive.code_block() }"
              @click="commands.code_block"
            >
              <v-icon color="#3ab508">mdi-code-tags</v-icon>
            </button>

            <button
              class="mx-1 menubar__button"
              @click="commands.horizontal_rule"
            >
              <span>-</span>
            </button>

            <button
              class="ml-5 menubar__button"
              @click="commands.undo"
            >
              <v-icon color="#3ab508">mdi-undo</v-icon>
            </button>

            <button
              class="menubar__button"
              @click="commands.redo"
            >
              <v-icon color="#3ab508">mdi-redo</v-icon>
            </button>

          </div>
        </editor-menu-bar>

        <v-row>
          <v-col cols="12" sm="10" offset-sm="1">
            <editor-content class="mt-8 editor__content" :editor="editor" />
          </v-col>
        </v-row>

      </div>

    </v-container>
  </div>
</template>

<script>
import { Editor, EditorContent, EditorMenuBar} from 'tiptap'
import {
  Blockquote,
  CodeBlock,
  HardBreak,
  Heading,
  OrderedList,
  BulletList,
  ListItem,
  TodoItem,
  TodoList,
  Bold,
  Code,
  Italic,
  Link,
  Strike,
  Underline,
  History,
} from 'tiptap-extensions'

  export default {
    name: 'HelloWorld',
    components: {
      EditorContent,
      EditorMenuBar
    },
    data: () => ({
      typedText: 'start typing...',
      editor: new Editor({
        extensions: [
          new Blockquote(),
          new CodeBlock(),
          new HardBreak(),
          new Heading({ levels: [1, 2, 3] }),
          new BulletList(),
          new OrderedList(),
          new ListItem(),
          new TodoItem(),
          new TodoList(),
          new Bold(),
          new Code(),
          new Italic(),
          new Link(),
          new Strike(),
          new Underline(),
          new History(),
        ],
        content: `
          <p>start typing...</p>
        `,
      }),
    }),
    beforeDestroy() {
      this.editor.destroy()
    },
  }
</script>

<style>
.screen {
  height: 10000px;
  font-family: 'Source Code Pro', monospace !important;
  color: #3ab508;
}

#title {
  font-size: 2rem;
  color: #3ab508;
  text-shadow: 2px 2px 5px #3ab508;
}

#subtitle {
  font-size: .8rem;
  color: #3ab508;
}

#input-15 {
  color: #3ab508;
}

*:focus {
  outline: none;
}

.ProseMirror {
  border: 1px solid #3ab508;
  border-radius: 5px;
  min-height: 700px;
  padding: 1rem;
}

</style>
