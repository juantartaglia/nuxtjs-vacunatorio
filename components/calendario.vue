<template>
  <div class="container">
    <div>Hola Soy el Calendario</div>
    <b-tabs position="is-centered" class="block">
      <b-tab-item label="Pediatria" icon="baby-face-outline">
        <b-table :data="pediatria">
          <template slot-scope="props">
            <b-table-column field="edad" label="Edad">{{props.row.edad}}</b-table-column>
            <b-table-column field="bcg" label="BCG">
              <Vacuna v-bind:vacuna="props.row.bcg"/>
            </b-table-column>
            <b-table-column field="cuadruple" label="Cuadruple">
              <Vacuna v-bind:vacuna="props.row.cuadruple"/>
            </b-table-column>
            <b-table-column field="doble" label="Doble">
              <Vacuna v-bind:vacuna="props.row.doble"/>
            </b-table-column>
            <b-table-column field="gripe" label="Gripe">
              <Vacuna v-bind:vacuna="props.row.gripe"/>
            </b-table-column>
            <b-table-column field="hepA" label="Hepatitis A">
              <Vacuna v-bind:vacuna="props.row.hepA"/>
            </b-table-column>
            <b-table-column field="hepB" label="Hepatitis B">
              <Vacuna v-bind:vacuna="props.row.hepB"/>
            </b-table-column>
            <b-table-column field="hpv" label="HPV">
              <Vacuna v-bind:vacuna="props.row.hpv"/>
            </b-table-column>
            <b-table-column field="meningococo" label="Meningococo">
              <Vacuna v-bind:vacuna="props.row.meningococo"/>
            </b-table-column>
            <b-table-column field="neumococo" label="Neumococo">
              <Vacuna v-bind:vacuna="props.row.neumococo"/>
            </b-table-column>
            <b-table-column field="rotavirus" label="Rotavirus">
              <Vacuna v-bind:vacuna="props.row.rotavirus"/>
            </b-table-column>
            <b-table-column field="sabin" label="Sabin">
              <Vacuna v-bind:vacuna="props.row.sabin"/>
            </b-table-column>
            <b-table-column field="tripleBacteriana" label="Triple Bacteriana Acelular">
              <Vacuna v-bind:vacuna="props.row.tripleBacteriana"/>
            </b-table-column>
            <b-table-column field="tripleViral" label="Triple Viral">
              <Vacuna v-bind:vacuna="props.row.tripleViral"/>
            </b-table-column>
            <b-table-column field="varicela" label="Varicela">
              <Vacuna v-bind:vacuna="props.row.varicela"/>
            </b-table-column>
          </template>
        </b-table>
      </b-tab-item>
      <b-tab-item label="Embarazadas" icon="human-pregnant">
        <b-table :data="embarazadas">
          <template slot-scope="props">
            <b-table-column field="edad" label="Edad">{{props.row.edad}}</b-table-column>
            <b-table-column field="bcg" label="BCG">
              <Vacuna v-bind:vacuna="props.row.bcg"/>
            </b-table-column>
            <b-table-column field="cuadruple" label="Cuadruple">
              <Vacuna v-bind:vacuna="props.row.cuadruple"/>
            </b-table-column>
            <b-table-column field="doble" label="Doble">
              <Vacuna v-bind:vacuna="props.row.doble"/>
            </b-table-column>
            <b-table-column field="gripe" label="Gripe">
              <Vacuna v-bind:vacuna="props.row.gripe"/>
            </b-table-column>
            <b-table-column field="hepA" label="Hepatitis A">
              <Vacuna v-bind:vacuna="props.row.hepA"/>
            </b-table-column>
            <b-table-column field="hepB" label="Hepatitis B">
              <Vacuna v-bind:vacuna="props.row.hepB"/>
            </b-table-column>
            <b-table-column field="hpv" label="HPV">
              <Vacuna v-bind:vacuna="props.row.hpv"/>
            </b-table-column>
            <b-table-column field="meningococo" label="Meningococo">
              <Vacuna v-bind:vacuna="props.row.meningococo"/>
            </b-table-column>
            <b-table-column field="neumococo" label="Neumococo">
              <Vacuna v-bind:vacuna="props.row.cuadruple"/>
            </b-table-column>
            <b-table-column field="rotavirus" label="Rotavirus">
              <Vacuna v-bind:vacuna="props.row.rotavirus"/>
            </b-table-column>
            <b-table-column field="sabin" label="Sabin">
              <Vacuna v-bind:vacuna="props.row.sabin"/>
            </b-table-column>
            <b-table-column field="tripleBacteriana" label="Triple Bacteriana Acelular">
              <Vacuna v-bind:vacuna="props.row.tripleBacteriana"/>
            </b-table-column>
            <b-table-column field="tripleViral" label="Triple Viral">
              <Vacuna v-bind:vacuna="props.row.tripleViral"/>
            </b-table-column>
            <b-table-column field="varicela" label="Varicela">
              <Vacuna v-bind:vacuna="props.row.varicela"/>
            </b-table-column>
          </template>
        </b-table>
      </b-tab-item>
      <b-tab-item label="Adultos" icon="human-male-female">
        <b-table :data="adultos">
          <template slot-scope="props">
            <b-table-column field="edad" label="Edad">{{props.row.edad}}</b-table-column>
            <b-table-column field="doble" label="Doble">
              <Vacuna v-bind:vacuna="props.row.doble" v-bind:id="props.row"/>
            </b-table-column>
            <b-table-column field="gripe" label="Gripe">
              <Vacuna v-bind:vacuna="props.row.gripe"/>
            </b-table-column>
            <b-table-column field="hepA" label="Hepatitis A">
              <Vacuna v-bind:vacuna="props.row.hepA"/>
            </b-table-column>
            <b-table-column field="hepB" label="Hepatitis B">
              <Vacuna v-bind:vacuna="props.row.hepB"/>
            </b-table-column>
            <b-table-column field="herpes" label="Herpes Zoster">
              <Vacuna v-bind:vacuna="props.row.herpes"/>
            </b-table-column>
            <b-table-column field="hpv" label="HPV">
              <Vacuna v-bind:vacuna="props.row.hpv"/>
            </b-table-column>
            <b-table-column field="meningococo" label="Meningococo">
              <Vacuna v-bind:vacuna="props.row.meningococo"/>
            </b-table-column>
            <b-table-column field="neumococo13" label="Neumococo 13">
              <Vacuna v-bind:vacuna="props.row.neumococo13"/>
            </b-table-column>
            <b-table-column field="neumococo23" label="Neumococo 23">
              <Vacuna v-bind:vacuna="props.row.neumococo23"/>
            </b-table-column>
            <b-table-column field="tripleBacteriana" label="Triple Bacteriana Acelular">
              <Vacuna v-bind:vacuna="props.row.tripleBacteriana"/>
            </b-table-column>
            <b-table-column field="tripleViral" label="Triple Viral">
              <Vacuna v-bind:vacuna="props.row.tripleViral"/>
            </b-table-column>
            <b-table-column field="varicela" label="Varicela">
              <Vacuna v-bind:vacuna="props.row.varicela"/>
            </b-table-column>
          </template>
        </b-table>
      </b-tab-item>
    </b-tabs>
  </div>
</template>

<script>
import Vacuna from "~/components/vacuna.vue";
import vacunas from "~/components/calendario.json";

export default {
  name: "Calendario",
  components: {
    Vacuna
  },
  data() {
    return vacunas;
  }
};
</script>

<style scoped>
</style>
