<template>
    <div class="left_info_wrap">
        <div class="left_info_title_box">
            <div class="left_info_img"><img src="../../public/img/icons8-정보.gif" alt=""></div>
            <p class="left_info_txt f20">Personal information</p>
        </div>
        <div class="left_info_cont">
            <ul class="left_info_cont_wrap">
                <li v-for="info in PersonalInfo" :key="info">
                    <div class="left_info_cont_img"><img v-bind:src="info.img" alt=""></div>
                    <div class="left_info_cont_txt">
                        <h2 class="f16">{{info.title}}</h2>
                        <p v-if="info.text !== 'https://github.com/potato980124'" class="f12">{{info.text}}</p>
                        <a href="https://github.com/potato980124" v-else  class="f12">https://github.com/potato980124</a>
                    </div>
                </li>
            </ul>
        </div>
    </div>    
</template>
<script>
export default {
    setup() {
        let PersonalInfo = [
            {title:"이름",text:"홍범진",img: require('../../public/img/user.png')},
            {title:"생년월일",text:"1999.01.24",img: require('../../public/img/calendar.png')},
            {title:"주소지",text:"서울특별시 성북구",img: require('../../public/img/pin.png')},
            {title:"연락처",text:"010-4752-3464",img: require('../../public/img/call.png')},
            {title:"이메일",text:"potato980124@gmail.com",img: require('../../public/img/email.png')},
            {title:"깃허브",text:"https://github.com/potato980124",img: require('../../public/img/github2.png')}
        ]
        return {
            PersonalInfo
        }
    },
}
</script>
<style scoped>
.left_info_title_box{
    display: flex;
    align-items: center;
    border-bottom: 1px solid #EDEDED;
    padding-bottom: 15px;
    box-sizing: border-box;
    gap: 10px;
}
.left_info_title_box>.left_info_img{
    width: 28px;
}
.left_info_title_box>.left_info_img>img{
    display: block;
    width: 100%;
}
.left_info_cont_wrap{
    display: flex;
    flex-wrap: wrap;
    margin-top: 50px;
}
.left_info_cont_wrap>li{
    width: 33.333%;
    display: flex;
    align-items: center;
    gap: 30px;
}
.left_info_cont_wrap>li:nth-child(4){
    margin-top: 35px
}
.left_info_cont_wrap>li:nth-child(5){
    margin-top: 35px
}
.left_info_cont_wrap>li:nth-child(6){
    margin-top: 35px
}
.left_info_cont_img{
    flex-shrink: 0;
    width: 32px;
}
.left_info_cont_img>img{
    display: block;
    width: 100%;
}
.left_info_cont_txt>h2{
    font-weight: bold;
}
.left_info_cont_txt>p{
    color: #7D7D7D;
}
</style>