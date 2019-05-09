<template>
  <div>
    <b-tooltip :label="vacuna.texto" size="is-small" multilined="true">
      <b-button
        @click="informacion(vacuna.id)"
        icon-left="information-outline"
        v-if="vacuna.id"
        :class="claseDinamica"
      ></b-button>
    </b-tooltip>
    <b-modal :active.sync="isImageModalActive">
      <div class="card">
        <div class="card-content">{{detalleVacuna}}</div>
      </div>
    </b-modal>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return { isImageModalActive: false, detalleVacuna: null };
  },
  name: "Vacuna",
  props: {
    vacuna: {
      id: String = "",
      texto: String = "",
      dosis: Number = 0
    }
  },
  methods: {
    informacion: function(id) {
      let baseUrl = "//docs.cnym.com.ar/atm/ds/dsGetVacuna.php?id=";
      axios
        .get(baseUrl + id, { headers: { "x-dsi-restful": 1 } })
        .then(res => {
          this.detalleVacuna = res.text;
        })
        .catch(err => {
          this.detalleVacuna =
            "Ops!!! Ocurrio un error al consular detalle de vacuna";
        })
        .finally(() => {
          this.isImageModalActive = true;
        });
    }
  },
  computed: {
    claseDinamica: function() {
      let valor = this.vacuna.dosis.toString();
      return "dosis-" + valor;
    }
  }
};
</script>


<style scoped>
.dosis-1 {
  background-color: #d141b3;
  color: whitesmoke;
}

.dosis-2 {
  background-color: #6ed141;
  color: whitesmoke;
}

.dosis-3 {
  background-color: #d0c340;
  color: whitesmoke;
}

.dosis-4 {
  background-color: #5484ED;
  color: whitesmoke;
}

.dosis-5 {
  background-color: #ffb878;
  color: whitesmoke;
}
</style>
