<script>
  import { enhance } from "$app/forms";
  import { supabaseClient } from "$lib/supabase";
  import { writable } from "svelte/store";

  export let data;

  // State to track if the auth-buttons are visible
  const isVisible = writable(false);

  const submitLogout = async ({ cancel }) => {
    const { error } = await supabaseClient.auth.signOut();
    if (error) {
      console.log(error);
    }
    cancel();
    isVisible.set(false); // Optionally hide after logout
    data.session = null; // Clear session data after logout
  };

  const toggleHidden = () => {
    isVisible.update((value) => !value);
  };
</script>

<div class="">
  {#if data.session}
    <p class="text-center">{data.session?.user.email}</p>

    <button
      class="flex btn btn-xs btn-primary mx-auto my-2"
      on:click={toggleHidden}
    >
      {#if $isVisible}
        Close
      {:else}
        Logout
      {/if}
    </button>

    <main
      class="auth-form auth-buttons {$isVisible
        ? ''
        : 'hidden'} flex-col justify-center items-center mx-auto gap-2"
    >
      <form
        class="auth-form flex flex-col justify-center items-center mx-auto gap-2"
        action="/logout"
        method="POST"
        use:enhance={submitLogout}
      >
        <button type="submit" class="btn btn-error">Confirm Logout</button>
      </form>
    </main>
  {:else}
    <main
      class="auth-form auth-buttons flex-col justify-center items-center mx-auto gap-2"
    >
      <div
        class="auth-form flex flex-col justify-center items-center mx-auto gap-2"
      >
        <p>Let's learn how to register and login users!</p>
        <div class="">
          <a href="/login" class="btn btn-primary">Login</a>
          <a href="/register" class="btn btn-secondary">Register</a>
        </div>
      </div>
    </main>
  {/if}
</div>
