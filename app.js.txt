document.addEventListener("DOMContentLoaded", () => {
  // Create GSAP animations for the hero section
  gsap.from("#hero .title", { opacity: 0, y: -50, duration: 1.5 });
  gsap.from("#hero .description", { opacity: 0, y: -30, duration: 1.5, delay: 0.5 });
  gsap.from(".cta-button", { opacity: 0, y: 20, duration: 1.5, delay: 1 });

  // Create ScrollMagic Scene for scrolling animations
  const controller = new ScrollMagic.Controller();

  // Animate Features Section
  const featureTimeline = gsap.timeline();
  featureTimeline.from(".feature", { opacity: 0, y: 100, stagger: 0.3, duration: 1 });

  new ScrollMagic.Scene({
    triggerElement: "#features",
    triggerHook: 0.8,
    duration: "100%"
  })
    .setTween(featureTimeline)
    .addTo(controller);

  // Animate Testimonials Section
  const testimonialsTimeline = gsap.timeline();
  testimonialsTimeline.from(".testimonials p", { opacity: 0, y: 30, stagger: 0.2, duration: 1 });

  new ScrollMagic.Scene({
    triggerElement: "#testimonials",
    triggerHook: 0.8,
    duration: "100%"
  })
    .setTween(testimonialsTimeline)
    .addTo(controller);
});
