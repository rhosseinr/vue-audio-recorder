<template>
  <button
    type="button"
    class="icon-button"
    :class="`icon-${name}`"
    @click="() => onClick()"
  >
    <span v-html="icons[name]" />
  </button>
</template>

<script>
export default {
  name: "IconButton",

  props: {
    name: { type: String },
  },
  data() {
    return {
      icons: {
        download:
          '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M3.5 13h9a.5.5 0 0 1 .09.992L12.5 14h-9a.5.5 0 0 1-.09-.992L3.5 13h9h-9ZM7.91 1.008L8 1a.5.5 0 0 1 .492.41l.008.09v8.792l2.682-2.681a.5.5 0 0 1 .638-.058l.07.058a.5.5 0 0 1 .057.638l-.058.069l-3.535 3.536a.5.5 0 0 1-.638.057l-.07-.057l-3.535-3.536a.5.5 0 0 1 .638-.765l.069.058L7.5 10.292V1.5a.5.5 0 0 1 .41-.492L8 1l-.09.008Z"/></svg>',
        upload:
          '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M3.5 2a.5.5 0 0 0 0 1h9a.5.5 0 0 0 0-1h-9Zm4.854 2.146a.5.5 0 0 0-.708 0l-3.5 3.5a.5.5 0 1 0 .708.708L7.5 5.707V13.5a.5.5 0 0 0 1 0V5.707l2.646 2.647a.5.5 0 0 0 .708-.708l-3.5-3.5Z"/></svg>',
        mic: '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M5.5 4.5a2.5 2.5 0 0 1 5 0V8a2.5 2.5 0 0 1-5 0V4.5ZM8 3a1.5 1.5 0 0 0-1.5 1.5V8a1.5 1.5 0 1 0 3 0V4.5A1.5 1.5 0 0 0 8 3ZM4 7.5a.5.5 0 0 1 .5.5a3.5 3.5 0 1 0 7 0a.5.5 0 0 1 1 0a4.5 4.5 0 0 1-4 4.473V13.5a.5.5 0 0 1-1 0v-1.027A4.5 4.5 0 0 1 3.5 8a.5.5 0 0 1 .5-.5Z"/></svg>',
        pause:
          '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M3.75 2A1.75 1.75 0 0 0 2 3.75v8.5c0 .966.784 1.75 1.75 1.75h1.5A1.75 1.75 0 0 0 7 12.25v-8.5A1.75 1.75 0 0 0 5.25 2h-1.5ZM3 3.75A.75.75 0 0 1 3.75 3h1.5a.75.75 0 0 1 .75.75v8.5a.75.75 0 0 1-.75.75h-1.5a.75.75 0 0 1-.75-.75v-8.5ZM10.75 2A1.75 1.75 0 0 0 9 3.75v8.5c0 .966.784 1.75 1.75 1.75h1.5A1.75 1.75 0 0 0 14 12.25v-8.5A1.75 1.75 0 0 0 12.25 2h-1.5ZM10 3.75a.75.75 0 0 1 .75-.75h1.5a.75.75 0 0 1 .75.75v8.5a.75.75 0 0 1-.75.75h-1.5a.75.75 0 0 1-.75-.75v-8.5Z"/></svg>',
        play: '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M5.745 3.064A.5.5 0 0 0 5 3.5v9a.5.5 0 0 0 .745.436l8-4.5a.5.5 0 0 0 0-.871l-8-4.5ZM4 3.5a1.5 1.5 0 0 1 2.235-1.307l8 4.5a1.5 1.5 0 0 1 0 2.615l-8 4.5A1.5 1.5 0 0 1 4 12.5v-9Z"/></svg>',
        save: '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M4 3a1 1 0 0 0-1 1v8a1 1 0 0 0 1 1V9.5A1.5 1.5 0 0 1 5.5 8h5A1.5 1.5 0 0 1 12 9.5V13a1 1 0 0 0 1-1V5.621a1 1 0 0 0-.293-.707l-1.621-1.621A1 1 0 0 0 10.379 3H10v1.5A1.5 1.5 0 0 1 8.5 6h-2A1.5 1.5 0 0 1 5 4.5V3H4Zm2 0v1.5a.5.5 0 0 0 .5.5h2a.5.5 0 0 0 .5-.5V3H6Zm5 10V9.5a.5.5 0 0 0-.5-.5h-5a.5.5 0 0 0-.5.5V13h6ZM2 4a2 2 0 0 1 2-2h6.379a2 2 0 0 1 1.414.586l1.621 1.621A2 2 0 0 1 14 5.621V12a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V4Z"/></svg>',
        stop: '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M12.5 3a.5.5 0 0 1 .5.5v9a.5.5 0 0 1-.5.5h-9a.5.5 0 0 1-.5-.5v-9a.5.5 0 0 1 .5-.5h9Zm-9-1A1.5 1.5 0 0 0 2 3.5v9A1.5 1.5 0 0 0 3.5 14h9a1.5 1.5 0 0 0 1.5-1.5v-9A1.5 1.5 0 0 0 12.5 2h-9Z"/></svg>',
        volume:
          '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path d="M8.694 2.04A.5.5 0 0 1 9 2.5v11a.5.5 0 0 1-.85.357l-2.927-2.875H3.5a1.5 1.5 0 0 1-1.5-1.5v-2.99a1.5 1.5 0 0 1 1.5-1.5h1.724l2.927-2.85a.5.5 0 0 1 .543-.103zm3.043 1.02l.087.058l.098.085c.063.056.15.138.252.245c.206.213.476.527.746.938a6.542 6.542 0 0 1 1.083 3.618a6.522 6.522 0 0 1-1.083 3.614c-.27.41-.541.724-.746.936l-.142.141l-.187.17l-.033.026a.5.5 0 0 1-.688-.72l.13-.117a5.49 5.49 0 0 0 .83-.985c.46-.7.919-1.73.919-3.065a5.542 5.542 0 0 0-.919-3.069a5.588 5.588 0 0 0-.54-.698l-.17-.176l-.184-.17a.5.5 0 0 1 .547-.832zM8 3.684L5.776 5.851a.5.5 0 0 1-.349.142H3.5a.5.5 0 0 0-.5.5v2.989a.5.5 0 0 0 .5.5h1.927a.5.5 0 0 1 .35.143L8 12.308V3.685zm2.738 1.374l.1.07l.133.126l.054.056c.114.123.26.302.405.54c.292.48.574 1.193.574 2.148c0 .954-.282 1.668-.573 2.148a3.388 3.388 0 0 1-.405.541l-.102.105l-.07.065l-.04.033l-.063.03c-.133.052-.442.139-.64-.108a.5.5 0 0 1 .012-.638l.134-.129l.034-.036c.075-.08.179-.208.284-.382c.21-.345.429-.882.429-1.63c0-.747-.219-1.283-.428-1.627a2.467 2.467 0 0 0-.223-.311l-.095-.105l-.069-.065a.5.5 0 0 1 .55-.83z" fill="currentColor" fill-rule="nonzero"/></svg>',
        volumeMute:
          '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M8.694 2.04A.5.5 0 0 1 9 2.5v11a.5.5 0 0 1-.85.357l-2.927-2.875H3.5a1.5 1.5 0 0 1-1.5-1.5v-2.99a1.5 1.5 0 0 1 1.5-1.5h1.724l2.927-2.85a.5.5 0 0 1 .543-.103ZM8 3.684L5.777 5.851a.5.5 0 0 1-.35.142H3.5a.5.5 0 0 0-.5.5v2.989a.5.5 0 0 0 .5.5h1.928a.5.5 0 0 1 .35.143L8 12.308V3.685Zm2.147 2.461a.5.5 0 0 1 .707 0l1.147 1.147l1.146-1.147a.5.5 0 1 1 .707.708L12.708 8l1.146 1.146a.5.5 0 1 1-.707.708L12 8.707l-1.147 1.147a.5.5 0 0 1-.707-.708L11.293 8l-1.146-1.146a.5.5 0 0 1 0-.708Z"/></svg>',
        record:
          '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M8 12a4 4 0 1 0 0-8a4 4 0 0 0 0 8ZM8 1a7 7 0 1 0 0 14A7 7 0 0 0 8 1ZM2 8a6 6 0 1 1 12 0A6 6 0 0 1 2 8Z"/></svg>',
        remove:
          '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M7 3h2a1 1 0 0 0-2 0ZM6 3a2 2 0 1 1 4 0h4a.5.5 0 0 1 0 1h-.564l-1.205 8.838A2.5 2.5 0 0 1 9.754 15H6.246a2.5 2.5 0 0 1-2.477-2.162L2.564 4H2a.5.5 0 0 1 0-1h4Zm1 3.5a.5.5 0 0 0-1 0v5a.5.5 0 0 0 1 0v-5ZM9.5 6a.5.5 0 0 1 .5.5v5a.5.5 0 0 1-1 0v-5a.5.5 0 0 1 .5-.5Zm-4.74 6.703A1.5 1.5 0 0 0 6.246 14h3.508a1.5 1.5 0 0 0 1.487-1.297L12.427 4H3.573l1.187 8.703Z"/></svg>',
        backward:
          '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M8.354 12.146a.5.5 0 0 1-.708.708l-4.5-4.5a.5.5 0 0 1 0-.708l4.5-4.5a.5.5 0 1 1 .708.708L4.207 8l4.147 4.146Zm4 0a.5.5 0 0 1-.708.708l-4.5-4.5a.5.5 0 0 1 0-.708l4.5-4.5a.5.5 0 0 1 .708.708L8.207 8l4.147 4.146Z"/></svg>',
        forward:
          '<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16"><path fill="currentColor" d="M7.646 3.854a.5.5 0 1 1 .708-.708l4.5 4.5a.5.5 0 0 1 0 .708l-4.5 4.5a.5.5 0 0 1-.708-.708L11.793 8L7.646 3.854Zm-4 0a.5.5 0 1 1 .708-.708l4.5 4.5a.5.5 0 0 1 0 .708l-4.5 4.5a.5.5 0 0 1-.708-.708L7.793 8L3.646 3.854Z"/></svg>',
      },
    };
  },

  methods: {
    onClick() {
      this.$emit("onClickIcon");
    },
  },
};
</script>

<style lang="scss">
.icon-button {
  border: none;
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: transparent;

  svg {
    height: 1.5em;
    width: 1.5em;
    color: var(--primary-color, #0f6cbd);
  }
}

.icon-remove svg,
.icon-record svg {
  color: var(--danger-color, #d13438);
}

.icon-stop svg {
  color: #333;
}
</style>
