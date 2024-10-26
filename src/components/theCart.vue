<template>
  <div class="bg-white px-6 py-4 max-w-[300px] rounded-[18px]">
    <div
      class="flex items-center justify-between pb-3 border-b border-solid border-[#F2F2F3]"
    >
      <h5 class="font-semibold text-2xl">Корзина</h5>
      <div class="bg-[#F2F2F3] px-4 py-[2px] rounded-md">4</div>
    </div>
    <div class="flex justify-between items-center">
      <div>
        <div class="flex py-3 border-b border-solid border-[#F2F2F3]">
          <img
            src="../assets/cartBurger.png"
            class="max-w-16 h-[52px] mr-1.5"
            alt=""
          />
          <div class="text-xs">
            <h6>Супер сырный</h6>
            <p class="text-[#B1B1B1] mb-1.5 mt-[1px]">512г</p>
            <p>550₽</p>
          </div>
        </div>
      </div>

      <div class="flex items-center bg-[#F2F2F3] px-3 py-[9px] rounded-xl h-10">
        <button>-</button>
        <div class="mx-4">1</div>
        <button>+</button>
      </div>
    </div>
    <div class="flex items-center justify-between my-4">
        <p>Итого</p>
        <div>1279₽</div>
    </div>
    <button class="text-white bg-[#FF7020] rounded-xl text-center py-3 px-[69px] text-nowrap transition hover:bg-[#FFAB08]">Оформить заказ</button>
    <div class="flex items-center mt-3">
        <img src="" alt="">
        <p class="text-xs ml-2">Бесплатная доставка</p>
    </div>
  </div>
</template>
