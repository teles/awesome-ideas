<template>
  <div class="outline-grid--no-sidebar">
    <header class="outline-grid__header">
      <h1 class="outline-grid__header__content">
        Ideias para Aplicativos 🆓
      </h1>
    </header>
    <div class="outline-grid__content">
      <amp-list
          width="auto"
          height="100"
          layout="fixed-height"
          src="https://api.jsonbin.io/b/5f787901302a837e95739b16"
          items="."
      >
        <amp-mustache>
          <template v-pre>
            <div class="idea-card">
              <h2 class="idea-card__title">{{title}}</h2>
              <p class="idea-card__subtitle">{{subtitle}}</p>
            </div>
          </template>
        </amp-mustache>
      </amp-list>
    </div>
  </div>
</template>

<style lang="sass">
@import '../sass/0 -helpers/breakpoints'
@import '../sass/2 - layout/outline-grid'

$card_background__red: #ff0200
$card_background__yellow: #fec600
$card_background__pink: #ff8c8b
$card_background__blue: #05afff
$card_background__green: #67dc00
$card_background__purple: #7803ff

amp-list [role='list']
  margin: 0 0 spacing(1) 0
  display: grid
  padding: 0 spacing(1)
  grid-gap: spacing(3)
  grid-template-columns: repeat(2, minmax(calc(50% - 20px), 1fr))

  @media(min-width: $screen-tablet-min)
    padding: 0
    grid-gap: spacing(2)
    grid-template-columns: repeat(4, minmax(calc(25% - 20px), 1fr))

.idea-card
  font-family: sans-serif
  height: 260px
  display: flex
  flex-direction: column
  padding: spacing(2)
  color: #1a181b
  background: #fff

  &:nth-child(6n)
    background-color: $card_background__red

  &:nth-child(6n+1)
    background-color: $card_background__yellow

  &:nth-child(6n+2)
    background-color: $card_background__pink

  &:nth-child(6n+3)
    background-color: $card_background__blue

  &:nth-child(6n+4)
    background-color: $card_background__green

  &:nth-child(6n+5)
    background-color: $card_background__purple

  +element('title')
    line-height: 1.6

  +element('subtitle')
    line-height: 1.6

</style>

<script>
export default {
    amp: 'only',
    ampLayout: 'default.amp'
}
</script>
