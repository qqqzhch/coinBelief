<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>您持有哪些币</h2>

<form class="form">
      <div  class="inputGroup" v-for="item in coinlist">
        <input v-on:change="select" :id="item.i" :name=item.i type="checkbox"/>
        <label :for="item.i">{{item.name}}</label>
      </div>
</form>
<div>
没有您持有的币？快快联系小编添加您持有的币吧

</div>
<div>
<img src='data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAASABIAAD/4QBYRXhpZgAATU0AKgAAAAgAAgESAAMAAAABAAEAAIdpAAQAAAABAAAAJgAAAAAAA6ABAAMAAAABAAEAAKACAAQAAAABAAABWKADAAQAAAABAAABWAAAAAD/7QA4UGhvdG9zaG9wIDMuMAA4QklNBAQAAAAAAAA4QklNBCUAAAAAABDUHYzZjwCyBOmACZjs+EJ+/8IAEQgBWAFYAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAMCBAEFAAYHCAkKC//EAMMQAAEDAwIEAwQGBAcGBAgGcwECAAMRBBIhBTETIhAGQVEyFGFxIweBIJFCFaFSM7EkYjAWwXLRQ5I0ggjhU0AlYxc18JNzolBEsoPxJlQ2ZJR0wmDShKMYcOInRTdls1V1pJXDhfLTRnaA40dWZrQJChkaKCkqODk6SElKV1hZWmdoaWp3eHl6hoeIiYqQlpeYmZqgpaanqKmqsLW2t7i5usDExcbHyMnK0NTV1tfY2drg5OXm5+jp6vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAQIAAwQFBgcICQoL/8QAwxEAAgIBAwMDAgMFAgUCBASHAQACEQMQEiEEIDFBEwUwIjJRFEAGMyNhQhVxUjSBUCSRoUOxFgdiNVPw0SVgwUThcvEXgmM2cCZFVJInotIICQoYGRooKSo3ODk6RkdISUpVVldYWVpkZWZnaGlqc3R1dnd4eXqAg4SFhoeIiYqQk5SVlpeYmZqgo6SlpqeoqaqwsrO0tba3uLm6wMLDxMXGx8jJytDT1NXW19jZ2uDi4+Tl5ufo6ery8/T19vf4+fr/2wBDAAYGBgYGBgoGBgoOCgoKDhIODg4OEhcSEhISEhccFxcXFxcXHBwcHBwcHBwiIiIiIiInJycnJywsLCwsLCwsLCz/2wBDAQcHBwsKCxMKChMuHxofLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi4uLi7/2gAMAwEAAhEDEQAAAfVNtW21bbVttW21bbVttW21bbVttW21bbVttW21bbVttW21bbVttW21bbVttW21bb5Wr6p3ytq+qd8ravqnfK2r6p2+Vq+qd8ravqnbVt8rfVNbb5Wr6p21bfK31TW3yt9U1ttW3ytq+qd8rfVNbb5Wr6p3ytq+qd8ravqnfK2r6p21bbVttW+Vvqn5Wr6p2+Vq+qd8ravqn5W+qflavqn5W+qdXyt9U7VttXyttq+qdvlat9U75Wr6p+Vvqn5WrfVO+Vq2+qdXytvqn5WrfVPytq+qflb6p+Vq+qdvlavqnfK2r6p+Vvqn5Wr6p21bbVttW+Vvqn5Wr6p+Vvqn5Wrbavqn5W+qflavqn5W+qflavqnfK2rb6p1bfK31TW2+Vq+qd8rfVNbfK2r6p+Vt9U1t8ravqnfK31TXyttq+qflb6p+Vq+qflb6p+Vq22r6p+Vvqn5Wr6p21bbVttW+Vvqn5Wr6p3ytq+qd8ravqn5W019UfK31T8rVvqnfK1bfVPytX1Tt8r1H1Tvlatvqn5Wr6p2+Vq31Tvlavqnb5Wr6p+Vvqn5Wrb6p+Vq+qflb6p+Vq+qd8ravqnfK2r6p+Vtq+qdtW21bbVttW21bfK31TW2+Vq+qdtW+V/qjVtvlatt9U18rb6p1fK22r6p3yt9U1vlb6p1fK2+qflavqn5W31TW3yt9U1ttW3ytq+qd8rfVNbfK2r6p21bbVttW2+Vq+qd8rfVNfK22r6p2+V6+qNvlavqn5W+qdW2+Vq+qflb6p1fK31TtW21fK2+qflatvqnVttXytvqnVtvlatvqn5Wr6p2+Vq31TtXytvqn5Wr6p21bbVttW+Vvqn5WrfVPyt9U1t8rfVNbfK2rbavqnfK2r6p2+Vq+qflbfVNfK2+qflatt9U1tvlavqn5W+qflatvqnV8rfVPyt9U18rfVPyt9U1tvlatt9U1t8rfVNb5W+qflavqnbVttW21b5W+qflavqnb5WrbfVNfK31TvlavqnfK2rb6p1fK31Tvlat1vvgK8i3sGonjfsGrx/2QcUXCFTr5W633yvlb6p+VtW+qd8rV9U/K21b6p+Vvqmvlb6p3ytW31T8rV9U7attq22rfK31Tq2+VtX1Tvlb6pr5W+qd8rV9U7at8rxq+qflb6p+Vq+qRFFRULHBEcmz24O+3C9Yu9gIo8+lSh/LVbfVOqJ+VvqmtvlbVt9U6tvlbVvqnattq22rbat8rfVOr5W+qflbV9U/K31T8rV9U7fK9Rvqn5Wr6p3ytq+qflb6p+Vq+qELRRGL1sU4a855r2+Kr0Dg/SMewgyD5/R3y19Tqr5W2+qa3yt9U/K1bfVPytX1T8rfVOr5W21fVPyttX1Ttq22rbat8rfVPytX1T8rx9U18rfVPytq+qdvlavqnbV8rfVO1fK31TvlavRfYFJojaGkHbHQVI+ZN6vB7B/H/OvqZdb5W+qflavqnfK2rfVPytq22r6p+VvqnVvlbfVNbbVttW21bb5WrfVPyt9U1t8rfVNfK31T8rTUfVO+Vq31TtW21Ya21EZP9TBT3U0G/wBUThUX5a+pPluvqnfK2r6p2+Vq231RU75W1fVPyttX1TvlbV9U7attq22rbavlb6p2r5W2+qa+VvqnfK1TH1T8rV9U7avlbb6pr5W63ktXou861fTPlfnX1RVf5Z519UUw8T971JX8ratvqnVvlbfVNfK22r6p+VvqnVon5Wr6p+Vvqn5Wr6p21bbVttW2+Vq+qdvlavqnR8r19U7fK1b6p3ytW+qflaajfVPytW21b6p2rfK2+qa2+VtW31T8r1G+qflavqnb5Wr6p+VvqnV8rfVPyt9U18rfVO+Vq31T8ravqn5W+qflavqnbVttW21bb5WrbfVNfK2+qflavqnfK2rb6p1fK2+qflavqn5W2r6p+VvqnV8rbfVNb5X+qNXyv9Ub5Wr6piflavqn5W2rb6p1fK2+qflattq31T8ravqnfK2r6p+Vt9U1ttW21bbVtvlavqnfK2r6p3ytq+qd8ravqn5W+qdW+VvqnVvlb6p1fK31T8rfVNbbVttW3yv9UV8rb6p1fK2+qflavqn5W+qYqflb6p+Vq+qdvlevqj5W+qflavqnb5WrbavqnbVttW21b5W+qflavqnb5Wr6p3ytq+qflb6p+Vq+qdtW3ytq22r6p3yt9U1vlbavqnb5Wr6p3yt9U18rb6p1bb5Wr6p+V4+qa3yt9U/K1fVO+VtX1T8rbV9U/K2+qaiflb6prbattq22rfK31T8rV9U/K31T8rVttX1T8rfVPytX1T8rfVOrbfK1fVPyttX1Tt8r19UbfK1b6p2rfK31T8rVvqn5W1b6pia+Vvqn5W+qa2+VtW+qdq+Vt9U/K1fVPyt9U/K1bfVPytX1Ttq22rbat8rfVPytX1TvlbV9U75W1fVPyttX1Ttq+VttX1TvlbVvqnfK1fVPytvqmvlaY+qa3ytvqmvlbfVPytX1T8rbVvqn5W+qa+Vt9U/K1fVO+VtW31Tq+Vvq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' style="width: 200px; hight: 200px">
</div>





  </div>
