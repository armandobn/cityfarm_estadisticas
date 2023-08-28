<template>
  <br>
  <div class="container">
    <div class="row">
      <div class="col-10"></div>
      <div class="col">
        <a href="https://stream.hivelive.me/donate/misticogama" style="color: #7205ee">Donaciones</a>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <button class="btn btn-primary" @click="calcular()">Calcular</button>
      </div>
    </div>
    <div class="row">

      <div class="col-6">
        <div class="row">
          <div class="col">
            <h3>Pozo de Agua</h3>
            <div class="form-floating mb-3">
              <input type="text" v-model="nivel_pozo_agua" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Nivel</label>
            </div>
            <div class="form-floating mb-3">
              <input type="text" v-model="horas_pozo_agua" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Horas</label>
            </div>
          </div>
          <div class="col">
            <h3>Fabrica de Energia</h3>
            <div class="form-floating mb-3">
              <input type="text" v-model="nivel_fabrica_energia" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Nivel</label>
            </div>
            <div class="form-floating mb-3">
              <input type="text" v-model="horas_fabrica_energia" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Horas</label>
            </div>

          </div>
        </div>

        <div class="row">
          <div class="col">
            <h3>Tierra Trigo</h3>
            <div class="form-floating mb-3">
              <input type="text" v-model="nivel_tierra_trigo" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Nivel</label>
            </div>
            <div class="form-floating mb-3">
              <input type="text" v-model="horas_tierra_trigo" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Horas</label>
            </div>


          </div>
          <div class="col">
            <h3>Tierra Trigo</h3>
            <div class="form-floating mb-3">
              <input type="text" v-model="nivel_tierra_trigo_2" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Nivel</label>
            </div>
            <div class="form-floating mb-3">
              <input type="text" v-model="horas_tierra_trigo_2" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Horas</label>
            </div>


          </div>
        </div>

        <div class="row">
          <div class="col">
            <h3>Tierra Maiz</h3>
            <div class="form-floating mb-3">
              <input type="text" v-model="nivel_tierra_maiz" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Nivel</label>
            </div>
            <div class="form-floating mb-3">
              <input type="text" v-model="horas_tierra_maiz" class="form-control" id="floatingInput"
                     placeholder="name@example.com">
              <label for="floatingInput">Horas</label>
            </div>


          </div>
          <div class="col">
            <div class="form-floating mb-3">
              <h3>Tierra Maiz</h3>
              <div class="form-floating mb-3">
                <input type="text" v-model="nivel_tierra_maiz_2" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Nivel</label>
              </div>
              <div class="form-floating mb-3">
                <input type="text" v-model="horas_tierra_maiz_2" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Horas</label>
              </div>
            </div>
          </div>

          <div class="row">
            <div class="col">
              <h3>Granja de Gallinas</h3>
              <div class="form-floating mb-3">
                <input type="text" v-model="nivel_granja_gallina" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Nivel</label>
              </div>
              <div class="form-floating mb-3">
                <input type="text" v-model="horas_granja_gallina" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Horas</label>
              </div>


            </div>
            <div class="col">
              <h3>Granja de Vacas</h3>
              <div class="form-floating mb-3">
                <input type="text" v-model="nivel_granja_vacas" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Nivel</label>
              </div>
              <div class="form-floating mb-3">
                <input type="text" v-model="horas_granja_vacas" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Horas</label>
              </div>


            </div>
          </div>

          <div class="row">
            <div class="col">
              <h3>Arboles</h3>
              <div class="form-floating mb-3">
                <input type="text" v-model="nivel_arboles" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Nivel</label>
              </div>
              <div class="form-floating mb-3">
                <input type="text" v-model="horas_arboles" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Horas</label>
              </div>

            </div>

            <div class="col">
              <h3>Arboles</h3>
              <div class="form-floating mb-3">
                <input type="text" v-model="nivel_arboles_2" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Nivel</label>
              </div>
              <div class="form-floating mb-3">
                <input type="text" v-model="horas_arboles_2" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Horas</label>
              </div>
            </div>

            <div class="col">
              <h3>Arboles</h3>
              <div class="form-floating mb-3">
                <input type="text" v-model="nivel_arboles_3" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Nivel</label>
              </div>
              <div class="form-floating mb-3">
                <input type="text" v-model="horas_arboles_3" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Horas</label>
              </div>

            </div>
          </div>

          <h2>MOLINO</h2>
          <div class="row">
            <div class="col">
              <h3>Madera</h3>
              <label>{{ molino.madera.tiempo }} horas</label>
              <div class="form-floating mb-3">
                <input type="text" v-model="molino_cant_madera" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Cantidad</label>
              </div>
            </div>
            <div class="col">
              <h3>Maiz</h3>
              <label>{{ molino.maiz.tiempo }} horas</label>
              <div class="form-floating mb-3">
                <input type="text" v-model="molino_cant_maiz" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Cantidad</label>
              </div>
            </div>

            <div class="col">
              <h3>Trigo</h3>
              <label>{{ molino.trigo.tiempo }} horas</label>
              <div class="form-floating mb-3">
                <input type="text" v-model="molino_cant_trigo" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Cantidad</label>
              </div>
            </div>
          </div>

          <div class="row">
            <div class="col">
              <h3>Leche</h3>
              <label>{{ molino.leche.tiempo }} horas</label>
              <div class="form-floating mb-3">
                <input type="text" v-model="molino_cant_leche" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Cantidad</label>
              </div>
            </div>
            <div class="col">
              <h3>Huevo</h3>
              <label>{{ molino.huevo.tiempo }} horas</label>
              <div class="form-floating mb-3">
                <input type="text" v-model="molino_cant_huevo" class="form-control" id="floatingInput"
                       placeholder="name@example.com">
                <label for="floatingInput">Cantidad</label>
              </div>
            </div>
          </div>

        </div>

      </div>
      <div class="col">

        <label for=""><h5>Obtenido Pozo de Agua</h5></label> <br>
        <label for="">Produccion de Agua: {{ produccion_agua }} </label> <br>
        <label for="">Consume: {{ requerimiento_energia_pozo }} Energia</label> <br>

        <label for=""><h5>Obtenido Fabrica Energia</h5></label><br>
        <label for="">Produccion de Energia: {{ produccion_energia }} </label><br>
        <label for="">Consume: {{ requerimiento_carbon_fabrica }} Carbon</label><br>

        <label for=""><h5>Obtenido Tierra Trigo</h5></label><br>
        <label for="">Produccion de Trigo: {{ produccion_trigo + produccion_trigo_2 }} </label><br>
        <label for="">Consume:
          {{ requerimiento_semilla_trigo_tierra_trigo + requerimiento_semilla_trigo_tierra_trigo_2 }} Semilla de Trigo</label>
        <br>
        <label for="">Consume: {{ requerimiento_agua_tierra_trigo + requerimiento_agua_tierra_trigo_2 }}
          Agua</label><br>

        <label for=""><h5>Obtenido Tierra Maiz</h5></label><br>
        <label for="">Produccion de Maiz: {{ produccion_maiz + produccion_maiz_2 }} </label><br>
        <label for="">Consume: {{ requerimiento_semilla_maiz_tierra_maiz + requerimiento_semilla_maiz_tierra_maiz_2 }}
          Semilla Maiz</label> <br>
        <label for="">Consume: {{ requerimiento_agua_tierra_maiz + requerimiento_agua_tierra_maiz_2 }}
          Agua</label><br>

        <label for=""><h5>Obtenido Granja Gallina</h5></label><br>
        <label for="">Produccion de Huevo: {{ produccion_huevo }} </label><br>
        <label for="">Consume: {{ requerimiento_bolsa_maiz_granja_gallina }} Bolsa Maiz</label> <br>
        <label for="">Consume: {{ requerimiento_agua_granja_gallina }} Agua</label><br>

        <label for=""><h5>Obtenido Granja Vacas</h5></label><br>
        <label for="">Produccion de Huevo: {{ produccion_leche }} </label><br>
        <label for="">Consume: {{ requerimiento_bolsa_trigo_granja_vaca }} Bolsa Trigo</label> <br>
        <label for="">Consume: {{ requerimiento_agua_granja_vaca }} Agua</label><br>

        <label for=""><h5>Obtenido Arboles</h5></label><br>
        <label for="">Produccion de Madera: {{
            produccion_madera + produccion_madera_2 + produccion_madera_3
          }} </label><br>
        <label for="">Consume:
          {{ requerimiento_agua_arboles + requerimiento_agua_arboles_2 + requerimiento_agua_arboles_3 }}
          Agua</label><br>

        <label for=""><h5>Molino Madera</h5></label><br>
        <label for="">Produccion de Carbon: {{ produccion_carbon }} </label><br>
        <label for="">Consume: {{ molino_cant_madera }} Madera</label><br>

        <label for=""><h5>Molino Maiz</h5></label><br>
        <label for="">Produccion de Bolsa Maiz: {{ produccion_bolsa_maiz }} </label><br>
        <label for="">Consume: {{ molino_cant_maiz }} Maiz</label><br>

        <label for=""><h5>Molino Trigo</h5></label><br>
        <label for="">Produccion de Bolsa Trigo: {{ produccion_bolsa_trigo }} </label><br>
        <label for="">Consume: {{ molino_cant_trigo }} Trigo</label><br>

        <div class="row">
          <div class="col">
            <label for=""><h5>Produccion Total</h5></label><br>
            <label for="">Energia: {{ total_energia }} </label><br>
            <label for="">Agua: {{ total_agua }} </label><br>
            <label for="">Maiz: {{ total_maiz }} </label><br>
            <label for="">Trigo: {{ total_trigo }} </label><br>
            <label for="">Bolsa Maiz: {{ total_bolsa_maiz }} </label><br>
            <label for="">Bolsa Trigo: {{ total_bolsa_trigo }} </label><br>
            <label for="">Leche: {{ total_leche }} </label><br>
            <label for="">Huevo: {{ total_huevo }} </label><br>
            <label for="">Madera: {{ total_madera }} </label><br>
            <label for="">Carbon: {{ total_carbon }} </label><br>
            <label for="">KOD: {{ total_kod }} </label><br>
            <label for="">HUESO: {{ total_hueso }} </label><br>

          </div>
          <div class="col">
            <label for=""><h5>Consumo Total</h5></label><br>
            <label for="">Energia: {{ consumo_energia }} </label><br>
            <label for="">Agua: {{ consumo_agua }} </label><br>
            <label for="">Carbon: {{ consumo_carbon }} </label><br>
            <label for="">Semilla Maiz: {{ consumo_semilla_maiz }} </label><br>
            <label for="">Semilla Trigo: {{ consumo_semilla_trigo }} </label><br>
            <label for="">Bolsa Trigo: {{ consumo_bolsa_trigo }} </label><br>
            <label for="">Bolsa Maiz: {{ consumo_bolsa_maiz }} </label><br>
          </div>
        </div>
        <div class="row">
          <div class="col">
            <label for=""><h5>Estadistica</h5></label><br>
            <label for="">Energia: {{ restar(total_energia, consumo_energia) }} </label><br>
            <label for="">Agua: {{ restar(total_agua, consumo_agua) }} </label><br>
            <label for="">Maiz: {{ restar(total_maiz, consumo_maiz) }} </label><br>
            <label for="">Trigo: {{ restar(total_trigo, consumo_trigo) }} </label><br>
            <label for="">Bolsa de Maiz: {{ restar(total_bolsa_maiz, consumo_bolsa_maiz) }} </label><br>
            <label for="">Bolsa de Trigo: {{ restar(total_bolsa_trigo, consumo_bolsa_trigo) }} </label><br>
            <label for="">Leche: {{ total_leche }} </label><br>
            <label for="">Huevo: {{ total_huevo }} </label><br>
            <label for="">Madera: {{ restar(total_madera, consumo_madera) }} </label><br>
            <label for="">Carbon: {{ restar(total_carbon, consumo_carbon) }} </label><br>
            <label for="">KOD: {{ total_kod }} </label><br>
            <label for="">HUESO: {{ total_hueso }} </label><br>
          </div>
        </div>
      </div>

    </div>
  </div>

