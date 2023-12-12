<script>
  import { fade } from 'svelte/transition';
  import Icon from "../public/recruit_logo.png";
</script>

<style lang="postcss">

  .navbar {
      @apply bg-opacity-50 backdrop-filter backdrop-blur-lg py-4;
      @apply flex justify-between items-center;
      @apply border-b-2 border-opacity-60;
      @apply shadow-md overflow-x-auto;
      @apply p-4 fixed top-0 w-full;
      @apply z-50;
  }

  .navbar-logo {
      @apply flex items-center; /* Align the logo and text horizontally */
      @apply pl-4; /* Left padding added */
      @apply transition-all duration-300 ease-in-out; /* Transition for the hover effect */
  }

  .navbar-logo img {
      @apply w-12 h-12 mr-2 rounded-full;
      @apply hover:scale-110; /* Hover scaling effect */
      @apply hover:rotate-6; /* Hover rotation effect */
      @apply hover:shadow-lg; /* Hover shadow effect */
  }

  .navbar-logo span {
      @apply text-lg font-semibold text-black w-[250px];
  }

  .navbar-buttons {
      @apply flex gap-4 items-center;
      @apply min-w-[30px];
      
  }

  .navbar-buttons a {
      @apply text-black no-underline text-base font-semibold transition-transform duration-300 transform-gpu;
      @apply px-4 py-2 rounded-md hover:bg-opacity-70 focus:outline-none;
      @apply transition-all duration-300 ease-in-out; /* New transition properties */
      @apply hover:from-blue-400 hover:via-blue-500 hover:to-blue-600;
      @apply hover:text-blue-500;
      @apply hover:shadow-lg;

      &:before {
          content: "";
          /* @apply absolute inset-0 bg-gradient-to-r from-blue-100 via-blue-500 to-blue-400 opacity-0 transition-opacity duration-300; */
          @apply mix-blend-multiply;
      }


      /* New hover effect for better visual appeal */
      &:hover {
          transform: scale(1.35);
      }
  }

</style>

<div class="navbar" transition:fade>
  <div class="navbar-logo">
      <img src={Icon} alt="Recruit Logo" />
      <span>RecruitRover</span>
  </div>

  <div class="navbar-buttons">
    <a href="/#_" id="_">Home</a>
    <a href="/#_" id="_">About</a>
    <a href="/#_" id="_">Contact</a>
    <hr/>
    </div>
</div>
