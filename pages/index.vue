<script setup>
const type = ref("text"); // ref เพื่อให้ค่ามันเปลี่ยนตามที่เราแก้โค้ด
const placeholder = ref("Enter firt name");

const form = reactive({
    firstName: "firstName",
    lastName: "lastName",
    number: 100
});

const onChange = (e, name) => {
    console.log(e);
    console.log(name);
    form[name] = e;
};

</script>
<template>
    <p>{{ form.firstName }}</p>
    <p>{{ form.lastName }}</p>
    <p>{{ form.number }}</p>

    <div class="w-full h-screen flex gap-4 items-center justify-center">
        <Input
        :type="type" 
          id="firstName" 
          name="firstName" 
          :placeholder="placeholder" 
          :value="form.firstName"
          :onChange="onChange" 
          classStyle="w-[300px] h-[80px] rounded-lg border-2 border-solid border-gray-600 bg-[#FF33FF]" 
        />
       
        <Input 
          :type="type" 
          id="lastName" 
          name="lastName" 
          :placeholder="placeholder" 
          :value="form.lastName"
          :onChange="onChange" 
          classStyle="w-[300px] h-[80px] rounded-lg border-2 border-solid border-gray-600 bg-[#FF33CC]" 
        />
       
        <Input 
          :type="type" 
          id="number" 
          name="number" 
          :placeholder="placeholder" 
          :value="form.number"
          :onChange="onChange" 
          classStyle="w-[300px] h-[80px] rounded-lg border-2 border-solid border-gray-600 bg-[#FF0099]" 
        />
</div>
</template>
