<template>
      <div class="right_info_wrap">
        <div class="right_info_title_box">
            <div class="right_info_img"><img src="../../public/img/book.gif" alt=""></div>
            <p class="right_info_txt f20">Education</p>
        </div>
        <div class="right_info_cont">
            <ul class="right_info_cont_wrap">
                <li v-for="info in EduInfo" :key="info">
                    <div class="right_info_left_cont">
                        <div class="right_info_left_cont_img" :style="{'background-image': 'url(' + info.img + ')',}">
                        </div>
                        <div class="right_info_cont_titbox">
                            <h1 class="f16">{{ info.title }}</h1>
                            <p class="f12">{{ info.subTit }}</p>
                        </div>
                    </div>
                    <div class="right_info_right_cont">
                        <p class="f12">{{ info.when }}</p>
                    </div>
                </li>
            </ul>
        </div>
    </div>    
</template>
<script>
export default {
    setup() {
        let EduInfo = [
            {title:"동아방송예술대학교",subTit:"방송기술계열(제작전공)",when:"2017.02 ~ 2022. 02",img: require('../../public/img/동방예대로고.png')},
            {title:"메가스터디 IT 신촌점",subTit:"파이썬 기초",when:"2021.09 ~ 2021. 10",img: require('../../public/img/메가스터디로고.jpg')},
            {title:"노원그린컴퓨터아카데미",subTit:"vue.js 프론트엔드 개발자 양성 과정",when:"2022.09 ~ 2023. 02",img: require('../../public/img/그린컴퓨터로고.png')},
        ]
        return {
            EduInfo
        }
    },
}
</script>
<style scoped>
.right_info_title_box{
    display: flex;
    align-items: center;
    border-bottom: 1px solid #EDEDED;
    padding-bottom: 15px;
    box-sizing: border-box;
    gap: 10px;
}
.right_info_title_box>.right_info_img{
    width: 28px;
}
.right_info_title_box>.right_info_img>img{
    display: block;
    width: 100%;
}
.right_info_cont_wrap{
    margin-top: 50px;
}
.right_info_cont_wrap>li{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.right_info_cont_wrap>li:nth-child(2){
    margin: 35px 0;
}
.right_info_left_cont{
    display: flex;
    gap: 15px;
}
.right_info_left_cont_img{
    width: 48px;
    height: 48px;
    background-image: url(../../public/img/동방예대로고.png);
    background-size: cover;
    background-position: center center;
}
.right_info_cont_titbox>h1{
    font-weight: bold;
}
.right_info_cont_titbox>p{
    color: #7D7D7D;
}
.right_info_right_cont>p{
     color: #7D7D7D;
}
</style>