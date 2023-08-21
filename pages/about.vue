<template>
    <div>
        <h1>about me</h1>
        <img :src="picture" :width="size" :height="size">
        <form @submit.prevent="submitForm">
            <label for="nickname">ชื่อเล่น :</label>
            <input type="text" v-model="nickName" id="nickname">
            <button type="submit">บันทึก</button>
        </form>
        <p>ชื่อ : {{ firstname }}</p>
        <p>นามสกุล : {{ lastname }}</p>
        <p>อายุ : {{ age }}</p>
        <p>ที่อยู่ : <span v-html="address"></span></p>
        <p>งานอดิเรก :</p>
        <ul>
            <li>{{ hobby[0] }}</li>
            <li>{{ hobby[1] }}</li>
            <li>{{ hobby[2] }}</li>
        </ul>
        <p>ข้อมูลพื้นฐาน :</p>
        <ul>
            <li>เพศ {{ general.gender }}</li>
            <li>น้ำหนัก {{ general.weight }}</li>
            <li>ส่วนสูง {{ general.height }}</li>
            <li>โรคประจำตัว {{ general.status }}</li>
        </ul>
        <button @click="showData">คลิกเพื่อดูข้อมูล</button>
        <button @click="increment(10)">เพิ่มค่า</button>
        <button @click="decrement(3)">ลดค่า</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            firstname: "kitsanaphong",
            lastname: "suebtrakunkiat",
            age: 20,
            address: "chonburi",
            picture: "https://scontent-sin6-2.xx.fbcdn.net/v/t39.30808-6/366630404_122097318950003350_8083312772731546622_n.jpg?_nc_cat=109&ccb=1-7&_nc_sid=be3454&_nc_eui2=AeE5hUBKmP7qYIRjiexXa1FVV-rmNFVfrpBX6uY0VV-ukJPeMq076BJgd5Cj_CvskIfPc8ubGgR4vURxP4BLbqe6&_nc_ohc=Rk-_6d2zYgEAX9oKE7E&_nc_ht=scontent-sin6-2.xx&oh=00_AfCJC8etS06rMr6mbnmEXB8znIMArMAzXiuzB4zwzqbMSw&oe=64D999DB",
            size: 150,
            hobby: ["อ่านการ์ตูน", "เล่นเกมส์", "ฟังเพลง"],
            general: {
                gender: "ชาย",
                weight: 92,
                height: 177,
                status: false
            },
            nickName: ""
        };
    },
    methods: {
        showData() {
            console.log(this.firstname);
            console.log(this.lastname);
            console.log(this.age);
            console.log(this.address);
            console.log(this.hobby);
            console.log(this.general);
            alert(this.firstname);
        },
        increment(value) {
            this.age += value;
        },
        decrement(value) {
            this.age -= value;
        },
        setNickName(event) {
            this.nickName = event.target.value;
        },
        submitForm() {
            alert('บันทึกสำเร็จ')
        }
    }
};
</script>
