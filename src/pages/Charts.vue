<template>
  <Layout>
    <div class="video-container">
      <section class="video layout">
        <div>
          <h2 class="text-center">Defenda o sus</h2>
          <p class="absolut-text">Atualmente o servidor contem 66 membros.</p>
          <p class="absolut-text"> Número de entrevistados 20 <b>(30,3%) </b>.</p>

          <div>
            <vue-apex-charts
              width="500"
              type="donut"
              :options="options"
              :series="series"
            ></vue-apex-charts>
          </div>
          <div>
            <vue-apex-charts
              width="500"
              type="donut"
              :options="semiDonutoptions"
              :labels="semiDonutoptions.labels"
              :series="semiDonutoptions.series"
            ></vue-apex-charts>
          </div>
        </div>
      </section>
    </div>
  </Layout>
</template>

<script>
import VueApexCharts from "vue-apexcharts";
export default {
  metaInfo: {
    title: "Dados",
  },
  components: {
    VueApexCharts,
  },
  data() {
    return {
      options: {
        chart: {
          id: "vuechart-example",
          type: "donut",
        },
        plotOptions: {
          pie: {
            donut: {
              labels: {
                show: true,
                name: {},
              },
            },
          },
        },

        labels: [
          "Coronovac",
          "Astrazeneca",
          "Pfizer",
          "Janssen",
          "Não vacinados",
        ],
        xaxis: {
          categories: [],
        },
      },
      series: [4, 3, 9, 3, 3],
      semiDonutoptions: {
        series: [13, 3, 3],
        labels: ["Primeira dose", "Segunda dose", "Não vacinados"],
        chart: {
          type: "donut",
        },
        plotOptions: {
          pie: {
            startAngle: -90,
            endAngle: 90,
            offsetY: 10,
            donut: {
              labels: {
                show: true,
                name: {},
              },
            },
          },
        },
        grid: {
          padding: {
            bottom: -80,
          },
        },
        responsive: [
          {
            breakpoint: 480,
            options: {
              chart: {
                width: 200,
              },
              legend: {
                position: "bottom",
              },
            },
          },
        ],
      },
    };
  },
};
</script>
<style scoped>
* {
  font-family: "Montserrat", "Segoe UI", Roboto, "Helvetica Neue", Arial,
    sans-serif;
  list-style-type: none;
}

h2 {
  font-size: 30px;
  font-weight: 600;
  color: #051128;
}
.banner-text {
  text-align: initial;
  font-size: 31px;
  font-weight: 600;
  color: #051128;
}

.absolut-text {
  font-size: 19px;
  font-weight: 600;
}

.deal {
  height: 492px;
  width: 426px;
  z-index: -1;
  float: right;
}

.description {
  line-height: 28px;
  padding-right: 59px;
}
.text-center {
  text-align: center;
}
.row {
  flex-direction: row;
}

.home-links a {
  margin-right: 1rem;
}

#svg-map path {
  fill: #1eb19e;
}

#svg-map text {
  fill: #fff;
  font: 12px;
  cursor: pointer;
}

#svg-map a {
  text-decoration: none;
}

#svg-map a:hover {
  cursor: pointer;
  text-decoration: none;
}

#svg-map a:hover path {
  fill: #003399 !important;
}

#svg-map .circle {
  fill: #66ccff;
}

#svg-map a:hover .circle {
  fill: #003399 !important;
  cursor: pointer;
}
</style>
