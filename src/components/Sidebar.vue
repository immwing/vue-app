<template>
  <div class="sidebar">
    <div class="header">
      <div class="avatar">
        <img src="../assets/avatar.jpg" alt="">
      </div>
      <div class="title">
        <h2>Jun Ying</h2>
        <h4>Frontend Developer.</h4>
      </div>
      <div class="content">
        <ul>
          <li><a href="/">Home</a></li>
          <li><a href="/about">About Me</a></li>
          <li><a href="/portfolio">Portfolio</a></li>
          <li><a href="/resume">Resume</a></li>
          <li><a href="/contact">Contact</a></li>
        </ul>
      </div>
      <div class="social-links">
        <ul>
          <li><a href="#"><i class="fab fa-facebook-f"></i></a></li>
          <li><a href="#"><i class="fab fa-instagram"></i></a></li>
          <li><a href="#"><i class="fab fa-weixin"></i></a></li>
          <li><a href="#"><i class="fab fa-line"></i></a></li>
        </ul>
      </div>
      <div class="copyright">
        © 2020 All rights reserved.
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'Rella',
    }
  },
  methods: {
    editTitle(event) {
      event.path[0].innerText = 'asd'
      console.log(event.path[0])
    }
  }
}
</script>

<style scoped>
.sidebar {
  height: 100%;
  width: 360px;
  position: fixed;
  top: 0;
  left: 0;
  background-color: #444;
  color: #fff;
  text-align: center;
}


.avatar { 
  position: relative;
  width: 200px;
  margin: 50px auto;
}
.avatar img {
  width: 100%;
  border: 3px solid #fff;
  border-radius: 50%;
}
.avatar::after {
  position: absolute;
  content: '';
  opacity: 0.3;
  top: 7%;
  left: 7%;
  border-radius: 50%;
  height: calc(100% + 0px);
  width: calc(100% + 0px);
  background-image: -webkit-repeating-radial-gradient(center center, #fff, #fff 1px, transparent 0px, transparent 100%);
  background-size: 6px 6px;
  z-index: -1;
}



.title {
  margin: 30px 0;
}
.title h2 {
  font-size: 36px;
  font-weight: 600;
  font-family: 'Poppins', Helvetica, sans-serif;
  line-height: 1.2em;
}
.title h4 {
  font-size: 18px;
  font-weight: 300;
  font-family: 'Poppins', Helvetica, sans-serif;
  color: #bbb;
  line-height: 1.2em;
}


.content {
  margin: 30px 100px;
  text-align: left;
}
.content ul {
  list-style: none;
  padding: 0;
}
.content ul li {
  margin: 10px 0px;
}
.content ul li a {
  font-size: 24px;
  text-decoration: none;
  color: #ddd;
  opacity: 0.8;
}
.content ul li a:hover {
  opacity: 1;
}


.social-links {
  margin: 30px 0;
}
.social-links ul {
  list-style: none;
  padding: 0;
}
.social-links ul li {
  display: inline-block;
  padding: 0px 5px;
}
.social-links ul li a {
  font-size: 20px;
  border-radius: 50%;
  display: block;
  width: 30px;
  height: 30px;
  line-height: 27px;
  text-decoration: none;
  color: #ddd;
}
.social-links ul li a:hover {
  background-color: rgba(255,255,255,.2);
}


.copyright {
  position: absolute;
  color: #bbb;
  left: 0;
  right: 0;
  bottom: 0;
  font-size: 12px;
  line-height: 1.2em;
  padding: 5px 10px 15px;
}
</style>