<template>
  <v-container class="processos">
    <v-card>
      <v-card-title>Processos vindos do Beremir</v-card-title>
      <v-card-subtitle
        >Aqui você encontra uma tabela de processos que passaram pela triagem do
        Beremir.</v-card-subtitle
      >
    </v-card>
    <v-card class="mt-5">
      <v-row class="mx-3">
        <v-col cols="12" sm="6" md="3">
          <label for="numeroProcesso" class="labels pb-3"
            >Número do Processo</label
          >
          <v-text-field
            v-model="numeroDoProcesso"
            id="numeroProcesso"
            dense
            placeholder="Número Processo"
            outlined
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="6">
          <label for="nome" class="labels pb-3">Nome</label>
          <v-text-field
            v-model="nome"
            id="nome"
            dense
            placeholder="Nome"
            outlined
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <label for="dataAjuizamento" class="labels pb-3"
            >Data Ajuizamento</label
          >
          <v-text-field
            v-model="dataAjuizamento"
            id="dataAjuizamento"
            dense
            type="date"
            outlined
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row class="mx-3">
        <v-col cols="12" sm="6" md="3">
          <label for="cpf" class="labels pb-3">CPF</label>
          <v-text-field
            v-model="cpf"
            id="cpf"
            dense
            placeholder="cpf"
            outlined
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <label for="dtDibInicial" class="labels pb-3">Dib Inicial</label>
          <v-text-field
            v-model="dibInicial"
            id="dtDibInicial"
            dense
            type="date"
            outlined
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <label for="dtDibFinal" class="labels pb-3">Dib Final</label>
          <v-text-field
            v-model="dibFinal"
            id="dtDibFinal"
            dense
            type="date"
            outlined
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <label for="rmi" class="labels pb-3">Renda Mensal</label>
          <v-text-field
            v-model="rmi"
            id="rmi"
            dense
            placeholder="R$ - "
            outlined
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row class="mx-3">
        <v-col cols="12" sm="6" md="3">
          <label for="beneficio" class="labels pb-3">Benefício</label>
          <v-text-field
            v-model="beneficio"
            id="beneficio"
            dense
            placeholder="Beneficio"
            outlined
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <label for="nb" class="labels pb-3">Número do benefíco</label>
          <v-text-field
            v-model="nb"
            id="nb"
            dense
            placeholder="Número do benefício"
            outlined
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <label for="dip" class="labels pb-3">Data Início de Pgt</label>
          <v-text-field
            v-model="dip"
            id="dip"
            dense
            type="date"
            outlined
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row class="mx-3">
        <v-col cols="12" sm="6" md="6">
          <label for="aps" class="labels pb-3">APS</label>
          <v-text-field
            v-model="aps"
            id="aps"
            dense
            placeholder="Aps"
            outlined
          ></v-text-field>
        </v-col>
      </v-row>
      <v-card-title>Tabela de Processos</v-card-title>
      <v-data-table
        :headers="headers"
        :items="infos"
        item-key="name"
        class="elevation-1"
      >
        <template v-slot:item="{ item }">
          <tr>
            <td
              class="py-3"
              style="color: rgb(107, 107, 218); cursor: pointer"
              @click="redirectToCalculo"
            >
              {{ item.nup }}
            </td>
            <td>{{ item.interessados }}</td>
            <td>
              <v-btn icon @click="redirectToCalculo">
                <v-icon color="success">mdi-file-eye-outline</v-icon>
              </v-btn>
            </td>
          </tr>
        </template>
      </v-data-table>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: "Processos",
  data: function () {
    return {
      numeroDoProcesso: "",
      nome: "",
      dataAjuizamento: "",
      cpf: "",
      dibInicial: "",
      dibFinal: "",
      rmi: "",
      beneficio: "",
      nb: "",
      dip: "",
      aps: "",
      headers: [
        { value: "nup", text: "NUP" },
        { value: "interessados", text: "Interessados " },
        { value: "actions" },
      ],
      infos: [
        {
          nup: "00457.02334/2021-18(ARQU/ER-SEAS-PRF1)1005832.2021.4.01.3900(TRF1_1)",
          interessados:
            "*AFONSO ROGRIGUES COSTA*INSTITUTO NACIONAL DO SEGURO SOCIAL[GERENCIA EXECUTIVA JUNDIAI]",
        },
        {
          nup: "00457.02334/2021-18(ARQU/ER-SEAS-PRF1)1005832.2021.4.01.3900(TRF1_1)",
          interessados:
            "*AFONSO ROGRIGUES COSTA*INSTITUTO NACIONAL DO SEGURO SOCIAL[GERENCIA EXECUTIVA JUNDIAI]",
        },
        {
          nup: "00457.02334/2021-18(ARQU/ER-SEAS-PRF1)1005832.2021.4.01.3900(TRF1_1)",
          interessados:
            "*AFONSO ROGRIGUES COSTA*INSTITUTO NACIONAL DO SEGURO SOCIAL[GERENCIA EXECUTIVA JUNDIAI]",
        },
        {
          nup: "00457.02334/2021-18(ARQU/ER-SEAS-PRF1)1005832.2021.4.01.3900(TRF1_1)",
          interessados:
            "*AFONSO ROGRIGUES COSTA*INSTITUTO NACIONAL DO SEGURO SOCIAL[GERENCIA EXECUTIVA JUNDIAI]",
        },
        {
          nup: "00457.02334/2021-18(ARQU/ER-SEAS-PRF1)1005832.2021.4.01.3900(TRF1_1)",
          interessados:
            "*AFONSO ROGRIGUES COSTA*INSTITUTO NACIONAL DO SEGURO SOCIAL[GERENCIA EXECUTIVA JUNDIAI]",
        },
        {
          nup: "00457.02334/2021-18(ARQU/ER-SEAS-PRF1)1005832.2021.4.01.3900(TRF1_1)",
          interessados:
            "*AFONSO ROGRIGUES COSTA*INSTITUTO NACIONAL DO SEGURO SOCIAL[GERENCIA EXECUTIVA JUNDIAI]",
        },
      ],
    };
  },
  methods: {
    redirectToCalculo() {
      this.$router.push(`/home`).catch(() => {});
    },
  },
};
</script>

<style>
.processos {
  height: auto;
  min-height: 120vh;
}
</style>