</template>

<script>
import data from './data';
export default {
  name: 'HelloWorld',
  methods: {
  select: function (item){
     console.log(item.target.checked)
     console.log(item.target.id)
     console.log(this.coinlist)
     var obj=[];
     this.coinlist.forEach(function(one){
       //console.log(item)
       if(one.i==parseInt(item.target.id)){
           one.checked=item.target.checked;

       }
       if(one.checked){
         obj.push(one);
       }
     })

     this.$emit('myevent',obj)


     }
  },
  data () {
    return {
      msg: '持币人的信仰',
      coinlist:data
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.inputGroup {
  background-color: #fff;
  display: block;
  margin: 10px 0;
  position: relative;
}
.inputGroup label {
  padding: 12px 30px;
  width: 100%;
  display: block;
  text-align: left;
  color: #3c454c;
  cursor: pointer;
  position: relative;
  z-index: 2;
  transition: color 200ms ease-in;
  overflow: hidden;
}
.inputGroup label:before {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  content: "";
  background-color: #5562eb;
  position: absolute;
  left: 50%;
  top: 50%;
  -webkit-transform: translate(-50%, -50%) scale3d(1, 1, 1);
          transform: translate(-50%, -50%) scale3d(1, 1, 1);
  transition: all 300ms cubic-bezier(0.4, 0, 0.2, 1);
  opacity: 0;
  z-index: -1;
}
.inputGroup label:after {
  width: 32px;
  height: 32px;
  content: "";
  border: 2px solid #d1d7dc;
  background-color: #fff;
  background-image: url("data:image/svg+xml,%3Csvg width='32' height='32' viewBox='0 0 32 32' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M5.414 11L4 12.414l5.414 5.414L20.828 6.414 19.414 5l-10 10z' fill='%23fff' fill-rule='nonzero'/%3E%3C/svg%3E ");
  background-repeat: no-repeat;
  background-position: 2px 3px;
  border-radius: 50%;
  z-index: 2;
  position: absolute;
  right: 30px;
  top: 50%;
  -webkit-transform: translateY(-50%);
          transform: translateY(-50%);
  cursor: pointer;
  transition: all 200ms ease-in;
}
.inputGroup input:checked ~ label {
  color: #fff;
}
.inputGroup input:checked ~ label:before {
  -webkit-transform: translate(-50%, -50%) scale3d(56, 56, 1);
          transform: translate(-50%, -50%) scale3d(56, 56, 1);
  opacity: 1;
}
.inputGroup input:checked ~ label:after {
  background-color: #54e0c7;
  border-color: #54e0c7;
}
.inputGroup input {
  width: 32px;
  height: 32px;
  order: 1;
  z-index: 2;
  position: absolute;
  right: 30px;
  top: 50%;
  -webkit-transform: translateY(-50%);
          transform: translateY(-50%);
  cursor: pointer;
  visibility: hidden;
}

.form {
  padding: 0 16px;
  max-width: 550px;
  margin: 50px auto;
  font-size: 18px;
  font-weight: 600;
  line-height: 36px;
  background-color: #d1d7dc;
}

body {

  font-family: "Fira Sans", sans-serif;
}

*,
*::before,
*::after {
  box-sizing: inherit;
}

html {
  box-sizing: border-box;
}

code {
  background-color: #9aa3ac;
  padding: 0 8px;
}
</style>
