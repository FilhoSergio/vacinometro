<template>
  <Layout>
    <div class="container">
      <div class="display layout">
        <h2 class="banner-text">
          <b> Vacinômetro </b> <br />
          A Locadora <b> </b> !
        </h2>

        <p class="description">
          Com a iniciativa, a locadora passa a fazer uma contagem e levantamento
          do índice de vacinados.
        </p>
        <a
          href="https://forms.gle/ZjAyYWXeWVkrGXodA"
          to="/about"
          class="btn-main-action"
        >
          Saiba mais
        </a>
      </div>

      <g-image
        alt="acordo"
        class="deal"
        src="~/assets/undraw_doctors_hwty.svg"
      />
    </div>
    <section class="layout-items">
      <h2 class="text-center">Medidas preventivas</h2>
      <div class="step step1">
        <div class="content-image">
          <div class="step-number">
            <div class="step-number-text"><h6>1</h6></div>
          </div>

          <g-image src="~/assets/mask.svg" />
          <p class="text-center p-content">
            Use máscara , de preferência pff2.
          </p>
        </div>
        <div class="content-image">
          <div class="step-number">
            <div class="step-number-text"><h6>2</h6></div>
          </div>
          <g-image src="~/assets/distance.svg" />
          <p class="text-center p-content">
            Evite aglomerações seja consciente.
          </p>
        </div>
        <div class="content-image content-image-icon">
          <div class="step-number">
            <div class="step-number-text"><h6>3</h6></div>
          </div>

          <g-image src="~/assets/clean.svg" />
          <p class="text-center p-content">
            Lave bem as mãos e utilize álcool 70%.
          </p>
          <span> </span>
        </div>
      </div>
    </section>
    <div class="features-steps video">
      <div
        style="margin-top: 100px;
    display: flex;
    align-items: center;
    justify-content: space-around;"
      >
        <div>
          <iframe
            width="347"
            height="265"
            src="https://www.youtube.com/embed/tUw6lRQ5cs4"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
        <div class="content">
          <div class="description-container" style="margin-left: 50px;">
            <h2>Atenção</h2>
            <g-image src="~/assets/bacteria.svg" />
            <p>
              A COVID-19 é uma doença infecciosa causada pelo novo coronavírus
              (SARS-CoV-2) e tem como principais sintomas febre, cansaço e tosse
              seca. Alguns pacientes podem apresentar dores, congestão nasal,
              dor de cabeça, conjuntivite, dor de garganta, diarreia, perda de
              paladar ou olfato, erupção cutânea na pele ou descoloração dos
              dedos das mãos ou dos pés. Esses sintomas geralmente são leves e
              começam gradualmente. Algumas pessoas são infectadas, mas
              apresentam apenas sintomas muito leves.
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="video-container">
      <section class="video layout">
        <div >
          <h2 class="text-center">Reunimos dados de várias partes do país.</h2>
          <div>
            <vue-apex-charts
              width="600"
              type="bar"
              :options="chartOptions"
              :series="series"
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
    title: "Vacinômetro",
  },
  components: {
    VueApexCharts,
  },
  data() {
    return {
      series: [
        {
          data: [2, 2, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1],
        },
      ],
      chartOptions: {
        chart: {
          type: "bar",
          height: 400,
          width: 400,
        },
        plotOptions: {
          bar: {
            borderRadius: 4,
            horizontal: true,
          },
        },
        dataLabels: {
          enabled: false,
        },
        xaxis: {
          categories: [
            "Fortaleza",
            "São Paulo",
            "Salvador",
            "Curitiba",
            "Recife",
            "Tatuí",
            "São Gonçalo do Amarente",
            "Arapiraca",
            "Aracaju",
            "Estância Velha",
            "Natal",
            "Pirangi",
            "Mossoró",
            "Jundiaí",
            "Oeiras",
            "Campos dos goytacazes",
          ],
        },
      },
    };
  },
};
</script>

<style>
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

.container {
  display: flex; /* or inline-flex */
}

