---
title: Go + Vuetify
date: 2020-06-27T09:01:10Z
draft: true
showDate: true
tags: [golang, learning]
---

I've been trying to learn Go for a while now, but in a very haphazard way. One of the most engaging and successful tutorials I found was [Davy Wybiral\'s series](https://www.youtube.com/playlist?list=PLmxT2pVYo5LDMV0epL4z4CUbxvIw6umg_) from a few years ago. I learned quite a bit from following those videos.

Building on the application I built following Davy's tutorial, I wanted to add Vuetify for some easy styling. I found this [short post](https://dev.to/sorincostea/vue-js-if-you-re-not-a-frontend-developer-2534) about using Vue.js without having to install a development environment, simply embedding the JavaScript into `index.html`, and I found I could do the same with Vuetify. There were a few things that tripped me up though, and I wanted to write them down to remember them for later.

## Include the required assets

Fonts and CSS are added to `<head>`.

{{< highlight html >}}
<head>
  <link href="https://fonts.googleapis.com/css?family=Roboto:100,300,400,500,700,900" rel="stylesheet">
  <link href="https://cdn.jsdelivr.net/npm/@mdi/font@5.x/css/materialdesignicons.min.css" rel="stylesheet">
  <link href="https://cdn.jsdelivr.net/npm/vuetify@2.x/dist/vuetify.min.css" rel="stylesheet">
  <title>{{ .Title }}</title>
  </head>
{{< /highlight >}}

The Vue.js and Vuetify scripts are added at the bottom of the page `body`.

{{< highlight html >}}
  <script src="https://cdn.jsdelivr.net/npm/vue@2.x/dist/vue.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/vuetify@2.x/dist/vuetify.js"></script>
{{< /highlight >}}

You'll also need to start a Vue.js instance:

{{< highlight html>}}
<script>
  new Vue({
    el: '#app',
    vuetify: new Vuetify()
  })
</script>
{{< /highlight >}}

## Add the app

Everything exists inside the `#app` div:

{{< highlight html >}}
<div id="app">
  <v-app>
  </v-app>
</div>
{{< /highlight >}}

## Include the material icons

This one threw me for a long time: although the Material icon *fonts* are included in the code above, the *icons* are not. Add the icons to the page's `head` with this:

{{< highlight html >}}
  <link href="https://fonts.googleapis.com/css?family=Material+Icons" rel="stylesheet">
{{< /highlight >}}

## Go and Vue template tags clash

Re-define the Vue.js template tags from `{{ item }}` to `${ item }` as follows. Just include this in the JavaScript that instantiates the app:

{{< highlight javascript >}}
    delimiters: ['${', '}']
{{< /highlight >}}
