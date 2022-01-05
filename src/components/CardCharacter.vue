Skip to content
Search or jump to…
Pull requests
Issues
Marketplace
Explore
 
@camiloaceve 
carloscdev
/
udemy-vue3-rick-and-morty
Public
Code
Issues
Pull requests
Actions
Projects
Wiki
Security
Insights
udemy-vue3-rick-and-morty/src/components/CardCharacter.vue

Carlos Córdova rick and morty with vue 3
Latest commit e4057fa on 29 Jul 2021
 History
 0 contributors
88 lines (86 sloc)  1.74 KB
   
<template>
  <div class="character">
    <img :src="character.image" :alt="character.name">
    <div class="character__info">
      <h3>{{ character.name }}</h3>
      <div class="status">
        <span
          :class="
            character.status == 'Alive' ? 'alive' :
            character.status == 'Dead' ? 'dead' :
            'default'"
        ></span>
        <span>{{ character.status }} - {{ character.species }}</span>
      </div>
      <div class="origen">
        <span>
          Origin: 
          {{ character.origin.name }}
        </span>
      </div>
      <div class="location">
        <span>
          Location: 
          {{ character.location.name }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['character']
}
</script>

<style lang="scss">
.character {
  background-color: var(--background-card);
  border-radius: 20px;
  box-shadow: 0 0 10px 1px var(--background-body);
  overflow: hidden;
  cursor: pointer;
  transition: transform 200ms ease-in-out;
  height: 100%;
  &:hover {
    transform: scale(1.05);
    h3 {
      color: var(--text-orange);
    }
  }
  span {
    color: var(--text-gray);
  }
  h3 {
    margin-bottom: 0.5rem;
  }
  &__info {
    padding: 1.5rem;
    .status{
      display: flex;
      align-items: center;
      margin-bottom: 0.5rem;
      span {
        color: var(--text-gray);
        &:first-child {
          width: 10px;
          height: 10px;
          border-radius: 50%;
          margin-right: 0.5rem;
        }
      }
      .alive {
        background-color: green;
      }
      .dead {
        background-color: red;
      }
      .default {
        background-color: white;
      }
    }
    .origen {
      margin-bottom: 0.5rem;
    }
  }
}
</style>
