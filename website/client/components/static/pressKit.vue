<template lang="pug">
  .container-fluid
    h1 {{ $t('presskit') }}
      p {{ $t('presskitText', { pressEnquiryEmail : PRESS_ENQUIRY_EMAIL }) }}
      p
        a.btn.btn-lg.btn-success(href='~assets/images/presskit/presskit.zip') presskit.zip

    div(v-for='(images, category) in imgs')
      h2 {{ $t('pk' + category) }}
      div(v-if='Array.isArray(images)')
        div(v-for='img in images')
          img.img-rendering-auto.press-img(:src="`assets/images/presskit/${category}/${img}.png`")
      div(v-else)
        div(v-for='(images, category) in images')
          h3 {{ $t('pk' + category) }}
          div(v-for='img in images')
            img.img-rendering-auto.press-img(:src="~`assets/images/presskit/${category}/${img}.png`")
</template>

<script>
  // @TODO: How to use images?
  // @TODO: EMAILS.PRESS_ENQUIRY_EMAIL
  const PRESS_ENQUIRY_EMAIL = 'admin@habitica.com';

  export default {
    data () {
      return {
        PRESS_ENQUIRY_EMAIL,
        imgs: {
          Promo: [
            'Promo',
            'Promo - Thin',
          ],
          Logo: [
            'Icon with Text',
            'Habitica Gryphon',
            'iOS',
            'Android',
          ],
          Boss: [
            'Basi-List',
            'Stagnant Dishes',
            'SnackLess Monster',
            'Laundromancer',
            'Necro-Vice',
            'Battling the Ghost Stag',
            'Dread Drag\'on of Dilatory',
          ],
          Samples: {
            Website: [
              'Tasks Page',
              'Equipment',
              'Market',
              'Guilds',
              'Challenges',
            ],
            iOS: [
              'Tasks Page',
              'Level Up',
              'Pets',
              'Party',
              'Boss',
            ],
            Android: [
              'User',
              'Tasks Page',
              'Reward',
              'Level Up',
              'Tavern',
              'Party',
            ],
          },
        },
      };
    },
  };
</script>