.layout-items {
  max-width: 1100px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.display {
  flex-direction: column;
  padding: 80px 0 80px 0;
}

.btn-main-action {
  padding: 12px 60px;
  font-weight: 600;
  font-size: 16px;
  text-transform: uppercase;
  border: none;
  border-radius: 4px;
  background-color: #1eb19e;
  margin-top: 20px;
  color: #ffff;
  display: inline-block;
  text-decoration: none;
}

.btn-action {
  padding: 12px 60px;
  font-weight: 600;
  font-size: 16px;
  text-transform: uppercase;
  border: none;
  border-radius: 4px;
  background-color: #1eb19e;
  color: #ffff;
  width: 180px;
  margin: 0 auto !important;
  display: block;
  text-decoration: none;
}

.btn-main-action:hover {
  background-color: #8defef;
  cursor: pointer;
}

.btn-main-action:focus {
  border: none;
  outline: none;
}

.image-container {
  width: 312px;
  height: 378.15px;
}
.step {
  margin-top: 100px;
  display: flex;

  align-items: center;

  justify-content: space-around;
}

.step-image {
  width: 117px;
  height: 87px;
  align-items: center;
  justify-content: center;
}

.step-image-1 {
  width: 110px;
  height: 75px;
  margin-top: 32px;
  margin-bottom: -14px;
}

.step-image-2 {
  width: 110px;
  height: 78px;
  margin-top: 32px;
  margin-bottom: -14px;
}

.step-image-3 {
  width: 79px;
  height: 93px;
  margin-top: 32px;
  margin-bottom: -14px;
}

.content-text {
  margin-top: 30px !important;
  line-height: 24px !important;
  font-style: normal;
  font-weight: 600;
  font-size: 19px;
  color: #051128;
  margin-bottom: 12px;
}

.content-image {
  width: 200px;
  height: 250px;
  background: #ffffff;
  box-shadow: 4px 4px 30px rgba(194, 194, 194, 0.31),
    0px 4px 50px rgba(203, 203, 203, 0.1);
  border-radius: 15px;
  padding: 12px;
}

.step-content-image {
  position: absolute;
  width: 56px;
  height: 56px;
  left: 1369px;
  top: 896px;

  background: #00c4c3;
}

.content-image .p-content {
  font-style: normal;
  font-weight: 600;
  /*font-size: 19px;*/
  line-height: 22px;
  margin-top: 44px;
  color: #051128;
}
.content-image span {
  font-size: 16px;
  line-height: 21, 79px;
  text-align: center;
  display: flex;
  color: #051128;
}
.content-image img {
  align-items: center;
  justify-content: center;
  text-align: center;
  display: block;
  margin-left: auto;
  margin-right: auto;
  margin-top: 30px;
  /* width: 120px;
  height: 108px; */
}

.content-image img .step-image-3 {
  margin-top: 30px;
}

/*  */

.step-number {
  color: #ffffff;
  display: table;
  position: absolute;
  width: 56px;
  height: 56px;
  position: relative;
  top: -30px;
  margin: 0 auto -35px;

  border-radius: 50%;
  background: #1eb19e;
}

.step-alt .step-number {
  background: #00c4c3;
}

.step-alt .image-container {
  order: 1;
}

.step-number .step-number-text {
  display: table-cell;
  vertical-align: middle;
  text-align: center;
}

.step-number .step-number-text h6 {
  font-family: "Montserrat";
  margin: 0;
  font-size: 22px;
  font-weight: 700;
  color: #ffffff !important;
  text-decoration: none !important;
}

/**** VIDEO */

.video-container {
  background-color: #fff;
  margin-top: 90px;;
}

.video-container:before {
  background: url("~@/assets/blob.svg");
  position: absolute;
  content: " ";
  width: 24vw;
  height: 90%;
  transform: rotate(24deg) translate(-200px, 0%);
  z-index: 0;
  left: 0;
  opacity: 0.2;
}

.note {
  background: #ffffff;
  box-shadow: 4px 4px 30px rgba(194, 194, 194, 0.31),
    0px 4px 50px rgba(203, 203, 203, 0.1);
  border-radius: 15px;
  position: relative;
  top: 90px;
  padding: 21px;
  width: 90%;
  margin: 0 auto;
  height: 500px;
}
.note h2 {
  font-family: Montserrat;
  font-style: normal;
  font-weight: bold;
  font-size: 34px;
  line-height: 20px;
  color: #051128;
}

/**** FEATURES *****/
.features {
  font-family: "Montserrat";
  text-align: center;
  margin-top: 80px;
}
.features h2 {
  font-size: 30px;
  font-weight: 600;
  color: #051128;
}
.features .subtitle {
  margin: auto;
  width: 460px;
  font-size: 14px;
  color: #808095;
  margin-top: 8px;
}
.features .features-steps {
  margin-top: 90px;
}
.features .features-steps .step {
  margin-top: 90px;
  display: flex;
  justify-content: space-around;
}
.features .features-steps .step .content {
  display: flex;
}
.features .features-steps .img-container {
  text-align: center;
}
.features .features-steps .step1 {
  width: 100px;
  height: 100px;
}

.features .features-steps .description-container {
  max-width: 350px;
  text-align: left;
  margin: auto;
}
.features .step-number {
  width: 50px;
  height: 50px;
  background: #051128;
  color: #ffffff;
  border-radius: 50%;
  display: table;
}
.features .step-alt .step-number {
  background: #23d3d3;
}
.features .step-alt .image-container {
  order: 1;
}
.features .step-number .step-number-text {
  display: table-cell;
  vertical-align: middle;
  text-align: center;
}
.features .step-number .step-number-text h6 {
  font-family: "Montserrat";
  margin: 0;
  font-size: 22px;
  font-weight: 700;
  color: #ffffff !important;
  text-decoration: none !important;
}
.features .features-steps h2 {
  font-size: 26px;
  font-weight: 600;
  margin-top: 10px;
}
.features .features-steps p {
  color: #818198;
  font-size: 16px;
  font-weight: 500;
}

@media only screen and (max-width: 768px) {
  .header {
    padding-bottom: 0;
    margin-bottom: 0;
  }
  .deal {
    width: 300px;
    height: 300px;
    margin: 0 auto;
    padding-top: 0px;
  }

  .banner-text {
    text-align: center;
  }
  .description {
    padding-right: 0px;
  }
  .container {
    flex-direction: column-reverse;
  }
  .btn-main-action {
    margin-top: 18px;
  }
  .btn-action {
    padding: 12px 30px;
  }
  .display {
    flex-direction: column;
    padding: 5px;
    text-align: center;
  }
  .step {
    display: block;
    margin-top: 60px;
  }

  .content-image {
    margin-top: 60px;
    width: 100%;
    padding: 0;
  }

  .content-text {
    margin-bottom: 0;
  }
  .content-image-icon {
    margin-bottom: 32px;
  }
  .content-image img {
    margin-top: 22px;
  }

  .content-image p {
    padding: 12px;
  }

  .content-image .p-content {
    margin-top: 30px;
    margin-bottom: 2px;
  }

  .content-image span {
    padding-left: 14px;
    padding-right: 14px;
    font-size: 15px;
  }

  .step-image-3 {
    margin-top: 12px;
  }

  .note {
    width: 90%;
    padding: 15px;
    top: 60px;
  }

  .note h2 {
    font-size: 25px;
  }
}
</style>
