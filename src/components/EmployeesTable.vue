<template>
<div>
  <v-data-table
    :headers="headers"
    :items="people"
    :items-per-page="5"
    class="elevation-1"
    @click:row="selectRow"
    :multi-sort="true"
  ></v-data-table>

  <v-card>
    <v-card-title>
      <h1>hello</h1>
    </v-card-title>
  </v-card>
  </div>
</template>

<script>
export default {
  name: 'EmployeesTable',
  props: {
    people: {
      type: Array,
      required: true
    },
    hello: {
      type: String,
      required: true
    }
  },
  data: () => ({
    headers: [
      { text: 'الايدي مال موظف', value: 'id' },
      { text: 'الاسم', value: 'name' },
      { text: 'العنوان الوظيفي', value: 'title' },
      { text: 'الراتب', value: 'salary' },
      { text: 'شكد حلوين من 10', value: 'hate' },
    ]
  }),
  methods: {
    selectRow(event) {
      const employee = {
        name: event.name,
        title: event.title
      }

      this.$emit('select-employee', employee)
    }
  }
}
</script>

<style lang="scss" scoped></style>
