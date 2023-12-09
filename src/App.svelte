<script>
  import Login from "./pages/Login.svelte";
  import Main from "./pages/Main.svelte";
  import NotFound from "./pages/NotFound.svelte";
  import Signup from "./pages/Signup.svelte";
  import Write from "./pages/Write.svelte";
  import Router from "svelte-spa-router";
  import "./css/style.css";
  import { user$ } from "./store";

  let login = false;

  const routes = {
    "/": Main,
    "/signup": Signup,
    "/write": Write,
    "*": NotFound,
  };
</script>

{#if !$user$}
  <Login />
{:else}
  <Router {routes} />
{/if}
