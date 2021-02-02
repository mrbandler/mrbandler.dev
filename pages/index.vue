<template>
    <div class="container">
        <CBox
            v-bind="mainStyles[colorMode]"
            d="flex"
            w="100vw"
            h="100vh"
            flex-dir="column"
            justify-content="center"
        >
            <CHeading text-align="center" mb="4">
                🏗 Under construction 🚧
            </CHeading>
            <CFlex justify="center" direction="column" align="center">
                <CBox mb="3">
                    <CIconButton
                        mr="3"
                        :icon="colorMode === 'light' ? 'moon' : 'sun'"
                        :aria-label="`Switch to ${
                            colorMode === 'light' ? 'dark' : 'light'
                        } mode`"
                        @click="toggleColorMode"
                    />
                </CBox>
            </CFlex>
        </CBox>
    </div>
</template>

<script lang="js">
import {
  CBox,
  CIconButton,
  CFlex,
  CHeading
} from '@chakra-ui/vue'

export default {
  name: 'App',
  components: {
    CBox,
    CIconButton,
    CFlex,
    CHeading
  },
  inject: ['$chakraColorMode', '$toggleColorMode'],
  data () {
    return {
      showModal: false,
      mainStyles: {
        dark: {
          bg: 'gray.700',
          color: 'whiteAlpha.900'
        },
        light: {
          bg: 'white',
          color: 'gray.900'
        }
      }
    }
  },
  computed: {
    colorMode () {
      return this.$chakraColorMode()
    },
    theme () {
      return this.$chakraTheme()
    },
    toggleColorMode () {
      return this.$toggleColorMode
    }
  }
}
</script>
