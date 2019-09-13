<template>
  <q-page class="flex flex-center">
    <!-- <h5>Title</h5> -->
    <div >
      <!-- <div class="search-wrapper">
        <input type="text" v-model="searchText" placeholder="Search title.."/>
            <label>Search title:</label>
      </div> -->
      <!-- <button @click="clearMessage">Clear</button> -->

    </div>
      
  <div class="q-pa-md">
    <q-table
      title="天主教及基督新教中文用語對照"
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
        <q-input borderless dense debounce="300" v-model="filter" placeholder="Search">
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
      visibleColumns: ['en', 'en-abbr', 'prot', 'prot-abbr', 'cath', 'cath-abbr'],
      columns: [
        {
          name: 'en',
          required: true,
          label: 'Egnlish',
          align: 'left',
          field: row => row.en,
          format: val => `${val}`,
          sortable: true
        },
        // { name: 'en', align: 'center', label: 'English', field: 'en', sortable: true },
        { name: 'en-abbr', label: 'en-abbr', field: 'en-abbr', sortable: true },
        { name: 'prot', label: 'prot', field: 'prot' },
        { name: 'prot-abbr', label: 'prot-abbr', field: 'prot-abbr' },
        { name: 'cath', label: 'cath', field: 'cath' },
        { name: 'cath-abbr', label: 'cath-abbr', field: 'cath-abbr', sortable: true },
      ],
      /*
      data: [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          prot: 24,
          protein: 4.0,
          sodium: 87,
          calcium: '14%',
          iron: '1%'
        },
        {
          name: 'Ice cream sandwich',
          calories: 237,
          fat: 9.0,
          prot: 37,
          protein: 4.3,
          sodium: 129,
          calcium: '8%',
          iron: '1%'
        },
        {
          name: 'Eclair',
          calories: 262,
          fat: 16.0,
          prot: 23,
          protein: 6.0,
          sodium: 337,
          calcium: '6%',
          iron: '7%'
        },
        {
          name: 'Cupcake',
          calories: 305,
          fat: 3.7,
          prot: 67,
          protein: 4.3,
          sodium: 413,
          calcium: '3%',
          iron: '8%'
        },
        {
          name: 'Gingerbread',
          calories: 356,
          fat: 16.0,
          prot: 49,
          protein: 3.9,
          sodium: 327,
          calcium: '7%',
          iron: '16%'
        },
        {
          name: 'Jelly bean',
          calories: 375,
          fat: 0.0,
          prot: 94,
          protein: 0.0,
          sodium: 50,
          calcium: '0%',
          iron: '0%'
        },
        {
          name: 'Lollipop',
          calories: 392,
          fat: 0.2,
          prot: 98,
          protein: 0,
          sodium: 38,
          calcium: '0%',
          iron: '2%'
        },
        {
          name: 'Honeycomb',
          calories: 408,
          fat: 3.2,
          prot: 87,
          protein: 6.5,
          sodium: 562,
          calcium: '0%',
          iron: '45%'
        },
        {
          name: 'Donut',
          calories: 452,
          fat: 25.0,
          prot: 51,
          protein: 4.9,
          sodium: 326,
          calcium: '2%',
          iron: '22%'
        },
        {
          name: 'KitKat',
          calories: 518,
          fat: 26.0,
          prot: 65,
          protein: 7,
          sodium: 54,
          calcium: '12%',
          iron: '6%'
        }
      ]
    */
      data:[
 {
   "en": "Genesis",
   "en-abbr": "Gn",
   "prot": "創世紀",
   "prot-abbr": "創",
   "cath": "創世紀",
   "cath-abbr": "創"
 },
 {
   "en": "Exodus",
   "en-abbr": "Ex",
   "prot": "出埃及記",
   "prot-abbr": "出",
   "cath": "出谷紀",
   "cath-abbr": "出"
 },
 {
   "en": "Leviticus",
   "en-abbr": "Lv",
   "prot": "利未記",
   "prot-abbr": "利",
   "cath": "肋未紀",
   "cath-abbr": "肋"
 },
 {
   "en": "Numbers",
   "en-abbr": "Nb",
   "prot": "民數記",
   "prot-abbr": "民",
   "cath": "戶籍紀",
   "cath-abbr": "戶"
 },
 {
   "en": "Deuteronomy",
   "en-abbr": "Dt",
   "prot": "申命記",
   "prot-abbr": "申",
   "cath": "申命紀",
   "cath-abbr": "申"
 },
 {
   "en": "Joshua",
   "en-abbr": "Jos",
   "prot": "約書亞記",
   "prot-abbr": "書",
   "cath": "若蘇厄書",
   "cath-abbr": "蘇"
 },
 {
   "en": "Judges",
   "en-abbr": "Jg",
   "prot": "士師記",
   "prot-abbr": "士",
   "cath": "民長紀",
   "cath-abbr": "民"
 },
 {
   "en": "Ruth",
   "en-abbr": "Rt",
   "prot": "路得記",
   "prot-abbr": "得",
   "cath": "盧德傳",
   "cath-abbr": "盧"
 },
 {
   "en": "1 Samuel",
   "en-abbr": "1S",
   "prot": "撒母爾記上",
   "prot-abbr": "撒上",
   "cath": "撒慕爾紀上",
   "cath-abbr": "撒上"
 },
 {
   "en": "2 Samuel",
   "en-abbr": "2S",
   "prot": "撒母爾記下",
   "prot-abbr": "撒下",
   "cath": "撒慕爾紀下",
   "cath-abbr": "撒下"
 },
 {
   "en": "1 Kings",
   "en-abbr": "1K",
   "prot": "列王記上",
   "prot-abbr": "王上",
   "cath": "列王紀上",
   "cath-abbr": "列上"
 },
 {
   "en": "2 Kings",
   "en-abbr": "2K",
   "prot": "列王記下",
   "prot-abbr": "王下",
   "cath": "列王紀下",
   "cath-abbr": "列下"
 },
 {
   "en": "1 Chronicles",
   "en-abbr": "1Ch",
   "prot": "歷代誌上",
   "prot-abbr": "代上",
   "cath": "編年紀上",
   "cath-abbr": "編上"
 },
 {
   "en": "2 Chronicles",
   "en-abbr": "2Ch",
   "prot": "歷代誌下",
   "prot-abbr": "代下",
   "cath": "編年紀下",
   "cath-abbr": "編下"
 },
 {
   "en": "1 Esdras",
   "en-abbr": "Ezr",
   "prot": "以斯拉書",
   "prot-abbr": "拉",
   "cath": "厄斯德拉上",
   "cath-abbr": "厄上"
 },
 {
   "en": "2 Esdras",
   "en-abbr": "Ne",
   "prot": "尼希米記",
   "prot-abbr": "尼",
   "cath": "厄斯德拉下",
   "cath-abbr": "厄下"
 },
 {
   "en": "Tobit",
   "en-abbr": "Tb",
   "prot": "",
   "prot-abbr": "",
   "cath": "多俾亞傳",
   "cath-abbr": "多"
 },
 {
   "en": "Judith",
   "en-abbr": "Jdt",
   "prot": "",
   "prot-abbr": "",
   "cath": "友弟德傳",
   "cath-abbr": "友"
 },
 {
   "en": "Esther",
   "en-abbr": "Est",
   "prot": "以斯帖記",
   "prot-abbr": "斯",
   "cath": "艾斯德爾傳",
   "cath-abbr": "艾"
 },
 {
   "en": "1 Maccabees",
   "en-abbr": "1Mc",
   "prot": "",
   "prot-abbr": "",
   "cath": "馬加伯上",
   "cath-abbr": "加上"
 },
 {
   "en": "2 Maccabees",
   "en-abbr": "2Mc",
   "prot": "",
   "prot-abbr": "",
   "cath": "馬加伯下",
   "cath-abbr": "加下"
 },
 {
   "en": "Job",
   "en-abbr": "Jb",
   "prot": "約伯記",
   "prot-abbr": "伯",
   "cath": "約伯傳",
   "cath-abbr": "約"
 },
 {
   "en": "Psalms",
   "en-abbr": "Ps",
   "prot": "詩篇",
   "prot-abbr": "詩",
   "cath": "聖詠集",
   "cath-abbr": "詠"
 },
 {
   "en": "Proverbs",
   "en-abbr": "Pr",
   "prot": "箴言",
   "prot-abbr": "箴",
   "cath": "箴言",
   "cath-abbr": "箴"
 },
 {
   "en": "Ecclesiastes",
   "en-abbr": "Qo",
   "prot": "傳道書",
   "prot-abbr": "傳",
   "cath": "訓道篇",
   "cath-abbr": "訓"
 },
 {
   "en": "Song of Solomon",
   "en-abbr": "Sg",
   "prot": "雅歌",
   "prot-abbr": "歌",
   "cath": "雅歌",
   "cath-abbr": "歌"
 },
 {
   "en": "Wisdom of Solomon",
   "en-abbr": "Ws",
   "prot": "",
   "prot-abbr": "",
   "cath": "智慧篇",
   "cath-abbr": "智"
 },
 {
   "en": "Wisdom of Jesus Son of Sirach",
   "en-abbr": "Si",
   "prot": "",
   "prot-abbr": "",
   "cath": "德訓篇",
   "cath-abbr": "德"
 },
 {
   "en": "Isaiah",
   "en-abbr": "Is",
   "prot": "以賽亞書",
   "prot-abbr": "賽",
   "cath": "依撒依亞",
   "cath-abbr": "依"
 },
 {
   "en": "Jeremiah",
   "en-abbr": "Jr",
   "prot": "耶利米書",
   "prot-abbr": "耶",
   "cath": "耶肋米亞",
   "cath-abbr": "耶"
 },
 {
   "en": "Lamentations",
   "en-abbr": "Lm",
   "prot": "耶利米哀歌",
   "prot-abbr": "哀",
   "cath": "耶肋米亞哀歌",
   "cath-abbr": "哀"
 },
 {
   "en": "Baruch",
   "en-abbr": "Ba",
   "prot": "",
   "prot-abbr": "",
   "cath": "巴路克",
   "cath-abbr": "巴"
 },
 {
   "en": "Ezekiel",
   "en-abbr": "Ezk",
   "prot": "以西結書",
   "prot-abbr": "結",
   "cath": "厄則克耳",
   "cath-abbr": "則"
 },
 {
   "en": "Daniel",
   "en-abbr": "Dn",
   "prot": "但以理書",
   "prot-abbr": "但",
   "cath": "達尼爾",
   "cath-abbr": "達"
 },
 {
   "en": "Hosea",
   "en-abbr": "Ho",
   "prot": "何西阿書",
   "prot-abbr": "何",
   "cath": "歐瑟亞",
   "cath-abbr": "歐"
 },
 {
   "en": "Joel",
   "en-abbr": "Jl",
   "prot": "約珥書",
   "prot-abbr": "珥",
   "cath": "岳厄爾",
   "cath-abbr": "岳"
 },
 {
   "en": "Amos",
   "en-abbr": "Am",
   "prot": "阿摩斯書",
   "prot-abbr": "摩",
   "cath": "亞毛斯",
   "cath-abbr": "亞"
 },
 {
   "en": "Obadiah",
   "en-abbr": "Ob",
   "prot": "俄巴底亞書",
   "prot-abbr": "俄",
   "cath": "亞北底亞",
   "cath-abbr": "北"
 },
 {
   "en": "Jonah",
   "en-abbr": "Jon",
   "prot": "約拿書",
   "prot-abbr": "拿",
   "cath": "約納",
   "cath-abbr": "納"
 },
 {
   "en": "Micah",
   "en-abbr": "Mi",
   "prot": "彌迦書",
   "prot-abbr": "彌",
   "cath": "米該亞",
   "cath-abbr": "米"
 },
 {
   "en": "Nahum",
   "en-abbr": "Na",
   "prot": "那鴻",
   "prot-abbr": "鴻",
   "cath": "納鴻",
   "cath-abbr": "鴻"
 },
 {
   "en": "Habakkuk",
   "en-abbr": "Hab",
   "prot": "哈巴谷書",
   "prot-abbr": "哈",
   "cath": "哈巴谷",
   "cath-abbr": "哈"
 },
 {
   "en": "Zephaniah",
   "en-abbr": "Zp",
   "prot": "西番亞書",
   "prot-abbr": "番",
   "cath": "索福尼亞",
   "cath-abbr": "索"
 },
 {
   "en": "Haggai",
   "en-abbr": "Hg",
   "prot": "哈該書",
   "prot-abbr": "該",
   "cath": "哈蓋",
   "cath-abbr": "蓋"
 },
 {
   "en": "Zechariah",
   "en-abbr": "Zc",
   "prot": "撒加利亞書",
   "prot-abbr": "亞",
   "cath": "匝加利亞",
   "cath-abbr": "匝"
 },
 {
   "en": "Malachi",
   "en-abbr": "Ml",
   "prot": "瑪拉基書",
   "prot-abbr": "瑪",
   "cath": "馬拉基亞",
   "cath-abbr": "拉"
 },
 {
   "en": "Matthew",
   "en-abbr": "Mt",
   "prot": "馬太福音",
   "prot-abbr": "太",
   "cath": "瑪竇福音",
   "cath-abbr": "瑪"
 },
 {
   "en": "Mark",
   "en-abbr": "Mk",
   "prot": "馬可福音",
   "prot-abbr": "可",
   "cath": "馬爾谷福音",
   "cath-abbr": "谷"
 },
 {
   "en": "Luke",
   "en-abbr": "Lk",
   "prot": "路加福音",
   "prot-abbr": "路",
   "cath": "路加福音",
   "cath-abbr": "路"
 },
 {
   "en": "John",
   "en-abbr": "Jn",
   "prot": "約翰福音",
   "prot-abbr": "約",
   "cath": "若望福音",
   "cath-abbr": "若"
 },
 {
   "en": "Acts",
   "en-abbr": "Ac",
   "prot": "使徒行傳",
   "prot-abbr": "徒",
   "cath": "宗徒大事錄",
   "cath-abbr": "宗"
 },
 {
   "en": "Romans",
   "en-abbr": "Rm",
   "prot": "羅馬人書",
   "prot-abbr": "羅",
   "cath": "羅馬書",
   "cath-abbr": "羅"
 },
 {
   "en": "1 Corinthians",
   "en-abbr": "1Co",
   "prot": "哥林多前書",
   "prot-abbr": "林前",
   "cath": "格林多前書",
   "cath-abbr": "格前"
 },
 {
   "en": "2 Corinthians",
   "en-abbr": "2Co",
   "prot": "哥林多後書",
   "prot-abbr": "林後",
   "cath": "格林多後書",
   "cath-abbr": "格後"
 },
 {
   "en": "Galatians",
   "en-abbr": "Ga",
   "prot": "加拉太書",
   "prot-abbr": "加",
   "cath": "迦拉達書",
   "cath-abbr": "迦"
 },
 {
   "en": "Ephesians",
   "en-abbr": "Ep",
   "prot": "以弗所書",
   "prot-abbr": "弗",
   "cath": "厄弗所書",
   "cath-abbr": "弗"
 },
 {
   "en": "Philippians",
   "en-abbr": "Ph",
   "prot": "腓力比書",
   "prot-abbr": "腓",
   "cath": "斐理伯書",
   "cath-abbr": "斐"
 },
 {
   "en": "Colossians",
   "en-abbr": "Col",
   "prot": "哥羅西書",
   "prot-abbr": "西",
   "cath": "哥羅森書",
   "cath-abbr": "哥"
 },
 {
   "en": "1 Thessalonians",
   "en-abbr": "1Th",
   "prot": "帖撒羅尼迦前書",
   "prot-abbr": "帖前",
   "cath": "得撒洛尼前書",
   "cath-abbr": "得前"
 },
 {
   "en": "2 Thessalonians",
   "en-abbr": "2Th",
   "prot": "帖撒羅尼迦後書",
   "prot-abbr": "帖後",
   "cath": "得撒洛尼後書",
   "cath-abbr": "得後"
 },
 {
   "en": "1 Timothy",
   "en-abbr": "1Tm",
   "prot": "提摩太前書",
   "prot-abbr": "提前",
   "cath": "弟茂德前書",
   "cath-abbr": "弟前"
 },
 {
   "en": "2 Timothy",
   "en-abbr": "2Tm",
   "prot": "提摩太後書",
   "prot-abbr": "提後",
   "cath": "弟茂德後書",
   "cath-abbr": "弟後"
 },
 {
   "en": "Titus",
   "en-abbr": "Tt",
   "prot": "提多書",
   "prot-abbr": "多",
   "cath": "弟鐸書",
   "cath-abbr": "鐸"
 },
 {
   "en": "Philemon",
   "en-abbr": "Phm",
   "prot": "斐利門書",
   "prot-abbr": "門",
   "cath": "費肋孟書",
   "cath-abbr": "費"
 },
 {
   "en": "Hebrews",
   "en-abbr": "Heb",
   "prot": "希伯來書",
   "prot-abbr": "來",
   "cath": "希伯來書",
   "cath-abbr": "希"
 },
 {
   "en": "James",
   "en-abbr": "Jm",
   "prot": "雅各書",
   "prot-abbr": "雅",
   "cath": "雅各伯書",
   "cath-abbr": "雅"
 },
 {
   "en": "1 Peter",
   "en-abbr": "1P",
   "prot": "彼得前書",
   "prot-abbr": "彼前",
   "cath": "伯多祿前書",
   "cath-abbr": "伯前"
 },
 {
   "en": "2 Peter",
   "en-abbr": "2P",
   "prot": "彼得後書",
   "prot-abbr": "彼後",
   "cath": "伯多祿後書",
   "cath-abbr": "伯後"
 },
 {
   "en": "1 John",
   "en-abbr": "1Jn",
   "prot": "約翰一書",
   "prot-abbr": "約壹",
   "cath": "若望一書",
   "cath-abbr": "若一"
 },
 {
   "en": "2 John",
   "en-abbr": "2Jn",
   "prot": "約翰二書",
   "prot-abbr": "約貳",
   "cath": "若望二書",
   "cath-abbr": "若二"
 },
 {
   "en": "3 John",
   "en-abbr": "3Jn",
   "prot": "約翰三書",
   "prot-abbr": "約參",
   "cath": "若望三書",
   "cath-abbr": "若三"
 },
 {
   "en": "Jude",
   "en-abbr": "Ude",
   "prot": "猶大書",
   "prot-abbr": "猶",
   "cath": "猶達書",
   "cath-abbr": "猶"
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
