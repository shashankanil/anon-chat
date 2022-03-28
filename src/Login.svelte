<script>
  import { user } from './user';

  let username;
  let password;

  function login() {
    user.auth(username, password, ({ err }) => err && alert(err));
  }

  function signup() {
    user.create(username, password, ({ err }) => {
      if (err) {
        alert(err);
      } else {
        login();
      }
    });
  }
</script>
<label for="username"><h2> Username </h2></label>
<input name="username" bind:value={username} minlength="3" maxlength="16" />
<label for="password"> <h2> Password <h2> </label>
<input name="password" bind:value={password} type="password" />
<button class="login" on:click={login}>Login</button>
<button class="login"  on:click={signup}>Sign Up</button>
  
