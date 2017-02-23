# scrollspy
滚动监听，根据滚动条的位置自动更新对应的导航目标

一、插件版

html:

    <div id="navbar">
      <ul class="nav">
        <li class="active"><a href="#01">01</a></li>
        <li><a href="#02">02</a></li>
        <li><a href="#03">03</a></li>
        <li><a href="#04">04</a></li>
        <li><a href="#05">05</a></li>
        <li><a href="#06">06</a></li>
        <li><a href="#07">07</a></li>
        <li><a href="#08">08</a></li>
        <li><a href="#09">09</a></li>
      </ul>
    </div>
    <div class="con">
      <div id="01">01</div>
      <br/><br/><br/><br/>
      <div id="02">02</div>
      <br/><br/><br/><br/>
      <div id="03">03</div>
      <br/><br/><br/><br/>
      <div id="04">04</div>
      <br/><br/><br/><br/>
      <div id="05">05</div>
      <br/><br/><br/><br/>
      <div id="06">06</div>
      <br/><br/><br/><br/>
      <div id="07">07</div>
      <br/><br/><br/><br/>
      <div id="08">08</div>
      <br/><br/><br/><br/>
      <div id="09">09</div>
    </div>

CSS:

    <style type="text/css">
    body{position:relative;height:100%;overflow:auto;}
    .nav{position:fixed;left:0;top:0;}
    .nav .active a{color:#bd1000;}
    .con{padding:0 0  0 100px;}
    </style>

JS:

      <script type="text/javascript" src="jquery.min.js"></script>
      <script type="text/javascript" src="scrollspy.js"></script>
      <script type="text/javascript">
      $('body').scrollspy({ target: '#navbar' })
      </script>

二、简易版

html:

    <div class="side">
        <ul>
            <li class="current" data-spy="about-intro"><a href="javascript:;">公司简介</a></li>
            <li data-spy="about-license"><a href="javascript:;">资质证照</a></li>
            <li data-spy="about-gerent"><a href="javascript:;">高管介绍</a></li>
            <li data-spy="about-timeline"><a href="javascript:;">平台大事记</a></li>
            <li data-spy="about-model"><a href="javascript:;">平台运营模式</a></li>
            <li data-spy="about-concept"><a href="javascript:;">平台优势</a></li>
            <li data-spy="about-spirit"><a href="javascript:;">团队风采</a></li>
            <li data-spy="about-office"><a href="javascript:;">办公环境</a></li>
            <li data-spy="about-partners"><a href="javascript:;">合作伙伴</a></li>
            <li data-spy="about-contact"><a href="javascript:;">联系我们</a></li>
        </ul>
    </div>

    <div class="main">
        <div class="about-intro">公司简介</div>
        <div class="about-license">资质证照</div>
        <div class="about-gerent">高管介绍</div>
        <div class="about-timeline">平台大事记</div>
        <div class="about-model">平台运营模式</div>
        <div class="about-concept">平台优势</div>
        <div class="about-spirit">团队风采</div>
        <div class="about-office">办公环境</div>
        <div class="about-partners">合作伙伴</div>
        <div class="about-contact">联系我们</div>
    </div>
    
CSS：

    <style type="text/css">
    .side{position:fixed;left::0;top:0;}
    .side .current a{color:#ff0000;}
    .main>div{text-align:center;height:300px;}
    </style>
    
JS：

    <script type="text/javascript" src="jquery.min.js"></script>
    <script type="text/javascript">
        var $li = $('.side li');
        $(window).on('scroll resize load',function(){
            $li.each(function(){
                if($('.'+$(this).attr('data-spy')).offset().top <= $(window).scrollTop()){
                    $(this).addClass('current').siblings('li').removeClass('current');
                }else{
                    return false;
                }
            });
        });
    </script>
