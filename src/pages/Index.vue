<template>
  <q-page class="padding">
    <div >
      <!-- <div class="search-wrapper">
        <input type="text" v-model="searchText" placeholder="Search title.."/>
            <label>Search title:</label>
      </div> -->
      <!-- <button @click="clearMessage">Clear</button> -->

    </div>
      
  <div class="q-pa-md">
    <q-table
      title="聖經書卷譯名"
      dense
      :data="data"
      :columns="columns"
      row-key="name"
      :pagination.sync="pagination"
      :visible-columns="visibleColumns"
      :filter="filter"
      hide-bottom
    >

      <!-- <template v-slot:top="props">
        <q-space />

        <q-select
          v-model="visibleColumns"
          multiple
          borderless
          dense
          options-dense
          :display-value="$q.lang.table.columns"
          emit-value
          map-options
          :options="columns"
          option-value="name"
          style="min-width: 150px"
        />
      </template> -->
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

<style>
</style>

<script>


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
        { name: 'prot', label: '新教漢語譯名', field: 'prot' },
        // { name: 'prot-abbr', label: 'prot-abbr', field: 'prot-abbr' },
        { name: 'cath', label: '天主教漢語譯名', field: 'cath' },
        // { name: 'cath-abbr', label: 'cath-abbr', field: 'cath-abbr', sortable: true },
      ],
      data: [
 {
   "en": "Genesis (Gn)",
   "prot": "創世紀 (創)",
   "cath": "創世紀 (創)"
 },
 {
   "en": "Exodus (Ex)",
   "prot": "出埃及記 (出)",
   "cath": "出谷紀 (出)"
 },
 {
   "en": "Leviticus (Lv)",
   "prot": "利未記 (利)",
   "cath": "肋未紀 (肋)"
 },
 {
   "en": "Numbers (Nb)",
   "prot": "民數記 (民)",
   "cath": "戶籍紀 (戶)"
 },
 {
   "en": "Deuteronomy (Dt)",
   "prot": "申命記 (申)",
   "cath": "申命紀 (申)"
 },
 {
   "en": "Joshua (Jos)",
   "prot": "約書亞記 (書)",
   "cath": "若蘇厄書 (蘇)"
 },
 {
   "en": "Judges (Jg)",
   "prot": "士師記 (士)",
   "cath": "民長紀 (民)"
 },
 {
   "en": "Ruth (Rt)",
   "prot": "路得記 (得)",
   "cath": "盧德傳 (盧)"
 },
 {
   "en": "1 Samuel (1S)",
   "prot": "撒母爾記上 (撒上)",
   "cath": "撒慕爾紀上 (撒上)"
 },
 {
   "en": "2 Samuel (2S)",
   "prot": "撒母爾記下 (撒下)",
   "cath": "撒慕爾紀下 (撒下)"
 },
 {
   "en": "1 Kings (1K)",
   "prot": "列王記上 (王上)",
   "cath": "列王紀上 (列上)"
 },
 {
   "en": "2 Kings (2K)",
   "prot": "列王記下 (王下)",
   "cath": "列王紀下 (列下)"
 },
 {
   "en": "1 Chronicles (1Ch)",
   "prot": "歷代誌上 (代上)",
   "cath": "編年紀上 (編上)"
 },
 {
   "en": "2 Chronicles (2Ch)",
   "prot": "歷代誌下 (代下)",
   "cath": "編年紀下 (編下)"
 },
 {
   "en": "1 Esdras (Ezr)",
   "prot": "以斯拉書 (拉)",
   "cath": "厄斯德拉上 (厄上)"
 },
 {
   "en": "2 Esdras (Ne)",
   "prot": "尼希米記 (尼)",
   "cath": "厄斯德拉下 (厄下)"
 },
 {
   "en": "Tobit (Tb)",
   "prot": "多比傳",
   "cath": "多俾亞傳 (多)"
 },
 {
   "en": "Judith (Jdt)",
   "prot": "猶滴傳",
   "cath": "友弟德傳 (友)"
 },
 {
   "en": "Esther (Est)",
   "prot": "以斯帖記 (斯)",
   "cath": "艾斯德爾傳 (艾)"
 },
 {
   "en": "1 Maccabees (1Mc)",
   "prot": "瑪加伯書上",
   "cath": "馬加伯上 (加上)"
 },
 {
   "en": "2 Maccabees (2Mc)",
   "prot": "瑪加伯書下",
   "cath": "馬加伯下 (加下)"
 },
 {
   "en": "Job (Jb)",
   "prot": "約伯記 (伯)",
   "cath": "約伯傳 (約)"
 },
 {
   "en": "Psalms (Ps)",
   "prot": "詩篇 (詩)",
   "cath": "聖詠集 (詠)"
 },
 {
   "en": "Proverbs (Pr)",
   "prot": "箴言 (箴)",
   "cath": "箴言 (箴)"
 },
 {
   "en": "Ecclesiastes (Qo)",
   "prot": "傳道書 (傳)",
   "cath": "訓道篇 (訓)"
 },
 {
   "en": "Song of Solomon (Sg)",
   "prot": "雅歌 (歌)",
   "cath": "雅歌 (歌)"
 },
 {
   "en": "Wisdom of Solomon (Ws)",
   "prot": "所羅門智訓",
   "cath": "智慧篇 (智)"
 },
 {
   "en": "Wisdom of Sirach (Si)",
   "prot": "便西拉智訓",
   "cath": "德訓篇 (德)"
 },
 {
   "en": "Isaiah (Is)",
   "prot": "以賽亞書 (賽)",
   "cath": "依撒依亞 (依)"
 },
 {
   "en": "Jeremiah (Jr)",
   "prot": "耶利米書 (耶)",
   "cath": "耶肋米亞 (耶)"
 },
 {
   "en": "Lamentations (Lm)",
   "prot": "耶利米哀歌 (哀)",
   "cath": "耶肋米亞哀歌 (哀)"
 },
 {
   "en": "Baruch (Ba)",
   "prot": "巴錄書",
   "cath": "巴路克 (巴)"
 },
 {
   "en": "Ezekiel (Ezk)",
   "prot": "以西結書 (結)",
   "cath": "厄則克耳 (則)"
 },
 {
   "en": "Daniel (Dn)",
   "prot": "但以理書 (但)",
   "cath": "達尼爾 (達)"
 },
 {
   "en": "Hosea (Ho)",
   "prot": "何西阿書 (何)",
   "cath": "歐瑟亞 (歐)"
 },
 {
   "en": "Joel (Jl)",
   "prot": "約珥書 (珥)",
   "cath": "岳厄爾 (岳)"
 },
 {
   "en": "Amos (Am)",
   "prot": "阿摩斯書 (摩)",
   "cath": "亞毛斯 (亞)"
 },
 {
   "en": "Obadiah (Ob)",
   "prot": "俄巴底亞書 (俄)",
   "cath": "亞北底亞 (北)"
 },
 {
   "en": "Jonah (Jon)",
   "prot": "約拿書 (拿)",
   "cath": "約納 (納)"
 },
 {
   "en": "Micah (Mi)",
   "prot": "彌迦書 (彌)",
   "cath": "米該亞 (米)"
 },
 {
   "en": "Nahum (Na)",
   "prot": "那鴻 (鴻)",
   "cath": "納鴻 (鴻)"
 },
 {
   "en": "Habakkuk (Hab)",
   "prot": "哈巴谷書 (哈)",
   "cath": "哈巴谷 (哈)"
 },
 {
   "en": "Zephaniah (Zp)",
   "prot": "西番亞書 (番)",
   "cath": "索福尼亞 (索)"
 },
 {
   "en": "Haggai (Hg)",
   "prot": "哈該書 (該)",
   "cath": "哈蓋 (蓋)"
 },
 {
   "en": "Zechariah (Zc)",
   "prot": "撒加利亞書 (亞)",
   "cath": "匝加利亞 (匝)"
 },
 {
   "en": "Malachi (Ml)",
   "prot": "瑪拉基書 (瑪)",
   "cath": "馬拉基亞 (拉)"
 },
 {
   "en": "Matthew (Mt)",
   "prot": "馬太福音 (太)",
   "cath": "瑪竇福音 (瑪)"
 },
 {
   "en": "Mark (Mk)",
   "prot": "馬可福音 (可)",
   "cath": "馬爾谷福音 (谷)"
 },
 {
   "en": "Luke (Lk)",
   "prot": "路加福音 (路)",
   "cath": "路加福音 (路)"
 },
 {
   "en": "John (Jn)",
   "prot": "約翰福音 (約)",
   "cath": "若望福音 (若)"
 },
 {
   "en": "Acts (Ac)",
   "prot": "使徒行傳 (徒)",
   "cath": "宗徒大事錄 (宗)"
 },
 {
   "en": "Romans (Rm)",
   "prot": "羅馬人書 (羅)",
   "cath": "羅馬書 (羅)"
 },
 {
   "en": "1 Corinthians (1Co)",
   "prot": "哥林多前書 (林前)",
   "cath": "格林多前書 (格前)"
 },
 {
   "en": "2 Corinthians (2Co)",
   "prot": "哥林多後書 (林後)",
   "cath": "格林多後書 (格後)"
 },
 {
   "en": "Galatians (Ga)",
   "prot": "加拉太書 (加)",
   "cath": "迦拉達書 (迦)"
 },
 {
   "en": "Ephesians (Ep)",
   "prot": "以弗所書 (弗)",
   "cath": "厄弗所書 (弗)"
 },
 {
   "en": "Philippians (Ph)",
   "prot": "腓力比書 (腓)",
   "cath": "斐理伯書 (斐)"
 },
 {
   "en": "Colossians (Col)",
   "prot": "哥羅西書 (西)",
   "cath": "哥羅森書 (哥)"
 },
 {
   "en": "1 Thessalonians (1Th)",
   "prot": "帖撒羅尼迦前書 (帖前)",
   "cath": "得撒洛尼前書 (得前)"
 },
 {
   "en": "2 Thessalonians (2Th)",
   "prot": "帖撒羅尼迦後書 (帖後)",
   "cath": "得撒洛尼後書 (得後)"
 },
 {
   "en": "1 Timothy (1Tm)",
   "prot": "提摩太前書 (提前)",
   "cath": "弟茂德前書 (弟前)"
 },
 {
   "en": "2 Timothy (2Tm)",
   "prot": "提摩太後書 (提後)",
   "cath": "弟茂德後書 (弟後)"
 },
 {
   "en": "Titus (Tt)",
   "prot": "提多書 (多)",
   "cath": "弟鐸書 (鐸)"
 },
 {
   "en": "Philemon (Phm)",
   "prot": "斐利門書 (門)",
   "cath": "費肋孟書 (費)"
 },
 {
   "en": "Hebrews (Heb)",
   "prot": "希伯來書 (來)",
   "cath": "希伯來書 (希)"
 },
 {
   "en": "James (Jm)",
   "prot": "雅各書 (雅)",
   "cath": "雅各伯書 (雅)"
 },
 {
   "en": "1 Peter (1P)",
   "prot": "彼得前書 (彼前)",
   "cath": "伯多祿前書 (伯前)"
 },
 {
   "en": "2 Peter (2P)",
   "prot": "彼得後書 (彼後)",
   "cath": "伯多祿後書 (伯後)"
 },
 {
   "en": "1 John (1Jn)",
   "prot": "約翰一書 (約壹)",
   "cath": "若望一書 (若一)"
 },
 {
   "en": "2 John (2Jn)",
   "prot": "約翰二書 (約貳)",
   "cath": "若望二書 (若二)"
 },
 {
   "en": "3 John (3Jn)",
   "prot": "約翰三書 (約參)",
   "cath": "若望三書 (若三)"
 },
 {
   "en": "Jude (Ude)",
   "prot": "猶大書 (猶)",
   "cath": "猶達書 (猶)"
 },
 {
   "en": "Revelation (Rev)",
   "prot": "啟示錄 (啟)",
   "cath": "默示錄 (默)"
 }
]

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
