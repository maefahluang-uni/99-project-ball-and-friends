<template>
  <v-card flat>
    <template v-slot:title>
      <div class="mx-right text-h3" style="font-size: 30px; padding: 16px;">ลูกหนี้งวดที่ 1</div>
    </template>
    <template v-slot:text class="text-right">
      <v-responsive class="mx-right" max-width="344">
        <v-text-field v-model="search" label="ค้นหา" append-inner-icon="mdi-magnify" single-line variant="outlined"
          hide-details></v-text-field></v-responsive>
    </template>

    <v-data-table :headers="headers" :items="desserts" :search="search"
      :header-props="{ style: 'background-color: #59A1C9; color: black;' }">   
      <template v-slot:item="{ item, index }">
        <tr :style="{ backgroundColor: index % 2 === 0 ? '#D9D9D9' : 'white' }">
          <td v-for="(value, key) in item" :key="key">
            <!-- Render a NuxtLink component for the "edit" column -->
            <template v-if="key === 'edit'">
              <NuxtLink :to="'/list/debtor' + item.no"> <!-- Adjust the route as per your setup -->
                <v-icon>mdi-pencil</v-icon> <!-- Edit icon -->
              </NuxtLink>
            </template>
            <template v-else>
              {{ value }}
            </template>
          </td>
        </tr>
      </template>
    </v-data-table>
  </v-card>
</template>
<script>
export default {
  data() {
    return {
      search: '',
      headers: [
        {
          align: 'start',
          key: 'no',
          sortable: true,
          title: 'ลำดับ',
        },
        { key: 'contract', title: 'เลขที่สัญญา' },
        { key: 'name', title: 'ชื่อ-นามสกุล' },
        { key: 'amout', title: 'ยอดเงิน' },
        { key: 'date', title: 'วันที่โทร' },
        { key: 'result', title: 'ผลการตอบกลับ', sortable: false, },
        { key: 'edit', title: 'บันทึก', sortable: false, },
      ],
      desserts: [
        {
          no: 1,
          contract: 12345678,
          name: 'นาย พงศ์กร ริมทาง',
          amout: '8,456',
          date: '09/11/2024',
          result: '',
          edit: '',
        },
        {
          no: 2,
          contract: 22345678,
          name: 'นาย ชิดชนก วงษ์คชศักดิ์',
          amout: '32,158',
          date: '23/02/2024',
          result: '',
          edit: '',
        },
        {
          no: 3,
          contract: 32345678,
          name: 'นางสาว เบญจมาศ น้อยวิเศษ',
          amout: '458,650',
          date: '03/04/2024',
          result: '',
          edit: '',
        },
        {
          no: 4,
          contract: 42345678,
          name: 'นาย ธรรมนิตย์ โต๊ะริม',
          amout: '654,822',
          date: '19/11/2024',
          result: '',
          edit: '',
        },
      ],
    }
  },
}
</script>