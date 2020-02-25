<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/poster.jpeg" width="800" height="450"><br><br>
    {{ time }} <br>
    <HelloWorld msg="since the leave campaign said Turkey is going to join the European Union."/>
  </div>
</template>

<script src="https://momentjs.com/downloads/moment.js"></script>
<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import '../static/moment'
import moment from 'moment'
import '../static/moment-precise-range'

function timeSince () {
  var brexitAnnouncment = moment.utc('2016-05-23T10:28:44+01:00')
  var timesince = moment.preciseDiff(brexitAnnouncment, Date.now())
  return timesince
};

export default {
  name: 'Home',
  components: {
    HelloWorld
  }, 
  data () {
    return {
      time: timeSince()
    }
  }
}
</script>
