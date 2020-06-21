<template>
  <div class="page">
    <counter></counter>
    <v-data-table
      :headers="headers"
      :search="search"
      :items="balanceTreeData"
      :loading="loading"
      :items-per-page="Number(limitValue) || 0"
      dense
      class="border"
      hide-default-footer
    >
      <template
        v-slot:[`header.${h.value}`]="{ header }"
        v-for="h in headers">
        <v-tooltip
          :key="h.text"
          bottom>
          <template v-slot:activator="{ on }">
            <span v-on="on">{{ h.text }}</span>
          </template>
          <span>{{ h.tooltip }}</span>
        </v-tooltip>
      </template>
    </v-data-table>

  </div>
</template>

<script>
import Counter from 'components/Counter'

export default {
  components: {
    Counter
  }
}
</script>
