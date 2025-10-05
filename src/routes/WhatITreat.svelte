<script lang="ts">
  interface Condition {
    title: string;
    description: string;
    imagePlaceholder: string;
    gradientColors: string;
  }

  const conditions: Condition[] = [
    {
      title: "Back & Neck Pain",
      description: "Specialized treatment for chronic and acute spinal conditions, helping you move freely without pain.",
      imagePlaceholder: "Icon Placeholder",
      gradientColors: "from-green-100 to-emerald-100"
    },
    {
      title: "Sports Injuries",
      description: "Expert rehabilitation for athletes and active individuals, getting you back to peak performance.",
      imagePlaceholder: "Icon Placeholder",
      gradientColors: "from-teal-100 to-cyan-100"
    },
    {
      title: "Joint Problems",
      description: "Relief from arthritis, stiffness, and mobility issues affecting hips, knees, shoulders, and more.",
      imagePlaceholder: "Icon Placeholder",
      gradientColors: "from-emerald-100 to-green-100"
    },
    {
      title: "Postural Issues",
      description: "Correct alignment problems and develop ergonomic habits for long-term wellness.",
      imagePlaceholder: "Icon Placeholder",
      gradientColors: "from-lime-100 to-green-100"
    },
    {
      title: "Headaches & Migraines",
      description: "Targeted treatment for tension headaches and migraine relief through manual therapy.",
      imagePlaceholder: "Icon Placeholder",
      gradientColors: "from-green-100 to-teal-100"
    },
    {
      title: "Stress & Tension",
      description: "Address physical manifestations of stress with holistic body-mind techniques.",
      imagePlaceholder: "Icon Placeholder",
      gradientColors: "from-emerald-100 to-teal-100"
    }
  ];
</script>

<section id="what-i-treat" class="py-24 lg:py-32 bg-gradient-to-b from-gray-50 to-white">
  <div class="max-w-7xl mx-auto px-6 lg:px-8">
    <div class="text-center mb-20">
      <span class="text-green-600 font-semibold text-sm tracking-widest uppercase mb-4 block">Conditions</span>
      <h2 class="text-5xl lg:text-6xl font-bold text-gray-900 mb-6">What I Treat</h2>
      <p class="text-xl text-gray-600 max-w-3xl mx-auto">Comprehensive care for a wide range of physical conditions and discomforts</p>
    </div>
    
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each conditions as condition}
        <div class="group bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl hover:-translate-y-1 transition-all duration-300">
          <div class="w-full h-48 bg-gradient-to-br {condition.gradientColors} rounded-xl mb-6 flex items-center justify-center overflow-hidden">
            <div class="text-gray-400 text-base">{condition.imagePlaceholder}</div>
          </div>
          <h3 class="text-2xl font-bold text-gray-900 mb-3 group-hover:text-green-600 transition-colors">{condition.title}</h3>
          <p class="text-gray-600 leading-relaxed">{condition.description}</p>
        </div>
      {/each}
    </div>
  </div>
</section>