</template>


<script setup>
import {ref} from 'vue'

const pozo_agua = {
  nivel: {
    1: {
      produccion: 1,
      tiempo: 4,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    },
    2: {
      produccion: 1,
      tiempo: 3,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    },
    3: {
      produccion: 1,
      tiempo: 2,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    },
    4: {
      produccion: 1,
      tiempo: 1,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    }
  }
};

const fabrica_energia = {
  nivel: {
    1: {
      produccion: 1,
      tiempo: 4,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    },
    2: {
      produccion: 1,
      tiempo: 3,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    },
    3: {
      produccion: 1,
      tiempo: 2,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    },
    4: {
      produccion: 1,
      tiempo: 1,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    }
  }
};

const granja_gallinas = {
  nivel: {
    1: {
      produccion: 2,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 1,
        agua: 2,
      }
    },
    2: {
      produccion: 4,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 2,
        agua: 4,
      }
    },
    3: {
      produccion: 6,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 3,
        agua: 6,
      }
    },
    4: {
      produccion: 8,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 4,
        agua: 8,
      }
    }
  }
};

const granja_vacas = {
  nivel: {
    1: {
      produccion: 2,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 2,
        agua: 3,
      }
    },
    2: {
      produccion: 4,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 4,
        agua: 6,
      }
    },
    3: {
      produccion: 6,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 6,
        agua: 9,
      }
    },
    4: {
      produccion: 8,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 12,
        agua: 8,
      }
    }
  }
};

