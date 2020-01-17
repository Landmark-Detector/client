<template>
  <div>
    <div class="container-fluid">
      <div class="row">
        <div class="col-12 p-0">
          <div id="carouselExampleIndicators" class="carousel slide carousel-fade" data-ride="carousel" data-interval="false">
            <ol class="carousel-indicators">
              <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active">1</li>
              <li data-target="#carouselExampleIndicators" data-slide-to="1">2</li>
              <li data-target="#carouselExampleIndicators" data-slide-to="2">3</li>
            </ol>
            <div class="carousel-inner">
              <div class="carousel-item active">
                <video autoplay muted loop id="myVideo">
                <source src="../../assets/videos/travel.mp4" type="video/mp4">
                Your browser does not support HTML5 video.
                </video>
                <div class="row min-height justify-content-center">
                  <div class="col-5">
                    <div class="" style="position:absolute; top:25%;">
                      <div class="text-center text-white">
                        <span class="list-number animated fadeIn delay-2s">1</span>
                        <h1 class="title animated fadeInDown delay-1s">Location</h1>
                        <p class="mt-3 font-thin desc animated fadeInLeft delay-2s">
                          Lorem Ipsum is simply dummy text of the <span class="font-weight-bold">printing</span> and typesetting industry. Lorem <span class="font-weight-bold">Ipsum</span> has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of <span class="font-weight-bold">type</span>
                        </p>
                        <a href="http://35.240.152.89/request-token" class="btn btn-login mt-5 animated fadeIn delay-2s"><span class="pr-3"><img src="../../assets/images/twitter.png" alt="twitter" width="32"></span>Sign in with twitter</a>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="carousel-item">
                <video autoplay muted loop id="myVideo">
                <source src="http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4" type="video/mp4">
                Your browser does not support HTML5 video.
                </video>
                <div class="row min-height justify-content-center">
                  <div class="col-5">
                    <div class="" style="position:absolute; top:25%;">
                      <div class="text-center text-white">
                        <span class="list-number animated fadeIn delay-2s">2</span>
                        <h1 class="title animated fadeInDown delay-1s">Photo</h1>
                        <p class="mt-3 font-thin desc animated fadeInLeft delay-2s">
                          Lorem Ipsum is simply dummy text of the <span class="font-weight-bold">printing</span> and typesetting industry. Lorem <span class="font-weight-bold">Ipsum</span> has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of <span class="font-weight-bold">type</span>
                        </p>
                        <p class="mt-3 font-thin desc animated fadeInLeft delay-2s">
                          Lorem Ipsum is simply dummy text of the <span class="font-weight-bold">printing</span> and typesetting industry. Lorem <span class="font-weight-bold">Ipsum</span> has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of <span class="font-weight-bold">type</span>
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="carousel-item">
                <video autoplay muted loop id="myVideo">
                <source src="http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ElephantsDream.mp4" type="video/mp4">
                Your browser does not support HTML5 video.
                </video>
                <div class="row min-height justify-content-center">
                  <div class="col-5">
                    <div class="" style="position:absolute; top:25%;">
                      <div class="text-center text-white">
                        <span class="list-number animated fadeIn delay-2s">3</span>
                        <h1 class="title animated fadeInDown delay-1s">Share</h1>
                        <p class="mt-3 font-thin desc animated fadeInLeft delay-2s">
                          Lorem Ipsum is simply dummy text of the <span class="font-weight-bold">printing</span> and typesetting industry. Lorem <span class="font-weight-bold">Ipsum</span> has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of <span class="font-weight-bold">type</span>
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "landingPage",
}
$('.carousel').carousel({
  interval: false
})
</script>

<style scoped>
#myVideo, #myVideo2 {
  position: absolute;
  right: 0;
  bottom: 0;
  min-width: 100%;
  min-height: 100%;
}
.min-height {
  min-height: 800px;
}

.font-thin {
  font-weight: 300;
}

.title {
  font-size: 60px;
  font-weight: 400;
}

.desc {
  line-height: 1.9rem;
  letter-spacing: 1px;
  font-size: 16px;
}

.carousel-indicators {
  bottom: unset;
  top: 50px;
  justify-content: left;
}

.btn {
  padding: 0.375rem 9rem;
  border-radius: 100px;
  font-weight: 700;
}

.btn-login {
  color: #fff;
  background-color: #1da1f2;
  border-color: #1da1f2;
}
.btn-login:hover {
  color: #fff;
}

.carousel-indicators li {
  text-indent: unset;
  width: unset;
  height: unset;
  padding: 2px 10px;
  border-radius: 50%;
  margin-left: 5px;
  margin-right: 5px;
  color: #636e72;
}

.list-number {
  border: 1px solid #fff;
  padding: 4px 12px;
  border-radius: 50%;
  font-size: 24px;
}
</style>
