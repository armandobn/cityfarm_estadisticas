<template>
  <br>
  <div class="container">
    <div class="row">
      <div class="col-10"></div>

    </div>

    <div class="row">
      <div class="col-md-4">
        <button class="btn btn-with-background" @click="calcular()">Calcular</button>
      </div>
      <div class="col-md-4 ms-auto"><a class=" btn-with-background" href="https://stream.hivelive.me/donate/misticogama"
                                       style="color: #7205ee; text-decoration: none;" target="_blank">Donaciones</a>
      </div>
    </div>


    <h5 class="text-with-shadown">Estadistica</h5>
    <div class="row  text-with-shadown">
      <div class="col">
        <RecursoComponent :src="'assets/energia.png'"
                          :width="9"
                          :cantidad="restar(total_energia, consumo_energia)"></RecursoComponent>
        <RecursoComponent :src="'assets/agua.png'"
                          :width="10"
                          :cantidad="restar(total_agua, consumo_agua)"></RecursoComponent>
        <RecursoComponent :src="'assets/madera.png'"
                          :width="10"
                          :cantidad="restar(total_madera, consumo_madera)"></RecursoComponent>
        <RecursoComponent :src="'assets/carbon.png'"
                          :width="10"
                          :cantidad="restar(total_carbon, consumo_carbon)"></RecursoComponent>
      </div>
      <div class="col">
        <RecursoComponent :src="'assets/maiz.png'"
                          :width="9"
                          :cantidad="restar(total_maiz, consumo_maiz)"></RecursoComponent>
        <RecursoComponent :src="'assets/trigo.png'"
                          :width="9"
                          :cantidad="restar(total_trigo, consumo_trigo)"></RecursoComponent>
        <RecursoComponent :src="'assets/bolsa_maiz.png'"
                          :width="9"
                          :cantidad="restar(total_bolsa_maiz, consumo_bolsa_maiz)"></RecursoComponent>
        <RecursoComponent :src="'assets/bolsa_trigo.png'"
                          :width="9"
                          :cantidad="restar(total_bolsa_trigo, consumo_bolsa_trigo)"></RecursoComponent>
      </div>
      <div class="col">
        <RecursoComponent :src="'assets/leche.png'"
                          :width="10"
                          :cantidad="restar(total_leche,consumo_leche)"></RecursoComponent>
        <RecursoComponent :src="'assets/huevo.png'"
                          :width="10"
                          :cantidad="restar(total_huevo,consumo_huevo)"></RecursoComponent>
        <RecursoComponent :src="'assets/kod.png'"
                          :width="9"
                          :cantidad="total_kod"></RecursoComponent>
        <RecursoComponent :src="'assets/hueso.png'"
                          :width="9"
                          :cantidad="total_hueso"></RecursoComponent>
      </div>
      <div class="col">
        <RecursoComponent :src="'assets/semilla_trigo.png'"
                          :width="10"
                          :cantidad="consumo_semilla_trigo"></RecursoComponent>
        <RecursoComponent :src="'assets/semilla_maiz.png'"
                          :width="10"
                          :cantidad="consumo_semilla_maiz"></RecursoComponent>

      </div>
    </div>

    <div class="row  text-with-shadown">
      <div class="col">
        <p>

          <button class="btn btn-with-background" data-bs-toggle="collapse" href="#collapseExample" role="button"
                  aria-expanded="false"
                  aria-controls="collapseExample">
            Produccion Total
          </button>
          <button class="btn btn-with-background" data-bs-toggle="collapse" href="#collapseObtenido" role="button"
                  aria-expanded="false"
                  aria-controls="collapseExample">
            Obtencion Invidividual
          </button>

        </p>
        <div class="collapse caja-cafe" id="collapseExample">
          <div class="card card-body relleno-cafe">
            <div class="row">
              <div class="col">
                <h5>Produccion Total</h5>
                <div class="row">
                  <div class="col">
                    <RecursoComponent :src="'assets/energia.png'"
                                      :width="10"
                                      :cantidad="total_energia"></RecursoComponent>
                    <RecursoComponent :src="'assets/agua.png'"
                                      :width="10"
                                      :cantidad="total_agua"></RecursoComponent>
                    <RecursoComponent :src="'assets/madera.png'"
                                      :width="10"
                                      :cantidad="total_madera"></RecursoComponent>
                    <RecursoComponent :src="'assets/carbon.png'"
                                      :width="10"
                                      :cantidad="total_carbon"></RecursoComponent>
                  </div>
                  <div class="col">
                    <RecursoComponent :src="'assets/maiz.png'"
                                      :width="10"
                                      :cantidad="total_maiz"></RecursoComponent>
                    <RecursoComponent :src="'assets/trigo.png'"
                                      :width="10"
                                      :cantidad="total_trigo"></RecursoComponent>
                    <RecursoComponent :src="'assets/bolsa_maiz.png'"
                                      :width="10"
                                      :cantidad="total_bolsa_maiz"></RecursoComponent>
                    <RecursoComponent :src="'assets/bolsa_trigo.png'"
                                      :width="10"
                                      :cantidad="total_bolsa_trigo"></RecursoComponent>
                  </div>
                  <div class="col">
                    <RecursoComponent :src="'assets/leche.png'"
                                      :width="10"
                                      :cantidad="total_leche"></RecursoComponent>
                    <RecursoComponent :src="'assets/huevo.png'"
                                      :width="10"
                                      :cantidad="total_huevo"></RecursoComponent>
                    <RecursoComponent :src="'assets/kod.png'"
                                      :width="10"
                                      :cantidad="total_kod"></RecursoComponent>
                    <RecursoComponent :src="'assets/hueso.png'"
                                      :width="10"
                                      :cantidad="total_hueso"></RecursoComponent>
                  </div>
                </div>

              </div>
              <div class="col">
                <h5>Consumo Total</h5>
                <div class="row">
                  <div class="col">
                    <RecursoComponent :src="'assets/energia.png'"
                                      :width="10"
                                      :cantidad="consumo_energia"></RecursoComponent>
                    <RecursoComponent :src="'assets/agua.png'"
                                      :width="10"
                                      :cantidad="consumo_agua"></RecursoComponent>
                    <RecursoComponent :src="'assets/madera.png'"
                                      :width="10"
                                      :cantidad="consumo_madera"></RecursoComponent>
                    <RecursoComponent :src="'assets/carbon.png'"
                                      :width="10"
                                      :cantidad="consumo_carbon"></RecursoComponent>

                  </div>
                  <div class="col">
                    <RecursoComponent :src="'assets/maiz.png'"
                                      :width="10"
                                      :cantidad="consumo_maiz"></RecursoComponent>
                    <RecursoComponent :src="'assets/trigo.png'"
                                      :width="10"
                                      :cantidad="consumo_trigo"></RecursoComponent>
                    <RecursoComponent :src="'assets/bolsa_maiz.png'"
                                      :width="10"
                                      :cantidad="consumo_bolsa_trigo"></RecursoComponent>
                    <RecursoComponent :src="'assets/bolsa_trigo.png'"
                                      :width="10"
                                      :cantidad="consumo_bolsa_maiz"></RecursoComponent>
                  </div>
                  <div class="col">
                    <RecursoComponent :src="'assets/semilla_trigo.png'"
                                      :width="10"
                                      :cantidad="consumo_semilla_trigo"></RecursoComponent>
                    <RecursoComponent :src="'assets/semilla_maiz.png'"
                                      :width="10"
                                      :cantidad="consumo_semilla_maiz"></RecursoComponent>
                    <RecursoComponent :src="'assets/leche.png'"
                                      :width="10"
                                      :cantidad="consumo_leche"></RecursoComponent>
                    <RecursoComponent :src="'assets/huevo.png'"
                                      :width="10"
                                      :cantidad="consumo_huevo"></RecursoComponent>
                  </div>
                </div>

              </div>
            </div>
          </div>
        </div>
        <div class="collapse caja-cafe" id="collapseObtenido">
          <div class="card card-body relleno-cafe ">
            <div class="row">
              <h3>Obtencion Individual</h3>

              <div class="row">
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Pozo de Agua'" :src-produccion="'assets/agua.png'"
                                             :src-consume="'assets/energia.png'" :produccion="produccion_agua"
                                             :consume2="0"
                                             :consume="requerimiento_energia_pozo"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Fabrica Energia'" :src-produccion="'assets/energia.png'"
                                             :src-consume="'assets/carbon.png'" :produccion="produccion_energia"
                                             :consume2="0"
                                             :consume="requerimiento_carbon_fabrica"></ObtencionRecursoComponent>
                </div>

                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Molino Leche'" :src-produccion="'assets/kod.png'"
                                             :src-consume="'assets/leche.png'" :produccion="total_kod"
                                             :consume2="0"
                                             :consume="consumo_leche"></ObtencionRecursoComponent>
                </div>

                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Molino Huevo'" :src-produccion="'assets/hueso.png'"
                                             :src-consume="'assets/huevo.png'" :produccion="total_hueso"
                                             :consume2="0"
                                             :consume="consumo_huevo"></ObtencionRecursoComponent>
                </div>

              </div>

              <div class="row">
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Tierra Trigo'"
                                             :src-produccion="'assets/trigo.png'" :src-consume="'assets/agua.png'"
                                             :produccion=" produccion_trigo + produccion_trigo_2"
                                             :consume="requerimiento_agua_tierra_trigo + requerimiento_agua_tierra_trigo_2"
                                             :otro-rercuso="true"
                                             :consume2="requerimiento_semilla_trigo_tierra_trigo + requerimiento_semilla_trigo_tierra_trigo_2"
                                             :src-consume2="'assets/semilla_trigo.png'"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Tierra Maiz'"
                                             :src-produccion="'assets/maiz.png'" :src-consume="'assets/agua.png'"
                                             :produccion="  produccion_maiz + produccion_maiz_2"
                                             :consume="requerimiento_agua_tierra_maiz + requerimiento_agua_tierra_maiz_2"
                                             :otro-rercuso="true"
                                             :consume2=" requerimiento_semilla_maiz_tierra_maiz + requerimiento_semilla_maiz_tierra_maiz_2"
                                             :src-consume2="'assets/semilla_maiz.png'"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Granja Gallina'"
                                             :src-produccion="'assets/huevo.png'" :src-consume="'assets/agua.png'"
                                             :produccion=" produccion_huevo"
                                             :consume="requerimiento_agua_granja_gallina"
                                             :otro-rercuso="true"
                                             :consume2=" requerimiento_bolsa_maiz_granja_gallina"
                                             :src-consume2="'assets/bolsa_maiz.png'"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Granja Vacas'"
                                             :src-produccion="'assets/leche.png'" :src-consume="'assets/agua.png'"
                                             :produccion=" produccion_leche"
                                             :consume="requerimiento_agua_granja_vaca"
                                             :otro-rercuso="true"
                                             :consume2=" requerimiento_bolsa_trigo_granja_vaca"
                                             :src-consume2="'assets/bolsa_trigo.png'"></ObtencionRecursoComponent>
                </div>

              </div>

              <div class="row">
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Molino Arboles'"
                                             :src-produccion="'assets/madera.png'"
                                             :produccion=" produccion_madera + produccion_madera_2 + produccion_madera_3"
                                             :src-consume="'assets/agua.png'"
                                             :consume2="0"
                                             :consume="requerimiento_agua_arboles + requerimiento_agua_arboles_2 + requerimiento_agua_arboles_3"
                                             :otro-rercuso="false"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Molino Madera'"
                                             :src-produccion="'assets/carbon.png'"
                                             :produccion=" produccion_carbon"
                                             :src-consume="'assets/madera.png'"
                                             :consume="molino_cant_madera"
                                             :consume2="0"
                                             :otro-rercuso="false"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Molino Maiz'"
                                             :src-produccion="'assets/bolsa_maiz.png'"
                                             :produccion=" produccion_bolsa_maiz"
                                             :src-consume="'assets/maiz.png'"
                                             :consume="molino_cant_maiz"
                                             :consume2="0"
                                             :otro-rercuso="false"></ObtencionRecursoComponent>
                </div>
                <div class="col-3">
                  <ObtencionRecursoComponent :titulo="'Molino Trigo'"
                                             :src-produccion="'assets/bolsa_maiz.png'"
                                             :produccion=" produccion_bolsa_trigo"
                                             :src-consume="'assets/trigo.png'"
                                             :consume="molino_cant_trigo"
                                             :consume2="0"
                                             :otro-rercuso="false"></ObtencionRecursoComponent>
                </div>
              </div>


            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col">


        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Pozo &nbsp &nbsp de &nbsp &nbsp Agua</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_pozo_agua" role="switch">
              <label class="form-check-label" for="pozo_agua"></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" id="floatingSelect" aria-label="Floating label select example"
                  v-model="nivel_pozo_agua"
                  :disabled="!checked_pozo_agua"
                  @change="onChange($event,'pozo_agua')">
            <option v-for="option in pozo_agua.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>

        <div class="form-floating mb-3 mt-3">
          <input type="number" class="form-control" id="floatingInput" placeholder="name@example.com"
                 :disabled="!checked_pozo_agua"
                 v-model="horas_pozo_agua">
          <label for="floatingInput">Horas</label>
        </div>
      </div>

      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Fabrica de Energia</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_fabrica_energia" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>


        <div class="form-floating">
          <select class="form-select" v-model="nivel_fabrica_energia" :disabled="!checked_fabrica_energia"
                  @change="onChange($event,'fabrica_energia')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in fabrica_energia.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>


        <div class="form-floating mb-3 mt-3">
          <input type="number" class="form-control" id="floatingInput" placeholder="name@example.com"
                 :disabled="!checked_fabrica_energia"
                 v-model="horas_fabrica_energia">
          <label for="floatingInput">Horas</label>
        </div>

      </div>
      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Granja de Gallinas</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_granja_gallinas" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_granja_gallina" :disabled="!checked_granja_gallinas"
                  @change="onChange($event,'granja_gallinas')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in granja_gallinas.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>

        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_granja_gallina"
                 :disabled="!checked_granja_gallinas"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Horas</label>
        </div>


      </div>
      <div class="col">


        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Granja &nbsp de &nbsp Vacas</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_granja_vacas" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_granja_vacas" :disabled="!checked_granja_vacas"
                  @change="onChange($event,'granja_vacas')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in granja_vacas.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>

        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_granja_vacas"
                 :disabled="!checked_granja_vacas"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Horas</label>
        </div>


      </div>
    </div>

    <div class="row">
      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Tierra Trigo</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_tierra_trigo_1" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>


        <div class="form-floating">
          <select class="form-select" v-model="nivel_tierra_trigo" :disabled="!checked_tierra_trigo_1"
                  @change="onChange($event,'tierra_trigo_1')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in tierra_trigo.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>


        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_tierra_trigo"
                 :disabled="!checked_tierra_trigo_1"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Horas</label>
        </div>


      </div>
      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Tierra Trigo</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_tierra_trigo_2" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>


        <div class="form-floating">
          <select class="form-select" v-model="nivel_tierra_trigo_2" :disabled="!checked_tierra_trigo_2"
                  @change="onChange($event,'tierra_trigo_2')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in tierra_trigo.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>
        <div class="form-floating mb-3  mt-3">
          <input type="number" v-model="horas_tierra_trigo_2"
                 :disabled="!checked_tierra_trigo_2"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Horas</label>
        </div>


      </div>
      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Tierra Maiz</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_tierra_maiz_1" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <div class="form-floating">
          <select class="form-select" v-model="nivel_tierra_maiz" :disabled="!checked_tierra_maiz_1"
                  @change="onChange($event,'tierra_maiz_1')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in tierra_maiz.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>
        <div class="form-floating mb-3  mt-3">
          <input type="number" v-model="horas_tierra_maiz"
                 :disabled="!checked_tierra_maiz_1"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Horas</label>
        </div>


      </div>
      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Tierra Maiz</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_tierra_maiz_2" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <div class="form-floating">
          <select class="form-select" v-model="nivel_tierra_maiz_2" :disabled="!checked_tierra_maiz_2"
                  @change="onChange($event,'tierra_maiz_2')"
                  id="floatingSelect" aria-label="Floating label select example">
            <option v-for="option in tierra_maiz.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>
        <div class="form-floating mb-3  mt-3">
          <input type="number" v-model="horas_tierra_maiz_2"
                 :disabled="!checked_tierra_maiz_2"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Horas</label>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Arboles</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_arboles_1" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_arboles" :disabled="!checked_arboles_1"
                  @change="onChange($event,'arboles_1')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in arboles.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>
        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_arboles"
                 :disabled="!checked_arboles_1"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Horas</label>
        </div>

      </div>

      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Arboles</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_arboles_2" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_arboles_2" :disabled="!checked_arboles_2"
                  @change="onChange($event,'arboles_2')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in arboles.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>
        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_arboles_2"
                 :disabled="!checked_arboles_2"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Horas</label>
        </div>
      </div>

      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Arboles</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_arboles_3" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <div class="form-floating">
          <select class="form-select" v-model="nivel_arboles_3" :disabled="!checked_arboles_3"
                  @change="onChange($event,'arboles_3')"
                  id="floatingSelect"
                  aria-label="Floating label select example">
            <option v-for="option in arboles.nivel" v-bind:value="option.nivel">
              {{ option.nivel }}
            </option>
          </select>
          <label for="floatingSelect">Nivel</label>
        </div>

        <div class="form-floating mb-3 mt-3">
          <input type="number" v-model="horas_arboles_3"
                 :disabled="!checked_arboles_3"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Horas</label>
        </div>

      </div>
    </div>

    <div class="row text-center">
      <h2 class="text-with-shadown">MOLINO</h2>
      <div class="col">


        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Madera</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_madera" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <label class="text-with-shadown">{{ molino.madera.tiempo }} horas</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_madera"
                 :disabled="!checked_molino_madera"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Cantidad</label>
        </div>
      </div>
      <div class="col">


        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Maiz</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_maiz" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <label class="text-with-shadown">{{ molino.maiz.tiempo }} horas</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_maiz"
                 :disabled="!checked_molino_maiz"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Cantidad</label>
        </div>
      </div>

      <div class="col">
        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Trigo</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_trigo" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>

        <label class="text-with-shadown">{{ molino.trigo.tiempo }} horas</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_trigo"
                 :disabled="!checked_molino_trigo"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Cantidad</label>
        </div>
      </div>

      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Leche</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_leche" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <label class="text-with-shadown">{{ molino.leche.tiempo }} horas</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_leche"
                 :disabled="!checked_molino_leche"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Cantidad</label>
        </div>
      </div>
      <div class="col">

        <div class="d-flex bd-highlight ">
          <div class="me-auto p-2 bd-highlight text-with-shadown"><h3>Huevo</h3></div>
          <div class="p-2 bd-highlight">
            <div class="form-check form-switch">
              <input class="form-check-input" type="checkbox" v-model="checked_molino_huevo" role="switch">
              <label class="form-check-label" for=""></label>
            </div>
          </div>
        </div>
        <label class="text-with-shadown">{{ molino.huevo.tiempo }} horas</label>
        <div class="form-floating mb-3">
          <input type="number" v-model="molino_cant_huevo"
                 :disabled="!checked_molino_huevo"
                 class="form-control" id="floatingInput"
                 placeholder="name@example.com">
          <label for="floatingInput">Cantidad</label>
        </div>
      </div>
    </div>

  </div>

