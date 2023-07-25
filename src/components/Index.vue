<script>
import PortfolioLinksContainer from './portfolio/LinksContainer';
import PortfolioVenturesContainer from './portfolio/VenturesContainer';

export default {
  components: {
    PortfolioLinksContainer,
    PortfolioVenturesContainer,
  },
};
</script>

<template>
  <main role="main">
    <div class="container">
      <h3 class="text-center">Ventures</h3>
      <hr />
      <PortfolioVenturesContainer />
      <h3 class="text-center">Find me here</h3>
      <hr />
      <PortfolioLinksContainer />
    </div>
  </main>
</template>
