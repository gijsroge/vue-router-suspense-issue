<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view v-slot="{ Component }">
    <template v-if="Component">
        <keep-alive>
          <suspense>
            <component :is="Component"></component>
            <template #fallback>
              <div>
                Loading...
              </div>
            </template>
          </suspense>
        </keep-alive>
    </template>
  </router-view>
</template>