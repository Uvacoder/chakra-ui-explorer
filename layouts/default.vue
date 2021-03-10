<!-- layouts/default.vue -->
<template>
  <div class="container">
    <c-theme-provider>
      <c-color-mode-provider #default="{ colorMode }">
        <c-box
          v-bind="mainStyles[colorMode]"
          w="100vw"
          h="100vh"
          as="section"
        >
          <c-reset />
          <nav-bar />
          <Nuxt />
        </c-box>
      </c-color-mode-provider>
    </c-theme-provider>
  </div>
</template>

<script>
import { CThemeProvider, CColorModeProvider, CReset, CBox } from '@chakra-ui/vue'
import NavBar from '@/components/NavBar'

export default {
  name: 'DefaultLayout',
  components: {
    CThemeProvider,
    CColorModeProvider,
    CReset,
    CBox,
    NavBar
  },
  data () {
    return {
      mainStyles: {
        dark: {
          bg: 'gray.900',
          color: 'whiteAlpha.900'
        },
        light: {
          bg: 'whiteAlpha.900',
          color: 'gray.900'
        }
      }
    }
  }
}
</script>

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
