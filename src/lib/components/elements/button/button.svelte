<script lang="ts">
  interface ButtonInfo {
    type: "button" | "link";
    text: string;
    color?: "blue" | "red" | "green" | "yellow" | "purple" | "orange" | "white" | "primary" | "secondary" | "tertiary";
    href?: string;
    icon?: string;
  }

  export let buttonInfo: ButtonInfo;

  let icon: string;
  if (buttonInfo.icon) {
    icon = `<i style="margin-right: 10px;" class="${buttonInfo.icon}"></i>`;
  }
</script>

{#if buttonInfo.type === "button"}
  <button class="button {buttonInfo.color}">
    {@html icon ?? ""}
    {buttonInfo.text}
  </button>
{:else if buttonInfo.type === "link"}
  <a href={buttonInfo.href} class="button {buttonInfo.color}">
    {@html icon ?? ""}
    {buttonInfo.text}
  </a>
{/if}

<style lang="scss">
  @import "src/lib/scss/colors.scss";
  @import "src/lib/scss/variables.scss";

  .button {
    background-color: #3D486B;
    color: #fff;
    padding: 10px 20px;
    border-radius: $button-radius;
    text-decoration: none;
    border: none;
    transition: all 0.2s ease-in-out;
    cursor: pointer;
  }

  .blue {
    background-color: $blue;
  }

  .red {
    background-color: $red;
  }

  .green {
    background-color: $green;
  }

  .yellow {
    background-color: $yellow;
  }

  .purple {
    background-color: $purple;
  }

  .orange {
    background-color: $orange;
  }

  .white {
    background-color: $white;
    color: $white-900;
  }

  .primary {
    background-color: $primary;
  }

  .secondary {
    background-color: $secondary;
  }

  .tertiary {
    background-color: $tertiary;

    &:hover {
      background-color: #212736;
    }
  }
</style>