<template>
    <div class='layout'  >
        <div class='first-div'>
<div>
          <h1>{{data.name}}</h1>
        <img src="../assets/glitch.png" alt="aquila-aveion">
        
</div>
      </div>
      
    <div class='second-div' >
        <div class="logos">
            <a  target='_blank' :href="'https://instagram.com/'+data.social_media.instagram">
            <IgIcon/>
            </a>
            <a target='_blank' :href="'https://twitter.com/'+data.social_media.twitter">
            <TwitterIcon/>
            </a>
            <a  target='_blank' :href="'https://snapchat.com/'+data.social_media.snapchat">
            <SnapIcon/>
            </a>
            
            <a target='_blank' :href="'mailto:' + data.social_media.email">
              <MailIcon/>
              </a>
        </div>
        <div>
          <ul>
            <li>HOME</li>
            <li>ABOUT</li>
            <li><img class='circle'  src="../assets/glitch-circle.png" alt="AA"></li>
            <li>GALLERY</li>
            <li>CONTACT</li>
          </ul>
       </div>
    </div>
  </div>

</template>

<script>

import IgIcon from './IgIcon';
import SnapIcon from './SnapIcon';
import MailIcon from './MailIcon';
import TwitterIcon from './TwitterIcon'
import axios from 'axios'
export default {
  name: 'AppLayout',
  components: {
    IgIcon, SnapIcon,MailIcon,TwitterIcon
  },

  data(){
    return{
      data: undefined
    };
  },

  created(){
    axios.get('https://hirng-x2021.glitch.me/api')
    .then(res=> [
      this.data = res.data
    ])
  }
}
</script>


<style scoped>

.layout{
  width: 1000px;
  display: flex;
  background-color: blue;
  color:#fff;
   height: 100vh;
   margin: auto;

}

.layout h1{
  line-height: 50px;
  letter-spacing: 10px;
  font-size: 40px;
}

.layout>div{
  width: 50%;
  display: flex;
  flex-direction: column;
}

.first-div{
  background-color: #e91c67;
  justify-content: flex-start;
  padding: 30px;
}

.first-div>div{
    position: relative;
    left: 270px;
}

.second-div{
  background-color: #ca2863;
  justify-content: space-between;
  align-items: flex-end;
  padding-right: 30px;
  padding-bottom: 30px;
}

.first-div img{
  width: 400px;
  height: 470px;
  z-index: 11;
  box-shadow: 0 0 10px rgba(0,0,0,0.6);
 
}

.second-div img{
  border-radius: 50%;
  width: 70px;
  height: 70px;
  position: relative;
  top: 20px;
}

ul{
position: relative;
right: 210px;
}

.logos{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 200px;
  position: relative;
  top: 230px;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
  cursor: pointer;
}

a{
  color: #fff;
}

</style>
