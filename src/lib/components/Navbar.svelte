<script lang="ts">
  import { page } from "$app/stores";
  const isActive = (cr: any, r: string) => {
    console.log("called" + " " + r);
    return cr === r;
  }

  const isInactive = () => {
    $page.route.id != "/"
  }


</script>

<style>
  nav div a {
    text-decoration: none;
  }

  .button {
    background-color: white;
    height: 75px;
    width: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: background-color 0.5s, color 0.5s;
    transition-timing-function: ease;
  }

  #other_buttons {
    margin-left: auto;
  }

  .active {
    color: orange;
  }

  .button:hover {
    background-color: blue;
    color: yellow;
  }

  a.active:hover {
    background-color: purple;
    color: red;
  }

  #navbar {
    display: flex;
    background-color: black;
  }
</style>

<nav id="navbar">
  <div id="home_button">
    <a class="button" href="/" class:active={isActive($page.route.id, "/")}>a</a>
  </div>

  <div id="other_buttons">
    <a class="button" href="/todo" class:active={isActive($page.route.id, "/todo")}>b</a>
  </div>
</nav>