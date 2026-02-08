<template>
  <div id="part1-documents" :class="background">
    <!-- <div v-if="page === 1" class="document1">

    </div> -->
    <div v-if="result !== ''" class="black-div"></div>
    <document class="document1" @result="sendResult" @to-end="toEnd"></document>
    <result class="result" :resultFrom="result" />
    <button class="back-btn" @click="openDit = !openDit">
   פתיחת פרטים
</button>
<div v-if="openDit" class="text-div">
  <p class="text">
חשודה – טוראי רותם בן שושן מ.א- 9753629 ת.ז- 396231467, טבחית בבח״א 10<br>
חשדות – אלימות כלפי חייל, הטלת מום, שיבוש הליכי חקירה ומשפט<br>
חוקר – רב״ט שחר שמעוני מ.א- 9354973, חוקר פלילי במצ״ח 6012<br>
סימוכין – מס׳ תיק 2025/0201 מתנהל במצ״ח
</p>
<p class="text">
במצ״ח ערבה התקבל דיווח המחשיד את טוראי רותם בן שושן באלימות כלפי חייל, הטלת מום ושיבוש הליכי חקירה.
החשודה נחקרה אודות החשדות הנ״ל בתאריך 04 בדצמבר 2025 בשעה 10:36.
טרם תחילת החקירה, יש צורך להזהיר את החשודה על פי חוק.
</p>
<p class="text">
יש למלא את כלל פרטי החשודה והחוקר, להסביר את החשדות ואת זכויותיה על פי חוק.
החשודה בחרה להתייעץ עם עורך דין רעות כהן בין השעות 10:43–11:04.
יש להחתים על כלל המסמכים ולציין כי גביית האמרה הועברה לכתיבה במחשב.
</p>
    </div>
  </div>
</template>

<script>
import document from "./document.vue";
import result from "./result.vue";
export default {
  components: {
    document,
    result
  },
  data() {
    return {
      inputs: [],
      reasonAnswer: "",
      roomUser: "",
      result: "",
      openDit: false,
    };
  },
  methods: {
    sendResult(res) {
      this.result = res;
    },
    toEnd() {
      this.$emit("to-end");
    },
  },
};
</script>

<style scoped>
.document1 {
  height: 95vh;
}
.result {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
}

.black-div {
  width: 100vw;
  height: 100vh;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  background-color: rgba(0, 0, 0, 0.623);
  pointer-events: none;
}
.back-btn {
  font-family: "rubik";
  font-weight: bold;
  font-size: 1rem;
  background-color: #be0000;
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  color: white;
  cursor: pointer;
  border: none;
  position: fixed;
  right: 1%;
  z-index: 3;
}
.text-div {
  position: absolute;
  top: 50%;
  left: 125%;
  transform: translate(-50%, -50%);
  z-index: 2;
  background-color: #be0000;
  padding: 1rem;
  border-radius: 2rem;
}
.text {
  color: white;
  width: 20rem;
  font-family: "rubik";

}
@media (max-width: 1290px) {
  .document1 {
  height: 85vh;
} 
.text-div {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  background-color: #be0000;
  padding: 1rem;
  border-radius: 2rem;
}

}
@media (max-width: 630px) {
  .document1 {
  height: 85vh;
} 

}
@media (max-width: 530px) {
  .document1 {
  height: 75vh;
} 
}
@media (max-width: 435px) {
  .document1 {
  height: 60vh;
  /* width: 10rem; */
} 
.back-btn {
  font-size: 0.8rem;
  top: -1rem;
}
}
@media (max-width: 360px) {
  .document1 {
  height: 53vh;
  /* width: 10rem; */
} 
}
@media (max-height: 660px) {
  .document1 {
  height: 65vh;
} 
}

</style>
