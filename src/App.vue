<script setup lang="ts">
const configData = config;
</script>

<template>
  <div class="github-io-container">
    <div class="github-io-header">
      <div class="github-io-title">👏🥵 你好</div>
    </div>

    <div class="github-io-cards">
      <div class="github-io-title">仓库</div>
      <div class="github-io-wrapper">
        <div class="github-io-card" v-for="(item, index) in configData" :key="index">
          <a :href="item.link">
            <h3>{{ item.name }}</h3>
            <p>{{ item.desc }}</p>
          </a>
        </div>
      </div>
    </div>

    <div class="github-io-links">
      <div class="github-io-link">
        <a href="https://space.bilibili.com/204271518">哔哩哔哩</a>
      </div>
      <div class="github-io-link">
        <a href="https://www.cnblogs.com/AurLemon">博客园</a>
      </div>
    </div>

    <div class="github-io-footer">
      <div class="github-io-avatar">
        <img src="./assets/images/avatar.jpg" alt="">
      </div>
      <div class="github-io-image github-io-logo">
        <a href="https://github.com/AurLemon">
          <img src="./assets/images/icons/GitHub_logo.svg" alt="">
        </a>
      </div>
      <div class="github-io-sitename">
        AurLemon GitHub
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .github-io-container {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    width: 60%;
    min-width: 650px;
    padding: 2rem;
    margin: 0 auto;

    @media screen and (max-width: 768px) { 
      width: unset;
      min-width: unset;
    }
  }

  .github-io-header {
    display: flex;
    align-items: center;
    gap: 0.75rem;

    .github-io-title {
      font-size: 32px;
    }
  }

  .github-io-cards {
    padding: 1rem;
    border-radius: 16px;
    background: var(--color-surface-0);
    min-height: 750px;

    .github-io-title {
      font-weight: 600;
      margin-bottom: 0.5rem;
    }

    .github-io-wrapper {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-gap: 0.5rem;

      @media screen and (max-width: 768px) { 
        grid-template-columns: repeat(1, 1fr);
      }
    }

    .github-io-card {
      color: var(--color-base);
      padding: 12px;
      border: 1px solid var(--background-dark-0);
      border-radius: 12px;
      transition: background 250ms ease;

      h3, p {
        margin: 0;
      }

      h3 {
        margin-bottom: 0.25rem;
      }

      &:hover {
        background: var(--background-color-primary--active);
      }
    }
  }

  .github-io-links {
    display: flex;
    justify-content: center;
    gap: 0.75rem;

    .github-io-link {
      background: var(--color-text--weaken);
      border-radius: 16px;
      padding: 3px 12px;
      transition: background 250ms ease;

      a {
        color: var(--color-surface-0);
        font-size: 12px;
        transition: color 250ms ease;
      }

      &:hover {
        background: var(--background-dark-0);

        a {
          color: var(--color-base);
        }
      }
    }
  }

  .github-io-footer {
    $avatar-value-length: 26px;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 0.5rem;
    margin-top: 1rem;

    .github-io-image {
      opacity: 0.8;
      transition: opacity 250ms ease;

      &:hover {
        opacity: 1;
      }
    }

    .github-io-logo {
      img {
        width: $avatar-value-length;
        height: $avatar-value-length;
        user-select: none;
      }
    }

    .github-io-avatar {
      img {
        width: $avatar-value-length;
        height: $avatar-value-length;
        border-radius: 50%;
        user-select: none;
      }
    }

    .github-io-sitename {
      font-size: 20px;
      font-weight: 600;
    }
  }
</style>
