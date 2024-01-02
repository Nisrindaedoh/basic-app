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
        class="first-name-input" />
       
        <Input 
        :type="type" 
        id="lastName" 
        name="lastName" 
        :placeholder="placeholder" 
        :value="form.lastName"
        :onChange="onChange" 
        class="last-name-input" />
       
        <Input 
        :type="type" 
        id="number" 
        name="number" 
        :placeholder="placeholder" 
        :value="form.number"
        :onChange="onChange" 
        class="number-input" />
</div>
</template>

<style scoped>
  .first-name-input {
    padding: 5px;
    margin-bottom: 10px;
    background-color: #d297c0;
   
  }

  .last-name-input {
    padding: 8px;
    margin-bottom: 12px;
    background-color: #c32ab9;
  }

  .number-input {
    padding: 6px;
    margin-bottom: 8px;
    background-color: #9e2d80;
  }
</style>