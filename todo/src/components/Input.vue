<template>
<v-continer>
    <v-select v-model="subject" 
    :items="items" 
    label="--กรุณากรอกข้อมูล--" solo>
    </v-select>

    <v-text-field v-model="work" 
    :items="items" 
    label="----เพิ่มข้อมูล----" solo>
    </v-text-field>

    <v-text-field v-model="Time" 
    :items="items" 
    label="----กำหนดส่ง----" solo>
    </v-text-field>

    <v-btn 
    color="primary" 
    class="mr-4"  
    @click="addTodo">
    เพิ่ม
    </v-btn>

</v-continer>
    
</template>
<script>
export default {
  data() {
    return{
      subject:null,
      work:"",
      Time:"",
      items: ['วิชาภาษาอังกฤษ',  
      'วิชาสถิติ','วิชาคณิตศาสตร์เพื่อคอมพิวเตอร์',  
      'วิชาสถาปัตยกรรมคอมพิวเตอร์', 
      'วิชาสุขภาพ', 
      'วิชาหลักการวิเคราะห์โปรแกรม','วิชาการพัฒนาโปรแกรมประยุกต์บนเว็บ',],
 
    }
  },
  methods:{  
    addTodo() {
      this.$emit("Addata", this.subject, this.work, this.Time);
      (this.subject = ""), (this.work = ""), (this.Time = "");
    },
  },
};
</script>

<style></style>