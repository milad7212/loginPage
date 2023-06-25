<template>
  <div
    class="h-screen bg-cover flex justify-center items-center bg-gradient-to-br from-orange-500 to-gray-900"
    :style="{ backgroundImage: `url(${backgroundImage})` }"
  >
    <div
      class="rounded-lg w-2/3 overflow-hidden shadow-xl grid grid-cols-[2fr_3fr]"
    >
      <div class="bg-white p-4 flex flex-col items-center">
        <img src="./assets/icon.png" class="w-[81px] h-[55px]" alt="" />
        <span class="text-[#FFA266] font-black my-4">ورود به سیستم</span>
        <div class="">
          <span class="block mb-4 my-2">نام کاربری</span>
          <div class="flex p-2 rounded-lg border border-gray-300">
            <img class="w-6 h-6" src="./assets/icons/userIcon.svg" />
            <input
              class="placeholder:text-xs placeholder:font-bold pr-4 outline-none"
              type="text"
              placeholder="نام کاربری را وارد کنید"
            />
          </div>

          <span class="block mb-4 my-2">رمز عبور</span>
          <div class="flex p-2 rounded-lg border border-gray-300">
            <img class="w-6 h-6" src="./assets/icons/lockIcon.svg" />
            <input
              class="placeholder:text-xs placeholder:font-bold pr-4 outline-none"
              type="password"
              placeholder="رمز عبور را وارد کنید"
            />
          </div>

          <p class="text-xs text-decoration-underline cursor-pointer my-4 mb-8 hover:font-black transition-all duration-150 ease-in">
            گذرواژه را فراموش کرده ام!
          </p>
          <div class="flex justify-between items-center mb-4">
            <input
              class="p-2 rounded-lg border w-32 border-gray-300 pr-4 outline-none text-left"
              type="text"
            />
            <div class="flex items-center ">
              <img
                class="w-6 h-6 ml-4 cursor-pointer hover:scale-95 active:scale-110"
                src="./assets/icons/refreshIcon.svg"
              />
              <div
                class="p-2 rounded-lg border border-gray-300 px-4 font-black"
              >
                <span>2</span><span>+</span><span>3</span>
              </div>
            </div>
          </div>
          <button
            class="bg-[#FFA266] text-white w-full my-4 py-2 rounded-md active:scale-95 transition-all duration-150 ease-in"
          >
            ورود
          </button>
        </div>
      </div>
      <div class="bg-[#32495F]/80 p-4 text-white hidden md:block">
        <div class="flex justify-center items-center gap-2 my-4">
          <div class="h-[1px] bg-gray-100 grow"></div>
          <span> اخبار و رویداد</span>
          <div class="h-[1px] bg-gray-100 grow"></div>
        </div>
        <p class="p-4 text-sm leading-8 text-justify font-bold">
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
        <div class="flex justify-center mb-4">
          <span>سامانه سیستم های اطلاعاتی شرکت ملی صنایع مس ایران</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import backgroundImage from "./assets/background.webp";
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
