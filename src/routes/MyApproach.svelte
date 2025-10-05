<script lang="ts">
  interface Pillar {
    icon: string;
    title: string;
    description: string;
  }

  const pillars: Pillar[] = [
    {
      icon: "🌿",
      title: "Holistic Care",
      description: "Treating the whole person—body, mind, and spirit—not just isolated symptoms."
    },
    {
      icon: "✨",
      title: "Personalized Plans",
      description: "Every treatment is tailored specifically to your unique needs and goals."
    },
    {
      icon: "🔬",
      title: "Evidence-Based",
      description: "Using proven, research-backed techniques that deliver real results."
    },
    {
      icon: "💪",
      title: "Empowering You",
      description: "Teaching you the tools and knowledge for sustainable, long-term wellness."
    }
  ];
</script>

<section id="my-approach" class="py-24 lg:py-32 bg-gradient-to-br from-green-500 to-emerald-600 text-white">
  <div class="max-w-7xl mx-auto px-6 lg:px-8">
    <div class="text-center mb-20">
      <span class="text-green-100 font-semibold text-sm tracking-widest uppercase mb-4 block">Philosophy</span>
      <h2 class="text-5xl lg:text-6xl font-bold mb-6">My Approach to Healing</h2>
      <p class="text-xl text-green-50 max-w-3xl mx-auto">Four pillars that guide every treatment session</p>
    </div>
    
    <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
      {#each pillars as pillar}
        <div class="bg-white/10 backdrop-blur-lg rounded-2xl p-8 text-center hover:bg-white/20 transition">
          <div class="w-16 h-16 bg-white/20 rounded-full flex items-center justify-center mx-auto mb-6 text-3xl">
            {pillar.icon}
          </div>
          <h3 class="text-2xl font-bold mb-4">{pillar.title}</h3>
          <p class="text-green-50 leading-relaxed">{pillar.description}</p>
        </div>
      {/each}
    </div>
  </div>
</section>