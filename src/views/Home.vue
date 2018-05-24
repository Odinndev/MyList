<template>

  <div class="heim">

<Button type="primary" @click="modal1 = true"><Icon type="ios-plus-empty"></Icon> New Blog Posts</Button>

 <Modal
        v-model="modal1"
        title="BLOG POSTS"
        @on-ok="ok"
        @on-cancel="cancel">
        <p>
          <form v-on:submit.prevent="addPost">
        <ul>
        <li><p>Img <Input v-model="newPost.img" placeholder="Img Url" style="width: 300px; margin-bottom: 10px;"></Input></p></li>
        <li><p>Title <Input v-model="newPost.title" placeholder="Title" style="width: 300px; margin-bottom: 10px;"></Input></p></li>
        <li><p>Desc <Input v-model="newPost.desc" placeholder="Description" style="width: 300px; padding 10px; margin-bottom: 10px;"></Input></p></li>
        <li><p>Date / Time <Input v-model="newPost.date" placeholder="Date / Time" style="width: 300px; padding 10px; margin-bottom: 10px;"></Input></p></li>       
        <li><p>Uppl <Input v-model="newPost.info" type="textarea" placeholder="Upplýsingar" style="width: 300px; padding 10px; margin-bottom: 10px;"></Input></p></li>
        </ul>

        <v-card-actions>
          <v-spacer></v-spacer>
          <input class="smit" type="submit" value="Vista"></input>
        </v-card-actions>

        </form>
        </p>
    </Modal>

<div class="post">
   <!-- <h1><Icon type="clock"></Icon> <span id="dateDemo"></span></h1> -->
    <h1 v-on:click="removePost2(post)" class="opnun" align="center" v-for="post in posts"> <img v-bind:src="post.img" alt=""> <br> 
      <Icon type="qr-scanner"></Icon> {{ post.title }} 
      <div class="desc"><Icon type="ios-information"></Icon> <span> {{ post.desc }}</span> </div><!-- .desc -->
      <span class="timi"><Icon type="ios-timer"></Icon> {{ post.date }}</span>
      <br>
      <p>{{ post.info }}</p></h1>
</div><!-- .post -->

  </div><!-- .heim -->

</template>

<script>
import Firebase from 'firebase'

let config = {
    apiKey: "AIzaSyBTa9Mfja0P9cS_Jk7fk8LigXyDxusX8I0",
    authDomain: "posts-e973f.firebaseapp.com",
    databaseURL: "https://posts-e973f.firebaseio.com",
    projectId: "posts-e973f",
    storageBucket: "posts-e973f.appspot.com",
    messagingSenderId: "195442724947"
}

let app = Firebase.initializeApp(config);
let db = app.database();

let postsRef = db.ref('posts');

export default {
  
  firebase: {
    posts: postsRef
  },

      data () {
        return {
          newPost: {
          img: '',
          title:   '',
          desc:   '',
          date:   '',
          info:   '',
          },
          // virkja valmoguleika
          modal1: false

    }
  },
  methods: {
      addPost: function() {
              postsRef.push(this.newPost);
              this.newPost.img = '';              
              this.newPost.title = '';
              this.newPost.desc = '';
              this.newPost.date = '';
              this.newPost.info = '';
            },
      removePost: function(post) {
        postsRef.child(post['.key']).remove();
      },

            change (status) {
                this.$Message.info('Opið：' + status);
            },

      next () {
        const active = parseInt(this.active)
        this.active = (active < 2 ? active + 1 : 0).toString()
      },
    }
}
</script>
