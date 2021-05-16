<template>
  <div id="app">
    <Header heading="Event Feedback"/>
    <div class="content">
      <!-- <div class="flex justify-center"> -->
      <div class="min-h-screen overflow-x-scroll py-12">
        <div
          class="bg-gray-100 rounded-lg px-3 py-3 column-width rounded mr-4 flex"
        >
          <!-- Draggable component comes from vuedraggable. It provides drag & drop functionality -->
          <!-- <draggable :list="columns" :animation="200" group="columns"> -->
            <div class="form-widget">
              <draggable :animation="200">
                <!-- Each element from here will be draggable and animated. Note :key is very important here to be unique both for draggable and animations to be smooth & consistent. -->
                <Form
                  v-for="(column) in columns"
                  :key="column.id"
                  :column="column"
                  class="mt-3 cursor-move"
                ></Form>
                <!-- </transition-group> -->
              </draggable>
            </div>
            <div class="widget">
              <button @click="addForm">
                <font-awesome-icon class="widget-icon"  :icon="['fa', 'plus-circle']" />
              </button>
              <font-awesome-icon class="widget-icon"  :icon="['fa', 'text-height']" />
              <font-awesome-icon class="widget-icon"  :icon="['fa', 'file-image']" />
              <font-awesome-icon class="widget-icon"  :icon="['fa', 'play']" />
              <font-awesome-icon class="widget-icon"  :icon="['fa', 'minus-square']" />
            </div>
        </div>
      </div>
    <!-- </div> -->
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import draggable from "vuedraggable";
import Form from "./components/Form.vue";

export default {
  name: 'App',
  components: {
    Header,
    Form,
    draggable
  },
  data() {
    return {
      columns: [
        {
          id: 1,
          title: "What do you Know about me",
          description: "Describe this"
        },
        {
          id: 2,
          title: "Provide documentation on integrations",
        },
        {
          id: 3,
          title: "Design shopping cart dropdown",
        },
        {
          id: 4,
          title: "Add discount code to checkout page",
        },
        {
          id: 5,
          title: "Test checkout flow",
        }
      ]
    }
  },
  methods: {
    addForm() {
      this.columns.push({
        id: "",
        title: ""
      })
    }
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #e2dbda;
  min-height: 100vh;
  padding-bottom: 50px;
}

</style>

<style scoped>
.content {
  max-width: 756px;
  display: block;
  margin: auto;
  padding-top: 50px;
}
/* .column-width {
  min-width: 320px;
  width: 320px;
} */
/* Unfortunately @apply cannot be setup in codesandbox, 
but you'd use "@apply border opacity-50 border-blue-500 bg-gray-200" here */
/* .ghost-card {
  opacity: 0.5;
  background: #F7FAFC;
  border: 1px solid #4299e1;
} */
.form-widget {
  width: 100%;
}
.widget {
  display: flex;
  flex-direction: column;
  background: #fff;
  padding: 10px;
  width: 35px;
  height: min-content;
  margin: 20px;
}
.widget-icon {
  margin: 15px 0;
}
button {
  border: none;
  background: none;
}
</style>
