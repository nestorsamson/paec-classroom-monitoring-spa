<template>
  <div class="flex justify-center">
    <div class="bg-white w-full h-screen  md:mx-54  shadow-2xl flex flex-col ">

      <div class="flex items-center">
        <div class="text-xl font-bold text-neutral-900 p-5">Settings</div>
      </div>

      <div class="h-20 bg-stone-200 flex  items-center   px-2.5 mx-4">
        <div class="flex items-center mb-1 ">
          <label class=" w-64 flex text-md text-black ">School Year </label>
        </div>
        <div class="grow"> </div>

        <div class="flex  w-40">
          <select class="select select-info select-sm  w-full ">
            <option disabled selected>Select school year</option>
            <option>2022-2023</option>
            <option>2023-2024</option>

          </select>
        </div>
      </div>



      <div class="h-20 bg-stone-white flex  items-center px-2.5 mx-4 ">
        <div class="flex  mb-1">
          <label class="flex text-md  text-black w-64  justify-start">Semester</label>
        </div>
        <div class=" grow"></div>
        <div class="flex gap-4  w-40">
          <div class="flex  text-gray-700">
            <input type="radio" name="radio-2" class="radio radio-info radio-sm mr-1" value="1" checked />
            <label>1st semester</label>
          </div>

          <div class="flex text-gray-700">
            <input type="radio" name="radio-2" class="radio radio-info radio-sm mr-1" value="2" />
            <label>2nd semester</label>
          </div>


        </div>
      </div>


      <div class="h-20 bg-stone-200 flex  items-center   px-2.5 mx-4">
        <div class="flex items-center mb-1 ">
          <label class="  flex  text-md text-black w-64 ">Start of school year </label>
        </div>
        <div class="grow"></div>
        <div class="flex w-40   justify-start">
          <select class="select select-info select-sm w-full ">
            <option disabled selected>Select start of school year</option>
            <option>January</option>
            <option>February</option>

          </select>
        </div>
      </div>



    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style></style>