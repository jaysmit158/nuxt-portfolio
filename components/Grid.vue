<template>
  <section class="p-8 m-auto max-w-screen-xl font-sans">
    <h3 class="text-xl mb-6">This is not a complete list of all projects I have worked on but is a mix of web apps, e-commerce websites, and static sites.</h3>
    <div class="grid grid-cols-1 md:grid-cols-4 place-content-evenly gap-8">
      <div
        :key="item.id"
        v-for="item in items"
        class="shadow-lg w-full box bg-white border-solid border border-teal-800 border-2"
      >
        <a :href="item.href" target="_blank">
          <img 
            v-if="item.img"
            :fetchpriority="item.id < 2 ? 'high' : 'low'"
            :class="{'setPixel': item.type === 'certification'}"
            :src="`/img/${item.img}.webp`"
            :alt="item.title"
            :title="item.title"
            :width="item.type === 'certification' ? '150' : '509'"
            :height="item.type === 'certification' ? '150': '363'"
          />
          <img 
            v-if="!item.img && item.type=='web_app'"
            :fetchpriority="item.id < 2 ? 'high' : 'low'"
            src="/img/web-app.webp"
            :alt="item.title"
            :title="item.title"
            width="509"
            height="363"
          />
          <h4 class="px-1">{{ item.title }}</h4>
          <h4 v-if="item.type" class="capitalize px-1">Project Type: {{ convert(item.type) }}</h4>
          <h4 v-if="item.identity" class="capitalize px-1"> Verification Id: {{ item.identity }}</h4>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Grid',
  data() {
    return {
      items: [
        { id: 0, type: 'certification', title: 'AWS Cloud Practitioner', identity: 'SK3P1BQKYJB4Q2SS', href: 'https://aws.amazon.com/verification', img:'aws-certified-cloud-practitioner'},
        { id: 1, type: 'web_app', title: 'Bond Search Tool', href: 'https://www.interactivebrokers.com/en/index.php?f=45559#/'},
        { id: 2, type: 'web_app', title: 'Global Analyst Seach Tool', href: 'https://www.interactivebrokers.com/en/index.php?f=49843#/'},
        { id: 3, type: 'web_app', title: 'Mutual Fund Search Tool', href: 'https://www.interactivebrokers.com/en/index.php?f=46321#/'},
        { id: 4, type: 'web_app', title: 'EUIBSI Bid/Ask Tool', href: 'https://www.interactivebrokers.ie/en/index.php?f=53691'},
        { id: 5, type: 'web_app', title: 'Stock Margin Calculator', href: 'https://www.interactivebrokers.com/en/trading/margin-calculator.php'},
        { id: 6, type: 'web_app', title: 'Stock Price Widget', href: 'https://www.interactivebrokers.com/stockpricequote/', img: 'stockpricequote'},
        { id: 7, type: 'website', title: 'Nagi Jewelers', href: 'https://nagijewelers.com/', img: 'nagi_jewelers'},
        { id: 8, type: 'website', title: 'Vanity Studio LLC', href: 'https://www.vanitystudiollc.com/', img: 'vanitystudiollc'},
        { id: 9, type: 'website', title: 'Pipsqueaks', href: 'https://shoppipsqueaks.com/', img: 'shoppips'},
        { id: 10, type: 'website', title: 'House of Sussie', href: 'https://houseofsussie.com/', img: 'houseofsussie'},
        { id: 11, type: 'website', title: 'Hubbell Water Rentals', href: 'https://rentawaterheater.com/', img: 'rentawaterheater'},
        { id: 12, type: 'website', title: 'Beaut Outerwear', href: 'https://beautouterwear.com/', img: 'beautouterwear'},
        { id: 13, type: 'website', title: 'McMedCPR', href: 'https://www.mcmedcpr.com/', img: 'mcmedcpr'},
        { id: 14, type: 'website', title: 'Booster Heater', href: 'https://boosterheater.com/', img:'boosterheater'},
        { id: 15, type: 'website', title: 'Ace Heaters', href: 'https://aceheaters.com/', img: 'aceheaters'}
      ]
    }
  },
  methods: {
    convert(value) {
      const converted = value === 'web_app' ? 'web app' : value;
      return converted;
    }
  }
}
</script>
<style>
  .box {
    transition: transform .2s; /* Animation */
    min-height:auto;
    background: rgb(128 128 128 / 12%);
  }
  .box:hover {
    transform: scale(1.1); 
  }
  .setPixel {
    margin: auto;
  }
</style>