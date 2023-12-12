<script>
  import { fade } from 'svelte/transition';

let showContainer = false;

const handleClick = () => {
  showContainer = !showContainer;
};


let bubble1, bubble2, bubble3;

$: if (showContainer) {
  bubble1.style = `opacity: 1; transform: translate(${Math.random() * 100}px, ${Math.random() * 100}px);`;
  bubble2.style = `opacity: 1; transform: translate(${Math.random() * 100}px, ${Math.random() * 100}px);`;
  bubble3.style = `opacity: 1; transform: translate(${Math.random() * 100}px, ${Math.random() * 100}px);`;
}

</script>

<style lang="postcss">

    .bubble {
        width: 10px;
        height: 10px;
        background-color: #4f46e5;
        border-radius: 50%;
        position: absolute;
        opacity: 0;
  }
  
    body {
        @apply font-sans bg-gradient-to-r from-blue-500 to-blue-800 via-blue-700 text-black;
    }

    .container {
        @apply mx-auto p-8 bg-white bg-opacity-20 backdrop-filter backdrop-blur-lg shadow-lg rounded-lg relative overflow-hidden;
    }

    .center {
        @apply flex justify-center items-center;
    }

    .header {
        @apply text-5xl font-extrabold mb-4 text-black tracking-wide relative z-10 text-center;
        font-family: 'Montserrat', sans-serif;
        letter-spacing: 1px;
    }


  @keyframes pulse-border {
    0%, 100% {
      transform: scale(1);
    }
    50% {
      transform: scale(1.1);
      opacity: 0;
    }
  }



    .summary {
        @apply text-2xl text-gray-700 mb-4 font-semibold relative z-10 text-center animate-pulse;
        font-family: 'Roboto', sans-serif;
        letter-spacing: 1px;
        transition: all 0.3s ease-in-out;
    }

    .summary:hover {
        @apply text-blue-500;
    }

    .get-started-btn {
        @apply bg-white text-blue-500 font-bold py-2 px-4 rounded-full transition duration-300 shadow-md focus:outline-none relative z-10 block mx-auto;
    }

    .get-started-btn:hover {
        @apply bg-white text-blue-700;
    }

    .content {
        @apply text-lg text-white leading-relaxed mb-6 font-light relative z-10 text-center ;
    }

    .features-list {
        @apply flex space-x-4 p-10 overflow-x-auto overflow-y-visible;
    }

    .feature-item {
        @apply min-w-[330px] relative z-10;
        transition: transform 0.3s ease-in-out;
    }

    .feature-item:hover {
        transform: scale(1.05);
    }

    .card {
        @apply bg-white border border-gray-200 p-6 rounded-md shadow-md hover:shadow-lg transition duration-300 relative z-10;
    }

    .card-title {
        @apply text-lg font-semibold mb-2 text-gray-800;
        font-family: 'Montserrat', sans-serif;
        letter-spacing: 0.5px;
    }

    .card-content {
        @apply text-gray-700;
        font-family: 'Poppins', sans-serif;
        letter-spacing: 0.5px;
    }

    .icon {
        @apply text-3xl mb-2;
    }

    .height-space {
        @apply pt-4;
    }

</style>

<br/>
<br/>
<br/>
<br/>
<br/>

<div class="header">
    Welcome to <span class="text-blue-500">RecruitRover</span> - ATeam HR Bot
</div>

<br/>
<br/>

<div class="container">
    <div class="summary">
        Elevate your recruitment process with ATeam, Zoho's intelligent HR bot. Streamline communication and automate interactions with candidates seamlessly.
    </div>
</div>

<br/>
<br/>
<br/>
<br/>
<br/>

<div class="center relative">
    <a href="#_" on:click={handleClick} class="inline-flex items-center justify-start py-6 pl-8 pr-16 overflow-hidden font-semibold text-indigo-600 transition-all duration-150 ease-in-out rounded hover:pl-14 hover:pr-8 bg-gray-50 group relative">
      {#if !showContainer}
        <span transition:fade="{{ duration: 0 }}" class="absolute bottom-0 left-0 w-full h-1 transition-all duration-150 ease-in-out bg-indigo-600 group-hover:h-full"></span>
        <span transition:fade="{{ duration: 0 }}" class="absolute right-0 pr-4 duration-200 ease-out group-hover:translate-x-12">
          <svg class="w-5 h-5 text-green-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path></svg>
        </span>
        <span transition:fade="{{ duration: 0 }}" class="absolute left-0 pl-2.5 -translate-x-12 group-hover:translate-x-0 ease-out duration-200">
          <svg class="w-5 h-5 text-green-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path></svg>
        </span>
        <span transition:fade="{{ duration: 0 }}" class="relative w-full text-left transition-colors duration-200 ease-in-out group-hover:text-white">Get Started!</span>
        <span bind:this={bubble1} class="bubble"></span>
        <span bind:this={bubble2} class="bubble"></span>
        <span bind:this={bubble3} class="bubble"></span>
      {/if}
    </a>
    {#if showContainer}
      <div transition:fade="{{ duration: 500 }}" class="container mt-8 p-4 bg-gray-200">
        <p class="text-lg text-indigo-800">
          Please tap the chat icon on the bottom right side to initiate a conversation.
        </p>
        <!-- Additional information goes here -->
      </div>
    {/if}
  </div>


<br/>
<br/>
<br/>
<br/>
<br/>

<div class="container">
<div class="features-list">
    <div class="feature-item card">
        
        <span class="feature-text card-content">
            <div class="card-title"><span class="icon">🌐</span>  List Opening Jobs</div>
            List opening jobs with user's desired criteria (salary bracket, job location, posting titles).
        </span>
    </div>
    <div class="feature-item card">
        
        <span class="feature-text card-content">
            <div class="card-title"><span class="icon">🔄</span>  Retrieve User Status</div>
            Retrieve the current status of existing users.
        </span>
    </div>

    <div class="feature-item card">
       
        <span class="feature-text card-content">
            <div class="card-title"> <span class="icon">💬</span>  User-Friendly Conversations</div>
            Natural and user-friendly bot conversation with a focus on effective GUI interaction.
        </span>
    </div>
    <div class="feature-item card">
        <span class="feature-text card-content">
            <div class="card-title"><span class="icon">🔗</span>  Zoho's Recruit API Integration</div>
            Integration with Zoho's Recruit API to associate users with opening jobs and retrieve their status.
        </span>
    </div>
</div>
</div>

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

<div class="container">
    <div class="summary">
        <a href="https://github.com/EphemeralSapient/HR_frontpage"> If the chat didn't appear then we are out of trial period. To check the website code, please visit github repo </a>
    </div>
</div>

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
