<template>
  <div>
    <h1>Welcome to my Nuxt3 app</h1>

    <div v-if="$auth.loggedIn">
      <NuxtLink to="/api/logout" external> Sign out </NuxtLink>
    </div>

    <div v-else>
      <LoginLink to="/api/login" external> Sign in </LoginLink>
      <RegisterLink to="/api/register" external> Sign up </RegisterLink>
    </div>
  </div>
</template>

<script setup lang="ts">
const auth = useState("auth");
const loggedIn = auth.value.loggedIn;

useSeoMeta({
  title: loggedIn ? "Logged in" : "Not logged in",
});
</script>
