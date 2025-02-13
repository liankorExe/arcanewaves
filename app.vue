<template>
  <div>
    <NuxtRouteAnnouncer />
    <Header/>
    <NuxtPage />
    <UNotifications :timeout="5" color="primary" />
  </div>
</template>
