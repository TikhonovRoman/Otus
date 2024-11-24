<template>
  <div class="card">
    <div class="card__top">
      <a href="#" class="card__image">
        <img :src="props.product.image" :alt="props.product.title" />
      </a>
    </div>
    <div class="card__bottom">
      <Rating :rating="product.rating"></Rating>
      <div class="card__price">{{ props.product.price }}</div>
      <div class="card__title">
        <a href="#">{{ props.product.title }}</a>
      </div>
      <div class="card__discription">
        {{ props.product.description }}
      </div>
      <IButton :text="'В корзину'" />
    </div>
  </div>
</template>

<script setup>
import Rating from '../ui/IRating.vue';
import IButton from '../ui/IButton.vue';

const props = defineProps({
  product: {
    type: Object
  }
}
)
</script>

<style scoped>
.card {
  width: 225px;
  min-height: 350px;
  box-shadow: 1px 2px 4px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  border-radius: 4px;
  transition: 0.2s;
  position: relative;
}

.card:hover {
  box-shadow: 4px 8px 16px rgba(255, 51, 61, 0.2);
}

.card__top {
  flex: 0 0 220px;
  position: relative;
  overflow: hidden;
}

.card__image {
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.card__image>img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  transition: 0.2s;
}

.card__image:hover>img {
  transform: scale(1.1);
}

.card__bottom {
  display: flex;
  flex-direction: column;
  height: 100%;
  padding: 10px;
}

.card__price {
  display: flex;
  margin-bottom: 10px;
  font-weight: 400;
  font-size: 17px;
  color: #606060;
  display: flex;
  justify-content: center;
}

.card__price::after {
  content: "$";
  margin-left: 4px;
  position: relative;
}

.card__price::before {
  content: "Price:";
  font-weight: 400;
  font-size: 16px;
  margin-right: 4px;
  color: #bfbfbf;
}

.card__title {
  margin-bottom: 10px;
  font-weight: 600;
  font-size: 1em;
  line-height: 1;
  color: #414141;
}

.card__title a {
  text-decoration: none;
  color: blue;
}

.card__discription {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  line-clamp: 3;
  -webkit-box-orient: vertical;
  width: 100%;
  overflow: hidden;
  text-overflow: ellipsis;
  margin-bottom: 10px;
  font-weight: 400;
  font-size: 1em;
  line-height: 1;
  color: #414141;
}
</style>