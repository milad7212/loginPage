<template>
  <div
    class="min-h-screen bg-cover flex flex-col justify-center items-center"
    :style="{ backgroundImage: `url(${backgroundImage})` }"
  >
    <div class="text-white flex justify-end w-4/5 md:w-2/3">
      <div class="font-black ml-2 flex items-end">
        <span class="ml-1 font-bold text-xs">ب.ظ</span>

        1.36
      </div>

      <div class="font-bold">
        <p class="">شنبه</p>
        <p class="">3 تیر</p>
      </div>
    </div>
    <div
      class="rounded-lg w-4/5 md:w-2/3 overflow-hidden shadow-xl grid md:grid-cols-[2fr_3fr] grid-cols-1"
    >
      <div class="bg-white p-4 flex flex-col items-center">
        <img src="./assets/icon.png" class="w-[81px] h-[55px]" alt="" />
        <span class="text-[#FFA266] font-black my-4">ورود به سیستم</span>
        <div class="">
          <span class="block mb-4 my-2">نام کاربری</span>
          <div class="flex p-2 rounded-lg border border-gray-300 group">
            <img
              class="w-5 h-5 group-hover:animate-bounce"
              src="./assets/icons/userIcon.svg"
            />
            <input
              class="placeholder:text-xs placeholder:font-bold pr-4 outline-none"
              type="text"
              placeholder="نام کاربری را وارد کنید"
            />
          </div>

          <div class="py-4">
            <span class="block mb-4 my-2">رمز عبور</span>
            <div class="flex p-2 rounded-lg border border-gray-300 group">
              <img
                class="w-5 h-5 group-hover:animate-bounce"
                src="./assets/icons/lockIcon.svg"
              />
              <input
                class="placeholder:text-xs placeholder:font-bold pr-4 outline-none flex-1"
                :type="showPassword ? 'text' : 'password'"
                placeholder="رمز عبور را وارد کنید"
              />
              <button
                class="w-5 h-5 cursor-pointer hover:scale-95 transition-all duration-150 ease-in"
                @click.prevent="showPassword = !showPassword"
              >
                <img
                  v-if="!showPassword"
                  src="./assets/icons/closeEyeIcon.svg"
                />
                <img v-if="showPassword" src="./assets/icons/openEyeIcon.svg" />
              </button>
            </div>
          </div>

          <p
            class="text-xs underline cursor-pointer my-2 mb-6 hover:font-black transition-all duration-150 ease-in"
          >
            گذرواژه را فراموش کرده ام!
          </p>
          <div class="flex justify-between items-center mb-4">
            <input
              class="p-2 rounded-lg border w-32 border-gray-300 pr-4 outline-none text-center"
              type="text"
              placeholder="کد امنیتی"
              v-model="sumRandomNumbers"
            />
            <div class="flex items-center">
              <img
                @click="changeNumbers"
                :class="[
                  'w-5',
                  'h-5',
                  'ml-2',
                  'cursor-pointer ',

                  'active:scale-110',
                  isRotateRefreshIcon ? 'animate-spin' : '',
                ]"
                src="./assets/icons/refreshIcon.svg"
              />
              <div
                class="p-2 rounded-lg w-20 flex justify-center items-center border border-gray-300 px-4 font-black select-none"
              >
                <span>{{ randomNum1 }}</span
                ><span class="mx-1">+</span>
                <span>{{ randomNum2 }}</span>
              </div>
            </div>
          </div>
          <button
            :disabled="isDisabledBtn"
            :class="[
              'text-white',
              'w-full',
              'my-4',
              'py-2',
              'rounded-md',
              'active:scale-95',
              'transition-all',
              'duration-150',
              'ease-in',
              isDisabledBtn
                ? 'cursor-not-allowed bg-[#FFA266]/40'
                : 'bg-[#FFA266]',
            ]"
          >
            ورود
          </button>
        </div>
      </div>
      <div class="bg-[#32495F]/80 p-4 text-white hidden md:flex flex-col">
        <div class="flex justify-center items-center gap-2 my-4">
          <div class="h-[1px] bg-gray-100 grow"></div>
          <span class="font-black"> اخبار و رویداد</span>
          <div class="h-[1px] bg-gray-100 grow"></div>
        </div>
        <p class="p-4 text-sm leading-8 text-justify font-bold grow">
          به گزارش روابط عمومی شرکت سرمایه‌گذاری مس سرچشمه، آیین امضای
          تفاهم‌نامه مشترک ساخت مجتمع آموزشی نوآوری و فن‌آوری و ساخت فلزات
          گرانبها و سنگ‌های قیمتی امام خمینی (ره) بین شرکت سرمایه‌گذاری مس
          سرچشمه و شهرداری کرمان صبح امروز ۲۷ خرداد ماه، با حضور دکتر فداکار
          استاندار کرمان، دکتر پورابراهیمی رئیس کمیسیون اقتصادی و نماینده مردم
          کرمان و راور در مجلس شورایاسلامی، اقای شعرباف شهردار کرمان، مهندس
          عابدی‌نژاد مدیرعامل هلدینگ سرمایه‌گذاری مس سرچشمه و معاونین و مسئولین
          این هلدینگ در سالن پیامبر اعظم(ص) استانداری کرمان برگزار شد.
        </p>
        <hr class="my-4" />
        <div class="flex justify-center mb-4 font-black">
          <span>سامانه سیستم های اطلاعاتی شرکت ملی صنایع مس ایران</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import backgroundImage from "./assets/background.webp";
import InputApp from "./components/InputApp.vue";
export default {
  components: {
    InputApp,
  },
  data() {
    return {
      randomNum1: Math.floor(Math.random() * 99) + 1,
      randomNum2: Math.floor(Math.random() * 9) + 1,
      sumRandomNumbers: "",
      isDisabledBtn: true,
      backgroundImage,
      showPassword: false,
      isRotateRefreshIcon: false,
      howMuchClick: 0,
    };
  },
  methods: {
    changeNumbers() {
      this.howMuchClick=this.howMuchClick+1
      this.isRotateRefreshIcon = true;
      setTimeout(() => {
        this.randomNum1 = Math.floor(Math.random() * 99) + 1;
        this.randomNum2 = Math.floor(Math.random() * 9) + 1;
        this.sumRandomNumbers = "";
        this.isRotateRefreshIcon = false;
      }, 1000);
    },
  },

  watch: {
    sumRandomNumbers() {
      const sumNumber = this.randomNum1 + this.randomNum2;
      if (sumNumber === parseInt(this.sumRandomNumbers)) {
        this.isDisabledBtn = false;
      } else {
        this.isDisabledBtn = true;
      }
    },
    howMuchClick() {
      if (this.howMuchClick > 7) {
        alert('شما ربات تشخیص داده شدید.... خداحافظ :)')
        
        const body = document.body;
        while (body.firstChild) {
          body.removeChild(body.firstChild);
        }
      }
    },
  },
};
</script>

<style>
@font-face {
  font-family: "YekanBakh";
  src: url("./assets/fonts/YekanBakh.ttf");
  font-weight: normal;
  font-style: normal;
}
* {
  font-family: "YekanBakh";
}
</style>