const tierra_maiz = {
  nivel: {
    1: {
      produccion: 5,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 1,
        agua: 4,

      },
    },
    2: {
      produccion: 10,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 2,
        agua: 8,
      },
    },
    3: {
      produccion: 15,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 3,
        agua: 12,
      },
    },
    4: {
      produccion: 20,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 4,
        agua: 16,
      },
    }
  }
};

const tierra_trigo = {
  nivel: {
    1: {
      produccion: 2,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 1,
        agua: 1,

      },
    },
    2: {
      produccion: 4,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 2,
        agua: 2,
      },
    },
    3: {
      produccion: 6,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 3,
        agua: 3,
      },
    },
    4: {
      produccion: 20,
      tiempo: 48,
      requerimiento: {
        semilla_trigo: 4,
        agua: 4,
      },
    }
  }
};

const arboles = {
  nivel: {
    1: {
      produccion: 5,
      tiempo: 72,
      requerimiento: {
        agua: 10,
      },
    },
    2: {
      produccion: 10,
      tiempo: 72,
      requerimiento: {
        agua: 20,
      }
    },
    3: {
      produccion: 15,
      tiempo: 72,
      requerimiento: {
        agua: 30,
      }
    },
    4: {
      produccion: 20,
      tiempo: 72,
      requerimiento: {
        agua: 40,
      }
    }

  }
};

