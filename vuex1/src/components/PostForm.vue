<template>
    <form @submit.prevent="submit">
        <input type="text" placeholder="title" v-model="title">
        <input type="text" placeholder="body" v-model="body">
        <button class="btn" type="submit">Create Post</button>
    </form>
</template>

<script>
import { mapMutations } from "vuex";
export default {
  data() {
    return {
      title: "",
      body: "",
    };
  },
  methods: {
    ...mapMutations(["createPost"]),
    submit() {
      this.createPost({
        title: this.title,
        body: this.body,
        id: Date.now()
      });
      this.title = this.body = "";
    }
  }
};
</script>

<style scoped>
input[type=text] {
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
  width: 100%;
}
input[type=text]:focus {
  width: 100%;
}

.btn {
	background:linear-gradient(to bottom, #44c767 5%, #5cbf2a 100%);
	background-color:#44c767;
	border:3px solid #18ab29;
	display:inline-block;
	cursor:pointer;
	color:#ffffff;
	font-family:Arial;
	font-size:18px;
	padding:12px 29px;
	text-decoration:none;
	text-shadow:3px 6px 9px #2f6627;
  margin-bottom: 1.5rem;
}
.btn:hover {
	background:linear-gradient(to bottom, #5cbf2a 5%, #44c767 100%);
	background-color:#5cbf2a;
}
.btn:active {
	position:relative;
	top:1px;
}

        
</style>