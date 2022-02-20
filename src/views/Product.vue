<template>
  <div
    class="bg-image d-flex justify-content-center align-items-center"
    style="background-color: rgb(243, 146, 107)"
  >
    <v-container>
      <center><h1 style="color: white">4U2</h1></center>
      <v-container class="d-flex flex-wrap">
        <v-card
          class="mx-auto mb-5"
          max-width="400"
          v-for="(i, index) in productlist"
          :key="index"
        >
          <br>
          <v-card-title>{{ i.name }}</v-card-title>
          <v-img class="text-black align-end" height="350px" :src="i.imageurl"></v-img>

          <v-card-subtitle class="pb-0">{{ i.rightText }}</v-card-subtitle>
          <br>

          <v-card-text class="text--primary">
            <div style="font-size: large">{{ i.leftText }}</div>
          </v-card-text>

          <v-card-actions>
            <v-btn color="red accent-1" text :to="'/detail/' + i.rightText"
              >detail</v-btn
            >
            <v-btn color="red accent-1" @click="selected(i)"> Add </v-btn>
          </v-card-actions>
        </v-card>
      </v-container>

      <table class="table table-striped table-hover"></table>
      <v-container
        ><h4 class="text-danger fs-1"> Total {{ total() }} Baht</h4></v-container
        >
      <v-container grid-list-xs class="white">
        <router-view :key="$route.path"></router-view>
      </v-container>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      productlist: [
        {
          name: "4U2 EST. HARDER",
          imageurl:
            "https://image.makewebeasy.net/makeweb/0/pyuHEt3NP/HAR_Packshot/HAR_C_01.jpg?v=202012190947",
          rightText:
            "ลิปแมทจุ่ม การันตี 'ไม่ติดMask!'สวยสับแบบปากแน่นไม่มีหลุด แมสก์ไม่เลอะอีกต่อไป เนื้อลิปนุ่ม ไม่ตกร่อง ปากไม่ตึง เบาสบายปาก คนปากแห้งใช้ได้ไม่เป็นขุย 15 เฉดสีใหม่ การันตีสวยทุกโทน ##ปริมาณสุทธิ 2 กรัม",
          leftText: "Price : 229",
          active: false,
          price: 229,
        },

        {
          name: "4U2 TOUCH MY LIP",
          imageurl:
            "https://image.makewebeasy.net/makeweb/0/pyuHEt3NP/TML_Packshot/TML_AB_01.jpg?v=202012190947",
          rightText:
            "รุ่นนี้การันตีความสวยและดี ทาแล้วปากสวยมากก 100% เนื้อมูสนุ่มมมม เบาสบายปาก เบลอร่องปากให้ตื้นขึ้น ปากฟูเหมือนเติมฟิลเลอร์ สาวปากแห้งใช้ได้สบายมาก ติดทนนาน10/10 ไปเลย!! สีสวยละมุนทั้ง 18 เฉดสี มีครบทุกโทนสีนู้ด ส้ม ชมพู น้ำตาล แดงตุ่นๆ ##ปริมาณสุทธิ 3 กรัม",
          leftText: "Price : 259",
          active: false,
          price: 259,
        },

        {
          name: "4U2 MINERAL TINT OIL",
          imageurl:
            "https://image.makewebeasy.net/makeweb/0/pyuHEt3NP/MTO_packshot/1.jpg?v=202012190947",
          rightText:
            "ทินท์ออยล์สุดฉ่ำ ที่สุดของปากฉ่ำ ระเรื่อๆ Glossy ดูสุขภาพดี ปากดูสวย อวบอิ่ม แบบสาวเกา มี 12 สี 3 โทน มีสารบำรุงVIT E และแร่ธาตุ Magnesium , Zinc , Copper จากฝรั่งเศส ช่วยต้านอนุมูลอิสระ และชะลอการเกิดริ้วรอย ##ปริมาณสุทธิ 3 กรัม",
          leftText: "Price : 259",
          active: false,
          price: 259,
        },
        {
          name: "4U2 MULTI PIPE",
          imageurl:
            "https://image.makewebeasy.net/makeweb/0/pyuHEt3NP/MTP/mtp_01a.jpg?v=202012190947",
          rightText:
            "ครีมเพ้นท์ เนื้อมูสนุ่มๆ เกลี่ยแล้วเนียนสุดๆ แต่งแต้มสีสันได้ทั้งแก้ม ตา ปาก มาในแพ็คเกจหลอดปุ๊กปิ้ก พกพาง่าย ชิ้นเดียวสวยครบออกจากบ้านได้เลย มีให้เลือกถึง 9 เฉดสี ##ปริมาณสุทธิ 6 กรัม",
          leftText: "Price : 259",
          active: false,
          price: 259,
        },
        {
          name: "4U2 LIP GLAM VOL.2",
          imageurl:
            "https://image.makewebeasy.net/makeweb/r_409x409/pyuHEt3NP/GL2_Pachshot/GL2_c_01.jpg?v=202012190947",
          rightText:
            "	ลิปบาล์มมีสี ลิปลูกรักของทุกคน ให้สีปากระเรื่อๆธรรมชาติ ฉ่ำๆ สุขภาพดี ทาง่าย ใช้ง่าย ทาได้ทุกวัน เฉดสีใหม่ ละมุน 9 สี คัดแล้วที่ทายังไงก็สวย",
          leftText: "Price : 199",
          active: false,
          price: 199,
        },
        {
          name: "4U2 LIP GLAM",
          imageurl:
            "https://image.makewebeasy.net/makeweb/r_409x409/pyuHEt3NP/GLM/GLM_03.jpg?v=202012190947",
          rightText:
            "ลิปเนื้อฉ่ำ Glossy Lip Balm ทาบางๆ 1 ครั้งได้ปากลุคสุขภาพดี Healthy Glow อุดมไปด้วยสารสกัดต่างๆที่ช่วยบำรุงริมฝีปาก เนื้อลิปคือเนียนนุ่มลื่น ทาง่าย พิกเมนท์สีสวยชัดเกินต้าน มีทั้งหมด 9 เฉดสี",
          leftText: "Price : 199",
          active: false,
          price: 199,
        },
      ],
    };
  },
  methods: {
    selected: function (i) {
      i.active = !i.active;
    },
    total: function () {
      var sum = 0;
      this.productlist.forEach(function (i) {
        if (i.active) {
          sum += i.price;
        }
      });
      return sum;
    },
  },
};
</script>

<style>
h2 {
  color: rgb(212, 212, 212);
}
</style>