const molino = {
  madera: {
    min: 2,
    max: 20,
    tiempo: 24,
    ratio: 8,
    fee: 1,
  },
  maiz: {
    min: 2,
    max: 20,
    tiempo: 72,
    ratio: 0.5,
    fee: 1,
  },
  trigo: {
    min: 1,
    max: 20,
    tiempo: 48,
    ratio: 1,
    fee: 1,
  },
  leche: {
    min: 4,
    max: 40,
    tiempo: 72,
    ratio: 2.5,
    fee: 1,
  },
  huevo: {
    min: 4,
    max: 40,
    tiempo: 72,
    ratio: 125,
    fee: 1,
  },
}


let nivel_pozo_agua = ref(1);
let horas_pozo_agua = ref(4);
let produccion_agua = ref(0);
let requerimiento_energia_pozo = ref(0);

let nivel_fabrica_energia = ref(1);
let horas_fabrica_energia = ref(4);
let produccion_energia = ref(0);
let requerimiento_carbon_fabrica = ref(0);

let nivel_tierra_maiz = ref(1);
let horas_tierra_maiz = ref(48);
let produccion_maiz = ref(0);
let requerimiento_semilla_maiz_tierra_maiz = ref(0);
let requerimiento_agua_tierra_maiz = ref(0);

let nivel_tierra_maiz_2 = ref(1);
let horas_tierra_maiz_2 = ref(48);
let produccion_maiz_2 = ref(0);
let requerimiento_semilla_maiz_tierra_maiz_2 = ref(0);
let requerimiento_agua_tierra_maiz_2 = ref(0);

