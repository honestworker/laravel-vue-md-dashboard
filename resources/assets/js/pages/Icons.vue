<template>
  <div class="content">
    <div class="md-layout">
      <div class="md-layout-item">
        <md-card class="md-card-plain">
          <md-card-header data-background-color="green">
            <h4 class="title">Vue Material - Icon</h4>
            <p class="category">
              <a target="_blank" href="https://vuematerial.io/components/icon">Vue Material</a>
            </p>
          </md-card-header>
          <md-card-content>
            <div class="iframe-container hidden-sm">
                <iframe src="https://vuematerial.io/components/icon">
                    <p>Material Icons</p>
                </iframe>
            </div>
          </md-card-content>          
        </md-card>

        <md-card class="md-card-plain">
          <md-card-header data-background-color="green">
            <h4 class="title">Material Design Icons</h4>
            <p class="category">
              <a target="_blank" href="https://design.google.com/icons/">Google</a>
            </p>
          </md-card-header>
          <md-card-content>
            <div class="iframe-container hidden-sm">
                <iframe src="https://design.google.com/icons/">
                    <p>Material Icons</p>
                </iframe>
            </div>
          </md-card-content>
        </md-card>
      </div>
    </div>
  </div>
</template>

<script>
import {
  StatsCard,
  ChartCard,
  NavTabsCard,
  NavTabsTable,
  OrderedTable
} from '@/components'

export default{
  components: {
    StatsCard,
    ChartCard,
    NavTabsCard,
    NavTabsTable,
    OrderedTable
  }
}
</script>
