<template>
  <div class="hello">
    <h1 >{{ msg }}</h1>
    
    
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function() {
    return { msg: "test" };
  },
  created: function() {
    var that = this;
    this.$http({
      method: "post",
      url: "/hello",
      data: {
        name: "wise",
        info: "wrong"
      }
    }).then(function(response) {
      that.msg = response.data.msg;
    });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
