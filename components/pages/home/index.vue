<template>
  <div>
    <BannerSection />
    <FeaturesSection />
    <TryFreeSection />
    <SubscribeForm />
    <PartnersSection />
    <TestimonialsSection />
    <PricingSection />
    <ContactUsSection />
  </div>
</template>

<script>
import BannerSection from '@/components/pages/home/banner-section'
import FeaturesSection from '@/components/pages/home/features-section'
import TryFreeSection from '@/components/pages/home/try-free-section'
import SubscribeForm from '@/components/pages/home/subscribe-form'
import PartnersSection from '@/components/pages/home/partners-section'
import TestimonialsSection from '@/components/pages/home/testimonials-section'
import PricingSection from '@/components/pages/home/pricing-section'
import ContactUsSection from '@/components/pages/home/contact-us-section'

export default {
  name: 'HomePage',
  components: {
    BannerSection,
    FeaturesSection,
    TryFreeSection,
    SubscribeForm,
    PartnersSection,
    TestimonialsSection,
    PricingSection,
    ContactUsSection
  }
}
</script>

<style lang="scss" scoped>

</style>
