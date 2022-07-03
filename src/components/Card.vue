<script setup lang="ts">
type User = {
  name: string;
  profession: string;
  profileImgSrc: string;
};

interface Props {
  title: string;
  user: User;
}

defineProps<Props>();
</script>

<template>
  <div class="card">
    <div class="card__user-container">
      <img
        class="card__user-img"
        v-bind:src="user.profileImgSrc"
        v-bind:alt="`${user.name} profile image`"
      />
      <div class="card__user-info-wrapper">
        <div class="card__user-name">{{ user.name }}</div>
        <div class="card__user-profession">{{ user.profession }}</div>
      </div>
    </div>
    <h2 class="card__title" v-html="title" />
  </div>
</template>

<style>
.card {
  padding: 1.25rem;
  width: 100%;
  background: var(--background-color);
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}

.card__title {
  margin-top: 1.25rem;
  font-family: 'Lora', sans-serif;
  font-size: 1.125rem;
  font-weight: 700;
}

.card__user-container {
  display: flex;
  align-items: center;
}

.card__user-img {
  height: 40px;
  width: 40px;
  border: none;
  border-radius: 100%;
}

.card__user-info-wrapper {
  margin-left: 0.875rem;
}

.card__user-name {
  font-size: 1.5rem;
  font-weight: 500;
}

.card__user-profession {
  margin-top: 0.375rem;
  font-size: 0.75rem;
  font-weight: 500;
  color: var(--secondary-text);
}

@media screen and (min-width: 768px) {
  .card {
    padding: 1.5rem;
  }

  .card__title {
    margin-top: 1.25rem;
  }

  .card__user-img {
    height: 50px;
    width: 50px;
  }

  .card__user-info-wrapper {
    margin-left: 1.25rem;
  }

  .card__user-profession {
    margin-top: 0.5rem;
  }
}
</style>

<script lang="ts">
export default {
  name: 'Card'
};
</script>
