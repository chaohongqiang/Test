<!DOCTYPE HTML>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta charset="utf-8">
<title>banner</title>
<style>
*{margin:0px; padding:0px;}
#banner{width:500px; height:200px; margin:0 auto; position:relative; overflow:hidden;}
#banner ul{position:absolute; width:500%; height:100%; left:0; top:0;}
#banner ul li{float:left;list-style:none;cursor:pointer;}
#banner ol{ position:absolute; bottom:10px;right:10px;}
#banner ol li{list-style:none; float:left; width:30px; height:30px; border:1px solid #FFF; box-sizing:border-box; text-align:center; line-height:30px; color:#000; cursor:pointer;}
.active{background:#ff6600;}
</style>
<script>
window.onload=function(){
    var oBanner=document.getElementById('banner');
    var oUl=oBanner.getElementsByTagName('ul')[0];
    var aBtn=oBanner.getElementsByTagName('ol')[0].getElementsByTagName('li');
    var now=0;
     for(var i=0;i<aBtn.length;i++){
       aBtn[i].index=i;
       aBtn[i].onclick=function (){
             now=this.index;
             tab();
         }
     }
   
     function tab(){
     for(var i=0;i<aBtn.length;i++)
	{
	aBtn[i].className='';
	}
	aBtn[now].className='active';
    oUl.style.left=-500*now+'px';
 
     }
     function next()
	{
         now++;
         if(now==aBtn.length)
	    {
		    now=0;
	    }
	    tab();  
	}

      var timer=setInterval(next,2000);
       oBanner.onmouseover=function ()
	{
		clearInterval(timer);
	};
	   oBanner.onmouseout=function ()
	{
		timer=setInterval(next,2000);
	};

    
}
</script>
</head>
<body>
<div id="banner">
  <ul>
      <li><img src="1.jpg" width="500px" height="200px" title="图片" alt="banner1"></li>
      <li><img src="2.jpg" width="500px" height="200px" title="图片" alt="banner2"></li>
      <li><img src="3.jpg" width="500px" height="200px" title="图片" alt="banner3"></li>
      <li><img src="4.jpg" width="500px" height="200px" title="图片" alt="banner4"></li>
  </ul>
    <ol>
      <li class="active">1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
  </ol>
</div>
</body>
</html>
