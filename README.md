# JavaScript

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=EUC-JP">
<title>widescreen images switching effects focus map with jQuery</title>
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.8.0/jquery.min.js"></script>
<script type="text/javascript" src="js/superslide.2.1.js"></script>
<style type="text/css">		
* {
	margin:0;
	padding:0;
	list-style:none;
}
body {
	background:#fff;
	font:normal 12px/22px  Arial, Helvetica, sans-serif;
	width:100%;
}
img {
	border:0;
}
a {
	text-decoration:none;
	color:#333;
}
a:hover {
	color:#1974A1;
}
#footer {
	text-align:center;
}
.slider {
	width:100%;
	min-width:980px;
	height:400px;
	position:relative;
	overflow:hidden;
	background:#fff;
	text-align:center;
}
.slider .bd {
	width:980px;
	position:absolute;
	left:50%;
	margin-left:-490px
}
.slider .bd li {
	width:980px;
	overflow:hidden;
}
.slider .bd li img {
	display:block;
	width:980px;
	height:400px;
}
.slider .tempWrap {
	overflow:visible !important
}
.slider .tempWrap ul {
	margin-left:-980px !important;
}
.slider .hd {
	position:absolute;
	width:100%;
	left:0;
	z-index:1;
	height:8px;
	bottom:20px;
	text-align:center;
}
.slider .hd li {
	display:inline-block;
	*display:inline;
	zoom:1;
	width:8px;
	height:8px;
	line-height:99px;
	overflow:hidden;
	background:url(images/slider-btn.png) 0 -10px no-repeat;
	margin:0 5px;
	cursor:pointer;
	filter:alpha(opacity=60);
	opacity:0.6;
}
.slider .hd li.on {
	background-position:0 0;
	filter:alpha(opacity=100);
	opacity:1;
}
.slider .pnBtn {
	position:absolute;
	z-index:1;
	top:0;
	width:100%;
	height:400px;
	cursor:pointer;
}
.slider .prev {
	left:-50%;
	margin-left:-490px;
}
.slider .next {
	left:50%;
	margin-left:490px;
}
.slider .pnBtn .blackBg {
	display:block;
	position:absolute;
	left:0;
	top:0;
	width:100%;
	height:400px;
	background:#fff;
	filter:alpha(opacity=50);
	opacity:0.5;
}
.slider .pnBtn .arrow {
	display:none;
	position:absolute;
	top:0;
	z-index:1;
	width:60px;
	height:400px;
}
.slider .pnBtn .arrow:hover {
	filter:alpha(opacity=60);
	opacity:0.6;
}
.slider .prev .arrow {
	top:50px;
	right:0;
	background:url(images/slider-arrow.png) -120px 0 no-repeat;
}
.slider .next .arrow {
	top:50px;
	left:0;
	background:url(images/slider-arrow.png) 0 0 no-repeat;
}

</style>
</head>
<body>
<div class="slider">
  <div class="bd">
    <ul>
      <li><iframe src="images/4-4.jpg" width="980" height="400" style="text-align:center" scrolling="NO" border="0" frameborder="0" marginheight="0" marginwidth="0"></iframe></li>
      <li><img src="images/2-2.jpg" /></li>
      <li><img src="images/1-1.jpg" /></li>  
     
    </ul>
  </div>
  <div class="hd">
    <ul>
    </ul>
  </div>
  <div class="pnBtn prev"> <span class="blackBg"></span> <a class="arrow" href="javascript:void(0)"></a> </div>
  <div class="pnBtn next"> <span class="blackBg"></span> <a class="arrow" href="javascript:void(0)"></a> </div>
</div>
<script type="text/javascript">

jQuery(".slider .bd li").first().before( jQuery(".slider .bd li").last() );

	jQuery(".slider").hover(function(){
		 
		 jQuery(this).find(".arrow").stop(true,true).fadeIn(300) 
		 },function(){ 
			jQuery(this).find(".arrow").fadeOut(300) });				
		 jQuery(".slider").slide(
			{ titCell:".hd ul", mainCell:".bd ul", effect:"leftLoop",autoPlay:true, vis:3,autoPage:true, trigger:"click"}
		
		);
</script>

</body>
</html>
