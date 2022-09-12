<template>
  <section class="p-8 m-auto max-w-screen-xl font-sans">
    <div class="grid grid-cols-1 md:grid-cols-4 place-content-evenly gap-8">
      <div
        :key="item.title"
        v-for="item in items"
        class="shadow-lg w-full box bg-white border-solid border border-teal-800 border-2"
      >
        <a :href="item.href" target="_blank">
          <img 
            v-if="item.img" 
            :class="{'setPixel': item.type === 'certification'}"
            :src="`/img/${item.img}.webp`"
            :alt="item.title"
            :title="item.title"
            :width="item.type === 'certification' ? '150' : '509'"
            :height="item.type === 'certification' ? '150': '363'"
          />
          <img 
            v-if="!item.img && item.type=='web_app'" 
            src="/img/web-app.webp"
            :alt="item.title"
            :title="item.title"
            width="509"
            height="363"
          />
          <h4 class="px-1">{{ item.title }}</h4>
          <h4 v-if="item.type" class="capitalize px-1">Project Type: {{ convert(item.type) }}</h4>
          <h4 v-if="item.id" class="capitalize px-1"> Verification Id: {{ item.id }}</h4>
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
        { type: 'certification', title: 'AWS Cloud Practitioner', id: 'SK3P1BQKYJB4Q2SS', href: 'https://aws.amazon.com/verification', img:'aws-certified-cloud-practitioner'},
        { type: 'web_app', title: 'Bond Search Tool', href: 'https://www.interactivebrokers.com/en/index.php?f=45559#/'},
        { type: 'web_app', title: 'Global Analyst Seach Tool', href: 'https://www.interactivebrokers.com/en/index.php?f=49843#/'},
        { type: 'web_app', title: 'Mutual Fund Search Tool', href: 'https://www.interactivebrokers.com/en/index.php?f=46321#/'},
        { type: 'web_app', title: 'EUIBSI Bid/Ask Tool', href: 'https://www.interactivebrokers.ie/en/index.php?f=53691'},
        { type: 'web_app', title: 'Stock Margin Calculator', href: 'https://www.interactivebrokers.com/en/trading/margin-calculator.php'},
        { type: 'web_app', title: 'Stock Price Widget', href: 'https://www.interactivebrokers.com/stockpricequote/', img: 'stockpricequote'},
        { type: 'website', title: 'Nagi Jewelers', href: 'https://nagijewelers.com/', img: 'nagi_jewelers'},
        { type: 'website', title: 'Vanity Studio LLC', href: 'https://www.vanitystudiollc.com/', img: 'vanitystudiollc'},
        { type: 'website', title: 'Pipsqueaks', href: 'https://shoppipsqueaks.com/', img: 'shoppips'},
        { type: 'website', title: 'House of Sussie', href: 'https://houseofsussie.com/', img: 'houseofsussie'},
        { type: 'website', title: 'Hubbell Water Rentals', href: 'https://rentawaterheater.com/', img: 'rentawaterheater'},
        { type: 'website', title: 'Beaut Outerwear', href: 'https://beautouterwear.com/', img: 'beautouterwear'},
        { type: 'website', title: 'McMedCPR', href: 'https://www.mcmedcpr.com/', img: 'mcmedcpr'},
        { type: 'website', title: 'Booster Heater', href: 'https://boosterheater.com/', img:'boosterheater'},
        { type: 'website', title: 'Ace Heaters', href: 'https://aceheaters.com/', img: 'aceheaters'}
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