</template>


<script setup>
import {ref, computed} from 'vue'
import RecursoComponent from "../components/RecursoComponent.vue";
import ObtencionRecursoComponent from "../components/ObtencionRecursoComponent.vue";

const pozo_agua = {
  nivel: {
    1: {
      nivel: 1,
      produccion: 1,
      tiempo: 4,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    },
    2: {
      nivel: 2,
      produccion: 1,
      tiempo: 3,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    },
    3: {
      nivel: 3,
      produccion: 1,
      tiempo: 2,
      requerimiento: {
        energia: 1,
      },
      almacenamiento: 8
    },
    4: {
      nivel: 4,
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
      nivel: 1,
      produccion: 1,
      tiempo: 4,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    },
    2: {
      nivel: 2,
      produccion: 1,
      tiempo: 3,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    },
    3: {
      nivel: 3,
      produccion: 1,
      tiempo: 2,
      requerimiento: {
        carbon: 2,
      },
      almacenamiento: 8
    },
    4: {
      nivel: 4,
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
      nivel: 1,
      produccion: 2,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 1,
        agua: 2,
      }
    },
    2: {
      nivel: 2,
      produccion: 4,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 2,
        agua: 4,
      }
    },
    3: {
      nivel: 3,
      produccion: 6,
      tiempo: 12,
      requerimiento: {
        bolsa_maiz: 3,
        agua: 6,
      }
    },
    4: {
      nivel: 4,
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
      nivel: 1,
      produccion: 2,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 2,
        agua: 3,
      }
    },
    2: {
      nivel: 2,
      produccion: 4,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 4,
        agua: 6,
      }
    },
    3: {
      nivel: 3,
      produccion: 6,
      tiempo: 24,
      requerimiento: {
        bolsa_trigo: 6,
        agua: 9,
      }
    },
    4: {
      nivel: 4,
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
      nivel: 1,
      produccion: 5,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 1,
        agua: 4,

      },
    },
    2: {
      nivel: 2,
      produccion: 10,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 2,
        agua: 8,
      },
    },
    3: {
      nivel: 3,
      produccion: 15,
      tiempo: 48,
      requerimiento: {
        semilla_maiz: 3,
        agua: 12,
      },
    },
    4: {
      nivel: 4,
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
      nivel: 1,
      produccion: 2,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 1,
        agua: 1,

      },
    },
    2: {
      nivel: 2,
      produccion: 4,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 2,
        agua: 2,
      },
    },
    3: {
      nivel: 3,
      produccion: 6,
      tiempo: 24,
      requerimiento: {
        semilla_trigo: 3,
        agua: 3,
      },
    },
    4: {
      nivel: 4,
      produccion: 20,
      tiempo: 24,
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
      nivel: 1,
      produccion: 5,
      tiempo: 72,
      requerimiento: {
        agua: 10,
      },
    },
    2: {
      nivel: 2,
      produccion: 10,
      tiempo: 72,
      requerimiento: {
        agua: 20,
      }
    },
    3: {
      nivel: 3,
      produccion: 15,
      tiempo: 72,
      requerimiento: {
        agua: 30,
      }
    },
    4: {
      nivel: 4,
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

let molino_cant_madera = ref(0);
let produccion_carbon = ref(0)

let molino_cant_maiz = ref(0);
let produccion_bolsa_maiz = ref(0)

let molino_cant_trigo = ref(0);
let produccion_bolsa_trigo = ref(0)

let molino_cant_leche = ref(0);
let produccion_kod = ref(0)

let molino_cant_huevo = ref(0);
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

let checked_pozo_agua = ref(false);
let checked_fabrica_energia = ref(false);
let checked_tierra_trigo_1 = ref(false);
let checked_tierra_trigo_2 = ref(false);
let checked_tierra_maiz_1 = ref(false);
let checked_tierra_maiz_2 = ref(false);
let checked_granja_gallinas = ref(false);
let checked_granja_vacas = ref(false);
let checked_arboles_1 = ref(false);
let checked_arboles_2 = ref(false);
let checked_arboles_3 = ref(false);
let checked_molino_madera = ref(false);
let checked_molino_maiz = ref(false);
let checked_molino_trigo = ref(false);
let checked_molino_leche = ref(false);
let checked_molino_huevo = ref(false);

function calcular() {

  let agua = pozo_agua.nivel[nivel_pozo_agua.value];
  produccion_agua.value = (horas_pozo_agua.value <= 0 || !checked_pozo_agua.value) ? 0 : parseFloat(horas_pozo_agua.value) / (agua.tiempo * agua.produccion)
  requerimiento_energia_pozo.value = (horas_pozo_agua.value <= 0 || !checked_pozo_agua.value) ? 0 : parseFloat(horas_pozo_agua.value) / (agua.tiempo * agua.requerimiento.energia)

  let energia = fabrica_energia.nivel[nivel_fabrica_energia.value];
  produccion_energia.value = (horas_fabrica_energia.value <= 0 || !checked_fabrica_energia.value) ? 0 : parseFloat(horas_fabrica_energia.value) / (energia.tiempo / energia.produccion)
  requerimiento_carbon_fabrica.value = (horas_fabrica_energia.value <= 0 || !checked_fabrica_energia.value) ? 0 : parseFloat(horas_fabrica_energia.value) / (energia.tiempo / energia.requerimiento.carbon)

  let maiz = tierra_maiz.nivel[nivel_tierra_maiz.value];
  produccion_maiz.value = (horas_tierra_maiz.value <= 0 || !checked_tierra_maiz_1.value) ? 0 : parseFloat(horas_tierra_maiz.value) / (maiz.tiempo / maiz.produccion)
  requerimiento_semilla_maiz_tierra_maiz.value = (horas_tierra_maiz.value <= 0 || !checked_tierra_maiz_1.value) ? 0 : parseFloat(horas_tierra_maiz.value) / (maiz.tiempo / maiz.requerimiento.semilla_maiz)
  requerimiento_agua_tierra_maiz.value = (horas_tierra_maiz.value <= 0 || !checked_tierra_maiz_1.value) ? 0 : parseFloat(horas_tierra_maiz.value) / (maiz.tiempo / maiz.requerimiento.agua)

  let maiz_2 = tierra_maiz.nivel[nivel_tierra_maiz_2.value];
  produccion_maiz_2.value = (horas_tierra_maiz_2.value <= 0 || !checked_tierra_maiz_2.value) ? 0 : parseFloat(horas_tierra_maiz_2.value) / (maiz_2.tiempo / maiz_2.produccion)
  requerimiento_semilla_maiz_tierra_maiz_2.value = (horas_tierra_maiz_2.value <= 0 || !checked_tierra_maiz_2.value) ? 0 : parseFloat(horas_tierra_maiz_2.value) / (maiz_2.tiempo / maiz_2.requerimiento.semilla_maiz)
  requerimiento_agua_tierra_maiz_2.value = (horas_tierra_maiz_2.value <= 0 || !checked_tierra_maiz_2.value) ? 0 : parseFloat(horas_tierra_maiz_2.value) / (maiz_2.tiempo / maiz_2.requerimiento.agua)

  let trigo = tierra_trigo.nivel[nivel_tierra_trigo.value];
  produccion_trigo.value = (horas_tierra_trigo.value <= 0 || !checked_tierra_trigo_1.value) ? 0 : parseFloat(horas_tierra_trigo.value) / (trigo.tiempo / trigo.produccion)
  requerimiento_semilla_trigo_tierra_trigo.value = (horas_tierra_trigo.value <= 0 || !checked_tierra_trigo_1.value) ? 0 : parseFloat(horas_tierra_trigo.value) / (trigo.tiempo / trigo.requerimiento.semilla_trigo)
  requerimiento_agua_tierra_trigo.value = (horas_tierra_trigo.value <= 0 || !checked_tierra_trigo_1.value) ? 0 : parseFloat(horas_tierra_trigo.value) / (trigo.tiempo / trigo.requerimiento.agua)

  let trigo_2 = tierra_trigo.nivel[nivel_tierra_trigo_2.value];
  produccion_trigo_2.value = (horas_tierra_trigo_2.value <= 0 || !checked_tierra_trigo_2.value) ? 0 : parseFloat(horas_tierra_trigo_2.value) / (trigo_2.tiempo / trigo_2.produccion)
  requerimiento_semilla_trigo_tierra_trigo_2.value = (horas_tierra_trigo_2.value <= 0 || !checked_tierra_trigo_2.value) ? 0 : parseFloat(horas_tierra_trigo_2.value) / (trigo_2.tiempo / trigo_2.requerimiento.semilla_trigo)
  requerimiento_agua_tierra_trigo_2.value = (horas_tierra_trigo_2.value <= 0 || !checked_tierra_trigo_2.value) ? 0 : parseFloat(horas_tierra_trigo_2.value) / (trigo_2.tiempo / trigo_2.requerimiento.agua)


  let huevo = granja_gallinas.nivel[nivel_granja_gallina.value];
  produccion_huevo.value = (horas_granja_gallina.value <= 0 || !checked_granja_gallinas.value) ? 0 : parseFloat(horas_granja_gallina.value) / (huevo.tiempo / huevo.produccion)
  requerimiento_bolsa_maiz_granja_gallina.value = (horas_granja_gallina.value <= 0 || !checked_granja_gallinas.value) ? 0 : parseFloat(horas_granja_gallina.value) / (huevo.tiempo / huevo.requerimiento.bolsa_maiz)
  requerimiento_agua_granja_gallina.value = (horas_granja_gallina.value <= 0 || !checked_granja_gallinas.value) ? 0 : parseFloat(horas_granja_gallina.value) / (huevo.tiempo / huevo.requerimiento.agua)

  let leche = granja_vacas.nivel[nivel_granja_vacas.value];
  produccion_leche.value = (horas_granja_vacas.value <= 0 || !checked_granja_vacas.value) ? 0 : parseFloat(horas_granja_vacas.value) / (leche.tiempo / leche.produccion)
  requerimiento_bolsa_trigo_granja_vaca.value = (horas_granja_vacas.value <= 0 || !checked_granja_vacas.value) ? 0 : parseFloat(horas_granja_vacas.value) / (leche.tiempo / leche.requerimiento.bolsa_trigo)
  requerimiento_agua_granja_vaca.value = (horas_granja_vacas.value <= 0 || !checked_granja_vacas.value) ? 0 : parseFloat(horas_granja_vacas.value) / (leche.tiempo / leche.requerimiento.agua)

  let madera = arboles.nivel[nivel_arboles.value];
  produccion_madera.value = (horas_arboles.value <= 0 || !checked_arboles_1.value) ? 0 : parseFloat(horas_arboles.value) / (madera.tiempo / madera.produccion)
  requerimiento_agua_arboles.value = (horas_arboles.value <= 0 || !checked_arboles_1.value) ? 0 : parseFloat(horas_arboles.value) / (madera.tiempo / madera.requerimiento.agua)

  let madera_2 = arboles.nivel[nivel_arboles_2.value];
  produccion_madera_2.value = (horas_arboles_2.value <= 0 || !checked_arboles_2.value) ? 0 : parseFloat(horas_arboles_2.value) / (madera_2.tiempo / madera_2.produccion)
  requerimiento_agua_arboles_2.value = (horas_arboles_2.value <= 0 || !checked_arboles_2.value) ? 0 : parseFloat(horas_arboles_2.value) / (madera_2.tiempo / madera_2.requerimiento.agua)

  let madera_3 = arboles.nivel[nivel_arboles_3.value];
  produccion_madera_3.value = (horas_arboles_3.value <= 0 || !checked_arboles_3.value) ? 0 : parseFloat(horas_arboles_3.value) / (madera_3.tiempo / madera_3.produccion)
  requerimiento_agua_arboles_3.value = (horas_arboles_3.value <= 0 || !checked_arboles_3.value) ? 0 : parseFloat(horas_arboles_3.value) / (madera_3.tiempo / madera_3.requerimiento.agua)

  let carbon = molino.madera;
  produccion_carbon.value = (!checked_molino_madera.value) ? 0 : carbon.ratio * molino_cant_madera.value;
  molino_cant_madera.value = (!checked_molino_madera.value) ? 0 : molino_cant_madera.value;

  let bolsa_maiz = molino.maiz;
  produccion_bolsa_maiz.value = (!checked_molino_maiz.value) ? 0 : bolsa_maiz.ratio * molino_cant_maiz.value;
  molino_cant_maiz.value = (!checked_molino_maiz.value) ? 0 : molino_cant_maiz.value;

  let bolsa_trigo = molino.trigo;
  produccion_bolsa_trigo.value = (!checked_molino_trigo.value) ? 0 : bolsa_trigo.ratio * molino_cant_trigo.value;
  molino_cant_trigo.value = (!checked_molino_trigo.value) ? 0 : molino_cant_trigo.value;

  let kod = molino.leche;
  produccion_kod.value = (!checked_molino_leche.value) ? 0 : kod.ratio * molino_cant_leche.value;
  molino_cant_leche.value = (!checked_molino_leche.value) ? 0 : molino_cant_leche.value;

  let hueso = molino.huevo;
  produccion_hueso.value = (!checked_molino_huevo.value) ? 0 : hueso.ratio * molino_cant_huevo.value;
  molino_cant_huevo.value = (!checked_molino_huevo.value) ? 0 : molino_cant_huevo.value;

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
  consumo_maiz.value = molino_cant_maiz.value;
  consumo_trigo.value = molino_cant_trigo.value;
  consumo_bolsa_trigo.value = requerimiento_bolsa_trigo_granja_vaca.value;
  consumo_bolsa_maiz.value = requerimiento_bolsa_maiz_granja_gallina.value;
  consumo_madera.value = molino_cant_madera.value;
  consumo_carbon.value = requerimiento_carbon_fabrica.value;
  consumo_leche.value = molino_cant_leche.value;
  consumo_huevo.value = molino_cant_huevo.value;

}

function onChange(event, tipo) {

  switch (tipo) {
    case 'pozo_agua':
      horas_pozo_agua.value = pozo_agua.nivel[event.target.value].tiempo;
      break;
    case 'fabrica_energia':
      horas_fabrica_energia.value = fabrica_energia.nivel[event.target.value].tiempo;
      break;
    case 'granja_gallinas':
      horas_granja_gallina.value = granja_gallinas.nivel[event.target.value].tiempo;
      break;
    case 'granja_vacas':
      horas_granja_vacas.value = granja_vacas.nivel[event.target.value].tiempo;
      break;
    case 'tierra_trigo_1':
      horas_tierra_trigo.value = tierra_trigo.nivel[event.target.value].tiempo;
      break;
    case 'tierra_trigo_2':
      horas_tierra_trigo_2.value = tierra_trigo.nivel[event.target.value].tiempo;
      break;
    case 'tierra_maiz_1':
      horas_tierra_maiz.value = tierra_maiz.nivel[event.target.value].tiempo;
      break;
    case 'tierra_maiz_2':
      horas_tierra_maiz_2.value = tierra_maiz.nivel[event.target.value].tiempo;
      break;
    case 'arboles_1':
      horas_arboles.value = arboles.nivel[event.target.value].tiempo;
      break;
    case 'arboles_2':
      horas_arboles_2.value = arboles.nivel[event.target.value].tiempo;
      break;
    case 'arboles_3':
      horas_arboles_3.value = arboles.nivel[event.target.value].tiempo;
      break;
    default:

  }

}

function restar(a, b) {
  return a - b
}



</script>

<style>

body {
  /*background: #a18262 !important;*/
  background: url('../assets/liso.png') repeat;
  background-clip: padding-box;
  background-origin: initial;
  background-position: 50%;
  border-image-repeat: repeat;
  border-image-slice: 8 8 8 8;
  border-image-source: url('../assets/detalle.png');
  border-image-width: 18px;
  border-style: solid;
  border-width: 15px;
  padding: 12px;
}

.text-with-shadown {
  color: white !important;
  text-shadow: 0px 0px 5px black;
}

.caja-cafe {
  background: #854C30;
  background-clip: padding-box;
  background-origin: initial;
  background-position: 50%;
  border-image-repeat: repeat;
  border-image-slice: 4 4 4 4;
  border-image-source: url('../assets/cafeBorde.png');
  border-image-width: 18px;
  border-style: solid;
  border-width: 15px;
  padding: 12px;
}

.relleno-cafe {
  background: #D27D2C !important;
}

.btn-with-background {
  background-image: url('../assets/button.png');
  background-size: 100% 100%;
  background-position: center center;
  text-align: center !important;
  color: white !important;
  font-weight: bold !important;
  padding: 1% 3% !important;
}

.boton-imagen {
  display: inline-block;
  position: relative;
}

.boton-imagen img {
  display: block;
  max-width: 100%;
}

.texto-boton {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 14px;
  color: white;
}

.form-floating label {
  background-color: transparent !important;
  color: white;
  font-weight: bold;
}


.form-floating input{
  background-color: #854C30;
  border-image-repeat: repeat;
  border-image-slice: 4 4 4 4;
  border-image-source: url('../assets/cafeBorde.png');
  border-image-width: 10px;
  border-style: solid;
  color: white;
  font-weight: bold;
  text-align: center;
  padding-top: 4% !important;
}

.form-floating input:focus {
  background-color: #854C30;
  color: white;
  font-weight: bold;
}

.form-floating input:disabled {
  background-color: gray;
}

.form-floating select {
  background-color: #854C30;
  border-image-repeat: repeat;
  border-image-slice: 4 4 4 4;
  border-image-source: url('../assets/cafeBorde.png');
  border-image-width: 10px;
  border-style: solid;
  color: white;
  font-weight: bold;
}

.form-floating select:disabled {
  background-color: gray;
}

.form-floating select:not(:focus) , select:focus {
  text-align-last: center;
}

.form-floating select option{
  text-align: center;
  display: flex;
  justify-content: center;
  color: white;
  font-weight: bold;
}

.form-floating>.form-select {
  padding-top: 4% !important;
}



</style>
