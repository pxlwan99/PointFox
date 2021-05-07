<template>
  <div>
    <div id="txt">
      <textarea id="text" cols="60" rows="20"></textarea><br />
      <button id="btn">提交留言</button>
      <div id="lis">
        <ol id="text_li"></ol>
      </div>
    </div>
    <div id="sidebar">
      <div class="header">
        <span class="col_fade">作者</span>
      </div>
      <div class="inner">
        <div class="user_card">
          <div>
            <a class="user_avatar" href="/user/thonatos">
              <img
                src="https://avatars.githubusercontent.com/u/958063?v=4&amp;s=120"
                title="thonatos"
              />
            </a>
            <span class="user_name"
              ><a class="dark" href="/user/thonatos">Thonatos</a></span
            >

            <div class="board clearfix">
              <div class="floor">
                <span class="big">积分: 255 </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
#sidebar {
  position: absolute;
  right: 10px;
  top: 80px;
  width: 290px;
}
.header {
  color: #51585c;
  border-radius: 3px 3px 0 0;
}
.inner {
  padding: 10px;
  border-radius: 0 0 3px 3px;
  background-color: #fff;
}
#lis {
  width: 500px;
  height: 200px;
  overflow: hidden;
  background-color: antiquewhite;
}
</style>