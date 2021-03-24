###  vue3中渲染函数咋用？
1、在.vue文件中使用vue3渲染函数？
2、vue实现一个div可以拖拽至网页中的任何位置？
#### div部分
<div class="anbaoxinxi" id="drift" @mousedown="mousedown">
 拖动内容
</div>
#### js部分
mousedown (event) {
      this.selectElement = document.getElementById('drift')
      var div1 = this.selectElement
      this.selectElement.style.cursor = 'move'
      this.isDowm = true
      var distanceX = event.clientX - this.selectElement.offsetLeft
      var distanceY = event.clientY - this.selectElement.offsetTop
      // alert(distanceX)
      // alert(distanceY)
      console.log(distanceX)
      console.log(distanceY)
      document.onmousemove = function (ev) {
        var oevent = ev || event
        div1.style.top = oevent.clientY - distanceY + 'px'
        div1.style.left = oevent.clientX - distanceX + 'px'
        div1.style.right = 'auto'
      }
      document.onmouseup = function () {
        document.onmousemove = null
        document.onmouseup = null
        div1.style.cursor = 'default'
      }
    }



