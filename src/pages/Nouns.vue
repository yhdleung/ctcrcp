<template>
  <q-page class="padding bg-brown-2">
  <div class="q-pa-md">
    <q-table
      title="聖經專用名詞譯名"
      dense
      :data="data"
      :columns="columns"
      row-key="name"
      :pagination.sync="pagination"
      :visible-columns="visibleColumns"
      :filter="filter"
      hide-bottom
    >
      <template v-slot:top-right>
        <q-input dense debounce="300" v-model="filter" placeholder="搜索">
          <template v-slot:append>
            <q-icon name="search" />
          </template>
        </q-input>
      </template>

    </q-table>
  </div>

  </q-page>
</template>

<script>
import nouns from 'assets/nouns.json';

export default {
  // name: 'PageIndex',
  data() {
    return{
      searchText: '',


      pagination: {
        sortBy: 'name',
        descending: false,
        // page: 2,
        rowsPerPage: 1000
      },
      filter: '',
      // visibleColumns: ['en', 'en-abbr', 'prot', 'prot-abbr', 'cath', 'cath-abbr'],
      visibleColumns: ['en', 'prot',  'cath' ],
      columns: [
        {
          name: 'en',
          required: true,
          label: '英語譯名',
          align: 'left',
          field: row => row.en,
          format: val => `${val}`,
          sortable: true
        },
        // { name: 'en', align: 'center', label: 'English', field: 'en', sortable: true },
        // { name: 'en-abbr', label: 'en-abbr', field: 'en-abbr', sortable: true },
        { name: 'prot', label: '基督新教漢語譯名', field: 'prot' },
        // { name: 'prot-abbr', label: 'prot-abbr', field: 'prot-abbr' },
        { name: 'cath', label: '天主教漢語譯名', field: 'cath' },
        // { name: 'cath-abbr', label: 'cath-abbr', field: 'cath-abbr', sortable: true },
      ],
      data: nouns 
    }
  },
  computed: {
    filteredList() {
      return this.postList.filter(post => {
        return post.title.toLowerCase().includes(this.searchText.toLowerCase());
      });
    }
  },
  methods: {
    clearMessage(){
      this.searchText = ''
    },
  }
} 

</script>
