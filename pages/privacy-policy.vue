<template>
  <section class="container">
    <h1>header + nav TODO</h1>
    <div>
      <h1>Privacy Policy</h1>
      <p>By accessing or using the Orbit Media Studios, Inc. Web site, you agree to the terms of this Online Privacy
        Policy, as outlined below. If you do not agree to these terms, please do not access or use this site.</p>

      <h2>Collection of Personal Information</h2>
      <p>When you engage in certain activities on this site, you may be asked to provide certain information about
        yourself by filling out and submitting an online form. It is completely optional for you to engage in these
        activities. If you elect to engage in these activities, however, you may be required to provide personal
        information, such as your name, mailing address, e-mail address, and other personal identifying information.
      </p>
      <p>
        When you submit personal information, you understand and agree that Orbit may transfer, store, and process your
        information in any of the countries in which Orbit maintain offices, including without limitation, the United
        States.
      </p>
      <p>
        Orbit collects this information in order to record and support your participation in the activities you select.
        Orbit also uses information that you provide as part of our effort to keep you informed about product upgrades,
        special offers, and other Orbit products and services. Orbit will never sell or share your information with
        other companies.
      </p>
    </div>

    <footer-bar/>
  </section>
</template>

<script>
  import HeaderBar from '~/components/HeaderBar.vue';
  import Navigation from '~/components/Navigation.vue';
  import FooterBar from '~/components/Footer/FooterBar.vue';

  export default {
    components: {
      HeaderBar,
      Navigation,
      FooterBar
    }
  };
</script>

<style lang="scss" scoped>
</style>
