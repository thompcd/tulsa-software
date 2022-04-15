<script>
import DiGithubBadge from 'svelte-icons/di/DiGithubBadge.svelte'
import FaSlack from 'svelte-icons/fa/FaSlack.svelte'

</script>

<footer>
  <div class="icons">
    <a href="https://github.com/tulsasoftware">
      <DiGithubBadge />
    </a>
    <a href="/">
      <FaSlack />
    </a>
  </div>
</footer>

<style>
  footer {
    text-align: center;
    margin-top: 2rem;
    margin-bottom: 1rem;
  }

  .icons{
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1em;
  }
  .icons * {
    width: 64px;
    height: 64px;
  }
</style>