let nivel_tierra_trigo = ref(1);
let horas_tierra_trigo = ref(24);
let produccion_trigo = ref(0);
let requerimiento_semilla_trigo_tierra_trigo = ref(0);
let requerimiento_agua_tierra_trigo = ref(0);

let nivel_tierra_trigo_2 = ref(1);
let horas_tierra_trigo_2 = ref(24);
let produccion_trigo_2 = ref(0);
let requerimiento_semilla_trigo_tierra_trigo_2 = ref(0);
let requerimiento_agua_tierra_trigo_2 = ref(0);

let nivel_granja_gallina = ref(1);
let horas_granja_gallina = ref(12);
let produccion_huevo = ref(0);
let requerimiento_bolsa_maiz_granja_gallina = ref(0);
let requerimiento_agua_granja_gallina = ref(0);

let nivel_granja_vacas = ref(1);
let horas_granja_vacas = ref(24);
let produccion_leche = ref(0);
let requerimiento_bolsa_trigo_granja_vaca = ref(0);
let requerimiento_agua_granja_vaca = ref(0);

let nivel_arboles = ref(1);
let horas_arboles = ref(72);
let produccion_madera = ref(0);
let requerimiento_agua_arboles = ref(0);

let nivel_arboles_2 = ref(1);
let horas_arboles_2 = ref(72);
let produccion_madera_2 = ref(0);
let requerimiento_agua_arboles_2 = ref(0);

let nivel_arboles_3 = ref(1);
let horas_arboles_3 = ref(72);
let produccion_madera_3 = ref(0);
let requerimiento_agua_arboles_3 = ref(0);

let molino_cant_madera = ref(2);
let produccion_carbon = ref(0)

let molino_cant_maiz = ref(2);
let produccion_bolsa_maiz = ref(0)

let molino_cant_trigo = ref(1);
let produccion_bolsa_trigo = ref(0)

let molino_cant_leche = ref(4);
let produccion_kod = ref(0)

let molino_cant_huevo = ref(4);
let produccion_hueso = ref(0)

let total_energia = ref(0)
let total_agua = ref(0)
let total_maiz = ref(0)
let total_trigo = ref(0)
let total_leche = ref(0)
let total_bolsa_maiz = ref(0)
let total_bolsa_trigo = ref(0)
let total_huevo = ref(0)
let total_madera = ref(0)
let total_carbon = ref(0)
let total_kod = ref(0)
let total_hueso = ref(0)


let consumo_energia = ref(0)
let consumo_agua = ref(0)
let consumo_semilla_maiz = ref(0)
let consumo_semilla_trigo = ref(0)
let consumo_maiz = ref(0)
let consumo_trigo = ref(0)
let consumo_bolsa_maiz = ref(0)
let consumo_bolsa_trigo = ref(0)
let consumo_leche = ref(0)
let consumo_huevo = ref(0)
let consumo_madera = ref(0)
let consumo_carbon = ref(0)

