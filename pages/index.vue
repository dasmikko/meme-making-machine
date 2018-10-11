<template>
    <section class="container">
      <Card title="Select an image" width="w-64">

        <div class="upload-field cursor-pointer select-none" v-on:dragenter="onDragOver" v-on:drop="onDropHandler" v-on:dragover="onDragOver" @click="$router.push('/editor')">
          <span class="text-grey">
            drop a file here <br>
            or <br>
            click here
          </span>
        </div>
      </Card>
    </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import TopBar from '~/components/TopBar/TopBar.vue'
import Button from '~/components/Button.vue'
import Card from '../components/Card.vue'

export default {
  components: {
    Logo,
    TopBar,
    Button,
    Card
  },
  methods: {
    onDragOver (event) {
      event.preventDefault()
    },
    onDropHandler (ev) {
      console.log('File(s) dropped')
      ev.preventDefault()


      if (ev.dataTransfer.items) {
        // Use DataTransferItemList interface to access the file(s)
        for (var i = 0; i < ev.dataTransfer.items.length; i++) {
          // If dropped items aren't files, reject them
          if (ev.dataTransfer.items[i].kind === 'file') {
            var file = ev.dataTransfer.items[i].getAsFile();
            console.log('... file[' + i + '].name = ' + file.name);
          }
        }
      } else {
        // Use DataTransfer interface to access the file(s)
        for (var i = 0; i < ev.dataTransfer.files.length; i++) {
          console.log('... file[' + i + '].name = ' + ev.dataTransfer.files[i].name);
        }
      }
    }
  }
}
</script>

<style lang="scss">

/* Sample `apply` at-rules with Tailwind CSS*/
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}

.btn {
  @apply bg-grey-light rounded-sm text-black p-2;

  &:hover {
    @apply bg-grey;
  }
}

.upload-field {
  @apply bg-blue-lightest rounded border-2 border-dashed border-blue-lighter py-10;
}


.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
