<template>
    <div class="hero-form">
        <div class="form">
            <input class="hero-input" type="text" v-if="column.title === '' || column.title === null" placeholder="Question">
            <h3  v-else class="heading-form">{{ column.title }}</h3>
            <div class="text-input">
                <textarea v-model="column.description" id="textarea" type="text" class="input-form" placeholder="Description"/>
            </div>
            <!-- <div class="radio-input">
               <input type="radio">
            </div> -->
        </div>
    <!-- <div class="bg-white shadow rounded px-3 pt-3 pb-5 border border-white"> -->
    <!-- </div> -->
    </div>
</template>
<script>
export default {
  components: {
  },
  props: {
    column: {
      type: Object,
      default: () => ({})
    }
  },
//   computed: {
//     badgeColor() {
//       const mappings = {
//         Design: "purple",
//         "Feature Request": "teal",
//         Backend: "blue",
//         QA: "green",
//         default: "teal"
//       };
//       return mappings[this.column.type] || mappings.default;
//     }
//   }
};
</script>

<style scoped>
.hero-form {
    background: #fff;
    padding: 20px;
    border-radius: 10px;
    margin-top: 20px;
}
.heading-form {
    font-size: 16px;
}
.hero-input {
    width: 80%;
    border: none;
    border-bottom: 1px solid grey;
    outline: none;
    height: 30px;
}
.input-form {
    width: 80%;
    border: none;
    border-bottom: 1px solid grey;
    outline: none;
    height: 30px;
    margin-top: 20px;
    padding: 0 10px;
    height: 40px;
    resize: none;
}
textarea {
}
</style>