function calcular() {
  let agua = pozo_agua.nivel[nivel_pozo_agua.value];
  produccion_agua.value = (horas_pozo_agua.value <= 0) ? 0 : parseFloat(horas_pozo_agua.value) / (agua.tiempo * agua.produccion)
  requerimiento_energia_pozo.value = (horas_pozo_agua.value <= 0) ? 0 : parseFloat(horas_pozo_agua.value) / (agua.tiempo * agua.requerimiento.energia)

  let energia = fabrica_energia.nivel[nivel_fabrica_energia.value];
  produccion_energia.value = (horas_fabrica_energia.value <= 0) ? 0 : parseFloat(horas_fabrica_energia.value) / (energia.tiempo / energia.produccion)
  requerimiento_carbon_fabrica.value = (horas_fabrica_energia.value <= 0) ? 0 : parseFloat(horas_fabrica_energia.value) / (energia.tiempo / energia.requerimiento.carbon)

  let maiz = tierra_maiz.nivel[nivel_tierra_maiz.value];
  produccion_maiz.value = (horas_tierra_maiz.value <= 0) ? 0 : parseFloat(horas_tierra_maiz.value) / (maiz.tiempo / maiz.produccion)
  requerimiento_semilla_maiz_tierra_maiz.value = (horas_tierra_maiz.value <= 0) ? 0 : parseFloat(horas_tierra_maiz.value) / (maiz.tiempo / maiz.requerimiento.semilla_maiz)
  requerimiento_agua_tierra_maiz.value = (horas_tierra_maiz.value <= 0) ? 0 : parseFloat(horas_tierra_maiz.value) / (maiz.tiempo / maiz.requerimiento.agua)

  console.log(requerimiento_semilla_maiz_tierra_maiz.value,maiz);

  let maiz_2 = tierra_maiz.nivel[nivel_tierra_maiz_2.value];
  produccion_maiz_2.value = (horas_tierra_maiz_2.value <= 0) ? 0 : parseFloat(horas_tierra_maiz_2.value) / (maiz_2.tiempo / maiz_2.produccion)
  requerimiento_semilla_maiz_tierra_maiz_2.value = (horas_tierra_maiz_2.value <= 0) ? 0 : parseFloat(horas_tierra_maiz_2.value) / (maiz_2.tiempo / maiz_2.requerimiento.semilla_maiz)
  requerimiento_agua_tierra_maiz_2.value = (horas_tierra_maiz_2.value <= 0) ? 0 : parseFloat(horas_tierra_maiz_2.value) / (maiz_2.tiempo / maiz_2.requerimiento.agua)

  let trigo = tierra_trigo.nivel[nivel_tierra_trigo.value];
  produccion_trigo.value = (horas_tierra_trigo.value <= 0) ? 0 : parseFloat(horas_tierra_trigo.value) / (trigo.tiempo / trigo.produccion)
  requerimiento_semilla_trigo_tierra_trigo.value = (horas_tierra_trigo.value <= 0) ? 0 : parseFloat(horas_tierra_trigo.value) / (trigo.tiempo / trigo.requerimiento.semilla_trigo)
  requerimiento_agua_tierra_trigo.value = (horas_tierra_trigo.value <= 0) ? 0 : parseFloat(horas_tierra_trigo.value) / (trigo.tiempo / trigo.requerimiento.agua)

  let trigo_2 = tierra_trigo.nivel[nivel_tierra_trigo_2.value];
  produccion_trigo_2.value = (horas_tierra_trigo_2.value <= 0) ? 0 : parseFloat(horas_tierra_trigo_2.value) / (trigo_2.tiempo / trigo_2.produccion)
  requerimiento_semilla_trigo_tierra_trigo_2.value = (horas_tierra_trigo_2.value <= 0) ? 0 : parseFloat(horas_tierra_trigo_2.value) / (trigo_2.tiempo / trigo_2.requerimiento.semilla_trigo)
  requerimiento_agua_tierra_trigo_2.value = (horas_tierra_trigo_2.value <= 0) ? 0 : parseFloat(horas_tierra_trigo_2.value) / (trigo_2.tiempo / trigo_2.requerimiento.agua)


  let huevo = granja_gallinas.nivel[nivel_granja_gallina.value];
  produccion_huevo.value = (horas_granja_gallina.value <= 0) ? 0 : parseFloat(horas_granja_gallina.value) / (huevo.tiempo / huevo.produccion)
  requerimiento_bolsa_maiz_granja_gallina.value = (horas_granja_gallina.value <= 0) ? 0 : parseFloat(horas_granja_gallina.value) / (huevo.tiempo / huevo.requerimiento.bolsa_maiz)
  requerimiento_agua_granja_gallina.value = (horas_granja_gallina.value <= 0) ? 0 : parseFloat(horas_granja_gallina.value) / (huevo.tiempo / huevo.requerimiento.agua)

  let leche = granja_vacas.nivel[nivel_granja_vacas.value];
  produccion_leche.value = (horas_granja_vacas.value <= 0) ? 0 : parseFloat(horas_granja_vacas.value) / (leche.tiempo / leche.produccion)
  requerimiento_bolsa_trigo_granja_vaca.value = (horas_granja_vacas.value <= 0) ? 0 : parseFloat(horas_granja_vacas.value) / (leche.tiempo / leche.requerimiento.bolsa_trigo)
  requerimiento_agua_granja_vaca.value = (horas_granja_vacas.value <= 0) ? 0 : parseFloat(horas_granja_vacas.value) / (leche.tiempo / leche.requerimiento.agua)

  let madera = arboles.nivel[nivel_arboles.value];
  produccion_madera.value = (horas_arboles.value <= 0) ? 0 : parseFloat(horas_arboles.value) / (madera.tiempo / madera.produccion)
  requerimiento_agua_arboles.value = (horas_arboles.value <= 0) ? 0 : parseFloat(horas_arboles.value) / (madera.tiempo / madera.requerimiento.agua)

  let madera_2 = arboles.nivel[nivel_arboles_2.value];
  produccion_madera_2.value = (horas_arboles_2.value <= 0) ? 0 : parseFloat(horas_arboles_2.value) / (madera_2.tiempo / madera_2.produccion)
  requerimiento_agua_arboles_2.value = (horas_arboles_2.value <= 0) ? 0 : parseFloat(horas_arboles_2.value) / (madera_2.tiempo / madera_2.requerimiento.agua)

  let madera_3 = arboles.nivel[nivel_arboles_3.value];
  produccion_madera_3.value = (horas_arboles_3.value <= 0) ? 0 : parseFloat(horas_arboles_3.value) / (madera_3.tiempo / madera_3.produccion)
  requerimiento_agua_arboles_3.value = (horas_arboles_3.value <= 0) ? 0 : parseFloat(horas_arboles_3.value) / (madera_3.tiempo / madera_3.requerimiento.agua)

  let carbon = molino.madera;
  produccion_carbon.value = carbon.ratio * molino_cant_madera.value;

  let bolsa_maiz = molino.maiz;
  produccion_bolsa_maiz.value = bolsa_maiz.ratio * molino_cant_maiz.value;

  let bolsa_trigo = molino.trigo;
  produccion_bolsa_trigo.value = bolsa_trigo.ratio * molino_cant_trigo.value;

  let kod = molino.leche;
  produccion_kod.value = kod.ratio * molino_cant_leche.value;

  let hueso = molino.huevo;
  produccion_hueso.value = hueso.ratio * molino_cant_huevo.value;

  total_energia.value = produccion_energia.value;
  total_agua.value = produccion_agua.value;
  total_maiz.value = produccion_maiz.value + produccion_maiz_2.value;
  total_trigo.value = produccion_trigo.value + produccion_trigo_2.value;
  total_bolsa_maiz.value = produccion_bolsa_maiz.value;
  total_bolsa_trigo.value = produccion_bolsa_trigo.value;
  total_huevo.value = produccion_huevo.value;
  total_leche.value = produccion_leche.value;
  total_madera.value = produccion_madera.value + produccion_madera_2.value + produccion_madera_3.value;
  total_carbon.value = produccion_carbon.value;
  total_kod.value = produccion_kod.value;
  total_hueso.value = produccion_hueso.value

  consumo_energia.value = requerimiento_energia_pozo.value;
  consumo_agua.value = requerimiento_agua_tierra_maiz.value + requerimiento_agua_tierra_maiz_2.value
      + requerimiento_agua_tierra_trigo.value + requerimiento_agua_tierra_trigo_2.value
      + requerimiento_agua_granja_gallina.value + requerimiento_agua_granja_vaca.value
      + requerimiento_agua_arboles.value + requerimiento_agua_arboles_2.value + requerimiento_agua_arboles_3.value;
  consumo_semilla_maiz.value = requerimiento_semilla_maiz_tierra_maiz.value + requerimiento_semilla_maiz_tierra_maiz_2.value;
  consumo_semilla_trigo.value = requerimiento_semilla_trigo_tierra_trigo.value + requerimiento_semilla_trigo_tierra_trigo_2.value;
  consumo_bolsa_trigo.value = requerimiento_bolsa_trigo_granja_vaca.value;
  consumo_bolsa_maiz.value = requerimiento_bolsa_maiz_granja_gallina.value;
  consumo_madera.value = molino_cant_madera.value;
  consumo_carbon.value = requerimiento_carbon_fabrica.value;
}

function restar(a, b) {
  return a - b
}


</script>

<style>

body {
  background: #a18262 !important;
}
</style>
